---
title: ¿Qué es la administración de aplicaciones de Microsoft Intune?
titleSuffix: ''
description: Obtenga información sobre funcionalidades de administración de aplicaciones cliente mediante la plataforma de Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/31/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 99dc504f8fc3148463288820dc810bab892e3081
ms.sourcegitcommit: 4f10625e8d12aec294067a1d9138cbce19707560
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87912393"
---
# <a name="what-is-microsoft-intune-app-management"></a>¿Qué es la administración de aplicaciones de Microsoft Intune?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como administrador de TI, puede usar Microsoft Intune para administrar las aplicaciones cliente que usan los trabajadores de su empresa. Esta funcionalidad se suma a la administración de dispositivos y la protección de datos. Una de las prioridades de un administrador es garantizar que los usuarios finales tengan acceso a las aplicaciones que necesitan para hacer su trabajo. Este objetivo puede ser difícil por las siguientes causas:
- La amplia variedad de plataformas de dispositivo y tipos de aplicaciones.
- La necesidad de administrar aplicaciones de los dispositivos de la empresa y de los dispositivos personales de los usuarios.
- Debe asegurarse de que la red y los datos permanecen seguros.

Aparte de todo esto, puede que quiera asignar y administrar aplicaciones en dispositivos que no están inscritos en Intune.

## <a name="mobile-application-management-mam-basics"></a>Aspectos básicos de la administración de aplicaciones móviles (MAM)

La [administración de aplicaciones móviles de Intune](app-lifecycle.md) hace referencia al conjunto de funciones de administración de Intune que le permite publicar, insertar, configurar, proteger, supervisar y actualizar aplicaciones móviles para los usuarios.

