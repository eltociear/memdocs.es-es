---
title: Uso de certificados de claves públicas y privadas en Microsoft Intune (Azure) | Microsoft Docs
description: Use los certificados de estándares de criptografía de clave pública (PKCS) con Microsoft Intune, trabaje con certificados raíz y plantillas de certificado, instale Microsoft Intune Connector (NDES) y use perfiles de configuración de dispositivo para un certificado PKCS.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28ca32bc65ee0c4647c22b10b6b5d47a25efa202
ms.sourcegitcommit: d4ed7b4369389fd8ab07d28a7fa507797b6c6e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89643623"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configuración y uso de certificados PKCS con Intune

Intune admite el uso de certificados de par de claves privadas y públicas (PKCS). Este artículo le será útil para configurar la infraestructura necesaria, como conectores de certificados locales, exportar un certificado PKCS y luego agregarlo a un perfil de configuración de dispositivo de Intune.

Microsoft Intune incluye opciones de configuración integradas para usar certificados PKCS para los procesos de acceso y autenticación de los recursos de la organización. Los certificados permiten autenticar y proteger el acceso a los recursos corporativos, como por ejemplo, una VPN o una red Wi-Fi. Para implementar esta configuración en los dispositivos, se usan perfiles de configuración de dispositivo de Intune.

Para más información sobre el uso de certificados PKCS, consulte [Certificados PFX importados](certificates-imported-pfx-configure.md).


## <a name="requirements"></a>Requisitos

Para usar certificados PKCS con Intune, debe contar con esta infraestructura:

