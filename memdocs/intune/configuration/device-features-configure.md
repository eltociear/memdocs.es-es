---
title: 'Creación de perfiles de dispositivos iOS/iPadOS o macOS con Microsoft Intune: Azure | Microsoft Docs'
description: Agregue o cree un perfil de dispositivo iOS, iPadOS o macOS. Configure las opciones de AirPrint, el diseño de la pantalla de inicio, las notificaciones de aplicaciones, el dispositivo compartido, el inicio de sesión único y los ajustes del filtro de contenido web en Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/06/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 349fdc7b0f13f0999b8c9993bcaba1d458ebac59
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83989196"
---
# <a name="add-ios-ipados-or-macos-device-feature-settings-in-intune"></a>Adición de la configuración de características de dispositivos iOS, iPadOS o macOS en Intune

Intune incluye muchas características y configuraciones que ayudan a los administradores a controlar dispositivos iOS, iPadOS y macOS. Por ejemplo, los administradores pueden:

- Permitir a los usuarios acceder a impresoras AirPrint en la red
- Agregar aplicaciones y carpetas a la pantalla principal, incluida la incorporación de nuevas páginas
- Elegir si se muestran las notificaciones de aplicación y cómo se muestran
- Configurar la pantalla de bloqueo para mostrar un mensaje o la etiqueta de recurso, especialmente para los dispositivos compartidos
- Proporcionar a los usuarios una experiencia de inicio de sesión único para compartir las credenciales entre aplicaciones
- Filtrar los sitios web que usan el lenguaje para adultos y permitir o bloquear sitios web específicos

Intune usa "perfiles de configuración" para crear y personalizar estas configuraciones para las necesidades de su organización. Después de agregar estas características en un perfil, puede insertarlo o implementarlo en los dispositivos iOS/iPadOS y macOS de la organización.

En este artículo se describen las distintas características que se pueden configurar y se muestra cómo crear un perfil de configuración de dispositivo. También puede ver todas las configuraciones disponibles para los dispositivos [iOS/iPadOS](ios-device-features-settings.md) y [macOS](macos-device-features-settings.md).

## <a name="airprint"></a>AirPrint

AirPrint es una característica de Apple que permite a los dispositivos imprimir archivos mediante una red inalámbrica. En Intune, puede agregar información de AirPrint a los dispositivos.