MAM permite administrar y proteger los datos de la organización dentro de una aplicación. Con **MAM sin inscripción** (MAM-WE), una aplicación profesional o educativa que contiene información confidencial puede administrarse en casi cualquier [dispositivo](app-management.md#app-management-capabilities-by-platform), incluidos los dispositivos personales en escenarios de **Bring Your Own Device** (BYOD). Muchas aplicaciones de productividad, como las aplicaciones de Microsoft Office, pueden administrarse mediante Intune MAM. Consulte la lista oficial de [aplicaciones protegidas de Microsoft Intune](apps-supported-intune-apps.md), disponible para uso público.

Intune MAM admite dos configuraciones:
- **Intune MDM + MAM**: Los administradores de TI solo pueden administrar aplicaciones mediante directivas de protección de aplicaciones y MAM en los dispositivos que están inscritos con la administración de dispositivos móviles (MDM) de Intune. Para administrar aplicaciones mediante MDM + MAM, los clientes deben usar la consola de Intune en Azure Portal (en https://portal.azure.com ).
- **MAM sin inscripción de dispositivos**: MAM sin inscripción de dispositivos o MAM-WE permite a los administradores de TI administrar aplicaciones mediante directivas de protección de aplicaciones y MAM en dispositivos no inscritos con Intune MDM. Esto significa que las aplicaciones pueden administrarse mediante Intune en dispositivos inscritos con proveedores de EMM de terceros. Para administrar aplicaciones mediante MAM-WE, los clientes deben usar la consola de Intune en Azure Portal (en https://portal.azure.com ). Además, Intune puede administrar las aplicaciones en dispositivos inscritos con otros proveedores de Enterprise Mobility Management (EMM) o no inscritos con MDM. Para más información sobre BYOD y EMS de Microsoft, consulte [Decisiones de tecnología para habilitar BYOD con Microsoft Enterprise Mobility + Security (EMS)](../fundamentals/byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Funcionalidades de administración de aplicaciones por plataforma

Intune ofrece diversas funcionalidades para ayudarle a conseguir las aplicaciones que necesita en los dispositivos en los que desea que se ejecuten. En la tabla siguiente se ofrece un resumen de las capacidades de administración de aplicaciones.

| Funcionalidad de administración de aplicaciones | Android o Android Enterprise | iOS/iPadOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------- | -------------------------- | ---------- | ----- | ---------- | ----------------- |
| Agregar y asignar aplicaciones a dispositivos y usuarios | Sí | Sí | Sí | Sí | Sí |
| Asignar aplicaciones a dispositivos no inscritos en Intune | Sí | Sí | No | No | No |
| Usar directivas de configuración de aplicaciones para controlar el comportamiento de inicio de las aplicaciones | Sí | Sí | No | No | No |
| Usar directivas de aprovisionamiento de aplicaciones móviles para renovar aplicaciones caducadas | No | Sí | No | No | No |
| Proteger los datos de empresa de las aplicaciones con directivas de protección de aplicaciones | Sí | Sí | No | No <sup>1</sup> | No |
| Quitar solo los datos corporativos de una aplicación instalada (eliminación selectiva de aplicaciones) | Sí | Sí | No | Sí | Sí |
| Supervisar las asignaciones de aplicaciones | Sí | Sí | Sí | Sí | Sí |
| Asignar y realizar el seguimiento de aplicaciones compradas por volumen desde una tienda de aplicaciones | No | No | No | Sí | No |
| Instalación obligatoria de aplicaciones en dispositivos (requerido) <sup>2</sup> | Sí | Sí | Sí | Sí | Sí |
| Instalación opcional en dispositivos desde el Portal de empresa (instalación disponible) | Sí <sup>3</sup> | Sí | Sí | Sí | Sí |
| Instalación de un acceso directo a una aplicación en Web (vínculo web) | Sí <sup>4</sup> | Sí | Sí | Sí | Sí |
| Aplicaciones internas (línea de negocio) | Sí | Sí | Sí | Sí | No |
| Aplicaciones de una tienda | Sí | Sí | No | Sí | Sí |
| Actualizar aplicaciones | Sí | Sí | No | Sí | Sí |

<sup>1</sup> Considere el uso de [Windows Information Protection](../protect/windows-information-protection-configure.md) para proteger aplicaciones en dispositivos que ejecutan Windows 10.<br>
<sup>2</sup> Se aplica solo a dispositivos administrados por Intune.<br>
<sup>3</sup> Intune admite aplicaciones disponibles del almacén de Google Play administrado en dispositivos empresariales Android.<br>
<sup>4</sup> Intune no proporciona la instalación de un acceso directo a una aplicación como vínculo web en dispositivos empresariales estándar de Android. Sin embargo, se proporciona compatibilidad con vínculos web para [dispositivos empresariales de Android dedicados con varias aplicaciones](../configuration/device-restrictions-android-for-work.md#device-experience). 


## <a name="get-started"></a>Introducción

Puede encontrar la mayoría de la información relacionada con las aplicaciones en la carga de trabajo **Aplicaciones**, a la que puede acceder haciendo lo siguiente:

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Seleccione **Aplicaciones**.

    ![Panel de carga de trabajo Aplicaciones](./media/app-management/apps-workload.png)

La carga de trabajo de las aplicaciones proporciona vínculos para acceder a la información y las funcionalidades comunes de esta. 

La parte superior del menú de navegación de la carga de trabajo de la aplicación proporciona detalles al respecto que se usan habitualmente:
- **Información general**: Seleccione esta opción para ver el nombre del inquilino, la entidad de MDM, la ubicación del inquilino, el estado de la cuenta, el estado de la instalación de la aplicación y el estado de la directiva de protección de aplicaciones.
- **Todas las aplicaciones**: Seleccione esta opción para mostrar una lista de todas las aplicaciones disponibles. Puede agregar más aplicaciones desde esta página. Además, puede ver el estado de cada aplicación, así como si están asignadas. Para obtener más información, consulte [Incorporación de aplicaciones](apps-add.md) y [Asignación de aplicaciones](apps-deploy.md).
- **Supervisión de aplicaciones**
    - **Licencias de aplicaciones**: vea, asigne y supervise las aplicaciones compradas por volumen de las tiendas de aplicaciones. Para obtener más información, consulte [Aplicaciones del Programa de Compras por Volumen (PCV) de iOS](vpp-apps-ios.md) y [Aplicaciones adquiridas por volumen en Microsoft Store para Empresas](windows-store-for-business.md).
    - **Aplicaciones detectadas**: vea las aplicaciones que ha asignado Intune o que están instaladas en un dispositivo. Para más información, consulte [Aplicaciones descubiertas de Intune](app-discovered-apps.md).
    - **Estado de instalación de la aplicación**: vea el estado de una asignación de aplicación que ha creado. Para obtener más información, consulte [Monitor app information and assignments with Microsoft Intune](apps-monitor.md#device-and-user-status-graphs) (Supervisión de información de aplicación y asignaciones con Microsoft Intune).
    - **Estado de protección de la aplicación**: vea el estado de una directiva de protección de aplicaciones de un usuario que haya seleccionado.
- **Por plataforma**: Seleccione estas plataformas para ver las aplicaciones disponibles por plataforma.
    - Windows
    - iOS
    - macOS
    - Android
- **Directiva**:
    - **Directivas de protección de aplicaciones**: seleccione esta opción para asociar valores de configuración con una aplicación y ayudar a proteger los datos de empresa que esta usa. Por ejemplo, podría restringir las funcionalidades de una aplicación para comunicarse con otras aplicaciones o podría pedir que el usuario escribiera un PIN para acceder a una aplicación de la empresa. Para obtener más información, consulte las [Directivas de protección de aplicaciones](app-protection-policies.md).
    - **Directivas de configuración de aplicaciones**: seleccione esta opción para proporcionar valores de configuración que podrían ser necesarios cuando el usuario ejecuta una aplicación. Para obtener más información, consulte [Directivas de configuración de aplicaciones](app-configuration-policies-use-ios.md), [Directivas de configuración de aplicaciones para iOS](app-configuration-policies-use-ios.md) y [Directivas de configuración de aplicaciones para Android](app-configuration-policies-overview.md).
    - **Perfiles de aprovisionamiento de aplicaciones de iOS**: las aplicaciones iOS incluyen un perfil y un código de aprovisionamiento que está firmado por un certificado. Cuando el certificado expira, ya no se puede ejecutar la aplicación. Intune proporciona las herramientas para asignar proactivamente una nueva directiva de perfil de aprovisionamiento a dispositivos que tengan aplicaciones cuya expiración esté próxima. Para obtener más información, consulte [Perfiles de aprovisionamiento de aplicaciones de iOS](app-provisioning-profile-ios.md).
    - **Directivas complementarias del modo S**: Seleccione esta opción para autorizar a más aplicaciones a ejecutarse en los dispositivos administrados en modo S. Para obtener más información, consulte [Directivas complementarias del modo S](apps-win32-s-mode.md).
    - **Conjuntos de directivas**: Seleccione esta opción para crear una colección asignable de aplicaciones, directivas y otros objetos de administración que se han creado. Para obtener más información, consulte [Conjuntos de directivas](../fundamentals/policy-sets.md).
- **Otros**:   
    - **Borrado selectivo de aplicaciones**: seleccione esta opción para quitar solo los datos corporativos de un dispositivo de un usuario seleccionado. Para obtener más información, consulte [Borrado selectivo de aplicaciones](apps-selective-wipe.md).
    - **Categorías de aplicaciones**: agregue, ancle y elimine los nombres de categoría de las aplicaciones.
    - **Libros electrónicos**: Algunas tiendas de aplicaciones permiten comprar varias licencias para una aplicación o libros que desea usar en la empresa. Para obtener más información, vea [Administración de aplicaciones y libros comprados por volumen con Microsoft Intune](vpp-apps.md).
- **Ayuda y soporte técnico**: solucione problemas, solicite soporte técnico o vea el estado de Intune. Para obtener más información, consulte [Solución de problemas](../fundamentals/help-desk-operators.md).

### <a name="try-the-interactive-guide"></a>Pruebe la guía interactiva
La guía interactiva [Administración y protección de aplicaciones para dispositivos móviles y de escritorio con Microsoft Endpoint Manager](https://mslearn.cloudguides.com/en-us/guides/Manage%20and%20protect%20mobile%20and%20desktop%20applications%20with%20Microsoft%20Endpoint%20Manager) le guía a través del Centro de administración de Microsoft Endpoint Manager para mostrarle cómo administrar dispositivos inscritos en Intune, aplicar el cumplimiento mediante directivas y proteger los datos de la organización.</br></br>

> [!VIDEO https://mslearn.cloudguides.com/en-us/guides/Manage%20and%20protect%20mobile%20and%20desktop%20applications%20with%20Microsoft%20Endpoint%20Manager]

## <a name="additional-information"></a>Información adicional
Los siguientes elementos de la consola de proporcionan funcionalidad relacionada con las aplicaciones:
- **Microsoft Store para Empresas**: configure la integración con Microsoft Store para Empresas. Luego, puede sincronizar las aplicaciones adquiridas en Intune, asignarlas y realizar el seguimiento de su uso de licencias. Para obtener más información, consulte [Aplicaciones adquiridas por volumen en Microsoft Store para Empresas](windows-store-for-business.md).
- **Certificado de Windows Enterprise**: aplique o vea el estado de un certificado de firma de código que se utiliza para distribuir aplicaciones de línea de negocio en los dispositivos de Windows administrados.
- **Certificado de Symantec para Windows**: aplique o vea el estado de un certificado de firma de código de Symantec que se necesita para distribuir archivos appx de XAP y WP8.x a dispositivos Windows 10 Mobile.
- **Claves de instalación de prueba de Windows**: agregue una clave de instalación de prueba de Windows que puede usarse para instalar una aplicación directamente en dispositivos en lugar de publicar y descargar la aplicación desde la tienda Windows. Para obtener más información, consulte [Carga de una aplicación de Windows](app-sideload-windows.md).
- **Tokens de VPP de Apple**: aplique y vea sus licencias del Programa de Compras por Volumen (PCV) de iOS/iPadOS. Para obtener más información, consulte [Aplicaciones de iOS/iPadOS compradas a través de un programa de compras por volumen](vpp-apps-ios.md).
- **Google Play administrado**: Google Play administrado es la tienda de aplicaciones empresariales de Google y el único origen de aplicaciones para Android Enterprise. Para obtener más información, consulte [Incorporación de aplicaciones de Google Play administrado a dispositivos Android Enterprise con Intune](apps-add-android-for-work.md).
- **Personalización**: personalice el Portal de empresa para adaptarlo a su empresa. Para obtener más información, consulte [Configuración de Portal de empresa](company-portal-app.md).

Para más información sobre las aplicaciones, consulte[Incorporación de aplicaciones a Microsoft Intune](../apps/apps-add.md).

## <a name="next-steps"></a>Pasos siguientes

- [Agregar una aplicación a Microsoft Intune](apps-add.md)
