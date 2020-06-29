---
title: Inscripción de dispositivos iOS/iPadOS en Intune
titleSuffix: Microsoft Intune
description: Configure la inscripción de dispositivos iOS/iPadOS en Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/23/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure;seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba44cca323dd2a3fbf756b86743dea403ce0b156
ms.sourcegitcommit: 387706b2304451e548d6d9c68f18e4764a466a2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85093065"
---
# <a name="enroll-iosipados-devices-in-intune"></a>Inscripción de dispositivos iOS/iPadOS en Intune

Intune permite la administración de dispositivos móviles (MDM) de iPads y iPhones para conceder acceso seguro a los usuarios al correo electrónico, os datos y las aplicaciones de la empresa.

Como administrador de Intune, puede configurar la inscripción para dispositivos iOS/iPadOS y iPadOS para tener acceso a los recursos de la empresa. Puede dejar que los usuarios inscriban sus propios dispositivos, lo que se conoce como inscripción "Bring Your Own Device" (BYOD). También puede configurar la inscripción de dispositivos de la empresa.

## <a name="prerequisites-for-iosipados-enrollment"></a>Requisitos previos para la inscripción de iOS/iPadOS

Antes de que pueda habilitar dispositivos iOS/iPadOS, complete estos pasos:

- [Asegúrese de que los dispositivos sean compatibles](../fundamentals/supported-devices-browsers.md).
- [Configurar Intune](../fundamentals/setup-steps.md): estos pasos configurar la infraestructura de Intune. En concreto, la inscripción de dispositivos requiere que [establezca su autoridad de MDM](../fundamentals/mdm-authority-set.md).
- [Obtención de un certificado push MDM de Apple](apple-mdm-push-certificate-get.md): Apple requiere un certificado para habilitar la administración de dispositivos iOS/iPadOS y macOS.

## <a name="user-owned-iosipados-and-ipados-devices-byod"></a>Dispositivos iOS/iPadOS y iPadOS de propiedad del usuario (BYOD)

Puede permitir que los usuarios inscriban sus dispositivos personales para la administración de Intune. Esto se conoce como "Bring Your Own Device" o BYOD. Existen tres opciones para la inscripción de usuarios:
- Las directivas de protección de aplicaciones proporcionan la experiencia BYOD más ligera, ofreciendo administración solo en el nivel de la aplicación. Sin embargo, si desea proteger también el dispositivo con un PIN complejo de seis dígitos, puede usar estas directivas junto con la inscripción de usuarios.
- La inscripción de dispositivos es lo que se puede considerar una inscripción típica de BYOD. Proporciona a los administradores una amplia gama de opciones de administración.
- La inscripción de usuarios es un proceso de inscripción más sencillo que proporciona a los administradores un subconjunto de opciones de administración de dispositivos. Esta característica actualmente está en versión preliminar. 

