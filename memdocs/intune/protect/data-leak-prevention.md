---
title: Evitar fugas de datos en dispositivos no administrados
titleSuffix: Microsoft Intune
description: Permitir el acceso a los datos corporativos de dispositivos y proteger los datos de las pérdidas de datos con Microsoft Intune.
keywords: protección de datos, evitar pérdidas, dispositivo, M365, Microsoft 365
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c979d6cf35611a419c4e27605b696c6ad3d85cd9
ms.sourcegitcommit: fde92731a7e27c892d32c63f515cf19545e02ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88996187"
---
# <a name="prevent-data-leaks-on-non-managed-devices-using-microsoft-intune"></a>Evitar fugas de datos en dispositivos no administrados con Microsoft Intune.

Si permite el acceso a datos corporativos hospedados en Microsoft 365, puede controlar la manera en que los usuarios comparten y guardan los datos sin riesgo de sufrir pérdidas de datos de forma intencionada o accidental. Microsoft Intune proporciona directivas de protección de aplicaciones que se establecen para proteger los datos corporativos de dispositivos propiedad del usuario. No es necesario que los dispositivos estén inscritos en el servicio de Intune. 

Las directivas de protección de aplicaciones configuradas con Intune también funcionan en los dispositivos administrados con una solución de administración de dispositivos que no sea de Microsoft. Los datos personales del dispositivo no se modifican. Solo el departamento de TI administra los datos de la empresa. 

Puede establecer directivas de protección de aplicaciones para aplicaciones móviles de Office en dispositivos que ejecutan Windows, iOS/iPadOS o Android para proteger los datos de la empresa. Estas directivas le permiten establecer directivas como el cifrado de datos de empresa o el PIN basado en aplicación, o bien opciones más avanzadas para restringir cómo usan los usuarios las acciones cortar, copiar, pegar y "Guardar como" entre aplicaciones administradas y aplicaciones no administradas. También puede borrar de forma remota datos corporativos sin requerir que los usuarios inscriban los dispositivos.

Las directivas de protección de aplicaciones de Intune son independientes de la administración de dispositivos. Las directivas de protección de aplicaciones le permiten administrar aplicaciones móviles de Office en dispositivos no administrados y en dispositivos administrados por Intune, así como en dispositivos administrados por soluciones MDM que no sean de Microsoft.

## <a name="before-you-begin"></a>Antes de comenzar

Se puede aplicar el siguiente plan de acción si se cumplen los siguientes requisitos:

* Su empresa está preparada para pasar de forma segura a la nube.
* Su empresa usa Microsoft 365 Exchange Online, SharePoint Online, OneDrive para la Empresa o Yammer.
* Su empresa tiene licencias de Microsoft 365, Enterprise Mobility + Security (EMS) o de Azure Information Protection.
* La empresa permite que los usuarios accedan a datos corporativos desde dispositivos Windows, iOS/iPadOS o Android personales o propiedad de la empresa.
* Su empresa no quiere requerir la inscripción de dispositivos personales en un servicio de administración de dispositivos.

## <a name="action-plan"></a>Plan de acción

Para dispositivos iOS/iPadOS y Android:

1. Vea cómo funcionan las [directivas de protección de aplicaciones](../apps/app-protection-policy.md).
2. Aprenda a [crear e implementar directivas de protección de aplicaciones](../apps/app-protection-policies.md) para las aplicaciones móviles de Office.
3. [Supervise las directivas de protección de aplicaciones](../apps/app-protection-policies-monitor.md) que cree e implemente.

Para dispositivos Windows 10:

1. Vea [cómo funciona Windows Information Protection (WIP)](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip).
2. Preparativos para configurar [directivas de protección de aplicaciones para Windows 10](../apps/app-protection-policies-configure-windows-10.md).
3. [Cree e implemente directivas de protección de aplicaciones de WIP con Intune](../apps/windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>Qué decir a los empleados o estudiantes

Según corresponda, comparta los vínculos siguientes para proporcionar más información:

* [Qué esperar cuando la aplicación iOS/iPadOS se administra con directivas de protección de aplicaciones](../fundamentals/end-user-mam-apps-ios.md)
* [What to expect when your Android app is managed by app protection policies](../fundamentals/end-user-mam-apps-android.md) (Qué esperar cuando la aplicación Android se administra con directivas de protección de aplicaciones)

## <a name="next-steps"></a>Pasos siguientes

¿Necesita ayuda para habilitar este u otros escenarios de EMS o Microsoft 365? Si tiene al menos 150 licencias para Microsoft 365, Enterprise Mobility + Security o Azure Active Directory Premium, aproveche las [ventajas de FastTrack](/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).
