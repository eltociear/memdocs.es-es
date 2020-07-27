---
title: ¿Qué es la inscripción de dispositivos de Microsoft Intune?
titleSuffix: Microsoft Intune
description: Obtenga información sobre la inscripción de dispositivos iOS/iPadOS, Android y Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e5d673c5688c4ab4f3219256412a098855af63ec
ms.sourcegitcommit: eccf83dc41f2764675d4fd6b6e9f02e6631792d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2020
ms.locfileid: "86461885"
---
# <a name="what-is-device-enrollment-in-intune"></a>¿Qué es la inscripción de dispositivos en Intune?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune permite administrar los dispositivos y las aplicaciones de sus recursos y su acceso a los datos de la empresa. Para usar esta administración de dispositivos móviles (MDM), primero es necesario inscribir los dispositivos en el servicio de Intune. Al inscribir un dispositivo, se emite un certificado MDM. Dicho certificado se usa para la comunicación con el servicio de Intune.

Como puede observar en las tablas siguientes, hay varias formas de inscribir los dispositivos de sus recursos. Cada método depende de la propiedad del dispositivo (personal o corporativo), el tipo de dispositivo (iOS, Windows o Android) y los requisitos de administración (restablecimiento, afinidad o bloqueo).

De manera predeterminada, los dispositivos de todas las plataformas pueden inscribirse en Intune. Sin embargo, puede [restringir dispositivos por plataforma](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="iosipados-enrollment-methods"></a>Métodos de inscripción de iOS/iPadOS

| **Método** | **Se requiere reinicio** | [**Afinidad de usuario**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Bloqueado** | **Detalles** |
|:---:|:---:|:---:|:---:|:---:|
| | Durante la inscripción, los dispositivos se borran. | Se asocia cada dispositivo a un usuario.| En caso afirmativo, los usuarios no pueden anular la inscripción de los dispositivos. | |
|**[BYOD](#bring-your-own-device)** | No| Sí | No | [Más información](apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| No |No |No | [Más información](device-enrollment-manager-enroll.md)|
|**[ADE](#apple-automated-device-enrollment)**| Sí | Opcional | Opcional|[Más información](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Sí | Opcional | No| [Más información](apple-configurator-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| No | No | No|[Más información](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>Métodos de inscripción de macOS

| **Método** |  **Se requiere reinicio** |  **Afinidad de usuario** | **Bloqueado** | **Detalles**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | No| Sí | No | [Más información](macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| No |No |No  | [Más información](device-enrollment-manager-enroll.md)|
|**[ADE](#apple-automated-device-enrollment)**| Sí | Opcional | Opcional|[Más información](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Métodos de inscripción de Windows

| **Método** | **Se requiere reinicio** | **Afinidad de usuario** | **Bloqueado** | **Detalles**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | No | Sí | No | [Más información](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| No |No |No |[Más información](device-enrollment-manager-enroll.md)|
|**Inscripción automática** | No |Sí |No | [Más información](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Autopilot** |Sí |Sí |No | [Más información](enrollment-autopilot.md)
|**Inscripción masiva** |No |No |No | [Más información](windows-bulk-enroll.md) |
|**Administración conjunta** |No |Sí |No | [Más información](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)
|**GPO** |No |Sí |No | [Más información](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Métodos de inscripción de Android

| **Personales** | **Métodos de inscripción** | **Se requiere reinicio** | **Afinidad de usuario** | **Bloqueado** | **Detalles**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrador de dispositivos Android**|**Iniciado por el usuario a través del Portal de empresa** | No | Sí | No | [Más información](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)|
|**Perfil de trabajo de Android Enterprise**|**Iniciado por el usuario a través del Portal de empresa**| No | Sí | No | [Más información](android-work-profile-enroll.md)|


&nbsp;

| **Corporativos** | **Métodos de inscripción** | **Se requiere reinicio** | **Afinidad de usuario** | **Bloqueado** | **Detalles**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrador de dispositivos Android**|**Iniciado por [usuarios degradados](#device-enrollment-manager) a través del Portal de empresa**| No | No | No |[Más información](device-enrollment-manager-enroll.md)|
|**Administrador de dispositivos Android**|**(IMEI o SN declarado previamente) Iniciado por el usuario a través del Portal de empresa**| No | Sí | No | [Más información](corporate-identifiers-add.md)|
|**Administradores de dispositivos Android con Zebra Mobility Extensions**|**Iniciado por el usuario o [usuarios degradados](#device-enrollment-manager) a través del Portal de empresa**| No | Sí, si es iniciado por el usuario, No si es iniciado por [usuarios degradados](#device-enrollment-manager) | No | [Más información](../configuration/android-zebra-mx-overview.md)|
|**Android Enterprise dedicado**|**NFC, Token, código QR, Zero Touch**| Sí | No | Configurable mediante directivas | [Más información](android-kiosk-enroll.md)|
|**Android Enterprise totalmente administrado**|**NFC, Token, código QR, Zero Touch**| Sí | Sí | Configurable mediante directivas | [Más información](android-dedicated-devices-fully-managed-enroll.md)|
|**Corporativo de Android Enterprise con Perfil de trabajo** | **NFC, Token, código QR, Zero Touch** | Sí | Sí | Configurable mediante directivas | [Más información](android-corporate-owned-work-profile-enroll.md)|

## <a name="bring-your-own-device"></a>Bring Your Own Device
Entre los dispositivos Bring Your Own Device (BYOD) se incluyen teléfonos, tabletas y equipos personales. Los usuarios instalan y ejecutan la aplicación Portal de empresa para inscribir sus dispositivos BYOD. Este programa permite a los usuarios acceder a los recursos de la compañía, como el correo electrónico.

## <a name="corporate-owned-device"></a>Dispositivo de propiedad corporativa
Entre los [dispositivos de propiedad corporativa (COD)](corporate-identifiers-add.md) se incluyen teléfonos, tabletas y equipos propiedad de la empresa facilitados a los recursos. La inscripción de COD permite escenarios como la inscripción automática, el uso compartido de dispositivos o los requisitos de inscripción autorizada previamente. Una forma habitual de inscribir dispositivos COD es utilizar el administrador de inscripción de dispositivos (DEM) por parte de un administrador. Los dispositivos iOS/iPadOS se pueden inscribir directamente a través de las herramientas de ADE proporcionadas por Apple. Los dispositivos con un número IMEI también se pueden identificar y etiquetar como de propiedad corporativa.

### <a name="device-enrollment-manager"></a>Administrador de inscripción de dispositivos
El administrador de inscripción de dispositivos (DEM) es una cuenta especial de usuario que se usa para inscribir y administrar varios dispositivos de la empresa. Los administradores pueden instalar el portal de empresa e inscribir muchos dispositivos sin usuario. Estos tipos de dispositivos son buenos para aplicaciones de punto de venta o de utilidad, por ejemplo, pero inadecuados para usuarios que necesitan acceso al correo electrónico o a los recursos de empresa. Obtenga más información sobre [DEM](device-enrollment-manager-enroll.md).

### <a name="apple-automated-device-enrollment"></a>Inscripción de dispositivo automatizada de Apple
La administración de la Inscripción de dispositivo automatizada (ADE) de Apple permite crear e implementar directivas "de forma inalámbrica" en dispositivos iOS/iPadOS y macOS que se han adquirido y administrado con ADE. El dispositivo se inscribe cuando los usuarios lo activan por primera vez y ejecutan el asistente de configuración. Este método admite el modo supervisado de iOS/iPadOS, que permite configurar un dispositivo con una funcionalidad específica.

Más información sobre la inscripción de ADE para iOS/iPadOS:

- [Inscripción de dispositivos iOS/iPadOS en Intune](ios-enroll.md)
- [Inscripción de dispositivos iOS/iPadOS con el Programa de inscripción de dispositivos](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
Los administradores de TI usan Apple Configurator a través de USB para preparar manualmente cada dispositivo corporativo para la inscripción mediante el Asistente de configuración. El administrador de TI crea un perfil de inscripción y lo exporta a Apple Configurator. Cuando los usuarios reciben sus dispositivos, se les solicita que ejecuten el Asistente de configuración para inscribirlos. Este método admite el modo **supervisado de iOS**, que a su vez permite las siguientes características:
- Inscripción bloqueada
- Modo de pantalla completa y otras configuraciones y restricciones avanzadas

Más información sobre la inscripción de iOS/iPadOS con Apple Configurator con el Asistente de configuración:

- [Inscripción de dispositivos iOS/iPadOS](ios-enroll.md)
- [Inscripción de dispositivos iOS/iPadOS con Configurator y el Asistente de configuración](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Para realizar una inscripción directa, el administrador debe inscribir cada dispositivo manualmente creando una directiva de inscripción y exportándola a Apple Configurator. Los dispositivos corporativos conectados por USB se inscriben directamente y no requieren un borrado. Los dispositivos se administran como dispositivos sin usuario. No se bloquean ni se supervisan y no son compatibles con el acceso condicional, la detección de jailbreak ni la administración de aplicaciones móviles.

Para más información sobre la inscripción de dispositivos iOS/iPadOS, vea:

- [Inscripción de dispositivos iOS/iPadOS](ios-enroll.md)
- [Inscripción de dispositivos iOS/iPadOS con Configurator y la inscripción directa](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpieza de dispositivos móviles tras la expiración del certificado MDM

El certificado MDM se renueva automáticamente cuando los dispositivos móviles se comunican con el servicio de Intune. Si se borran los dispositivos móviles o estos no pueden comunicarse con el servicio de Intune durante un tiempo, el certificado MDM no se renueva. El dispositivo se quita del portal de Azure 180 días después de que expire el certificado MDM.
