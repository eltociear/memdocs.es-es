---
title: 'Inscripción de dispositivos macOS: Apple Business Manager o Apple School Manager'
titleSuffix: ''
description: Obtenga información sobre cómo inscribir dispositivos macOS corporativos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7afe3897c040673ad869584e1e8e8f55f4fc08ff
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88911903"
---
# <a name="automatically-enroll-macos-devices-with-the-apple-business-manager-or-apple-school-manager"></a>Inscripción automática de dispositivos macOS con Apple Business Manager o Apple School Manager

> [!IMPORTANT]
> Apple ha dejado de usar recientemente el Programa de inscripción de dispositivos (DEP) de Apple y ahora emplea la Inscripción de dispositivo automatizada (ADE) de Apple. Intune está en proceso de actualizar su interfaz de usuario para reflejarlo. Hasta que se completen estos cambios, seguirá viendo el *Programa de inscripción de dispositivos* en el portal de Intune. Cada vez que se muestre, usará la Inscripción de dispositivos automatizada.

Puede configurar la inscripción de Intune de los dispositivos macOS comprados mediante [Apple Business Manager](https://business.apple.com/) o [Apple School Manager](https://school.apple.com/) de Apple. Puede usar cualquiera de estas inscripciones para un gran número de dispositivos sin siquiera tener que tocarlos. Puede enviar dispositivos macOS directamente a los usuarios. Cuando el usuario activa el dispositivo, se ejecuta el Asistente para la instalación con opciones preconfiguradas y el dispositivo se inscribe en la administración de Intune.

Para configurar la inscripción, use los portales de Intune y Apple. Puede crear perfiles de inscripción que contengan opciones que se apliquen a los dispositivos durante la inscripción.

Ni la inscripción de Apple Business Manager ni Apple School Manager funcionan con el [administrador de inscripción de dispositivos](device-enrollment-manager-enroll.md).

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Requisitos previos

- Dispositivos comprados en [Apple School Manager](https://school.apple.com/) o [Inscripción de dispositivos automatizada de Apple](http://deploy.apple.com)
- Una lista de números de serie o un número de pedido de compra.
- [Entidad de MDM](../fundamentals/mdm-authority-set.md)
- [Certificado push MDM de Apple](../enrollment/apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-ade-token"></a>Obtención de un token de ADE de Apple

Para poder inscribir dispositivos macOS con ADE o Apple School Manager, necesita un archivo de token (.p7m) de Apple. Este token permite a Intune sincronizar información sobre los dispositivos propiedad de su organización. También permite que Intune cargue los perfiles de inscripción en Apple y en estos perfiles a los dispositivos.

Use el portal de Apple para crear un token. También puede usar el portal de Apple para asignar dispositivos a Intune para la administración.

> [!NOTE]
> Si elimina el token desde el portal clásico de Intune antes de realizar la migración a Azure, Intune podría restaurar un token de Apple eliminado. Puede volver a eliminar el token desde Azure Portal.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Paso 1. Descargue el certificado de clave pública de Intune necesario para crear el token.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **macOS** > **Inscripción de macOS** > **Tokens del programa de inscripción** > **Agregar**.

    ![Obtenga un token del programa de inscripción.](./media/device-enrollment-program-enroll-macos/image01.png)

2. Conceda a Microsoft permiso para enviar información de usuario y dispositivo a Apple al seleccionar **Acepto**.

   ![Captura de pantalla del panel Token del Programa de inscripción en el área de trabajo de Certificados de Apple para descargar la clave pública.](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Seleccione **Descargar la clave pública** para descargar y guardar localmente el archivo de la clave de cifrado (.pem). El archivo .pem se usa para solicitar un certificado de relación de confianza en el portal de Apple.

### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Paso 2. Use la clave para descargar un token de Apple.

1. Seleccione **Crear un token mediante Apple Business Manager** o **Crear un token mediante Apple School Manager** para abrir el portal adecuado de Apple e iniciar sesión con el id. de Apple de la empresa. Puede usar este id. de Apple para renovar el token.
2. Para DEP, en el portal de Apple, elija **Empezar** mientras que, para **Programa de inscripción de dispositivos** > **Administrar servidores** > **Agregar servidor de MDM**.
3. Para Apple School Manager, en el portal de Apple, elija **Servidores de MDM** > **Agregar servidor de MDM**.
4. Escriba el **nombre del servidor MDM** y, después, elija **Siguiente**. El nombre del servidor es su referencia para identificar el servidor de administración de dispositivos móviles (MDM). No es el nombre ni la dirección URL del servidor de Microsoft Intune.

5. Se abre el cuadro de diálogo **Agregar&lt;Nombre del servidor&gt;** , indicando **Cargar la clave pública**. Seleccione **Elegir archivo…** para cargar el archivo .pem y, después, elija **Siguiente**.

6. Vaya a **Programas de implementación** &gt; **Programa de inscripción de dispositivos** &gt; **Administrar dispositivos**.
7. En **Elegir dispositivos por**, especifique cómo se identifican los dispositivos:
    - **Número de serie**
    - **Número de pedido**
    - **Cargar archivo CSV**.

   ![Captura de pantalla sobre cómo especificar Elegir dispositivos por número de serie, estableciendo Elegir acción como Asignar al servidor y seleccionando el nombre de servidor.](./media/device-enrollment-program-enroll-macos/enrollment-program-token-specify-serial.png)

8. En **Elegir acción**, pulse **Asignar al servidor**, seleccione el &lt;NombreDeServidor&gt; especificado para Microsoft Intune y pulse **Aceptar**. El portal de Apple asigna los dispositivos especificados al servidor de Intune para la administración y, después, muestra **Asignación completa**.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Paso 3. Guarde el identificador de Apple usado para crear este token

En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), proporcione el identificador de Apple como referencia futura.

![Captura de pantalla sobre cómo especificar el identificador de Apple que se ha usado para crear y buscar el token del Programa de inscripción.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Paso 4. Cargue el token
En el cuadro **Token de Apple**, vaya al archivo de certificado (.pem), seleccione **Abrir** y después **Crear**. Con el certificado push, Intune puede inscribir y administrar dispositivos macOS insertando la directiva en los dispositivos inscritos. Intune se sincroniza automáticamente con Apple para ver la cuenta del programa de inscripción.

## <a name="create-an-apple-enrollment-profile"></a>Creación de un perfil de inscripción de Apple

Ahora que ha instalado el token, puede crear un perfil de inscripción para dispositivos. Un perfil de inscripción de dispositivos define la configuración que se aplica a un grupo de dispositivos durante la inscripción.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **macOS** > **Inscripción de macOS** > **Tokens del programa de inscripción**.
2. Seleccione un token, elija **Perfiles** y después **Crear perfil** > **macOS**.

    ![Cree una captura de pantalla del perfil.](./media/device-enrollment-program-enroll-macos/image04.png)

3. En la página **Básico**, escriba la información pertinente en **Nombre** y **Descripción** para el perfil con fines administrativos. Los usuarios no ven estos detalles. Puede usar este campo de **nombre** para crear un grupo dinámico en Azure Active Directory. Use el nombre de perfil para definir el parámetro enrollmentProfileName para asignar dispositivos con este perfil de inscripción. Obtenga más información sobre los [grupos dinámicos de Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices).

    ![Nombre y descripción del perfil.](./media/device-enrollment-program-enroll-macos/createprofile.png)

4. En **Plataforma**, elija **macOS**.

5. Seleccione **Siguiente** para ir a la página **Configuración de administración**.

6. En **Afinidad de usuario**, elija si los dispositivos con este perfil deben o no inscribirse con o sin un usuario asignado.
    - **Inscribir con afinidad de usuario**: seleccione esta opción para dispositivos que pertenezcan a usuarios y necesiten usar la aplicación Portal de empresa para hacer uso de servicios, como instalar aplicaciones. Si se usa ADFS, la afinidad de usuario debe ser [Punto de conexión mixto/nombre de usuario de WS-Trust 1.3](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff608241(v=ws.10)). [Más información](/powershell/module/adfs/get-adfsendpoint?view=win10-ps). La autenticación multifactor no es compatible con dispositivos ADE macOS con afinidad de usuario.

    - **Inscribir sin afinidad de usuario**: seleccione esta opción para dispositivos no afiliados con un usuario único. Use esta opción para dispositivos que realizan tareas sin tener acceso a datos de usuario local. Las aplicaciones como Portal de empresa no funcionan.

6. Para **Inscripción bloqueada**, elija si quiere o no que la inscripción de dispositivos esté bloqueada con este perfil. **Sí** deshabilita la configuración de macOS que permite que el perfil de administración se quite del menú **Preferencias del sistema** o a través del **Terminal**. Tras la inscripción del dispositivo, no se puede cambiar esta configuración sin borrar el dispositivo.

7. Seleccione **Siguiente** para ir a la página **Asistente de configuración**.

8. En la página **Asistente de configuración**, establezca las siguientes opciones del perfil:

    ![Personalización del Asistente de configuración.](./media/device-enrollment-program-enroll-macos/setupassistantcustom-macos.png)

    | Configuración de departamento | Descripción |
    |---|---|
    | <strong>Nombre de departamento</strong> | Aparece cuando los usuarios pulsan <strong>Acerca de la configuración</strong> durante la activación. |
    | <strong>Teléfono del departamento</strong> | Aparece cuando el usuario hace clic en el botón <strong>Necesito ayuda</strong> durante la activación. |

    Cuando el usuario configura el dispositivo, es posible mostrar u ocultar varias pantallas del asistente de configuración.
    - Si elige **Ocultar**, la pantalla no se mostrará durante la configuración. Después de configurar el dispositivo, el usuario seguirá teniendo la posibilidad de ir al menú **Ajustes** para configurar la característica.
    - Si elige **Mostrar**, la pantalla se mostrará durante la configuración. A veces, el usuario puede omitir la pantalla sin realizar ninguna acción. Sin embargo, posteriormente podrá ir al menú **Ajustes** del dispositivo para configurar la característica. 

    | Configuración de pantallas del asistente | Si elige **Mostrar**, durante la configuración se producirá lo siguiente en el dispositivo: |
    |------------------------------------------|------------------------------------------|
    | <strong>Código de acceso</strong> | Se solicitará un código de acceso al usuario. Solicite siempre un código de acceso para dispositivos no protegidos a menos que el acceso esté controlado de otra manera (como el modo de quiosco que restringe el dispositivo a una aplicación). En iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>Servicios de ubicación</strong> | Se solicitará la ubicación del usuario. En macOS 10.11 y versiones posteriores y iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>Restaurar</strong> | Se mostrará la pantalla Aplicaciones y datos. En esta pantalla el usuario tendrá la opción de restaurar o transferir datos de una copia de seguridad de iCloud al configurar el dispositivo. En macOS 10.9 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>ID de Apple</strong> | El usuario tendrá la opción de iniciar sesión con su id. de Apple y usar iCloud. En macOS 10.9 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores.   |
    | <strong>Términos y condiciones</strong> | El usuario deberá aceptar los términos y condiciones de Apple. En macOS 10.9 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>Touch ID</strong> | El usuario tendrá la opción de configurar una identificación con huella digital para el dispositivo. En macOS 10.12.4 y versiones posteriores e iOS/iPadOS 8.1 y versiones posteriores. |
    | <strong>Apple Pay</strong> | El usuario tendrá la opción de configurar Apple Pay en el dispositivo. En macOS 10.12.4 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>Zoom</strong> | El usuario tendrá la opción de ampliar el contenido de la pantalla al configurar el dispositivo. En iOS/iPadOS 8.3 y versiones posteriores. |
    | <strong>Siri</strong> | El usuario tendrá la opción de configurar Siri. En macOS 10.12 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>Datos de diagnóstico</strong> | Se mostrará la pantalla Diagnóstico al usuario. En esta pantalla el usuario podrá enviar datos de diagnóstico a Apple. En macOS 10.9 y versiones posteriores e iOS/iPadOS 7.0 y versiones posteriores. |
    | <strong>FileVault</strong> | Se muestra la pantalla de cifrado de FileVault 2 al usuario. En macOS 10.10 y versiones posteriores. |
    | <strong>Diagnósticos de iCloud</strong> | Se muestra la pantalla de análisis de iCloud al usuario. En macOS 10.12.4 y versiones posteriores. |
    | <strong>Almacenamiento en iCloud</strong> | Se muestra la pantalla de documentos y escritorio de iCloud al usuario. En macOS 10.13.4 y versiones posteriores. |
    | <strong>Tono de visualización</strong> | El usuario tendrá la opción de configurar el tono de visualización. En macOS 10.13.6 y versiones posteriores e iOS/iPadOS 9.3.2 y versiones posteriores. |
    | <strong>Aspecto</strong> | Se mostrará la pantalla Aspecto al usuario. En macOS 10.14 y versiones posteriores e iOS/iPadOS 13.0 y versiones posteriores. |
    | <strong>Registro</strong> | Se muestra la pantalla de registro al usuario. En macOS 10.9 y versiones posteriores. |
    | <strong>Tiempo de pantalla</strong> | Se mostrará la pantalla Tiempo de pantalla. En macOS 10.15 y versiones posteriores e iOS/iPadOS 12.0 y versiones posteriores. |
    | <strong>Privacidad</strong> | Se mostrará la pantalla Privacidad al usuario. En macOS 10.13.4 y versiones posteriores e iOS/iPadOS 11.3 y versiones posteriores. |
    
9. Elija **Siguiente** para ir a la página **Revisar y crear**.

10. Para guardar el perfil, elija **Crear**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos administrados

Ahora que Intune tiene permiso para administrar los dispositivos, puede sincronizar Intune con Apple para ver los dispositivos administrados en Intune en Azure Portal.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **macOS** > **Inscripción de macOS** > **Tokens del programa de inscripción**.

2. Elija un token en la lista > **Dispositivos** > **Sincronizar**. ![Captura de pantalla del nodo Dispositivos del Programa de inscripción seleccionado y el vínculo Sincronizar pulsado.](./media/device-enrollment-program-enroll-macos/image06.png)

   Para cumplir con las condiciones de Apple relativas a un tráfico del programa de inscripción aceptable, Intune impone las restricciones siguientes:
   - Una sincronización completa no se puede ejecutar más de una vez cada siete días. Durante una sincronización completa, Intune captura la lista actualizada completa de números de serie asignados al servidor MDM de Apple conectado a Intune. Tras eliminar un dispositivo del Programa de inscripción desde el portal de Intune sin anular su asignación del servidor MDM de Apple en el portal de Apple, no se podrá volver a importar a Intune hasta que se ejecute la sincronización completa.   
   - Una sincronización se ejecuta automáticamente cada 24 horas. También puede sincronizar haciendo clic en el botón **Sincronizar** (no más de una vez cada 15 minutos). Todas las solicitudes de sincronización tardan 15 minutos en finalizar. El botón **Sincronizar** queda deshabilitado hasta que se completa la sincronización. Esta sincronización actualizará el estado del dispositivo existente e importará nuevos dispositivos asignados al servidor MDM de Apple.

## <a name="assign-an-enrollment-profile-to-devices"></a>Asignar un perfil de inscripción a los dispositivos

Debe asignar un perfil del Programa de inscripción a los dispositivos para poder inscribirlos.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **macOS** > **Inscripción de macOS** > **Tokens del programa de inscripción** y elija un token de la lista.
2. Elija **Dispositivos** > Elija los dispositivos de la lista > **Asignar perfil**.
3. En **Asignar perfil**, elija un perfil para los dispositivos y seleccione **Asignar**.

### <a name="assign-a-default-profile"></a>Asignación de un perfil predeterminado

Puede elegir un perfil de macOS y iOS/iPadOS predeterminado para aplicarlo a todos los dispositivos que se inscriben en un token específico. 

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **macOS** > **Inscripción de macOS** > **Tokens del programa de inscripción** y elija un token de la lista.
2. Elija **Establecer perfil predeterminado**, seleccione un perfil en la lista desplegable y después seleccione **Guardar**. Este perfil se aplicará a todos los dispositivos que se inscriben en el token.

## <a name="distribute-devices"></a>Distribución de los dispositivos

Ha habilitado la administración y sincronización entre Apple e Intune, y ha asignado un perfil para permitir que sus dispositivos se inscriban. Ahora puede distribuir los dispositivos a los usuarios. Los dispositivos con afinidad de usuario necesitan que a cada usuario se le asigne una licencia de Intune. Los dispositivos sin afinidad de usuario necesitan una licencia de dispositivo. Un dispositivo activado no puede aplicar un perfil de inscripción hasta que se haya borrado.

## <a name="renew-an-ade-token"></a>Renovación de un token de ADE

1. Vaya a deploy.apple.com.  
2. En **Administrar servidores**, elija el servidor MDM asociado con el archivo de token que desea renovar.
3. Elija **Generar nuevo token**.

    ![Captura de pantalla de Generar nuevo token.](./media/device-enrollment-program-enroll-macos/generatenewtoken.png)

4. Elija **Su token de servidor**.  
5. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción** y elija un token.
    ![Captura de pantalla de Tokens del programa de inscripción.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Elija **Renovar token** y escriba el identificador de Apple usado para crear el token original.  
    ![Captura de pantalla de Generar nuevo token.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

7. Cargue el token recién descargado.  
8. Elija **Renovar token**. Verá la confirmación de que el token se renovó.
    ![Captura de pantalla de confirmación.](./media/device-enrollment-program-enroll-macos/confirmation.png)

## <a name="next-steps"></a>Pasos siguientes

Después de inscribir dispositivos macOS, puede empezar a [administrarlos](../remote-actions/device-management.md).