- **Dominio de Active Directory**:  
  todos los servidores mencionados en esta sección deben estar unidos al dominio de Active Directory.

  Para más información sobre cómo instalar y configurar Active Directory Domain Services (AD DS), vea [Planeación y diseño de AD DS](/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Entidad de certificación**:  
   entidad de certificación empresarial (CA).

  Para más información sobre cómo instalar y configurar los Servicios de certificados de Active Directory (AD CS), vea [Active Directory Certificate Services Step-by-Step Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772393(v=ws.10)) (Guía detallada de los Servicios de certificados de Active Directory).

  > [!WARNING]  
  > Intune requiere ejecutar AD CS con una entidad de certificación (CA) empresarial, no una CA independiente.

- **Cliente**:  
  se usa para conectarse a la CA empresarial.

- **Certificado raíz**:  
  Una copia exportada del certificado raíz desde la CA empresarial.

- **Conector de certificado PFX para Microsoft Intune**:

  Para obtener información sobre el conector de certificados PFX, incluidos los requisitos previos y las versiones de lanzamiento, vea [Conectores de certificados](certificate-connectors.md).

  > [!IMPORTANT]
  > A partir de la versión 6.2008.60.607 del conector de certificados PFX, ya no se requiere el conector de Microsoft Intune para los perfiles de certificado PKCS. 
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportación del certificado raíz desde la CA empresarial

Para autenticar un dispositivo con VPN, Wi-Fi u otros recursos, el dispositivo necesita un certificado de entidad de certificación intermedio. Los pasos siguientes explican cómo obtener el certificado requerido desde la CA empresarial.

**Usar una línea de comandos**:  

1. inicie sesión en el servidor de la entidad de certificación raíz con la cuenta de administrador.

2. Vaya a **Inicio** > **Ejecutar** y, después, escriba **Cmd** para abrir el símbolo del sistema.

3. Especifique **certutil -ca.cert ca_name.cer** para exportar el certificado raíz como un archivo denominado *ca_name.cer*.

## <a name="configure-certificate-templates-on-the-ca"></a>Configuración de plantillas de certificado en la CA

1. Inicie sesión en la entidad de certificación empresarial con una cuenta que tenga privilegios de administración.
2. En la consola de la **entidad de certificación**, haga clic con el botón derecho en **Plantillas de certificado** y seleccione **Administrar**.
3. Busque la plantilla de certificado **Usuario**, haga clic con el botón derecho en ella y elija **Duplicar plantilla** para abrir **Propiedades de plantilla nueva**.

    > [!NOTE]
    > Para casos de cifrado y firma de correo electrónico S/MIME, muchos administradores usan certificados independientes para la firma y el cifrado. Si va a usar Servicios de certificados de Active Directory de Microsoft, puede usar la plantilla **Solo la firma de Exchange** para los certificados de firma de correo electrónico S/MIME y la plantilla **Usuario de Exchange** para los certificados de cifrado S/MIME.  Si va a usar una entidad de certificación de terceros, le recomendamos que revise las instrucciones para configurar las plantillas de firma y cifrado.

4. En la pestaña **Compatibilidad**:

    - Establezca **Entidad de certificación** en **Windows Server 2008 R2**
    - Establezca **Destinatario del certificado** en **Windows 7 / Server 2008 R2**

5. En la pestaña **General**, establezca el **nombre para mostrar de la plantilla** en un nombre significativo para usted.

    > [!WARNING]
    > El **nombre de la plantilla** predeterminado es el mismo que el **nombre para mostrar de la plantilla** *sin espacios*. Apunte el nombre de la plantilla, lo necesitará más adelante.

6. En **Tratamiento de la solicitud**, seleccione **Permitir que la clave privada se pueda exportar**.

    > [!NOTE]
    > A diferencia de SCEP, con PKCS, la clave privada del certificado se genera en el servidor en el que el conector está instalado, y no en el dispositivo. Es necesario que la plantilla de certificado permita la exportación de la clave privada, para que Certificate Connector pueda exportar el certificado PFX y enviarlo al dispositivo. 
    >
    > Aun así, tenga en cuenta que los certificados se instalan en el propio dispositivo con la clave privada marcada como no exportable.

7. En **Criptografía**, confirme que el **Tamaño mínimo de clave** esté establecido en 2048.
8. En **Nombre del firmante**, elija **Proporcionado por el solicitante**.
9. En **Extensiones**, confirme que ve Sistema de cifrado de archivos, Correo seguro y Autenticación de cliente en las **Directivas de aplicación**.

    > [!IMPORTANT]
    > En el caso de plantillas de certificado de iOS/iPadOS, vaya a la pestaña **Extensiones**, actualice **Uso de la clave** y confirme que no está seleccionada la opción **Firma como prueba de origen**.

10. En **Seguridad**, agregue la cuenta de equipo para el servidor donde instala Microsoft Intune Connector. Permita que esta cuenta tenga los permisos **Lectura** e **Inscripción**.
11. Seleccione **Aplicar** > **Aceptar** para guardar la plantilla de certificado. Cierre la **consola Plantillas de certificado**.
12. En la consola de la **entidad de certificación**, haga clic con el botón derecho en **Plantillas de certificado** > **Nuevo** > **Plantilla de certificado que se va a emitir**. Elija la plantilla que ha creado en los pasos anteriores. Seleccione **Aceptar**.
13. Para que el servidor administre los certificados de los dispositivos inscritos en Intune, siga estos pasos:

    1. Haga clic con el botón secundario en la entidad de certificación y elija **Propiedades**.
    2. En la pestaña Seguridad, agregue la cuenta de equipo del servidor donde se ejecutan los conectores (**Microsoft Intune Connector** o **conector de certificados PFX para Microsoft Intune**). 
    3. Conceda los permisos **Emitir y administrar certificados** y **Solicitar certificados** a la cuenta de equipo.

14. Cierre la sesión de la entidad de certificación empresarial.

## <a name="download-install-and-configure-the-pfx-certificate-connector"></a>Descarga, instalación y configuración del conector de certificados PFX

Antes de comenzar, [revise los requisitos del conector](certificate-connectors.md) y asegúrese de que el entorno y el servidor de Windows están preparados para admitir el conector.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Administración de inquilinos** > **Conectores y tokens** > **Conectores de certificados** >  **+ Agregar**.

3. Haga clic en *Descargar el software de Certificate Connector* para el conector de PKCS #12 y guarde el archivo en una ubicación a la que pueda acceder desde el servidor en el que va a instalar el conector.

   ![Descarga de Microsoft Intune Connector](./media/certficates-pfx-configure/download-connector.png)

4. Una vez finalizada la descarga, inicie sesión en el servidor y ejecute el instalador (PfxCertificateConnectorBootstrapper.exe).  
   - Cuando acepta la ubicación de instalación predeterminada, el conector se instala en `Program Files\Microsoft Intune\PFXCertificateConnector`.
   - El servicio de conector se ejecuta en la cuenta de sistema local. Si se requiere un servidor proxy para el acceso a Internet, confirme que la cuenta de servicio local puede acceder a la configuración de proxy en el servidor.

5. El Conector de certificado PFX para Microsoft Intune se abre en la pestaña **Inscripción** después de la instalación. Para habilitar la conexión con Intune, **inicie sesión**, y escriba una cuenta con permisos de administrador global de Azure o de Intune.

   > [!WARNING]
   > De forma predeterminada, en Windows Server, la opción **Configuración de seguridad mejorada de Internet Explorer** está establecida en **Activada**, lo que puede causar problemas con el inicio de sesión en Office 365.

6. Seleccione la pestaña **Cuenta de CA** y escriba las credenciales de una cuenta que tenga el permiso Emitir y administrar certificados en la entidad de certificación emisora. Estas credenciales se usarán para realizar la revocación de certificados en la entidad de certificación. 

    **Aplique** los cambios.

7. Cierre la ventana.

8. En el Centro de administración de Microsoft Endpoint Manager, vuelva a **Administración de inquilinos** > **Conectores y tokens** > **Conectores de certificado**. En unos minutos, se muestra una marca de verificación verde y se actualiza el estado de la conexión. El servidor del conector puede comunicarse ahora con Intune.

## <a name="create-a-trusted-certificate-profile"></a>Creación de un perfil de certificado de confianza

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione y vaya a **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. Escriba las propiedades siguientes:
   - **Plataforma**: elija la plataforma de los dispositivos que recibirán este perfil.
   - **Perfil**: seleccione **Certificado de confianza**.
  
4. Seleccione **Crear**.

5. En **Básico**, escriba las propiedades siguientes:
   - **Nombre**: escriba un nombre descriptivo para el nuevo perfil. Asígnele un nombre a los perfiles para que pueda identificarlos de manera sencilla más adelante. Por ejemplo, un buen nombre de perfil es *Perfil de certificado de confianza en toda la empresa*.
   - **Descripción**: escriba una descripción para el perfil. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.

7. En **Configuración**, especifique el certificado de entidad de certificación raíz del archivo .cer que ha exportado anteriormente.

   > [!NOTE]
   > En función de la plataforma que ha elegido en el **paso 3**, es posible que tenga o no la opción de seleccionar el **Almacén de destino** del certificado.

   ![Crear un perfil y cargar un certificado de confianza](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png)

8. Seleccione **Siguiente**.

9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

   Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione el usuario o los grupos que van a recibir el perfil. Planee la implementación de este perfil de certificado en los mismos grupos que reciben el perfil de certificado PKCS. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](../configuration/device-profile-assign.md).

    Seleccione **Siguiente**.

