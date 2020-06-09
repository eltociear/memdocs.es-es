---
title: Configuración del conector SandBlast MTD de Check Point con Intune
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo integrar Intune con SandBlast Mobile Threat Defense de Check Point para controlar el acceso de los dispositivos móviles a los recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/09/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a0645c771b304bfb4930f5cd365b9291366499b1
ms.sourcegitcommit: 42a4a4454e56fa681f0ad39f5e585492dfbad286
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84330923"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Conector de defensa contra amenazas SandBlast Mobile de Check Point con Intune

Puede controlar el acceso desde dispositivos móviles a recursos corporativos mediante el acceso condicional basado en la evaluación de riesgos efectuada por SandBlast Mobile de Check Point, una solución de defensa contra amenazas móviles integrada en Microsoft Intune. El riesgo se evalúa según la telemetría recopilada de dispositivos que ejecutan la aplicación SandBlast Mobile de Check Point.

Puede configurar directivas de acceso condicional según la evaluación de riesgos de SandBlast Mobile de Check Point habilitada mediante las directivas de cumplimiento de dispositivos de Intune, que puede usar a fin de permitir o bloquear dispositivos que no cumplan los requisitos para que no obtengan acceso a recursos corporativos en función de las amenazas detectadas.

> [!NOTE]
> Este proveedor de Mobile Threat Defense no es compatible con dispositivos no inscritos.

## <a name="supported-platforms"></a>Plataformas compatibles

- **Android 4.1 y versiones posteriores**

- **iOS 8 y versiones posteriores**

## <a name="pre-requisites"></a>Requisitos previos

- Azure Active Directory Premium

- Suscripción a Microsoft Intune

- Suscripción a Check Point SandBlast Mobile Threat Defense
  - Consulte el [sitio web de CheckPoint SandBlast](https://www.checkpoint.com/) para obtener más información.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>¿Cómo ayudan Intune y SandBlast Mobile de Check Point a proteger los recursos de su empresa?

La aplicación Sandblast Mobile de Check Point para iOS/iPadOS y Android captura telemetría del sistema de archivos, la pila de red, los dispositivos y las aplicaciones si está disponible y, después, envía los datos de telemetría al servicio en la nube de Sandblast de Check Point para evaluar el riesgo del dispositivo frente a las amenazas móviles.

La directiva de cumplimiento de dispositivos de Intune incluye una regla para el conector de defensa contra amenazas SandBlast Mobile de Check Point, que se basa en la evaluación de riesgos de SandBlast de Check Point. Cuando esta regla está habilitada, Intune evalúa la conformidad del dispositivo con la directiva que habilitó. Si se detecta que el dispositivo no cumple con la directiva, se bloqueará el acceso de los usuarios a los recursos corporativos, como Exchange Online y SharePoint Online. Los usuarios también reciben los pasos de la aplicación móvil de SandBlast de Check Point instalada en sus dispositivos para resolver el problema y volver a obtener acceso a los recursos corporativos.

Estos son algunos escenarios frecuentes:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Control del acceso basado en amenazas de aplicaciones malintencionadas

Cuando se detectan aplicaciones malintencionadas, como malware, en los dispositivos, puede bloquearlos de la siguiente manera hasta que la amenaza se resuelva:

- Conectarse al correo electrónico corporativo

- Sincronizar los archivos corporativos mediante la aplicación OneDrive para el trabajo

- Acceder a las aplicaciones de empresa

*Bloquear cuando se detectan aplicaciones malintencionadas:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: bloqueo cuando se detectan aplicaciones malintencionadas](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-2.PNG)

*Acceso concedido tras la corrección:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: acceso concedido](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Controlar el acceso basándose en amenazas en la red

Detecte amenazas para la red, como **ataques de tipo Man-in-the-middle**, y proteja el acceso a las redes Wi-Fi según el riesgo del dispositivo.

*Bloquear el acceso de red a través de Wi-Fi:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: bloqueo del acceso de red a través de Wi-Fi](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-4.PNG)

*Acceso concedido tras la corrección:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: acceso a través de Wi-Fi concedido](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar el acceso a SharePoint Online basándose en amenazas en la red

Detecte amenazas para la red, como **ataques de tipo Man-in-the-middle**, y evite la sincronización de archivos corporativos según el riesgo del dispositivo.

*Bloqueo de SharePoint Online cuando se detectan amenazas a la red:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: bloqueo del acceso a SharePoint Online](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-6.PNG)

*Acceso concedido tras la corrección:*

> [!div class="mx-imgBorder"]
> ![Check Point MTD: acceso concedido a SharePoint Online](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-mtd-7.PNG)

<!-- ### Control access on unenrolled devices based on threats from malicious apps

When the Check Point Sandblast Mobile Threat Defense solution considers a device to be infected:
> [!div class="mx-imgBorder"]
> ![App protection policy blocks due to detected malware](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/sandblast-app-policy-block.png)

Access is granted on remediation:

> [!div class="mx-imgBorder"]
> ![Access is granted on remediation for App protection policy](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/sandblast-app-policy-remediated.png)
-->

## <a name="next-steps"></a>Pasos siguientes

- [Integrar SandBlast Mobile de Check Point con Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Configurar la aplicación SandBlast Mobile de CheckPoint](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Creación de directiva de cumplimiento de dispositivos de SandBlast Mobile de CheckPoint](mtd-device-compliance-policy-create.md)

- [Habilitar el conector SandBlast Mobile MTD de CheckPoint](mtd-connector-enable.md)
