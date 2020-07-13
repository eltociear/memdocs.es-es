---
title: Guía para desarrolladores acerca del SDK de aplicaciones de Microsoft Intune para iOS
description: El SDK de aplicaciones de Microsoft Intune para iOS permite incorporar directivas de protección de aplicaciones de Intune (también conocidas como APP o directivas MAM) a la aplicación iOS nativa.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/04/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: has-adal-ref
ms.collection: M365-identity-device-management
ms.openlocfilehash: a69176e347453131c76d669b14fd7ec37b331071
ms.sourcegitcommit: ba36a60b08bb85d592bfb8c4bbe6d02a47858b09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052500"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Guía para desarrolladores acerca del SDK de aplicaciones de Microsoft Intune para iOS

> [!NOTE]
> Plantéese leer primero el artículo [Introducción al SDK para aplicaciones de Microsoft Intune](app-sdk-get-started.md), en el que se explica cómo prepararse para la integración en cada una de las plataformas compatibles.
>
> Para descargar el SDK, consulte [Descargar los archivos del SDK](../developer/app-sdk-get-started.md#download-the-sdk-files).

El SDK de aplicaciones de Microsoft Intune para iOS permite incorporar directivas de protección de aplicaciones de Intune (también conocidas como APP o directivas MAM) a la aplicación iOS nativa. Una aplicación habilitada para MAM es aquella que está integrada con el SDK para aplicaciones de Intune. Los administradores de TI pueden implementar directivas de protección de aplicaciones en la aplicación móvil cuando Intune la administra activamente.

## <a name="prerequisites"></a>Requisitos previos

- Necesitará un equipo Mac OS con OS X 10.12.6 o posterior y que tenga instalado Xcode 9 o posterior.

- La aplicación debe estar destinada para iOS 11 o posterior.

- Revise los [términos de licencia del SDK de aplicaciones de Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS.pdf). Imprima y conserve una copia de los términos de licencia para sus registros. Al descargar y usar el SDK de aplicaciones de Intune para iOS, acepta dichos términos.  Si no los acepta, no use el software.

- Descargue los archivos del SDK de aplicaciones de Intune para iOS en [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk-repository"></a>Contenido del repositorio del SDK

Los siguientes archivos son relevantes para las aplicaciones o las extensiones que no contienen código Swift o que se compilan con una versión de Xcode anterior a la 10.2:

* **IntuneMAM.framework**: marco del SDK de aplicaciones Intune. Se recomienda vincular este marco de trabajo a la aplicación o las extensiones para habilitar la administración de aplicaciones cliente de Intune, aunque es posible que algunos desarrolladores prefieran las ventajas de rendimiento de la biblioteca estática. Vea las opciones siguientes.

* **libIntuneMAM.a**: biblioteca estática del SDK de aplicaciones de Intune. Los desarrolladores pueden optar por vincular la biblioteca estática en lugar del marco de trabajo. Dado que las bibliotecas estáticas se insertan directamente en el binario de la aplicación o la extensión en tiempo de compilación, hay algunas ventajas de rendimiento en tiempo de inicio si se usa la biblioteca estática. Pero su integración en la aplicación es un proceso más complicado. Si la aplicación incluye alguna extensión, la vinculación de la biblioteca estática a la aplicación y las extensiones se traduce en un mayor tamaño del lote de aplicaciones, ya que la biblioteca estática se inserta en cada binario de aplicación o extensión. Al usar el marco de trabajo, las aplicaciones y las extensiones pueden compartir el mismo binario del SDK de Intune, lo que da lugar a un tamaño de aplicación más pequeño.

* **IntuneMAMResources.bundle**: lote de recursos que contiene los recursos en los que se basa el SDK. El lote de recursos solo es necesario para las aplicaciones que integran la biblioteca estática (libIntuneMAM.a).

Los siguientes archivos son relevantes para las aplicaciones o las extensiones que contienen código Swift y que se compilan con Xcode 10.2 y versiones superiores:

* **IntuneMAMSwift.framework**: el marco de trabajo Swift de Intune App SDK. Este marco de trabajo contiene todos los encabezados de las API a las que va a llamar la aplicación. Vincule este marco de trabajo a la aplicación o las extensiones para habilitar la administración de aplicaciones cliente de Intune.

* **IntuneMAMSwiftStub.framework**: el marco de trabajo de stub de Swift de Intune App SDK. Se trata de una dependencia necesaria de IntuneMAMSwift.framework que las aplicaciones o las extensiones deben vincular.


Los siguientes archivos son relevantes para todas las aplicaciones y las extensiones:

* **IntuneMAMConfigurator**: una herramienta que se usa para configurar el archivo Info.plist de la aplicación o la extensión con los cambios mínimos necesarios para la administración de Intune. Según la funcionalidad de la aplicación o la extensión, es posible que deba realizar cambios manuales adicionales en Info.plist.

* **Encabezados**: expone las API públicas de Intune App SDK. Estos encabezados están incluidos en los marcos de trabajo IntuneMAM/IntuneMAMSwift, así que los desarrolladores que usan cualquiera de ellos no necesitan agregarlos manualmente a su proyecto. Los desarrolladores que decidan vincular con la biblioteca estática (libIntuneMAM.a), deben incluir manualmente estos encabezados en el proyecto.

Los siguientes archivos de encabezado incluyen las API, los tipos de datos y los protocolos que Intune App SDK pone a disposición de los desarrolladores:

-  IntuneMAMAppConfig.h
-  IntuneMAMAppConfigManager.h
-  IntuneMAMDataProtectionInfo.h
-  IntuneMAMDataProtectionManager.h
-  IntuneMAMDefs.h
-  IntuneMAMDiagnosticConsole.h
-  IntuneMAMEnrollmentDelegate.h
-  IntuneMAMEnrollmentManager.h
-  IntuneMAMEnrollmentStatus.h
-  IntuneMAMFileProtectionInfo.h
-  IntuneMAMFileProtectionManager.h
-  IntuneMAMLogger.h
-  IntuneMAMPolicy.h
-  IntuneMAMPolicyDelegate.h
-  IntuneMAMPolicyManager.h
-  IntuneMAMVersionInfo.h

Los desarrolladores pueden hacer que el contenido de todos los encabezados anteriores esté disponible con tan solo importar IntuneMAM.h.


## <a name="how-the-intune-app-sdk-works"></a>Cómo funciona el SDK para aplicaciones de Intune

El objetivo del SDK para aplicaciones de Intune para iOS es agregar capacidades de administración a las aplicaciones de iOS con mínimos cambios en el código. Cuantos menos cambios se hagan en el código, menor será el tiempo de comercialización, pero sin afectar a la coherencia y la estabilidad de la aplicación móvil.


## <a name="build-the-sdk-into-your-mobile-app"></a>Integrar el SDK en la aplicación móvil

Para habilitar el SDK para aplicaciones de Intune, siga estos pasos:

1. **Opción 1: marco de trabajo (recomendado)** : Si usa Xcode 10.2+ y la aplicación o extensión contiene código de Swift, vincule `IntuneMAMSwift.framework` e `IntuneMAMSwiftStub.framework` al destino: arrastre `IntuneMAMSwift.framework` e `IntuneMAMSwiftStub.framework` a la lista **Embedded Binaries** (Binarios insertados) del destino del proyecto.

    De lo contrario, vincule `IntuneMAM.framework` al destino: Arrastre `IntuneMAM.framework` a la lista **Embedded Binaries** (Binarios insertados) del destino del proyecto.

   > [!NOTE]
   > Si usa el marco de trabajo, debe extraer manualmente las arquitecturas de simulador del marco de trabajo universal antes de enviar la aplicación al App Store. Vea [Enviar la aplicación a la Tienda de aplicaciones](#submit-your-app-to-the-app-store) para más información.

   **Opción 2: biblioteca estática**: esta opción solo está disponible para las aplicaciones o extensiones que no contienen código de Swift o que se han compilado con Xcode < 10.2. vincular a la biblioteca `libIntuneMAM.a`. Arrastre la bibloteca `libIntuneMAM.a` en la lista de **Linked Frameworks and Libraries** (Marcos y bibliotecas vinculados) del destino del proyecto.

    ![Intune App SDK para iOS: marcos y bibliotecas vinculados](./media/app-sdk-ios/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Agregue `-force_load {PATH_TO_LIB}/libIntuneMAM.a` a cualquiera de lo siguiente, reemplazando `{PATH_TO_LIB}` por la ubicación del SDK para aplicaciones de Intune:
   * Ajuste de la configuración de compilación `OTHER_LDFLAGS` del proyecto.
   * **Otras marcas del enlazador** de la interfaz de usuario de Xcode.

     > [!NOTE]
     > Para encontrar `PATH_TO_LIB`, seleccione el archivo `libIntuneMAM.a` y elija **Obtener información** en el menú **Archivo**. Copie y pegue la información **Dónde** (la ruta de acceso) de la sección **General** de la ventana **Información**.

     Agregue el lote de recursos `IntuneMAMResources.bundle` al proyecto al arrastrarlo desde **Copiar recursos del lote**, en **Fases de compilación**.

     ![SDK de aplicaciones de Intune para iOS: copiar recursos del lote](./media/app-sdk-ios/intune-app-sdk-ios-copy-bundle-resources.png)
         
2. Agregue estos marcos de trabajo de iOS al proyecto:  
   -  MessageUI.framework  
   -  Security.framework  
   -  CoreServices.framework  
   -  SystemConfiguration.framework  
   -  libsqlite3.tbd  
   -  libc++.tbd  
   -  ImageIO.framework  
   -  LocalAuthentication.framework  
   -  AudioToolbox.framework  
   -  QuartzCore.framework  
   -  WebKit.framework

3. Para habilitar el uso compartido de la cadena de claves (si aún no está habilitado), elija **Capacidades** en cada destino del proyecto y habilite el modificador del **uso compartido de cadena de claves**. El uso compartido de cadena de claves es necesario para que continúe con el siguiente paso.

   > [!NOTE]
   > El perfil de aprovisionamiento debe admitir nuevos valores de uso compartido de cadena de claves. Los grupos de acceso a cadena de claves deben admitir un carácter comodín. Para comprobar esto, abra el archivo .mobileprovision en un editor de texto, busque **keychain-access-groups** y asegúrese de que tiene un carácter comodín. Por ejemplo:
   >
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Después de habilitar el uso compartido de cadena de claves, siga los pasos para crear un grupo de acceso independiente en el que se almacenarán los datos de Intune App SDK. Puede crear un grupo de acceso a cadenas de claves mediante la interfaz de usuario o mediante el archivo de derechos. Si utiliza la interfaz de usuario para crear el grupo de acceso de la cadena de claves, asegúrese de seguir estos pasos:

     a. Si la aplicación móvil no tiene ningún grupo de acceso a cadena de claves definido, agregue el identificador del lote de la aplicación como el **primer** grupo.
    
    b. Agregue el grupo de cadena de claves compartido `com.microsoft.intune.mam` a los grupos de acceso existentes. El SDK para aplicaciones de Intune usa este grupo de acceso para almacenar datos.
    
    c. Agregue `com.microsoft.adalcache` a los grupos de acceso existentes.
    
      ![Intune App SDK iOS: uso compartido de cadena de claves](./media/app-sdk-ios/intune-app-sdk-ios-keychain-sharing.png)
    
    d. Si edita el archivo de derechos directamente, en lugar de usar la interfaz de usuario de Xcode mostrada anteriormente para crear los grupos de acceso a cadena de claves, anteponga `$(AppIdentifierPrefix)` a dichos grupos (Xcode lo hace automáticamente). Por ejemplo:
    
      - `$(AppIdentifierPrefix)com.microsoft.intune.mam`
      - `$(AppIdentifierPrefix)com.microsoft.adalcache`
    
      > [!NOTE]
      > Un archivo de derechos es un archivo XML que es exclusivo para la aplicación móvil. Se utiliza para especificar permisos especiales y capacidades en su aplicación iOS. Si la aplicación no disponía anteriormente de un archivo de títulos, Xcode generará uno para la aplicación después de habilitar el uso compartido de la cadena claves (paso 3). Asegúrese de que identificador de lote de aplicaciones sea la primera entrada de la lista.

5. Incluya cada protocolo que la aplicación pasa a `UIApplication canOpenURL` en la matriz `LSApplicationQueriesSchemes` del archivo Info.plist de la aplicación. Asegúrese de guardar los cambios antes de continuar con el paso siguiente.

6. Si su aplicación no usa aún FaceID, asegúrese de que la [clave NSFaceIDUsageDescription Info.plist](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW75) esté configurada con un mensaje predeterminado. Este es un requisito para que iOS pueda informar al usuario de cómo la aplicación pretende usar FaceID. La configuración de una directiva de protección de la aplicación de Intune permite usar FaceID como método para acceder a la aplicación cuando este lo ha configurado el administrador de TI.

7. Use la herramienta IntuneMAMConfigurator que se incluye en el [repositorio de SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) para finalizar la configuración de Info.plist de la aplicación. La herramienta tiene tres parámetros:

   |Propiedad|Cómo usarla|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (Opcional) `<Path to the output plist>`. |

Si el parámetro "-o" no se especifica, el archivo de entrada se modificará en contexto. La herramienta es idempotente y debe volver a ejecutarse cada vez que se realicen cambios en Info.plist o los derechos de la aplicación. También debe descargar y ejecutar la versión más reciente de la herramienta al actualizar el SDK de Intune, en caso de que los requisitos de configuración de Info.plist hayan cambiado en la versión más reciente.

## <a name="configure-adalmsal"></a>Configuración de ADAL/MSAL

> [!NOTE]
> Azure Active Directory (Azure AD) Authentication Library (ADAL) y Azure AD Graph API quedarán obsoletos próximamente. Para obtener más información, consulte [Actualización de aplicaciones para el uso de la biblioteca de autenticación de Microsoft (MSAL) y Microsoft Graph API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/update-your-applications-to-use-microsoft-authentication-library/ba-p/1257363).

Intune App SDK puede usar la [Biblioteca de autenticación de Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) o la [Biblioteca de autenticación de Microsoft](https://github.com/AzureAD/microsoft-authentication-library-for-objc) para los escenarios de inicio condicional y de autenticación. También se basa en ADAL/MSAL para registrar la identidad del usuario con el servicio de MAM para la administración sin escenarios de inscripción de dispositivos.

Normalmente, ADAL/MSAL requiere que las aplicaciones se registren con Azure Active Directory (AAD) y que creen un identificador de cliente único y un URI de redirección para garantizar la seguridad de los tokens concedidos a la aplicación. Si su aplicación ya usa ADAL o MSAL para la autenticación de usuarios, la aplicación debe utilizar los valores de registro existentes y reemplazar los valores predeterminados de Intune App SDK. Esto garantiza que no se pida a los usuarios autenticarse dos veces (una por parte del SDK para aplicaciones de Intune y otra por parte de la aplicación).

Si la aplicación aún no usa ADAL ni MSAL y no necesita acceder a ningún recurso de AAD, no tiene que configurar ningún registro de aplicación cliente en AAD si decide integrar ADAL. Si decide integrar MSAL, tiene que configurar un registro de aplicación e invalidar el identificador de cliente y el URI de redireccionamiento de Intune predeterminados.  

Se recomienda que la aplicación se vincule a la versión más reciente de [ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) o [MSAL](https://github.com/AzureAD/microsoft-authentication-library-for-objc/releases).

### <a name="link-to-adal-or-msal-binaries"></a>Vínculo a los binarios de ADAL o MSAL

**Opción 1:** siga [estos pasos](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) para vincular la aplicación a los binarios de ADAL.

**Opción 2:** como alternativa, puede seguir [estas instrucciones](https://github.com/AzureAD/microsoft-authentication-library-for-objc#installation) para vincular la aplicación a los binarios de MSAL.

1. Si la aplicación no tiene definido ningún grupo de acceso a cadenas de claves, agregue el identificador de lote de la aplicación como primer grupo.

2. Habilite el inicio de sesión único (SSO) de ADAL/MSAL agregando `com.microsoft.adalcache` a los grupos de acceso de la cadena de claves.

3. En caso de que esté estableciendo explícitamente el grupo de cadenas de claves de caché compartida de ADAL, asegúrese de que esté establecido en `<appidprefix>.com.microsoft.adalcache`. ADAL lo establecerá automáticamente a menos que lo reemplace. Si quiere especificar un grupo de cadenas de claves personalizado para reemplazar a `com.microsoft.adalcache`, hágalo en el archivo Info.plist en IntuneMAMSettings, mediante la clave `ADALCacheKeychainGroupOverride`.

### <a name="configure-adalmsal-settings-for-the-intune-app-sdk"></a>Establecer la configuración de ADAL/MSAL para Intune App SDK

Si la aplicación ya usa ADAL o MSAL para la autenticación y tiene su propia configuración de Azure Active Directory, puede hacer que Intune App SDK use la misma configuración durante la autenticación en AAD. Esto garantiza que la aplicación no vuelva a solicitar la autenticación al usuario. Vea [Configurar Intune App SDK](#configure-settings-for-the-intune-app-sdk) para obtener información sobre cómo rellenar las opciones siguientes:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Si su aplicación ya usa ADAL o MSAL, son necesarias las siguientes configuraciones:

1. En el archivo Info.plist del proyecto, en el diccionario **IntuneMAMSettings** con el nombre de clave `ADALClientId`, especifique el ClientID que se usará para llamadas de ADAL.

2. Además, en el diccionario **IntuneMAMSettings** con el nombre de clave `ADALAuthority`, especifique la entidad de Azure AD.

3. En el diccionario **IntuneMAMSettings** con el nombre de clave `ADALRedirectUri`, especifique el URI de redireccionamiento que se usará para llamadas de ADAL. También puede especificar `ADALRedirectScheme` en su lugar, si el URI de redireccionamiento de la aplicación está en el formato `scheme://bundle_id`.

Además, las aplicaciones pueden invalidar esta configuración de Azure AD en runtime. Para ello, basta con establecer las propiedades `aadAuthorityUriOverride`, `aadClientIdOverride` y `aadRedirectUriOverride` en la instancia `IntuneMAMPolicyManager`.

4. Asegúrese de que se siguen los pasos para conceder los permisos de aplicación de iOS para el servicio Directiva de protección de aplicaciones (APP). Siga las instrucciones de la [guía de introducción al SDK de Intune](app-sdk-get-started.md#next-steps-after-integration) sobre cómo [conceder a su aplicación acceso al servicio Intune App Protection (opcional)](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional).  

> [!NOTE]
> El enfoque de Info.plist se recomienda para todos los valores que sean estáticos y no tengan que determinarse en runtime. Los valores asignados a las propiedades de `IntuneMAMPolicyManager` tienen prioridad sobre los valores correspondientes especificados en Info.plist y se conservarán incluso después de reiniciar la aplicación. El SDK continuará usándolos para las protecciones de directivas hasta que se anule la inscripción del usuario o los valores se borren o cambien.

### <a name="if-your-app-does-not-use-adal-or-msal"></a>Si su aplicación no usa ADAL ni MSAL

Como se ha mencionado anteriormente, Intune App SDK puede usar la [Biblioteca de autenticación de Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) o la [Biblioteca de autenticación de Microsoft](https://github.com/AzureAD/microsoft-authentication-library-for-objc) para sus escenarios de inicio condicional y de autenticación. También se basa en ADAL/MSAL para registrar la identidad del usuario con el servicio de MAM para la administración sin escenarios de inscripción de dispositivos. Si **la aplicación no usa ADAL ni MSAL para su propio mecanismo de autenticación**, es posible que deba configurar opciones de AAD personalizadas, en función de la biblioteca de autenticación que decida integrar:   

ADAL: Intune App SDK proporcionará valores predeterminados para parámetros ADAL y controlará la autenticación en Azure AD. Los desarrolladores no tienen que especificar ningún valor para la configuración de ADAL mencionada anteriormente. 

MSAL: los desarrolladores deben crear un registro de aplicación en AAD con un URI de redireccionamiento personalizado en el formato que se especifica [aquí](https://github.com/AzureAD/microsoft-authentication-library-for-objc/wiki/Migrating-from-ADAL-Objective-C-to-MSAL-Objective-C#app-registration-migration). Los desarrolladores deben establecer los valores `ADALClientID` y `ADALRedirectUri` mencionados anteriormente o las propiedades `aadClientIdOverride` y `aadRedirectUriOverride` equivalentes en la instancia de `IntuneMAMPolicyManager`. Los desarrolladores también deben asegurarse de seguir el paso 4 de la sección anterior para conceder al registro de aplicación acceso al servicio de protección de aplicaciones de Intune.

### <a name="special-considerations-when-using-msal"></a>Consideraciones especiales a la hora de usar MSAL 

1. **Compruebe la vista web**: se recomienda que las aplicaciones no usen SFSafariViewController, SFAuthSession ni ASWebAuthSession como vista web para las operaciones de autenticación interactiva de MSAL iniciadas por la aplicación. Si, por alguna razón, la aplicación debe usar una de estas vistas web para las operaciones interactivas de autenticación de MSAL, también debe establecer `SafariViewControllerBlockedOverride` en `true` en el diccionario `IntuneMAMSettings` del archivo Info.plist de la aplicación. WARNING: Esto desactivará los enlaces de SafariViewController de Intune para habilitar la sesión de autenticación. Esto plantea un riesgo de pérdida de datos en cualquier parte de la aplicación si esta usa SafariViewController para ver datos corporativos, por lo que la aplicación no debe mostrar datos corporativos en ninguno de esos tipos de vista web.
2. **Vincule ADAL y MSAL**: los desarrolladores deben elegir si quieren que Intune prefiera MSAL en lugar de ADAL en este escenario. De forma predeterminada, Intune prefiere las versiones de ADAL admitidas a las versiones de MSAL compatibles si ambas están vinculadas en tiempo de ejecución. Intune solo prefiere una versión de MSAL compatible cuando, en el momento de la primera operación de autenticación de Intune, `IntuneMAMUseMSALOnNextLaunch` es `true` en `NSUserDefaults`. Si `IntuneMAMUseMSALOnNextLaunch` es `false` o no está establecido, Intune revierte al comportamiento predeterminado. Como sugiere el nombre, se produce un cambio en `IntuneMAMUseMSALOnNextLaunch` en el siguiente inicio.


## <a name="configure-settings-for-the-intune-app-sdk"></a>Establecer la configuración de Intune App SDK

Puede usar el diccionario **IntuneMAMSettings** del archivo Info.plist de la aplicación para instalar y configurar Intune App SDK. Si no se ve el diccionario IntuneMAMSettings en el archivo Info.plist, debe crearlo.

En el diccionario IntuneMAMSettings, puede agregar las opciones admitidas siguiente para configurar Intune App SDK.

Es posible que se hayan tratado algunos de estos valores en las secciones anteriores y que otros no se apliquen a todas las aplicaciones.

Setting  | Tipo  | Definición | ¿Necesario?
--       |  --   |   --       |  --
ADALClientId  | String  | Identificador de cliente de Azure AD de la aplicación. | Requerido para todas las aplicaciones que usan MSAL y cualquier aplicación de ADAL que acceda a un recurso de AAD que no sea de Intune. |
ADALAuthority | String | Entidad de Azure AD de la aplicación en uso. Debe usar su propio entorno donde se hayan configurado cuentas de AAD. | Opcional. Se recomienda si la aplicación es una aplicación de línea de negocio personalizada compilada para su uso en una sola organización o inquilino de AAD. Si este valor está ausente, se usa la entidad de AAD común.|
ADALRedirectUri  | String  | URI de redireccionamiento de Azure AD de la aplicación. | ADALRedirectUri o ADALRedirectScheme es requerido para todas las aplicaciones que usan MSAL y cualquier aplicación de ADAL que acceda a un recurso de AAD que no sea de Intune.  |
ADALRedirectScheme  | String  | Esquema de redireccionamiento de Azure AD de la aplicación. Puede usarse en lugar de ADALRedirectUri si el URI de redireccionamiento de la aplicación está en el formato `scheme://bundle_id`. | ADALRedirectUri o ADALRedirectScheme es requerido para todas las aplicaciones que usan MSAL y cualquier aplicación de ADAL que acceda a un recurso de AAD que no sea de Intune. |
ADALLogOverrideDisabled | Boolean  | Especifica si el SDK enrutará todos los registros de ADAL/MSAL (incluidas las llamadas de ADAL desde la aplicación de haberlas) a su propio archivo de registro. El valor predeterminado es NO. Establezca la opción en SÍ si la aplicación establecerá su propia devolución de llamada de registros ADAL/MSAL. | Opcional. |
ADALCacheKeychainGroupOverride | String  | Especifica el grupo de cadena de claves que se usará para la caché de ADAL/MSAL en lugar de "com.microsoft.adalcache". Tenga en cuenta que no contiene el prefijo de identificador de la aplicación. Ese se anexará a la cadena proporcionada en tiempo de ejecución. | Opcional. |
AppGroupIdentifiers | Matriz de cadenas  | Matriz de grupos de aplicación de la sección de grupos de com.apple.security.application-groups de derechos de la aplicación. | Se requiere si la aplicación usa grupos de aplicaciones. |
ContainingAppBundleId | String | Especifica el identificador del lote de la aplicación contenedora de la extensión. | Se requiere para las extensiones de iOS. |
DebugSettingsEnabled| Boolean | Si se establece en Sí, se pueden aplicar directivas de prueba en el lote de configuración. Las aplicaciones *no* se deben proporcionar con esta opción habilitada. | Opcional. El valor predeterminado es No. |
AutoEnrollOnLaunch| Boolean| Especifica si la aplicación debe intentar inscribir automáticamente al ejecutarse, o en caso de que se haya detectado una identidad administrada existente que aún no lo haya hecho. El valor predeterminado es NO. <br><br> Notas: Si no se encuentra ninguna identidad administrada, o bien si no hay ningún token válido disponible en la caché de ADAL/MSAL para la identidad, el intento de inscripción devuelve un error en modo silencioso sin solicitar las credenciales, a menos que en la aplicación también se establezca MAMPolicyRequired en SÍ. | Opcional. El valor predeterminado es No. |
MAMPolicyRequired| Boolean| Especifica si se bloqueará el inicio de la aplicación en caso de que no tenga una directiva de protección de aplicaciones de Intune. El valor predeterminado es NO. <br><br> Notas: Las aplicaciones no se pueden enviar a App Store con MAMPolicyRequired establecido en SÍ. Al establecer MAMPolicyRequired en SÍ, AutoEnrollOnLaunch también debe establecerse en SÍ. | Opcional. El valor predeterminado es No. |
MAMPolicyWarnAbsent | Boolean| Especifica si la aplicación avisará al usuario durante el inicio en caso de que no tenga una directiva de protección de aplicaciones de Intune. <br><br> Nota: Los usuarios podrán seguir usando la aplicación sin directiva después de descartar la advertencia. | Opcional. El valor predeterminado es No. |
MultiIdentity | Boolean| Especifica si la aplicación es compatible con varias identidades. | Opcional. El valor predeterminado es No. |
SafariViewControllerBlockedOverride | Boolean| Deshabilita los enlaces de SafariViewController de Intune para habilitar la autenticación de MSAL mediante SFSafariViewController, SFAuthSession o ASWebAuthSession. | Opcional. El valor predeterminado es No. ADVERTENCIA: Puede producir una pérdida de datos si se usa de forma incorrecta. Habilite solo si resulta absolutamente necesario. Vea [Consideraciones especiales a la hora de usar MSAL](#special-considerations-when-using-msal) para obtener detalles.  |
SplashIconFile <br>SplashIconFile~ipad | String  | Especifica el archivo del icono de la pantalla de presentación (inicio) de Intune. | Opcional. |
SplashDuration | Número | Cantidad mínima de tiempo en segundos en que se mostrará la pantalla de presentación de Intune al iniciar la aplicación. El valor predeterminado es 1,5. | Opcional. |
BackgroundColor| String| Especifica el color de fondo de los componentes de la interfaz de usuario del SDK de Intune. Acepta una cadena RGB hexadecimal con el formato #XXXXXX, donde las X pueden ir de 0 a 9 o de A a F. Se puede omitir la almohadilla.   | Opcional. Tiene como valor predeterminado el color de fondo del sistema, que puede variar entre las distintas versiones de iOS y según la configuración del modo oscuro de iOS. |
ForegroundColor| String| Especifica el color de primer plano de los componentes de la interfaz de usuario del SDK de Intune, como el color del texto. Acepta una cadena RGB hexadecimal con el formato #XXXXXX, donde las X pueden ir de 0 a 9 o de A a F. Se puede omitir la almohadilla.  | Opcional. Tiene como valor predeterminado el color de las etiquetas del sistema, que puede variar entre las versiones de iOS y según la configuración del modo oscuro de iOS. |
AccentColor | String| Especifica el color de énfasis de los componentes de la interfaz de usuario del SDK de Intune, como el color del texto de los botones y el color de resaltado del cuadro del PIN. Acepta una cadena RGB hexadecimal con el formato #XXXXXX, donde las X pueden ir de 0 a 9 o de A a F. Se puede omitir la almohadilla.| Opcional. El valor predeterminado es el azul del sistema. |
SecondaryBackgroundColor| String| Especifica el color de fondo secundario para las pantallas de MTD. Acepta una cadena RGB hexadecimal con el formato #XXXXXX, donde las X pueden ir de 0 a 9 o de A a F. Se puede omitir la almohadilla.   | Opcional. El valor predeterminado es blanco. |
SecondaryForegroundColor| String| Especifica el color de primer plano secundario de las pantallas de MTD, como el color de la nota al pie. Acepta una cadena RGB hexadecimal con el formato #XXXXXX, donde las X pueden ir de 0 a 9 o de A a F. Se puede omitir la almohadilla.  | Opcional. El valor predeterminado es gris. |
SupportsDarkMode| Boolean | Especifica si la combinación de colores de la interfaz de usuario del SDK de Intune debe respetar la configuración del modo oscuro del sistema, si no se ha establecido ningún valor explícito para BackgroundColor/ForegroundColor/AccentColor. | Opcional. El valor predeterminado es YES. |
MAMTelemetryDisabled| Boolean| Especifica si el SDK no enviará los datos de telemetría a su back-end.| Opcional. El valor predeterminado es No. |
MAMTelemetryUsePPE | Boolean | Especifica si el SDK de MAM va a enviar datos al back-end de telemetría de PPE. Úselo cuando pruebe las aplicaciones con la directiva de Intune para que los datos de telemetría de prueba no se mezclen con los datos del cliente. | Opcional. El valor predeterminado es No. |
MaxFileProtectionLevel | String | Opcional. Permite que la aplicación especifique el `NSFileProtectionType` máximo que puede admitir. Este valor invalida la directiva enviada por el servicio si el nivel es mayor que el que la aplicación puede admitir. Valores posibles: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Boolean | Se establece en SÍ para las extensiones de acción Abrir en. Vea la sección Uso compartido de datos a través de UIActivityViewController para obtener más información. |
WebViewHandledURLSchemes | Matriz de cadenas | Especifica los esquemas de dirección URL que controla WebView de la aplicación. | Se requiere si la aplicación usa WebView para controlar direcciones URL a través de vínculos o JavaScript. |
DocumentBrowserFileCachePath | String | Si la aplicación usa el [`UIDocumentBrowserViewController`](https://developer.apple.com/documentation/uikit/uidocumentbrowserviewcontroller?language=objc) para examinar los archivos de varios proveedores de archivos, puede establecer esta ruta de acceso relativa al directorio particular en el espacio aislado de la aplicación para que el SDK de Intune pueda quitar archivos administrados descifrados en esa carpeta. | Opcional. El valor predeterminado es el directorio `/Documents/`. |
VerboseLoggingEnabled | Boolean | Si se establece en YES, Intune realizará el registro en modo detallado. | Opcional. El valor predeterminado es NO |

## <a name="receive-app-protection-policy"></a>Recibir la directiva de protección de aplicaciones

### <a name="overview"></a>Introducción

Para recibir la directiva de protección de aplicaciones de Intune, las aplicaciones deben iniciar una solicitud de inscripción en el servicio MAM de Intune. Las aplicaciones pueden configurarse en la consola de Intune para recibir la directiva de protección de aplicaciones con o sin inscripción de dispositivos. La directiva de protección de aplicaciones sin inscripción, también conocida como **APP-WE** o MAM-WE, permite administrar las aplicaciones mediante Intune sin necesidad de que el dispositivo esté inscrito en la administración de dispositivos móviles (MDM) de Intune. En ambos casos, se requiere la inscripción en el servicio MAM de Intune para recibir la directiva.

> [!Important]
> El SDK de aplicaciones de Intune para iOS usa claves de cifrado de 256 bits cuando el cifrado se habilita mediante las directivas de protección de aplicaciones. Todas las aplicaciones deberán tener una versión de SDK actual para permitir el uso compartido de datos.

### <a name="apps-that-already-use-adal-or-msal"></a>Aplicaciones que ya usan ADAL o MSAL

> [!NOTE]
> Azure Active Directory (Azure AD) Authentication Library (ADAL) y Azure AD Graph API quedarán obsoletos próximamente. Para obtener más información, consulte [Actualización de aplicaciones para el uso de la biblioteca de autenticación de Microsoft (MSAL) y Microsoft Graph API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/update-your-applications-to-use-microsoft-authentication-library/ba-p/1257363).

Las aplicaciones que ya usan ADAL o MSAL deben llamar al método `registerAndEnrollAccount` en la instancia `IntuneMAMEnrollmentManager` una vez que el usuario se haya autenticado correctamente:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

Al llamar al método `registerAndEnrollAccount`, el SDK registrará la cuenta de usuario e intentará inscribir la aplicación en nombre de esta cuenta. Si, por cualquier motivo, se produce un error en la inscripción, el SDK intentará volver a realizar la inscripción automáticamente 24 horas más tarde. Con fines de depuración, la aplicación puede recibir [notificaciones](#status-result-and-debug-notifications) a través de un delegado sobre los resultados de las solicitudes de inscripción.

Una vez que se haya invocado esta API, la aplicación puede seguir funcionando de la manera habitual. Si la inscripción se realiza correctamente, el SDK le notificará al usuario que se debe reiniciar la aplicación. En ese momento el usuario puede reiniciar la aplicación.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@"user@foo.com"];
```

### <a name="apps-that-do-not-use-adal-or-msal"></a>Aplicaciones que no usan ADAL ni MSAL

Las aplicaciones que no inician la sesión del usuario con ADAL o MSAL pueden recibir directivas de protección de aplicaciones del servicio MAM de Intune mediante una llamada a la API para que el SDK controle la autenticación. Las aplicaciones deben usar esta técnica si no han autenticado a un usuario con Azure AD pero siguen necesitando recuperar la directiva de protección de aplicaciones para ayudar a proteger los datos. Un ejemplo es si otro servicio de autenticación se utiliza para iniciar sesión en la aplicación, o si la aplicación no admite el inicio de sesión en absoluto. Para ello, la aplicación puede llamar al método `loginAndEnrollAccount` en la instancia `IntuneMAMEnrollmentManager`:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

Al llamar a este método, el SDK pedirá al usuario las credenciales si no se encuentra ningún token existente. El SDK intentará inscribir la aplicación con el servicio MAM de Intune en nombre de la cuenta de usuario proporcionada. Se puede llamar al método con "nulo" como identidad. En este caso, el SDK se inscribirá con el usuario administrado existente en el dispositivo (en el caso de MDM), o bien le pedirá al usuario un nombre de usuario si no encuentra ninguno.

Si se produce un error en la inscripción, la aplicación debe considerar la posibilidad de llamar a esta API de nuevo en el futuro, en función de los detalles del error. La aplicación puede recibir [notificaciones](#status-result-and-debug-notifications) a través de un delegado sobre los resultados de las solicitudes de inscripción.

Una vez que se haya invocado esta API, la aplicación puede seguir funcionando de la manera habitual. Si la inscripción se realiza correctamente, el SDK le notificará al usuario que se debe reiniciar la aplicación.

Ejemplo:

```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@"user@foo.com"];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Permitir que Intune controle la autenticación y la inscripción durante el inicio

Si quiere que el SDK de Intune controle toda la autenticación mediante ADAL/MSAL y la inscripción antes de que la aplicación termine de iniciarse, y la aplicación siempre requiere la directiva de APP, no es necesario usar la API `loginAndEnrollAccount`. Simplemente puede establecer los dos valores siguientes en SÍ en el diccionario IntuneMAMSettings del archivo Info.plist de la aplicación.

Setting  | Tipo  | Definición |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Boolean| Especifica si la aplicación debe intentar inscribir automáticamente al ejecutarse, o en caso de que se haya detectado una identidad administrada existente que aún no lo haya hecho. El valor predeterminado es NO. <br><br> Nota: Si no se encuentra ninguna identidad administrada, o bien si no hay ningún token válido disponible en la caché de ADAL/MSAL para la identidad, el intento de inscripción devuelve un error en modo silencioso sin solicitar las credenciales, a menos que en la aplicación también se establezca MAMPolicyRequired en SÍ. |
MAMPolicyRequired| Boolean| Especifica si se bloqueará el inicio de la aplicación en caso de que no tenga una directiva de protección de aplicaciones de Intune. El valor predeterminado es NO. <br><br> Nota: Las aplicaciones no se pueden enviar a App Store con MAMPolicyRequired establecido en SÍ. Al establecer MAMPolicyRequired en SÍ, AutoEnrollOnLaunch también debe establecerse en SÍ. |

Si elige esta opción para la aplicación, no es necesario que controle el reinicio de la aplicación después de la inscripción.

### <a name="deregister-user-accounts"></a>Anulación del registro de cuentas de usuario

Antes de que un usuario cierre sesión en una aplicación, la aplicación debe eliminar el registro del usuario del SDK. Esto garantizará que:

1. Ya no se realizarán reintentos de inscripción para la cuenta del usuario.

2. Se quitará la directiva de protección de la aplicación.

3. Si la aplicación inicia un borrado selectivo (opcional), se eliminan todos los datos corporativos.

Antes de que el usuario cierre sesión, la aplicación debe llamar al siguiente método en la instancia de `IntuneMAMEnrollmentManager`:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Es necesario llamar a este método antes de eliminar los tokens de Azure AD de la cuenta de usuario. El SDK necesita que los tokens AAD de la cuenta del usuario realicen solicitudes específicas en el servicio MAM de Intune en nombre del usuario.

Si la aplicación va a eliminar por sí misma los datos corporativos, la marca `doWipe` se puede establecer en False. De lo contrario, la aplicación puede hacer que el SDK inicie un borrado selectivo. Esto provocará una llamada al delegado de borrado selectivo de la aplicación.

Ejemplo:

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@"user@foo.com" withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Notificaciones de estado, resultados y depuración

La aplicación puede recibir notificaciones de estado, resultados y depuración sobre las solicitudes siguientes en el servicio de MAM de Intune:

* Solicitudes de inscripción
* Solicitudes de actualización de directivas
* Solicitudes de anulación de inscripción

Las notificaciones se presentan a través de métodos de delegado en `IntuneMAMEnrollmentDelegate.h`:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;
```

Estos métodos delegados devuelven un objeto `IntuneMAMEnrollmentStatus` que contiene la información siguiente:

* La identidad de la cuenta asociada a la solicitud
* El código de estado que indica el resultado de la solicitud
* Una cadena de error con una descripción del código de estado
* Objeto `NSError`. Este objeto está definido en `IntuneMAMEnrollmentStatus.h` junto con los códigos de estado específicos que se pueden devolver.

### <a name="sample-code"></a>Código de ejemplo

A continuación se muestran implementaciones de ejemplo de los métodos delegados:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Reinicio de la aplicación

Cuando una aplicación recibe directivas de MAM por primera vez, deberá reiniciarse para aplicar los enlaces necesarios. Para notificar a la aplicación que se debe producir un reinicio, el SDK proporciona un método delegado en `IntuneMAMPolicyDelegate.h`.

```objc
 - (BOOL) restartApplication
```

El valor devuelto por este método le indicará al SDK si la aplicación debe controlar el reinicio necesario:

* Si se devuelve True, la aplicación debe controlar el reinicio.

* Si devuelve false, el SDK reiniciará la aplicación después de que se devuelva este método. El SDK mostrará inmediatamente un cuadro de diálogo que indica al usuario que reinicie la aplicación.

## <a name="customize-your-apps-behavior-with-apis"></a>Personalizar el comportamiento de la aplicación mediante API

Intune App SDK tiene varias API a las que se puede llamar para obtener información sobre la directiva de Intune APP que se implementa en la aplicación. Puede usar estos datos para personalizar el comportamiento de la aplicación. En la tabla siguiente se proporciona información sobre algunas clases esenciales de Intune que se van a usar.

Class | Descripción
----- | -----------
IntuneMAMPolicyManager.h | La clase IntuneMAMPolicyManager expone la directiva de Intune APP implementada en la aplicación. En particular, expone las API que son útiles para [Habilitar varias identidades](app-sdk-ios.md#enable-multi-identity-optional). |
IntuneMAMPolicy.h | La clase IntuneMAMPolicy expone algunas configuraciones de directiva de MAM que se aplican a la aplicación. La mayor parte de estas opciones de configuración de directiva se exponen para que la aplicación pueda personalizar su interfaz de usuario. La mayoría de las configuraciones de directiva se aplican mediante el SDK y no la aplicación. No obstante, hay algunas excepciones. Los desarrolladores de aplicaciones deben revisar los comentarios de este encabezado para determinar cuáles son las API que se pueden usar en los escenarios de su aplicación. |
IntuneMAMFileProtectionManager.h | La clase IntuneMAMFileProtectionManager expone las API que la aplicación puede usar para proteger de forma explícita los archivos y directorios en función de una identidad proporcionada. La identidad puede estar administrada mediante Intune o no administrada, y el SDK aplicará la directiva de MAM adecuada. El uso de esta clase es opcional. |
IntuneMAMDataProtectionManager.h | La clase IntuneMAMDataProtectionManager expone las API que la aplicación puede usar para proteger los búferes de datos dada una identidad. La identidad puede estar administrada mediante Intune o no administrada, y el SDK aplicará el cifrado de la forma adecuada. |

## <a name="implement-allowed-accounts"></a>Implementación de cuentas permitidas

Intune permite a los administradores de TI especificar las cuentas en las que el usuario puede iniciar sesión. Las aplicaciones pueden consultar en Intune App SDK la lista especificada de cuentas permitidas y, después, asegurarse de que solo las cuentas permitidas inicien sesión en el dispositivo.

Para consultar las cuentas permitidas, la aplicación debe comprobar la propiedad `allowedAccounts` en `IntuneMAMEnrollmentManager`. La propiedad `allowedAccounts` es una matriz que contiene las cuentas permitidas o nada. Si la propiedad está vacía, no se ha especificado ninguna cuenta permitida.

Las aplicaciones también pueden reaccionar a los cambios de la propiedad `allowedAccounts` si observan la notificación `IntuneMAMAllowedAccountsDidChangeNotification`. La notificación se envía cada vez que cambia el valor de la propiedad `allowedAccounts`.

## <a name="implement-file-encryption-required"></a>Implementación de cifrado de archivos requerido

La API `isFileEncryptionRequired` definida en `IntuneMAMPolicy.h` informa a las aplicaciones de que el administrador de TI requiere que las aplicaciones usen el cifrado de Intune en los archivos guardados en el disco. Si `isFileEncryptionRequired` es "true", la aplicación debe asegurarse de que todos los archivos guardados en disco por la aplicación se cifren con las API de `IntuneMAMFile.h`, `IntuneMAMFileProtectionManager.h` y `IntuneMAMFDataProtectionManager.h`.

Para reaccionar a los cambios de esta directiva, las aplicaciones pueden observar la notificación `IntuneMAMDataProtectionDidChangeNotification` definida en `IntuneMAMFDataProtectionManager.h`.

## <a name="implement-save-as-and-open-from-controls"></a>Implementación de los controles Guardar como y Abrir desde

Intune permite a los administradores de TI seleccionar las ubicaciones en las que una aplicación administrada puede guardar datos o desde las que puede abrir datos. Las aplicaciones pueden consultar en el SDK de MAM de Intune las ubicaciones de almacenamiento en las que guardar permitidas mediante la API `isSaveToAllowedForLocation`, que se define en `IntuneMAMPolicy.h`. Las aplicaciones también pueden consultar en el SDK de MAM de Intune las ubicaciones de almacenamiento desde las que abrir permitidas mediante la API `isOpenFromAllowedForLocation`, que se define en `IntuneMAMPolicy.h`.

Antes de que las aplicaciones puedan guardar datos administrados en una ubicación local o de almacenamiento en la nube, deben realizar una comprobación con la API `isSaveToAllowedForLocation` para saber si el administrador de TI permite que los datos se guarden ahí.
Antes de abrir datos en una aplicación desde una ubicación de almacenamiento en la nube o local, la aplicación debe consultar la API `isOpenFromAllowedForLocation` para saber si el administrador de TI ha permitido que los datos se abran desde allí.

Si las aplicaciones usan las API `isSaveToAllowedForLocation` o `isOpenFromAllowedForLocation`, deben pasar el UPN de la ubicación de almacenamiento, si está disponible.

### <a name="supported-save-locations"></a>Ubicaciones de almacenamiento admitidas

La API `isSaveToAllowedForLocation` proporciona constantes para comprobar si el administrador de TI permite que los datos se guarden en las ubicaciones siguientes definidas en `IntuneMAMPolicy.h`:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive
* IntuneMAMSaveLocationCameraRoll
* IntuneMAMSaveLocationAccountDocument

Las aplicaciones deben usar las constantes de `isSaveToAllowedForLocation` para comprobar si los datos se pueden guardar en ubicaciones que se consideran "administradas", como OneDrive para la Empresa, o bien "personales". Además, la API debe usarse cuando la aplicación no puede determinar si una ubicación es "administrada" o "personal".

La constante `IntuneMAMSaveLocationLocalDrive` debe usarse cuando la aplicación guarda datos en cualquier ubicación del dispositivo local. Del mismo modo, se debe usar la constante `IntuneMAMSaveLocationCameraRoll` si la aplicación guarda una foto en el álbum de cámara.

Si la cuenta de la ubicación de destino es desconocida, se debe pasar `nil`. Las ubicaciones `IntuneMAMSaveLocationLocalDrive` e `IntuneMAMSaveLocationCameraRoll` siempre deben emparejarse con una cuenta `nil`.

### <a name="supported-open-locations"></a>Ubicaciones de apertura admitidas

La API `isOpenFromAllowedForLocation` proporciona constantes para comprobar si el administrador de TI permite que los datos se abran desde las ubicaciones siguientes definidas en `IntuneMAMPolicy.h`.

* IntuneMAMOpenLocationOther
* IntuneMAMOpenLocationOneDriveForBusiness
* IntuneMAMOpenLocationSharePoint
* IntuneMAMOpenLocationCamera
* IntuneMAMOpenLocationLocalStorage
* IntuneMAMOpenLocationAccountDocument

Las aplicaciones deben usar las constantes de `isOpenFromAllowedForLocation` para comprobar si se pueden abrir datos desde ubicaciones que se consideran "administradas", como OneDrive para la Empresa, o bien "personales". Además, debe usarse la API cuando la aplicación no puede determinar si una ubicación es "administrada" o "personal".

Se debe usar la constante `IntuneMAMOpenLocationCamera` cuando la aplicación abra datos de la cámara o del álbum de fotos.

Se debe usar la constante `IntuneMAMOpenLocationLocalStorage` cuando la aplicación abra datos desde cualquier ubicación del dispositivo local.

Se debe usar la constante `IntuneMAMOpenLocationAccountDocument` cuando la aplicación abra un documento que tiene una identidad de cuenta administrada (vea la sección "Datos compartidos" a continuación).

Si la cuenta de la ubicación de origen es desconocida, se debe pasar `nil`. Las ubicaciones `IntuneMAMOpenLocationLocalStorage` e `IntuneMAMOpenLocationCamera` siempre deben emparejarse con una cuenta `nil`.

### <a name="unknown-or-unlisted-locations"></a>Ubicaciones desconocidas o que no figuran en la lista

Si la ubicación deseada no aparece en las enumeraciones `IntuneMAMSaveLocation` o `IntuneMAMOpenLocation` o es desconocida, se debe usar una de dos ubicaciones.
* Si se accede a la ubicación de almacenamiento con una cuenta administrada, se debe usar la ubicación `IntuneMAMSaveLocationAccountDocument` (`IntuneMAMOpenLocationAccountDocument` para abrir).
* De lo contrario, use la ubicación `IntuneMAMSaveLocationOther` (`IntuneMAMOpenLocationOther` para abrir).

Es importante aclarar la distinción entre cuenta administrada y cuenta que comparte el UPN de la cuenta administrada. Por ejemplo, una cuenta administrada con un UPN "user@contoso.com" que ha iniciado en OneDrive no es igual que una cuenta con un UPN "user@contoso.com" que ha iniciado sesión en Dropbox. Si se accede a un servicio desconocido o que no figura en la lista al iniciar sesión en la cuenta administrada (por ejemplo, "user@contoso.com" ha iniciado sesión en OneDrive), debe representarse mediante la ubicación `AccountDocument`. Si el servicio desconocido o que no figura en la lista inicia sesión mediante otra cuenta (por ejemplo, "user@contoso.com" ha iniciado sesión en Dropbox), no accede a la ubicación con una cuenta administrada y debe representarse mediante la ubicación `Other`.

### <a name="sharing-blocked-alert"></a>Uso compartido de alerta de bloqueo

Se puede usar una función auxiliar de interfaz de usuario si se llama a la API `isSaveToAllowedForLocation` o `isOpenFromAllowedForLocation` y se descubre que bloquea la acción de guardado o apertura. Si la aplicación quiere notificar al usuario que la acción se ha bloqueado, puede llamar a la API `showSharingBlockedMessage` definida en `IntuneMAMUIHelper.h` para presentar una vista de alerta con un mensaje genérico.

## <a name="share-data-via-uiactivityviewcontroller"></a>Compartir datos a través de UIActivityViewController

A partir de la versión 8.0.2, Intune App SDK puede filtrar las acciones `UIActivityViewController` para que solo las ubicaciones de recursos compartidos administrados de Intune estén disponibles para la selección. Este comportamiento se controlará mediante la directiva de transferencia de datos de aplicación.

### <a name="copy-to-actions"></a>Acciones "Copiar a"

Al compartir documentos a través de `UIActivityViewController` y `UIDocumentInteractionController`, en iOS se muestran acciones "Copiar en" para cada aplicación que admita la apertura del documento que se comparte. Las aplicaciones declaran los tipos de documento que admiten a través de la configuración `CFBundleDocumentTypes` en su archivo Info.plist. Este tipo de uso compartido ya no estará disponible si la directiva no permite el uso compartido con aplicaciones no administradas. Como reemplazo, los usuarios tendrán que agregar una extensión de acción que no sea de interfaz de usuario a la aplicación y vincularla a Intune App SDK. La extensión de acción es un simple código auxiliar. El SDK implementará el comportamiento del uso compartido de archivos. Siga estos pasos:

1. La aplicación debe tener al menos un elemento schemeURL definido en `CFBundleURLTypes` en su archivo Info.plist junto con su homólogo `-intunemam`. Por ejemplo:
    ```objc
    <key>CFBundleURLSchemes</key>
    <array>
        <string>launch-com.contoso.myapp</string>
        <string>launch-com.contoso.myapp-intunemam</string>
    </array>
    ```

2. La aplicación y la extensión de acción deben compartir al menos un grupo de aplicaciones, y el grupo de aplicaciones debe aparecer en la matriz `AppGroupIdentifiers` bajo los diccionarios IntuneMAMSettings de la aplicación y la extensión.

3. Tanto la aplicación como la extensión de acción deben tener la funcionalidad Uso compartido de cadenas de claves y compartir el grupo de cadena de claves `com.microsoft.intune.mam`.

4. Asigne a la extensión de acción el nombre "Abrir en" seguido del nombre de la aplicación. Localizar el archivo Info.plist según sea necesario.

5. Proporcione un icono de plantilla para la extensión como se describe en la [documentación para desarrolladores de Apple](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/). Como alternativa, la herramienta IntuneMAMConfigurator puede usarse para generar estas imágenes desde el directorio .app de la aplicación. Para hacerlo, ejecute lo siguiente:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

6. En IntuneMAMSettings, en el archivo Info.plist de la extensión, agregue un valor booleano denominado `OpenInActionExtension` con el valor SÍ.

7. Configure `NSExtensionActivationRule` para admitir un único archivo y todos los tipos de `CFBundleDocumentTypes` de la aplicación con el prefijo `com.microsoft.intune.mam`. Por ejemplo, si la aplicación admite public.text y public.image, la regla de activación sería:

    ```objc
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image").@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Actualización de las extensiones de recurso Compartir y Acción

Si la aplicación ya contiene las extensiones Compartir o Acción, su `NSExtensionActivationRule` tendrá que modificarse para permitir los tipos de Intune. Para cada tipo admitido por la extensión, agregue un tipo adicional con el prefijo `com.microsoft.intune.mam`. Por ejemplo, si la regla de activación existente es:  

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
    ).@count > 0
).@count > 0
```

Se debe cambiar a:

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data"
    ).@count > 0
).@count > 0
```

> [!NOTE]
> La herramienta IntuneMAMConfigurator puede usarse para agregar los tipos de Intune a la regla de activación. Si la regla de activación existente utiliza las constantes de cadena predefinidas (por ejemplo, NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText, etc.), la sintaxis del predicado puede llegar a ser bastante compleja. La herramienta IntuneMAMConfigurator también puede usarse para convertir la regla de activación de las constantes de cadena en una cadena de predicado al agregar los tipos de Intune.

### <a name="what-the-ui-should-look-like"></a>Aspecto de la interfaz de usuario

Interfaz de usuario anterior:

![Uso compartido de datos - Interfaz de usuario de uso compartido anterior de iOS](./media/app-sdk-ios/sharing-UI-old.png)

Interfaz de usuario nueva:

![Uso compartido de datos - Interfaz de usuario de uso compartido nueva de iOS](./media/app-sdk-ios/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>Habilitar la configuración de destino (configuración de la aplicación de APP y MAM) para las aplicaciones de iOS

La configuración de destino de MAM (también denominada configuración de aplicación de MAM) permite que una aplicación reciba datos de configuración a través del SDK de Intune. El desarrollador o el propietario de la aplicación debe definir y comunicar a los clientes de Intune el formato y las variantes de estos datos.

Los administradores de Intune pueden seleccionar como destino e implementar los datos de configuración mediante Azure Portal de Intune y Graph API de Intune. A partir de la versión 7.0.1 de Intune App SDK para iOS, a las aplicaciones que estén participando en la configuración de destino de MAM se les pueden proporcionar datos de la configuración de destino de MAM mediante el servicio MAM. Los datos de configuración de la aplicación se insertan a través del servicio MAM directamente en la aplicación, y no a través del canal de MDM. Intune App SDK proporciona una clase para tener acceso a los datos recuperados de estas consolas. Los elementos siguientes son requisitos previos:

* La aplicación necesita estar inscrita en el servicio MAM de Intune para acceder a la interfaz de usuario de la configuración de destino de MAM. Para obtener más información, vea [Recepción de la directiva de protección de aplicaciones](#receive-app-protection-policy).

* Incluya `IntuneMAMAppConfigManager.h` en el archivo de origen de la aplicación.

* Llame a `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` para obtener el objeto de configuración de la aplicación.

* Llame al selector adecuado en el objeto `IntuneMAMAppConfig`. Por ejemplo, si la clave de la aplicación es una cadena, querrá usar `stringValueForKey` o `allStringsForKey`. Vea `IntuneMAMAppConfig.h` para obtener una descripción detallada de los valores devueltos y las condiciones de error.

Para más información sobre las capacidades de Graph API, vea la [referencia de Graph API](https://developer.microsoft.com/graph/docs/concepts/overview).

Para obtener más información sobre cómo crear una directiva de configuración de aplicaciones destinada a MAM en iOS, vea la sección de la configuración de aplicaciones destinadas a MAM en [Uso de directivas de configuración de aplicaciones de Microsoft Intune para iOS/iPadOS](../apps/app-configuration-policies-use-ios.md).

## <a name="telemetry"></a>Telemetría

De manera predeterminada, Intune App SDK para iOS recopila la telemetría en los tipos de evento siguientes:

* **Inicio de la aplicación**: para ayudar a Microsoft Intune a obtener información sobre el uso de la aplicación habilitada para MAM por tipo de administración (inscripción de MAM con MDM, de MAM sin MDM, etc.).

* **Llamadas de inscripción**: para ayudar a Microsoft Intune a obtener información sobre la tasa de éxito y otras métricas de rendimiento de las llamadas de inscripción desde el cliente.

* **Acciones de Intune**: para ayudar a diagnosticar los problemas y garantizar la funcionalidad de Intune, se recopila información sobre las acciones del SDK de Intune.

> [!NOTE]
> Si decide no enviar datos de telemetría del SDK para aplicaciones de Intune a Microsoft desde su aplicación móvil, debe deshabilitar la transmisión de telemetría de Intune App SDK. Establezca la propiedad `MAMTelemetryDisabled` en SÍ en el diccionario IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Habilitar varias identidades (opcional)

De forma predeterminada, el SDK aplicará una directiva a la aplicación en su conjunto. La característica de varias identidades es una característica MAM que puede habilitar para aplicar una directiva en un nivel por identidad. Esto requiere más participación en la aplicación que otras características de MAM.

La aplicación debe informar al SDK de la aplicación cuando intente cambiar la identidad activa. El SDK también notificará a la aplicación cuando se requiera un cambio de identidad. Actualmente, solo se admite una identidad administrada. Una vez que el usuario inscriba el dispositivo o la aplicación, el SDK usa esta identidad y la considera la identidad administrada principal. Los demás usuarios de la aplicación se tratarán como usuarios no administrados con una configuración de directiva sin restricciones.

Tenga en cuenta que una identidad se define simplemente como una cadena. Las identidades no distinguen mayúsculas de minúsculas. Las solicitudes al SDK podrían no devolverse con el mismo uso de mayúsculas y minúsculas que se empleó originalmente al establecer la identidad.

### <a name="identity-overview"></a>Información general sobre la identidad

Una identidad es simplemente el nombre de usuario de una cuenta (por ejemplo, user@contoso.com). Los desarrolladores pueden establecer la identidad de la aplicación en los siguientes niveles:

* **Identidad de proceso**: establece la identidad de todo el proceso y se usa principalmente para aplicaciones de una sola identidad. Esta identidad afecta a todas las tareas, los archivos y la interfaz de usuario.

* **Identidad de la interfaz de usuario**: determina qué directivas se aplican a las tareas de la interfaz de usuario en el subproceso principal, como cortar/copiar/pegar, PIN, autenticación y uso compartido de datos. La identidad de la interfaz de usuario no afecta a las tareas de archivos como el cifrado y la copia de seguridad.

* **Identidad de subproceso**: afecta a qué directivas se aplican en el subproceso actual. Esta identidad afecta a todas las tareas, los archivos y la interfaz de usuario.

La aplicación es responsable de establecer las identidades correctamente, tanto si el usuario está administrado como si no.

En todo momento, los subprocesos tienen una identidad eficaz para las tareas de la interfaz de usuario y las tareas de archivos. Esta es la identidad que se usa para comprobar qué directivas se deben aplicar, en caso de que las haya. Si la identidad es "Ninguna identidad" o si el usuario no está administrado, no se aplica ninguna directiva. Los diagramas siguientes muestran cómo se determinan las identidades reales.

  ![SDK de aplicaciones de Intune para iOS: proceso de determinación de identidad](./media/app-sdk-ios/ios-thread-identities.png)

### <a name="thread-queues"></a>Colas de subprocesos

Las aplicaciones a menudo envían tareas sincrónicas y asincrónicas a colas de subprocesos. El SDK intercepta las llamadas a Grand Central Dispatch (GCD) y asocia la identidad del subproceso actual a las tareas enviadas. Cuando finalizan las tareas, el SDK cambia temporalmente la identidad del subproceso a la identidad asociada con la tarea, finaliza las tareas y restaura la identidad del subproceso original.


Dado que `NSOperationQueue` se basa en GCD, `NSOperations` se ejecutará en la identidad del subproceso en el momento en que las tareas se agreguen a `NSOperationQueue`. `NSOperations` o las funciones que se envían usando GCD directamente también pueden cambiar la identidad del subproceso actual cuando se ejecutan. Esta identidad invalidará la identidad heredada del subproceso que envía.

### <a name="file-owner"></a>Propietario del archivo

El SDK hace un seguimiento de las identidades de los propietarios del archivo local y aplica las directivas según corresponda. El propietario del archivo se establece cuando el archivo se crea o se abre en modo de truncamiento. El propietario se establece en la identidad de la tarea de archivo efectiva del subproceso que realiza la tarea.

Las aplicaciones también pueden establecer la identidad del propietario del archivo explícitamente mediante `IntuneMAMFilePolicyManager`. Las aplicaciones pueden usar `IntuneMAMFilePolicyManager` para recuperar el propietario del archivo y establecer la identidad de la interfaz de usuario antes de mostrar el contenido del archivo.

### <a name="shared-data"></a>Datos compartidos

Si la aplicación crea archivos que contienen datos de los usuarios administrados y no administrados, la aplicación es responsable de cifrar los datos del usuario administrado. Puede cifrar los datos mediante el uso de las API `protect` y `unprotect` en `IntuneMAMDataProtectionManager`.

El método `protect` acepta una identidad que puede ser un usuario administrado o no administrado. Si el usuario está administrado, se cifrarán los datos. Si el usuario no está administrado, se agregará un encabezado a los datos para cifrar la identidad, pero los datos no se cifrarán. Puede usar el método `protectionInfo` para recuperar el propietario de los datos.

### <a name="share-extensions"></a>Extensiones de recurso compartido

Si la aplicación contiene una extensión de recurso compartido, el propietario del elemento que se comparte se puede recuperar mediante el método `protectionInfoForItemProvider` en `IntuneMAMDataProtectionManager`. Si el elemento compartido es un archivo, el SDK controlará la configuración de propietario del archivo. Si el elemento compartido son datos, la aplicación es responsable de establecer el propietario del archivo si estos datos se almacenan en un archivo, y de la llamada a la API de `setUIPolicyIdentity` antes de mostrar estos datos en la interfaz de usuario.

### <a name="turn-on-multi-identity"></a>Activar varias identidades

De forma predeterminada, se considera que las aplicaciones son de una única identidad. El SDK establece la identidad del proceso en el usuario inscrito. Para habilitar la compatibilidad con varias identidades, agregue un valor booleano denominado `MultiIdentity` y un valor SÍ al diccionario IntuneMAMSettings en el archivo Info.plist de la aplicación.

> [!NOTE]
> Cuando se habilita la característica de varias identidades, la identidad del proceso, la identidad de la interfaz de usuario y las identidades de subproceso se establecerán en "nulo". La aplicación es responsable de la configuración de forma adecuada.

### <a name="switch-identities"></a>Cambiar identidades

* **Cambio de identidad iniciado por la aplicación**:

    Cuando se inicia una aplicación con varias identidades, se considera que se ejecuta en una cuenta desconocida no administrada. La interfaz de usuario de inicio condicional no se ejecutará ni se aplicará ninguna directiva en la aplicación. La aplicación es responsable de notificarle al SDK si debe cambiarse la identidad. Normalmente, esto ocurre cada vez que la aplicación va a mostrar los datos de una cuenta de usuario específica.

    Un ejemplo es cuando el usuario intenta abrir un documento, un buzón o una pestaña en un portátil. La aplicación debe notificar al SDK antes de que el archivo, el buzón o la pestaña se abra realmente. Esto se hace mediante la API `setUIPolicyIdentity` en `IntuneMAMPolicyManager`. Se debe llamar a esta API tanto si el usuario está administrado como si no. Si el usuario está administrado, el SDK llevará a cabo las comprobaciones de inicio condicional (como la detección de jailbreak, PIN y autenticación).

    El resultado del cambio de identidad se devuelve a la aplicación de forma asincrónica a través de un controlador de finalización. La aplicación debe posponer la apertura del documento, el buzón de correo o la ficha hasta que se devuelva un código de resultado correcto. Si se produce un error en el cambio de identidad, la aplicación debe cancelar la tarea.

* **Cambio de identidad iniciado por el SDK**:

    A veces, el SDK debe pedirle a la aplicación que cambie a una identidad específica. Las aplicaciones de varias identidades deben implementar el método `identitySwitchRequired` en `IntuneMAMPolicyDelegate` para controlar esta solicitud.

    Cuando se llama a este método, si la aplicación puede atender la solicitud para cambiar a la identidad especificada, debe pasar `IntuneMAMAddIdentityResultSuccess` al controlador de finalización. Si no puede atender el cambio de identidad, la aplicación debe pasar `IntuneMAMAddIdentityResultFailed` al controlador de finalización.

    La aplicación no tiene que llamar a `setUIPolicyIdentity` en respuesta a esta llamada. Si el SDK necesita que la aplicación cambie a una cuenta de usuario no administrado, se pasará la cadena vacía en la llamada a `identitySwitchRequired`.

* **Borrado selectivo**:

    Cuando la aplicación se borra de forma selectiva, el SDK llama al método `wipeDataForAccount` en `IntuneMAMPolicyDelegate`. La aplicación es responsable de quitar la cuenta del usuario especificado y todos los datos asociados. El SDK puede quitar todos los archivos que pertenecen al usuario, y lo hará si la aplicación devuelve FALSE tras la llamada a `wipeDataForAccount`.

    Tenga en cuenta que este método se llama desde un subproceso en segundo plano. La aplicación no debe devolver un valor hasta que se hayan quitado todos los datos del usuario (a excepción de los archivos si la aplicación devuelve el valor FALSE).

## <a name="siri-intents"></a>Intenciones de Siri
Si la aplicación se integra con las intenciones de Siri, asegúrese de leer los comentarios de `areSiriIntentsAllowed` en `IntuneMAMPolicy.h` para obtener instrucciones sobre cómo admitir este escenario. 
    
## <a name="notifications"></a>Notificaciones
Si la aplicación recibe notificaciones, asegúrese de leer los comentarios de `notificationPolicy` en `IntuneMAMPolicy.h` para obtener instrucciones sobre cómo admitir este escenario.  Se recomienda que las aplicaciones se registren para `IntuneMAMPolicyDidChangeNotification` como se describe en `IntuneMAMPolicyManager.h` y que comuniquen este valor a su instancia de `UNNotificationServiceExtension` a través de la cadena de claves.
## <a name="displaying-web-content-within-application"></a>Representación de contenido web dentro de la aplicación
Si la aplicación tiene la capacidad de mostrar sitios web en una vista web, y las páginas web que se muestran tienen la capacidad de navegar a sitios arbitrarios, la aplicación será responsable de establecer la identidad actual para que los datos administrados no se puedan filtrar a través de la vista web. Ejemplos de esto son las páginas web "Sugerir una característica" o "Comentarios" que tienen vínculos directos o indirectos a un motor de búsqueda.
Las aplicaciones de varias identidades deben llamar a setUIPolicyIdentity de IntuneMAMPolicyManager y pasar la cadena vacía antes de mostrar la vista web. Una vez que se cierra la vista web, la aplicación debe llamar a setUIPolicyIdentity y pasar la identidad actual.
Las aplicaciones de una sola identidad deben llamar a setCurrentThreadIdentity de IntuneMAMPolicyManager y pasar la cadena vacía antes de mostrar la vista web. Una vez que se cierra la vista web, la aplicación debe llamar a setCurrentThreadIdentity y no pasar nada.

## <a name="ios-best-practices"></a>Prácticas recomendadas de iOS

Aquí hay algunas prácticas recomendadas para el desarrollo de iOS:

* El sistema de archivos iOS distingue mayúsculas de minúsculas. Asegúrese de que el caso sea correcto para los nombres de archivo como `libIntuneMAM.a` y `IntuneMAMResources.bundle`.

* Si Xcode tiene problemas para encontrar `libIntuneMAM.a`, puede corregir el problema agregando la ruta de acceso a esta biblioteca en las rutas de acceso de búsqueda del enlazador.

## <a name="faqs"></a>Preguntas más frecuentes

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>¿Son todas las API direccionables a través de Swift nativo o la interoperabilidad de Objective-C y Swift?

Las API de Intune App SDK solo están en Objective-C y no admiten Swift **nativo**. Se requiere la interoperabilidad de Swift con Objective-C.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>¿Es necesario registrar todos los usuarios de la aplicación con el servicio de APP-WE?

No. De hecho, solo se deben registrar las cuentas profesionales o educativas con el SDK de aplicaciones de Intune. Las aplicaciones son responsables de determinar si una cuenta se usa en un contexto profesional o educativo.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>¿Qué ocurre con los usuarios que ya han iniciado sesión en la aplicación? ¿Es necesario inscribirlos?

La aplicación es responsable de inscribir a los usuarios después de que se han autenticado correctamente. La aplicación también es responsable de la inscripción de cualquier cuenta existente que se presente antes de que la aplicación tuviera una funcionalidad MAM sin MDM.

Para ello, la aplicación debe usar el método `registeredAccounts:`. Este método devuelve un NSDictionary que contiene todas las cuentas registradas en el servicio de MAM de Intune. Si algunas de las cuentas existentes en la aplicación no están en la lista, la aplicación debe registrar e inscribir dichas cuentas mediante `registerAndEnrollAccount:`.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>¿Con qué frecuencia debe el SDK volver a intentar las inscripciones?

El SDK volverá a intentar automáticamente todas las inscripciones en las que se produjo un error transcurrido un intervalo de 24 horas. El SDK lo hace para asegurarse de que, en caso de que la organización de un usuario habilitara MAM después de que el usuario hubiese iniciado sesión en la aplicación, el usuario se inscriba correctamente y reciba las directivas.

El SDK dejará de intentarlo cuando detecte que el usuario ha inscrito correctamente en la aplicación. Esto se debe a que solo un usuario puede inscribir una aplicación en un momento dado. Si el usuario ha anulado la inscripción, los reintentos comenzarán de nuevo transcurrido dicho intervalo de 24 horas.

### <a name="why-does-the-user-need-to-be-deregistered"></a>¿Por qué es necesario anular el registro del usuario?

El SDK realizará periódicamente estas acciones en segundo plano:

* Si la aplicación aún no se ha inscrito, intentará inscribir todas las cuentas registradas cada 24 horas.
* Si la aplicación está inscrita, el SDK comprobará si hay actualizaciones de la directiva de MAM cada 8 horas.

Al el registro de un usuario, se le notifica al SDK que el usuario ya no usará la aplicación y que el SDK puede interrumpir todos los eventos periódicos para esa cuenta de usuario. También se desencadena la anulación de la inscripción de la aplicación y un borrado selectivo si es necesario.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>¿Debo establecer la marca doWipe en True en el método de anulación del registro?

Se debe llamar a este método antes de que el usuario cierre la sesión en la aplicación.  Si los datos del usuario se eliminan de la aplicación como parte del cierre de sesión, `doWipe` se puede establecer en False. Sin embargo, si la aplicación no elimina los datos del usuario, `doWipe` se debe establecer en True para que el SDK pueda eliminar los datos.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>¿Hay otras maneras de anular la inscripción de una aplicación?

Sí, el administrador de TI puede enviar un comando de borrado selectivo a la aplicación. Así podrá cancelar el registro y cancelar la inscripción del usuario, y borrará los datos del usuario. El SDK se encarga automáticamente de esta situación y envía una notificación a través del método delegado de anulación de inscripción.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>¿Hay una aplicación de ejemplo en la que se muestre cómo integrar el SDK?

Sí. Recientemente hemos renovado nuestra aplicación de ejemplo de código abierto [Wagr for iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App). Ahora Wagr está habilitada para la directiva de protección de aplicaciones mediante Intune App SDK.

### <a name="how-can-i-troubleshoot-my-app"></a>¿Cómo puedo solucionar problemas de mi aplicación?

El SDK de Intune para iOS 9.0.3 y versiones superiores permite agregar una consola de diagnóstico dentro de la aplicación móvil para probar directivas y registrar errores. `IntuneMAMDiagnosticConsole.h` define la interfaz de la clase `IntuneMAMDiagnosticConsole`, que los desarrolladores pueden usar para mostrar la consola de diagnóstico de Intune. Durante la prueba, esto permite a los usuarios finales o a los desarrolladores recopilar y compartir registros de Intune para ayudar a diagnosticar cualquier problema que puedan tener. Esta API es opcional para los integradores.

## <a name="submit-your-app-to-the-app-store"></a>Enviar la aplicación a la Tienda de aplicaciones

Las compilaciones de marco y biblioteca estáticas de Intune App SDK son archivos binarios universales. Esto significa que tienen código para todas las arquitecturas de simulador y dispositivo. Apple rechazará las aplicaciones enviadas a la Tienda de aplicaciones si contienen código de simulador. Al compilar con la biblioteca estática para las compilaciones de solo dispositivo, el enlazador eliminará automáticamente el código de simulador. Siga los pasos siguientes para asegurarse de que se quite todo el código de simulador antes de cargar la aplicación a la Tienda de aplicaciones.

1. Asegúrese de que `IntuneMAM.framework` está en el escritorio.

2. Ejecute estos comandos:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```

    El primer comando elimina las arquitecturas de simulador del archivo DYLIB del marco. El segundo comando copia el archivo DYLIB solo de dispositivos de nuevo en el directorio del marco.