Para obtener una lista de los valores que puede configurar en Intune, vea [AirPrint en iOS/iPadOS](ios-device-features-settings.md#airprint) y [AirPrint en macOS](macos-device-features-settings.md#airprint).

Para más información sobre AirPrint, consulte [Acerca de AirPrint](https://support.apple.com/HT201311) en el sitio web de Apple.

Se aplica a:

- iOS 7.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes
- macOS 10.10 y versiones más recientes

## <a name="app-notifications"></a>Notificaciones de la aplicación

Elija cómo las aplicaciones de los dispositivos iOS e iPadOS reciben las notificaciones. Por ejemplo, envíe notificaciones de aplicación para que se muestren en el centro de notificaciones, se muestren en la pantalla de bloqueo o reproduzcan un sonido.

Para obtener una lista de las opciones que puede configurar en Intune, vea [Notificaciones de la aplicación en iOS/iPadOS](ios-device-features-settings.md#app-notifications).

Para más información sobre esta característica, consulte [Notificaciones](https://developer.apple.com/notifications/) en el sitio web de Apple.

Se aplica a:

- iOS 9.3 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

## <a name="associated-domains"></a>Dominios asociados

Los dominios asociados permiten crear una relación entre los dominios, como `contoso.com` y las aplicaciones. Esta característica permite:

- Compartir datos y credenciales de inicio de sesión entre las aplicaciones y los sitios web de la organización.
- Usar las características de aplicaciones basadas en su sitio web, como la extensión de aplicación de inicio de sesión único, vínculos universales y el relleno automático de contraseñas.

  Por ejemplo, cree un dominio asociado para permitir que el relleno automático de contraseñas recomiende credenciales, como una contraseña, para los sitios web asociados a la aplicación.

Para una lista de los valores que puede configurar en Intune, consulte [Dominios asociados en macOS](macos-device-features-settings.md#associated-domains).

Para más información sobre esta característica, consulte [Configuración de los dominios asociados de una aplicación](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) en el sitio web de Apple.

Se aplica a:

- macOS 10.15 y versiones más recientes

## <a name="home-screen-layout"></a>Diseño de la pantalla principal

Estas configuraciones definen el diseño de aplicaciones y carpetas en la base y las pantallas principales de los dispositivos iOS e iPadOS. Puede:

- Usar la configuración del **Dock** para agregar aplicaciones o carpetas a la pantalla. Por ejemplo, muestre Safari y la aplicación Mail en el Dock del dispositivo.
- Agregar las **páginas** que quiera que aparezcan en la pantalla principal y las aplicaciones que desee que se muestren en cada página. Por ejemplo, agregue una página **Contoso** y agregue la aplicación de configuración en esta página.

Para obtener una lista de los valores que puede configurar en Intune, vea [Diseño de la pantalla de inicio en iOS/iPadOS](ios-device-features-settings.md#home-screen-layout).

Se aplica a:

- iOS 9.3 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

## <a name="lock-screen-message"></a>Mensaje de la pantalla de bloqueo

Use esta configuración para mostrar un mensaje o un texto personalizado en la ventana de inicio de sesión y la pantalla de bloqueo. Por ejemplo, puede escribir el mensaje "En caso de pérdida, devolver a..." y mostrar la información sobre la etiqueta del recurso.

Para obtener una lista de los valores que puede configurar en Intune, vea [Configuración de mensajes de la pantalla de bloqueo en iOS/iPadOS](ios-device-features-settings.md#lock-screen-message).

Para más información sobre el mensaje de la pantalla de bloqueo, consulte [LockScreenMessage](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) en el sitio web de Apple.

Se aplica a:

- iOS 9.3 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

## <a name="login-items"></a>Elementos de inicio de sesión

Use esta característica para elegir las aplicaciones, las aplicaciones personalizadas, los archivos y las carpetas que se abren cuando los usuarios inician sesión en los dispositivos.

Para una lista de los valores que puede configurar en Intune, consulte [Elementos de inicio de sesión en macOS](macos-device-features-settings.md#login-items).

Se aplica a:

- macOS 10.13 y versiones más recientes

## <a name="login-window"></a>Ventana de inicio de sesión

Controle la apariencia de la pantalla de inicio de sesión y las funciones disponibles para los usuarios antes de que inicien sesión. Por ejemplo, agregue un banner con un mensaje personalizado, elija si se muestra el botón de suspensión, etc.

Para una lista de los valores que puede configurar en Intune, consulte [Ventana de inicio de sesión en macOS](macos-device-features-settings.md#login-window).

Se aplica a:

- macOS 10.7 y versiones más recientes

## <a name="single-sign-on"></a>Inicio de sesión único

La mayoría de las aplicaciones de línea de negocio (LOB) necesita cierto nivel de autenticación de usuario para ofrecer seguridad. En muchos casos, la autenticación requiere que los usuarios escriban las mismas credenciales varias veces. Para mejorar la experiencia del usuario, los desarrolladores pueden crear aplicaciones que usen el inicio de sesión único (SSO). El uso del inicio de sesión único reduce el número de veces que un usuario debe escribir las credenciales.

El perfil de inicio de sesión único se basa en Kerberos. Kerberos es un protocolo de autenticación de red que utiliza criptografía de clave secreta para autenticar aplicaciones cliente-servidor. La configuración de Intune define la información de la cuenta de Kerberos al acceder a los servidores o a las aplicaciones especificadas, y controla los desafíos de Kerberos relacionados con las páginas web y las aplicaciones nativas. Apple recomienda usar la [extensión de la aplicación de SSO de Kerberos](#single-sign-on-app-extension) (en este artículo) en lugar de la configuración de SSO.  

Para usar el inicio de sesión único, asegúrese de que tiene:

- Una aplicación programada para buscar el almacén de credenciales del usuario en el inicio de sesión único en el dispositivo.
- Intune configurado para el inicio de sesión único para dispositivos iOS/iPadOS.

Para obtener una lista de los valores que puede configurar en Intune, vea [Inicio de sesión único en iOS/iPadOS](ios-device-features-settings.md#single-sign-on).

Se aplica a:

- iOS 7.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

## <a name="single-sign-on-app-extension"></a>Extensión de aplicación de inicio de sesión único

Estas opciones configuran una extensión de aplicación que habilita el inicio de sesión único (SSO) para los dispositivos iOS, iPados y macOS. La mayoría de las aplicaciones de línea de negocio (LOB) y sitios web de la organización necesitan cierto nivel de autenticación de usuario segura. En muchos casos, la autenticación requiere que los usuarios escriban las mismas credenciales varias veces. El inicio de sesión único proporciona a los usuarios acceso a las aplicaciones y los sitios web después de escribir sus credenciales una vez. El inicio de sesión único también proporciona una mejor experiencia de autenticación para los usuarios y reduce el número de avisos repetidos de credenciales.

En Intune, use estas opciones para configurar una extensión de aplicación de inicio de sesión único creada por la organización, el proveedor de identidades, Microsoft o Apple. La extensión de la aplicación de inicio de sesión único controla la autenticación de los usuarios. Estas opciones configuran las extensiones de aplicación de inicio de sesión único de tipo credencial y redirección.

- El tipo de redirección está diseñado para protocolos de autenticación modernos, como OpenID Connect, OAuth y SAML2. Puede usar una extensión de redireccionamiento genérica en dispositivos macOS. En el caso de dispositivos iOS/iPadOS, puede elegir entre la extensión de SSO de Microsoft Azure AD ([complemento de Microsoft Enterprise Single Sign-On](https://docs.microsoft.com/azure/active-directory/develop/apple-sso-plugin)) y una extensión de redireccionamiento genérica.
- El tipo de credencial está diseñado para flujos de autenticación de desafío y respuesta. Puede elegir entre una extensión de credenciales específica de Kerberos proporcionada por Apple y una extensión de credenciales genérica.

Para obtener una lista de las opciones que puede configurar en Intune, vea [Extensión de la aplicación de inicio de sesión único de iOS/iPadOS](ios-device-features-settings.md#single-sign-on-app-extension) y [Extensión de la aplicación de inicio de sesión único de macOS](macos-device-features-settings.md#single-sign-on-app-extension).

Para más información sobre cómo desarrollar una extensión de aplicación de inicio de sesión único, consulte [Enterprise SSO extensible](https://developer.apple.com/videos/play/tech-talks/301) en el sitio web de Apple. Para leer la descripción de Apple de la característica, visite [Ajustes de carga "Exten. inicio sesión único"](https://support.apple.com/guide/mdm/single-sign-on-extensions-mdmfd9cdf845/web). 

> [!NOTE]
> La característica de **extensión de la aplicación de inicio de sesión único** es diferente de la característica **Inicio de sesión único**:
>
> - La configuración de la **extensión de aplicación de inicio de sesión único** se aplica a los dispositivos iPadOS 13.0 (y versiones más recientes), iOS 13.0 (y versiones más recientes) y macOS 10.15 (y versiones más recientes). La configuración del **inicio de sesión único** se aplica a los dispositivos iPad 13.0 (y versiones más recientes) e iOS 7.0 y versiones más recientes.
>
> - La configuración de la **extensión de aplicación de inicio de sesión único** define las extensiones que usan los proveedores de identidades o las organizaciones para ofrecer una experiencia de inicio de sesión empresarial sin problemas. La configuración **Inicio de sesión único** define la información de la cuenta de Kerberos para cuando los usuarios acceden a servidores o aplicaciones.
>
> - La **extensión de la aplicación de inicio de sesión único** usa el sistema operativo Apple para autenticarse. Por tanto, podría proporcionar una experiencia de usuario final mejor que la del **inicio de sesión único**.
>
> - Desde la perspectiva del desarrollo, con la **extensión de aplicación de inicio de sesión único** puede usar cualquier tipo de redirección o autenticación de inicio de sesión único de credenciales. Con el **inicio de sesión único**, solo puede usar la autenticación de inicio de sesión único de Kerberos.
>
> - La **extensión de aplicación de inicio de sesión único** de Kerberos fue desarrollada por Apple y está integrada en las plataformas iOS/iPadOS 13.0+ y macOS 10.15+. La extensión integrada de Kerberos se puede usar para registrar usuarios en aplicaciones nativas y sitios web que admitan la autenticación Kerberos. **Inicio de sesión único** no es una implementación de Apple de Kerberos.
>
> - La **extensión de aplicación de inicio de sesión único** integrada de Kerberos controla los desafíos de Kerberos para las aplicaciones y páginas web al igual que el **inicio de sesión único**. Pero la extensión integrada de Kerberos admite cambios de contraseña y se comporta mejor en redes empresariales. Al decidir entre la **extensión de aplicación de inicio de sesión único** de Kerberos y el **inicio de sesión único**, se recomienda usar la extensión ya que ofrece un rendimiento y una funcionalidad mejorados.

Se aplica a:

- iOS 13.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes
- macOS 10.15 y versiones más recientes

## <a name="wallpaper"></a>Fondo de pantalla

Agregue una imagen .png, .jpg o .jpeg personalizada a los dispositivos iOS/iPadOS supervisados. Por ejemplo, use Intune para agregar un logotipo de empresa a la pantalla de bloqueo de los dispositivos.

Para obtener una lista de los valores que puede configurar en Intune, vea [Fondo de pantalla en iOS/iPadOS](ios-device-features-settings.md#wallpaper).

Se aplica a:

- iOS
- IPadOS 13.0 y versiones más recientes

## <a name="web-content-filter"></a>Filtro de contenido web

Esta configuración puede usar el algoritmo de Autofiltro integrado de Apple para evaluar páginas web y bloquear contenido y lenguaje para adultos. También puede crear una lista de vínculos web permitidos y vínculos web restringidos. Por ejemplo, puede permitir que se abran solo los sitios web de `contoso`.

Para obtener una lista de los valores que puede configurar en Intune, vea [Filtro de contenido web en iOS/iPadOS](ios-device-features-settings.md#web-content-filter).

Se aplica a:

- iOS 7.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

## <a name="create-the-profile"></a>Creación del perfil

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba las propiedades siguientes:

    - **Plataforma**: seleccione la plataforma de los dispositivos. Las opciones son:  

        - **iOS/iPadOS**
        - **macOS**

    - **Perfil**: seleccione **Características del dispositivo**.

4. Seleccione **Crear**.
5. En **Básico**, escriba las propiedades siguientes:

    - **Nombre**: escriba un nombre descriptivo para la directiva. Asígnele un nombre a las directivas para que pueda identificarlas de manera sencilla más adelante. Por ejemplo, un nombre de directiva válido es **macOS: Configura la pantalla de inicio de sesión**.
    - **Descripción**: escriba una descripción para la directiva. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.

7. En **Opciones de configuración**, las opciones que puede configurar serán diferentes, según la plataforma que haya elegido. Elija la plataforma para la configuración detallada:

    - [iOS/iPadOS](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

8. Seleccione **Siguiente**.
9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

    Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione los usuarios o grupos que van a recibir el perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](device-profile-assign.md).

    Seleccione **Siguiente**.

11. En **Revisar y crear**, revise la configuración. Si selecciona **Crear**, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.

## <a name="next-steps"></a>Pasos siguientes

El perfil se crea, pero puede que todavía no haga nada. Después, [asigne el perfil](device-profile-assign.md) y [supervise el estado](device-profile-monitor.md).

Vea todas las configuraciones de características de dispositivo para dispositivos [iOS/iPadOS](ios-device-features-settings.md) y [macOS](macos-device-features-settings.md).
