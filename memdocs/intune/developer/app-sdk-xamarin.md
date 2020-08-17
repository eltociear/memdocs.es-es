---
title: Enlaces Xamarin del SDK para aplicaciones de Microsoft Intune
description: Los enlaces Xamarin del SDK para aplicaciones de Intune habilitan la directiva de protección de aplicaciones de Intune en las aplicaciones para iOS y Android creadas con Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/06/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune, has-adal-ref
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3d54a03290b7d2020b6ec13b64f985613c0a292d
ms.sourcegitcommit: 4f10625e8d12aec294067a1d9138cbce19707560
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87912320"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Enlaces Xamarin del SDK para aplicaciones de Microsoft Intune

> [!NOTE]
> Puede que quiera leer primero el artículo [Introducción a Intune App SDK](app-sdk-get-started.md), en el que se explica cómo preparar la integración en cada plataforma compatible.

## <a name="overview"></a>Introducción
Los [enlaces Xamarin del SDK para aplicaciones de Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) habilitan la [directiva de protección de aplicaciones de Intune](../apps/app-protection-policy.md) en las aplicaciones para iOS y Android creadas con Xamarin. Los enlaces permiten a los desarrolladores integrar fácilmente funciones de protección de la aplicación de Intune en su aplicación basada en Xamarin.

Los enlaces Xamarin del SDK para aplicaciones de Microsoft Intune permiten incorporar directivas de protección de aplicaciones de Intune, (también conocidas como directivas MAM o APP), a sus aplicaciones desarrolladas con Xamarin. Una aplicación MAM es aquella que está integrada con Intune App SDK. Los administradores de TI pueden implementar directivas de protección de aplicaciones en la aplicación móvil cuando Intune la administra activamente.

## <a name="whats-supported"></a>¿Qué se admite?

### <a name="developer-machines"></a>Equipos de desarrollador
* Windows (Visual Studio versión 15.7+)
* macOS

### <a name="mobile-app-platforms"></a>Plataformas de aplicaciones móviles
* Android
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Escenarios de administración de aplicaciones móviles de Intune

* Intune APP-WE (sin inscripción de dispositivos)
* Dispositivos inscritos con MDM de Intune
* Dispositivos inscritos con EMM de terceros

Ahora, las aplicaciones Xamarin compiladas con los enlaces Xamarin del SDK para aplicaciones de Intune pueden recibir directivas de protección de aplicaciones de Intune en dispositivos inscritos con la administración de dispositivos móviles (MDM) de Intune y en dispositivos no inscritos.

## <a name="prerequisites"></a>Requisitos previos