Tras completar los requisitos previos y asignar licencias a los usuarios, estos podrán descargar la aplicación Portal de empresa de Intune del App Store y seguir las instrucciones de inscripción. Puede personalizar la declaración de privacidad del Portal de empresa en dispositivos iOS o iPadOS como se explica en [Personalización de las aplicaciones del Portal de empresa de Intune, el sitio web del Portal de empresa y las aplicaciones de Intune](../apps/company-portal-app.md#configuration).

## <a name="company-owned-iosipados-devices"></a>Dispositivos iOS/iPadOS propiedad de la empresa

En las organizaciones que adquieran dispositivos para sus usuarios, Intune admite los siguientes métodos de inscripción de dispositivos de empresa para iOS/iPadOS:

- Inscripción de dispositivo automatizada (ADE) de Apple
- Apple School Manager
- Inscripción de Apple Configurator mediante el Asistente de configuración
- Inscripción directa de Apple Configurator

También puede inscribir dispositivos iOS/iPadOS de empresa con una cuenta de [administrador de inscripción de dispositivos](device-enrollment-manager-enroll.md).

## <a name="automated-device-enrollment"></a>Inscripción de dispositivo automatizada

Las organizaciones pueden adquirir dispositivos iOS/iPadOS con la Inscripción de dispositivo automatizada (ADE) de Apple. ADE permite implementar un perfil de inscripción "de forma inalámbrica" para incluir los dispositivos en la administración. Para obtener más información, vea [Inscripción automática de dispositivos iOS/iPadOS con Inscripción de dispositivos automatizada de Apple](device-enrollment-program-enroll-ios.md).

## <a name="user-enrollment"></a>Inscripción de usuarios
La inscripción de usuario proporciona a los administradores un subconjunto de opciones de administración en comparación con otros métodos de inscripción. Para más información, vea [Acciones admitidas en la inscripción de usuarios, contraseñas y otras opciones](ios-user-enrollment-supported-actions.md) y [Configuración de la inscripción de usuarios de iOS/iPadOS y iPadOS](ios-user-enrollment.md).

## <a name="apple-school-manager"></a>Apple School Manager

Apple School Manager es un programa de compra e inscripción de dispositivos para centros escolares. Al igual que ADE, puede implementar un perfil para inscribir dispositivos en la administración. Más información sobre [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator

Puede inscribir dispositivos iOS/iPadOS con la ejecución de Apple Configurator en un equipo Mac. Para preparar los dispositivos, se conectan mediante USB y se instala un perfil de inscripción. Puede inscribir dispositivos con Apple Configuration de dos maneras:

- Inscripción con el Asistente de configuración: borra el dispositivo, lo prepara para ejecutar el Asistente de configuración e instala las directivas de la empresa para el nuevo usuario del dispositivo.
- Inscripción directa: no borra el dispositivo y lo inscribe con una directiva predefinida. Este método está destinado a los dispositivos sin afinidad de usuario.

Más información sobre [Inscripción de Apple Configurator](apple-configurator-enroll-ios.md).

## <a name="use-the-company-portal-on-ade-enrolled-or-apple-configurator-enrolled-devices"></a>Uso del Portal de empresa en dispositivos inscritos mediante ADE o Apple Configurator

Los dispositivos configurados con afinidad de usuario pueden instalar y ejecutar la aplicación del Portal de empresa para descargar aplicaciones y administrar dispositivos. Después de recibir sus dispositivos, los usuarios deben realizar una serie de pasos adicionales para completar el Asistente de configuración e instalar la aplicación del portal de empresa.

La afinidad de usuario es necesaria para admitir lo siguiente:

- Aplicaciones de administración de aplicaciones móviles (MAM)
- Acceso condicional al correo electrónico y los datos de la empresa.
- Aplicación de portal de empresa

### <a name="how-users-enroll-corporate-owned-iosipados-devices-with-user-affinity"></a>Inscripción de dispositivos iOS/iPadOS de empresa con afinidad de usuario

1. Cuando los usuarios encienden su dispositivo, se les pide que completen el Asistente de configuración.
2. Una vez finalizada la instalación, se pide a los usuarios un identificador de Apple. Deben proporcionar un identificador de Apple para que el dispositivo instale el portal de empresa.
3. El dispositivo iOS/iPadOS instala automáticamente la aplicación Portal de empresa desde App Store.
4. Los usuarios deben abrir la aplicación del portal de empresa e iniciar sesión con las credenciales (como el nombre único personal o UPN) que estén asociadas con su suscripción en Intune.
5. Después de iniciar sesión, la inscripción se completa. Ahora, los usuarios pueden usar este dispositivo con el conjunto completo de funcionalidades.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Acerca de los dispositivos administrados de propiedad corporativa sin afinidad de usuario

Los dispositivos configurados sin afinidad de usuario no admiten el portal de empresa y no se debe instalar en ellos la aplicación. El portal de empresa está diseñado para usuarios que tienen credenciales corporativas y que necesitan acceso a recursos corporativos personalizados (como el correo electrónico). Los dispositivos inscritos sin afinidad de usuario no están diseñados para tener un inicio de sesión de usuario dedicado. Los quioscos multimedia, los puntos de venta (PDV) y los dispositivos de utilidad compartida son casos de uso típicos de dispositivos inscritos sin afinidad de usuario.

En caso de que la afinidad de usuario sea necesaria, asegúrese de que el perfil de inscripción del dispositivo tenga seleccionada la **afinidad de usuario** antes de inscribirlo. Para cambiar el estado de afinidad en un dispositivo, debe cancelar su inscripción y realizarla de nuevo.

## <a name="see-also"></a>Vea también

[Solución de problemas con la inscripción de dispositivos iOS/iPadOS en Microsoft Intune](https://support.microsoft.com/help/4039809)
