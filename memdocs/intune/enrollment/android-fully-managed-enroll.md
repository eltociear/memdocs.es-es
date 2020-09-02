---
title: Configuración de la inscripción en Intune de dispositivos Android Enterprise totalmente administrados
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo inscribir dispositivos Android Enterprise totalmente administrados en Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure;seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b0324755ef4706e1642357ae7a4e7dc90e719a7e
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88915201"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices"></a>Configuración de la inscripción en Intune de dispositivos Android Enterprise totalmente administrados 

Los dispositivos Android Enterprise totalmente administrados son dispositivos de propiedad corporativa que están asociados a un solo usuario y se usan exclusivamente para el trabajo y no para uso personal. Los administradores pueden administrar todo el dispositivo y aplicar controles de directiva que no están disponibles para perfiles de trabajo, como:
- Permitir la instalación de aplicaciones solo desde Google Play administrado
- Bloquear la desinstalación de aplicaciones administradas
- Impedir que los usuarios restablezcan los dispositivos a los valores de fábrica, etc.

Con Intune es más fácil instalar aplicaciones y aplicar una configuración a los dispositivos Android de la empresa, incluidos los dispositivos Android Enterprise totalmente administrados. Para más detalles sobre Android Enterprise, vea [Requisitos para usar dispositivos Android en una empresa](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Requisitos técnicos

Debe tener un inquilino independiente de Intune para administrar dispositivos Android Enterprise totalmente administrados. La administración de dispositivos totalmente administrados no está disponible en la consola de administración heredada de Silverlight.

Los dispositivos deben cumplir estos requisitos para administrarse como dispositivo Android Enterprise totalmente administrados:

- SO Android versión 6.0 y posteriores.
- Los dispositivos deben ejecutar una versión de Android que tenga conectividad con Servicios de Google para móviles (GMS). Los dispositivos deben tener GMS disponible y deben ser capaces de conectarse a GMS.

No hay ninguna restricción en cuanto al fabricante u OEM del dispositivo si se cumplen los requisitos anteriores.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Configurar la inscripción de dispositivos Android Enterprise totalmente administrados

Para configurar la administración de dispositivos Android Enterprise totalmente administrados, siga estos pasos:

1. Para prepararse para administrar dispositivos móviles, debe [establecer la entidad de administración de dispositivos móviles (MDM) en **Microsoft Intune**](../fundamentals/mdm-authority-set.md). Este elemento solo se establece una vez, la primera vez que configura Intune para la administración de dispositivos móviles.
2. [Conecte su cuenta de inquilino de Intune a su cuenta de Android Enterprise](connect-intune-android-enterprise.md).
3. [Permitir dispositivos de usuario de propiedad corporativa](#enable-corporate-owned-user-devices)
4. [Inscribir dispositivos totalmente administrados](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Permitir dispositivos de usuario de propiedad corporativa

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y elija **Dispositivos** > **Android** > **Inscripción de Android**  > **Dispositivos de usuario totalmente administrados de propiedad corporativa** .
2. En **Allow users to enroll corporate-owned user devices** (Permitir a los usuarios inscribir dispositivos de usuario de propiedad corporativa), elija **Sí**.

> [!NOTE]
> Si ha definido una directiva de acceso condicional de Azure AD que use el control de concesión *requerir que un dispositivo se marque como compatible* o una directiva de bloqueo y se aplique a **Todas las aplicaciones en la nube**, **Android** y **Exploradores**, debe excluir la aplicación en la nube de **Microsoft Intune** de esta directiva. Esto se debe a que el proceso de instalación de Android usa una pestaña de Chrome para autenticar a los usuarios durante la inscripción. Para más información, vea [Documentación sobre el acceso condicional de Azure AD](/azure/active-directory/conditional-access/).

Cuando esta opción se establece en **Sí**, proporciona un token de inscripción (una cadena aleatoria) y un código QR para el inquilino de Intune. Este token de inscripción único es válido para todos los usuarios y no expira. Según el sistema operativo Android y la versión del dispositivo, puede usar el token o un código QR para inscribir el dispositivo.

## <a name="enroll-the-fully-managed-devices"></a>Inscribir dispositivos totalmente administrados
Ahora puede [inscribir sus dispositivos totalmente administrados](android-dedicated-devices-fully-managed-enroll.md) (pero no al usar cuentas de DEM).

## <a name="next-steps"></a>Pasos siguientes
- [Agregar directivas de configuración de dispositivos Android Enterprise totalmente administrados](../configuration/device-restrictions-android-for-work.md#fully-managed-dedicated-and-corporate-owned-work-profile)
- [Configurar directivas de configuración de aplicaciones para dispositivos Android Enterprise totalmente administrados](../apps/app-configuration-policies-use-android.md)