Revise los [términos de licencia](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Imprimir y conservar una copia de los términos de licencia para sus archivos. Al descargar y usar los enlaces Xamarin del SDK de aplicaciones de Intune, acepta dichos términos. Si no los acepta, no use el software.

El SDK de Intune se basa en la herramienta [Biblioteca de autenticación de Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/v2-overview) para sus escenarios de inicio condicional y [autenticación](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/), que requieren que las aplicaciones se configuren con [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Si la aplicación ya se ha configurado para usar MSAL y tiene su propio id. de cliente personalizado para la autenticación con Azure Active Directory, asegúrese de seguir los pasos para conceder permisos a la aplicación de Xamarin para el servicio de administración de dispositivos móviles (MAM) de Intune. Siga las instrucciones de la sección [Proporcione a la aplicación acceso al servicio Intune App Protection](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional) de la [Introducción al SDK para aplicaciones de Microsoft Intune](app-sdk-get-started.md).

## <a name="security-considerations"></a>Consideraciones de seguridad

Para evitar posibles suplantaciones de identidad, la divulgación de información y ataques de elevación de privilegios:

* Asegúrese de que el desarrollo de una aplicación de Xamarin se realiza en una estación de trabajo segura.
* Asegúrese de que los enlaces proceden de un origen válido de Microsoft:
  * [Perfil de NuGet de MS Intune App SDK](https://www.nuget.org/profiles/msintuneappsdk)
  * [Repositorio de GitHub de Xamarin de Intune App SDK](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* Defina la configuración de NuGet para que el proyecto confíe en los paquetes NuGet firmados y sin modificar.
Vea [Instalación de paquetes firmados](https://docs.microsoft.com/nuget/consume-packages/installing-signed-packages) para obtener más información.
* Proteja el directorio de salida que contiene la aplicación de Xamarin. Considere el uso de un directorio de nivel de usuario para la salida.


## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilitar directivas de protección de aplicaciones de Intune en su aplicación móvil iOS
1. Agregue el [paquete de NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) a su proyecto Xamarin.iOS.
2. Siga los pasos generales necesarios para integrar el SDK de aplicaciones de Intune en una aplicación móvil de iOS. Puede comenzar con el paso 3 de las instrucciones de integración de la [Guía para desarrolladores sobre el SDK de aplicaciones de Intune para iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Puede omitir el paso final de esa sección consistente en ejecutar IntuneMAMConfigurator, ya que esta herramienta se incluye en el paquete Microsoft.Intune.MAM.Xamarin.iOS y se ejecutará automáticamente en tiempo de compilación.
    **Importante**: la habilitación del uso compartido de la cadena de claves para una aplicación es ligeramente diferente en Visual Studio en comparación con Xcode. Abra el plist de derechos de la aplicación y asegúrese de que está habilitada la opción "Habilitar cadena de claves" y de que se han agregado los grupos de uso compartido de la cadena de claves adecuados en esa sección. A continuación, asegúrese de que se especifica el plist de derechos en el campo "Derechos personalizados" de las opciones del proyecto "Firma de lote para iOS" para todas las combinaciones de configuración/plataforma adecuadas.
3. Una vez que se agregan los enlaces y la aplicación está correctamente configurada, la aplicación puede empezar a usar las API del SDK de Intune. Para ello, debe incluir el espacio de nombres siguiente:

      ```csharp
      using Microsoft.Intune.MAM;
      ```

4. Para empezar a recibir las directivas de protección de aplicaciones, la aplicación debe inscribirse en el servicio de MAM de Intune. Si en la aplicación no se usa la [Biblioteca de autenticación de Microsoft](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) para autenticar a los usuarios y quiere que el SDK de Intune administre la autenticación, la aplicación deberá proporcionar el UPN del usuario al método LoginAndEnrollAccount de IntuneMAMEnrollmentManager:

      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

      Las aplicaciones podrían pasar un valor nulo si el UPN del usuario es desconocido en el momento de hacer la llamada. En este caso, se pedirá a los usuarios que escriban su dirección de correo electrónico y su contraseña.
      
      Si en la aplicación ya se usa MSAL para autenticar a los usuarios, puede configurar una experiencia de inicio de sesión único (SSO) entre la aplicación y el SDK de Intune. En primer lugar, deberá reemplazar la configuración predeterminada de AAD que usa el SDK de Intune por la de la aplicación. Puede hacerlo mediante el diccionario IntuneMAMSettings de Info.plist de la aplicación, como se menciona en [Guía para desarrolladores acerca del SDK de aplicaciones de Microsoft Intune para iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), o bien puede hacerlo en el código a través de las propiedades de invalidación de AAD de la clase IntuneMAMSettings. El enfoque de Info.plist se recomienda para las aplicaciones cuyos valores de MSAL son estáticos, aunque se recomienda usar las propiedades de invalidación para las aplicaciones que los determinan en tiempo de ejecución. Cuando se hayan configurado todas las opciones del inicio de sesión único, su aplicación debe proporcionar el UPN del usuario al método RegisterAndEnrollAccount de IntuneMAMEnrollmentManager una vez que se haya autenticado correctamente:

      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```

      Las aplicaciones pueden determinar el resultado de un intento de inscripción implementando el método EnrollmentRequestWithStatus en una subclase de IntuneMAMEnrollmentDelegate y estableciendo la propiedad Delegate de IntuneMAMEnrollmentManager en una instancia de esa clase. 

      Una vez efectuada la inscripción correctamente, las aplicaciones pueden determinar el UPN de la cuenta inscrita (si antes era desconocido) consultando la siguiente propiedad: 

      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
### <a name="sample-applications"></a>Aplicaciones de ejemplo
En [GitHub](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) hay disponibles aplicaciones de ejemplo que resaltan la funcionalidad de MAM de las aplicaciones de Xamarin.iOS.

> [!NOTE] 
> No hay ningún Remapper para iOS/iPadOS. La integración en una aplicación de Xamarin.Forms debería ser igual que para un proyecto normal de Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Habilitación de directivas de protección de aplicaciones de Intune en la aplicación móvil Android
1. Agregue el [paquete de NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) a su proyecto Xamarin.Android.
    1. Para aplicaciones Xamarin.Forms, agregue también el [paquete NuGet Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) al proyecto Xamarin.Android. 
2. Siga los pasos generales necesarios para [integrar el SDK de aplicaciones de Intune](app-sdk-android.md) en una aplicación móvil Android y consulte este documento para más detalles.

### <a name="xamarinandroid-integration"></a>Integración de Xamarin.Android

Encontrará una descripción general muy completa para integrar el SDK de aplicaciones de Intune en la [Guía para desarrolladores sobre el SDK de aplicaciones de Microsoft Intune](app-sdk-android.md). Según vaya leyendo la guía e integrando el SDK de aplicaciones de Intune con la aplicación de Xamarin, comprobará que en las secciones siguientes se resaltan las diferencias entre la implementación de una aplicación nativa de Android desarrollada en Java y una aplicación de Xamarin desarrollada en C#. Estas secciones deben tratarse como complementarias y no pretende sustituir la lectura de la guía en su totalidad.

#### <a name="remapper"></a>Remapper
A partir de la versión 1.4428.1, se puede agregar el paquete `Microsoft.Intune.MAM.Remapper` a una aplicación de Xamarin.Android como [herramientas de compilación](app-sdk-android.md#build-tooling) para efectuar reemplazos de clase MAM, métodos y servicios del sistema. Si se incluye Remapper, las partes de reemplazo equivalentes a MAM de las secciones Métodos renombrados y Aplicación MAM se realizan automáticamente cuando se compila la aplicación.

Para impedir que Remapper aplique MAM a una clase, se puede agregar la siguiente propiedad al archivo `.csproj` de los proyectos.

```xml
  <PropertyGroup>
    <ExcludeClasses>Semicolon separated list of relative class paths to exclude from MAM-ification</ExcludeClasses>
  </PropertyGroup>
```

> [!NOTE]
> Actualmente Remapper impide la depuración en aplicaciones de Xamarin.Android. Se recomienda la integración manual para depurar la aplicación.

#### <a name="renamed-methods"></a>[Métodos renombrados](app-sdk-android.md#renamed-methods)
En muchos casos, un método que se encuentra en la clase Android se marca como final de la clase de reemplazo MAM. En este caso, la clase de reemplazo MAM proporciona un método con un nombre similar (generalmente lleva el sufijo `MAM`) que es el que se debe reemplazar. Por ejemplo, al derivar desde `MAMActivity`, en lugar de reemplazar `OnCreate()` y llamar a `base.OnCreate()`, `Activity` debe reemplazar a `OnMAMCreate()` y llamar a `base.OnMAMCreate()`.

#### <a name="mam-application"></a>[Aplicación MAM](app-sdk-android.md#mamapplication)
La aplicación debe definir una clase `Android.App.Application`. Si se integra MAM de forma manual, debe heredarse de `MAMApplication`. Asegúrese de que la subclase esté correctamente representada con el atributo `[Application]` y de que invalide al constructor `(IntPtr, JniHandleOwnership)`.

```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

> [!NOTE]
> Un problema con los enlaces de Xamarin de MAM puede hacer que la aplicación se bloquee cuando se implementa en modo de depuración. Como alternativa, el atributo `Debuggable=false` debe agregarse a la clase `Application` y la marca `android:debuggable="true"` debe quitarse del manifiesto si se estableció manualmente.

#### <a name="enable-features-that-require-app-participation"></a>[Habilitación de características que requieren la participación de la aplicación](app-sdk-android.md#enable-features-that-require-app-participation)
Ejemplo: determine si se requiere un PIN para la aplicación

```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```

Ejemplo: determine el usuario primario de Intune

```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```

Ejemplo: determine si se permite guardar en un dispositivo o en almacenamiento en nube

```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdk"></a>[Registro para recibir notificaciones del SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
La aplicación se debe registrar para recibir notificaciones del SDK mediante la creación de `MAMNotificationReceiver` y su registro mediante `MAMNotificationReceiverRegistry`. Para ello, se proporcionan el receptor y el tipo de notificación deseada en `App.OnMAMCreate`, como se ilustra en el ejemplo siguiente:

```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
        registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-manager"></a>[Administrador de inscripción de MAM](app-sdk-android.md#mamenrollmentmanager)

```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Integración de Xamarin.Forms

Para las aplicaciones `Xamarin.Forms` el paquete `Microsoft.Intune.MAM.Remapper` remplaza las clases de MAM automáticamente mediante la inserción de clases `MAM` en la jerarquía de clases `Xamarin.Forms` de uso común. 

> [!NOTE]
> Se debe realizar la integración de Xamarin.Forms además de la integración de Xamarin.Android detallada anteriormente. Remapper se comporta de forma diferente en las aplicaciones de Xamarin.Forms, por lo que se deben seguir realizando los reemplazos de MAM manuales.

Una vez agregado el reasignador al proyecto, deberá realizar los reemplazos equivalentes de MAM. Por ejemplo, `FormsAppCompatActivity` y `FormsApplicationActivity` pueden seguir utilizándose en las invalidaciones de aplicación proporcionada a `OnCreate` y `OnResume` se reemplaza por `OnMAMCreate` y `OnMAMResume` equivalentes de MAM respectivamente.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```

Si no se realizan los reemplazos, pueden producirse los siguientes errores de compilación hasta que realice las sustituciones:
* [Error del compilador CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Este error suele aparecer con el formato ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Es lo que se espera porque, cuando el reasignador modifica la herencia de clases de Xamarin, algunas funciones pasarán a ser `sealed` y se agregará una nueva variante de MAM para el reemplazo.
* [Error del compilador CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): este error suele aparecer con el formato ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Como el reasignador cambia la herencia de algunas clases de Xamarin, algunas de las funciones miembro se cambian a `public`. Si reemplaza cualquiera de estas funciones, es posible que deba cambiar esos modificadores de acceso por esos reemplazos para que también sean `public`.

> [!NOTE]
> El reasignador reescribe una dependencia que Visual Studio emplea para la finalización automática de IntelliSense. Por tanto, es posible que deba volver a cargar y recompilar el proyecto cuando se agrega el reasignador para que IntelliSense reconozca correctamente los cambios.

#### <a name="troubleshooting"></a>Solucionar problemas
* Si encuentra una pantalla en blanco en la aplicación al inicio, es posible que tenga que forzar las llamadas de navegación para que se ejecuten en el subproceso principal.
* Los enlaces Xamarin del SDK de Intune no admiten aplicaciones que usan un marco multiplataforma como MvvmCross debido a conflictos entre MvvmCross y las clases MAM de Intune. Aunque es posible que algunos clientes hayan logrado una integración correcta después de mover sus aplicaciones a Xamarin.Forms simple, no se proporcionan instrucciones explícitas ni complementos para los desarrolladores de aplicaciones que usan MvvmCross.

### <a name="company-portal-app"></a>Aplicación Portal de empresa
Los enlaces Xamarin del SDK de Intune dependen de la presencia de la aplicación [Portal de empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) para Android en el dispositivo para habilitar las directivas de protección de aplicaciones. El Portal de empresa recupera las directivas de protección de aplicaciones del servicio Intune. Cuando se inicializa la aplicación, carga la directiva y el código para aplicar dicha directiva desde el Portal de empresa. No es necesario que el usuario haya iniciado sesión.

> [!NOTE]
> Si la aplicación Portal de empresa no está en el dispositivo **Android**, una aplicación administrada por Intune tiene el mismo comportamiento que una aplicación normal que no admite las directivas de protección de aplicaciones de Intune.

Para la protección de aplicaciones sin inscripción de dispositivo, _**no**_ es necesario que el usuario inscriba el dispositivo con la aplicación Portal de empresa.

### <a name="sample-applications"></a>Aplicaciones de ejemplo
En [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) hay disponibles aplicaciones de ejemplo que resaltan la funcionalidad de MAM de las aplicaciones de Xamarin.Android y Xamarin.Forms.

## <a name="support"></a>Compatibilidad
Si la organización actualmente es cliente de Intune, consulte con su representante de soporte técnico de Microsoft para abrir una incidencia de soporte técnico y crear un caso [en la página de incidencias de GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). Recibirá ayuda en cuanto sea posible. 