11. (*Se aplica solo a Windows 10*) En **Reglas de aplicación**, especifique las reglas de aplicación para restringir la asignación de este perfil. Puede elegir asignar o no asignar el perfil en función de la edición del sistema operativo o la versión de un dispositivo.

  Para más información, consulte [Reglas de aplicabilidad](../configuration/device-profile-create.md#applicability-rules) en *Creación de un perfil de dispositivo en Microsoft Intune*.

12. En **Revisar y crear**, revise la configuración. Si selecciona Crear, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.

## <a name="create-a-pkcs-certificate-profile"></a>Creación de un perfil de certificado PKCS

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione y vaya a **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. Escriba las propiedades siguientes:
   - **Plataforma**: seleccione la plataforma de los dispositivos. Las opciones son:
     - Administrador de dispositivos Android
     - Android Enterprise > Perfil de trabajo de propiedad corporativa, dedicado y totalmente administrado
     - Android Enterprise > solo perfil de trabajo
     - iOS/iPadOS
     - macOS
     - Windows 10 y versiones posteriores
   - **Perfil**: seleccione **PKCS certificate** (Certificado PKCS).

   > [!NOTE]
   > En los dispositivos con un perfil de Android Enterprise, los certificados que se instalan con un perfil de certificado PKCS no son visibles en el dispositivo. Para confirmar la correcta implementación de certificados, compruebe el estado del perfil en la consola de Intune.
4. Seleccione **Crear**.

5. En **Básico**, escriba las propiedades siguientes:
   - **Nombre**: escriba un nombre descriptivo para el nuevo perfil. Asígnele un nombre a los perfiles para que pueda identificarlos de manera sencilla más adelante. Por ejemplo, un buen nombre de perfil sería *Perfil de PKCS de toda la empresa*.
   - **Descripción**: escriba una descripción para el perfil. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.
7. En **Opciones de configuración**, las opciones que puede configurar serán diferentes, según la plataforma que haya elegido. Seleccione la plataforma para obtener la configuración detallada: Administrador de dispositivos Android, Android Enterprise, iOS/iPadOS, Windows 10
   
   |Setting     | Plataforma     | Detalles   |
   |------------|------------|------------|
   |**Umbral de renovación (%)**        |<ul><li>Todos         |El valor recomendado es del 20 %.  | 
   |**Período de validez del certificado**  |<ul><li>Todos         |si no ha cambiado la plantilla de certificado, esta opción puede estar establecida en un año. |
   |**Proveedor de almacenamiento de claves (KSP)**   |<ul><li>Windows 10  |en el caso de Windows, seleccione la ubicación del dispositivo en la que quiera almacenar las claves. |
   |**Entidad de certificación**      |<ul><li>Todos         |muestra el nombre de dominio completo (FQDN) interno de la CA empresarial.  |
   |**Nombre de la entidad de certificación** |<ul><li>Todos         |muestra el nombre de la CA empresarial, por ejemplo "Contoso Certification Authority". |
   |**Nombre de plantilla de certificado**    |<ul><li>Todos         |Enumera el nombre de la plantilla de certificado. |
   |**Tipo de certificado**             |<ul><li>Android Enterprise (*perfil de trabajo*)</li><li>iOS</li><li>macOS</li><li>Windows 10 y versiones posteriores|Seleccione un tipo: <ul><li> los certificados **Usuario** pueden contener atributos de usuario y dispositivo en el asunto y SAN del certificado. </il><li>Los certificados **Dispositivo** solo pueden contener atributos de dispositivo en el asunto y SAN del certificado. Use Dispositivo en escenarios como, por ejemplo, dispositivos sin usuario (como los quioscos multimedia) u otros dispositivos compartidos.  <br><br> Esta selección afecta al formato de nombre del firmante. |
   |**Formato de nombre del firmante**          |<ul><li>Todos         |Para obtener más información sobre cómo configurar el formato de nombre del sujeto, vea [Formato de nombre del sujeto](#subject-name-format) más adelante en este artículo.  <br><br> En la mayoría de las plataformas, use la opción **Nombre común**, a menos que se precise otra. <br><br>En las plataformas siguientes, el formato de nombre del firmante viene determinado por el tipo de certificado: <ul><li>Android Enterprise (*Perfil de trabajo*)</li><li>iOS</li><li>macOS</li><li>Windows 10 y versiones posteriores</li></ul>  <p>  |
   |**Nombre alternativo del firmante**     |<ul><li>Todos         |En *Atributo*, seleccione **Nombre principal de usuario (UPN)** , a menos que se precise otra cosa, configure un *Valor* correspondiente y, después, haga clic en **Agregar**. <br><br>Para obtener más información, vea [Formato de nombre del sujeto](#subject-name-format) más adelante en este artículo.|
   |**Uso mejorado de clave**           |<ul><li> Administrador de dispositivos Android </li><li>Android Enterprise (*Propietario del dispositivo*, *Perfil de trabajo*) </li><li>Windows 10 |Los certificados suelen requerir *Autenticación de cliente* para que el usuario o dispositivo pueda autenticarse en un servidor. |
   |**Permitir el acceso de todas las aplicaciones a la clave privada** |<ul><li>macOS  |Establezca esta opción en **Habilitar** para dar acceso a la clave privada de certificados PKCS a aquellas aplicaciones que estén configuradas para el dispositivo Mac asociado. <br><br> Para más información sobre esta configuración, vea *AllowAllAppsAccess* de la sección de carga de certificado de la [referencia de perfiles de configuración](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) en la documentación para desarrolladores de Apple. |
   |**Certificado raíz**             |<ul><li>Administrador de dispositivos Android </li><li>Android Enterprise (*Propietario del dispositivo*, *Perfil de trabajo*) |Seleccione un perfil de certificado de CA raíz asignado previamente. |

8. Seleccione **Siguiente**.

9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

   Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione el usuario o los grupos que van a recibir el perfil. Planee la implementación de este perfil de certificado en los mismos grupos que reciben el perfil de certificado de confianza. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](../configuration/device-profile-assign.md).

    Seleccione **Siguiente**.

11. En **Revisar y crear**, revise la configuración. Si selecciona Crear, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.


### <a name="subject-name-format"></a>Formato de nombre del sujeto

Al crear un perfil de certificado PKCS para las plataformas siguientes, las opciones de formato de nombre del firmante dependen del tipo de certificado que seleccione: **Usuario** o **Dispositivo**.  

Plataformas:

- Android Enterprise (*Perfil de trabajo*)
- iOS
- macOS
- Windows 10 y versiones posteriores

> [!NOTE]
> Existe un problema conocido en el uso de SCEP para obtener certificados [similar al problema que se produce con SCEP](certificates-profile-scep.md#avoid-certificate-signing-requests-with-escaped-special-characters), cuando el nombre del firmante en la solicitud de firma de certificado (CSR) resultante incluye uno de los siguientes caracteres como carácter de escape (precedido por una barra diagonal inversa \\):
> - \+
> - ;
> - ,
> - =

- **Tipo de certificado de usuario**  
  Las opciones de formato de *Formato de nombre del firmante* incluyen dos variables: **Nombre común (CN)** y **dirección de correo electrónico (E)** . **Nombre común (CN)** se puede establecer en cualquiera de las siguientes variables:

  - **CN={{UserName}}** : nombre principal de usuario, como janedoe@contoso.com.
  - **CN={{AAD_Device_ID}}** : identificador asignado al registrar un dispositivo en Azure Active Directory (AD). Este identificador normalmente se usa para autenticarse en Azure AD.
  - **CN={{SERIALNUMBER}}** : número de serie (SN) único que normalmente usa el fabricante para identificar un dispositivo.
  - **CN={{IMEINumber}}** : número exclusivo de identidad de equipo móvil internacional (IMEI) usado para identificar un teléfono móvil.
  - **CN={{OnPrem_Distinguished_Name}}** : Secuencia de nombres distintivos relativos separados por comas, como *CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

    Para usar la variable *{{OnPrem_Distinguished_Name}}* , asegúrese de sincronizar el atributo de usuario *onpremisesdistinguishedname* mediante [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) con la instancia de Azure AD.

  - **CN={{onPremisesSamAccountName}}** : los administradores pueden sincronizar el atributo samAccountName de Active Directory con Azure AD mediante Azure AD Connect en un atributo llamado *onPremisesSamAccountName*. Intune puede sustituir esa variable como parte de una solicitud de emisión de certificado en el asunto de un certificado. El atributo samAccountName es el nombre de inicio de sesión del usuario que se utiliza para admitir clientes y servidores de una versión anterior de Windows (anterior a Windows 2000). El formato de nombre de inicio de sesión de usuario es el siguiente: *NombreDeDominio\usuario de prueba*, o bien solo *usuario de prueba*.

    Para usar la variable *{{onPremisesSamAccountName}}* , asegúrese de sincronizar el atributo de usuario *onPremisesSamAccountName* mediante [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) con la instancia de Azure AD.

  Mediante una combinación de una o muchas de estas variables y cadenas estáticas, puede crear un formato de nombre de firmante personalizado como este:  
  - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
  
  Ese ejemplo incluye un formato de nombre de firmante en el que se usan las variables CN y E, y cadenas para los valores Unidad organizativa, Organización, Ubicación, Estado y País. [CertStrToName](/windows/win32/api/wincrypt/nf-wincrypt-certstrtonamea) describe esta función y sus cadenas admitidas.

- **Tipo de certificado de dispositivo**  
  Las opciones de formato para el formato de nombre del firmante incluyen las variables siguientes: 
  - **{{AAD_Device_ID}}**
  - **{{Device_Serial}}**
  - **{{Device_IMEI}}**
  - **{{SerialNumber}}**
  - **{{IMEINumber}}**
  - **{{AzureADDeviceId}}**
  - **{{WiFiMacAddress}}**
  - **{{IMEI}}**
  - **{{DeviceName}}**
  - **{{FullyQualifiedDomainName}}** *(Solo aplicable para dispositivos Windows y unidos a dominio)*
  - **{{MEID}}**

  Puede especificar estas variables, seguidas del texto de la variable, en el cuadro de texto. Por ejemplo, el nombre común de un dispositivo denominado *Dispositivo1* se puede agregar como **CN={{DeviceName}}Dispositivo1**.

  > [!IMPORTANT]  
  > - Al especificar una variable, incluya el nombre de la variable entre corchetes { } como se muestra en el ejemplo, para evitar un error.  
  > - Una persona con acceso al dispositivo podría suplantar las propiedades del dispositivo que se usan en el *asunto* o *SAN*, como **IMEI**, **SerialNumber** y **FullyQualifiedDomainName**.
  > - Un dispositivo debe admitir todas las variables especificadas en un perfil de certificado para que ese perfil se instale en ese dispositivo.  Por ejemplo, si se usa **{{IMEI}}** en el nombre del firmante de un perfil SCEP y se asigna a un dispositivo que no tiene un número IMEI, se producirá un error en la instalación del perfil.

## <a name="next-steps"></a>Pasos siguientes

[Use SCEP para los certificados](certificates-scep-configure.md), o bien [emita certificados PKCS a partir de un servicio web de administración de PKI de Symantec](certificates-digicert-configure.md).

[Solución de problemas de los perfiles de certificado PKCS](../protect/troubleshoot-pkcs-certificate-profiles.md)
