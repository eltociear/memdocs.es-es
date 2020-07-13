---
title: Creación de una directiva de protección de aplicaciones de Mobile Threat Defense (MTD) con Intune
titleSuffix: Microsoft Intune
description: Cree una directiva de protección de aplicaciones de Mobile Threat Defense (MTD) con Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 92d57fe2c63789c6e9f97c8ec835f6ded784ebad
ms.sourcegitcommit: 7de54acc80a2092b17fca407903281435792a77e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "85972120"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Creación de una directiva de protección de aplicaciones de Mobile Threat Defense con Intune

Intune con Mobile Threat Defense (MTD) le ayuda a detectar amenazas y a evaluar el riesgo en dispositivos móviles. Puede crear una directiva de protección de aplicaciones de Intune que evalúe el riesgo para determinar si el dispositivo puede acceder a los datos corporativos o no.

> [!NOTE]
> Este artículo se aplica a todos los asociados de Mobile Threat Defense que admiten directivas de protección de aplicaciones:
>
> - Better Mobile (Android, iOS/iPadOS)
> - Lookout for Work (Android, iOS/iPadOS)
> - Wandera (Android, iOS/iPadOS)
> - Zimperium (Android, iOS/iPadOS)

## <a name="before-you-begin"></a>Antes de comenzar

Como parte de la configuración de MTD, en la consola del partner de MTD se crea una directiva que clasifica las distintas amenazas como alta, media y baja. Ahora, lo que hay que hacer es establecer el nivel de Mobile Threat Defense en la directiva de protección de aplicaciones de Intune.

Requisitos previos de la directiva de protección de aplicaciones con MTD:

- Configurar la integración de MTD con Intune Sin esta integración, la directiva de protección de aplicaciones de MTD no tendrá ningún efecto.

## <a name="to-create-an-mtd-app-protection-policy"></a>Para crear una directiva de protección de aplicaciones de MTD

Use el procedimiento para [crear una directiva de protección de aplicaciones para iOS/iPadOS o Android](../apps/app-protection-policies.md#app-protection-policies-for-iosipados-and-android-apps) y use la siguiente información en las páginas *Aplicaciones*, *Inicio condicional* y *Asignaciones*:

- **Aplicaciones**: Seleccione las aplicaciones a las que quiere que se apliquen las directivas de protección de aplicaciones. En este conjunto de características, estas aplicaciones se bloquean o se borran de forma selectiva en función de la evaluación de riesgos del dispositivo del proveedor de Mobile Threat Defense elegido.
- **Inicio condicional**:  Bajo *Condiciones del dispositivo*, use el cuadro desplegable para seleccionar el **Nivel máximo de amenazas de dispositivo permitido**.

  Opciones para el **Valor** del nivel de amenaza:

  - **Protegido**: este nivel es el más seguro. El dispositivo no puede tener ninguna amenaza presente y aún puede tener acceso a los recursos de la empresa. Si se encuentra alguna amenaza, el dispositivo se clasificará como no conforme.
  - **Bajo**: el dispositivo se evalúa como compatible si solo hay amenazas de nivel bajo. Cualquier valor por encima coloca al dispositivo en un estado de no conformidad.
  - **Media**: el dispositivo se evalúa como compatible si las amenazas que se encuentran en él son de nivel bajo o medio. Si se detectan amenazas de nivel alto, se determinará que el dispositivo no es compatible.
  - **Alta**: este nivel es el menor seguro, ya que permite todos los niveles de amenaza y usa Mobile Threat Defense solo con fines informativos. Los dispositivos deben tener activada la aplicación MTD con esta configuración.

  Opciones para **Acción**:

  - **Bloquear acceso**
  - **Borrar datos**

- **Asignaciones**: Asigne la directiva a los grupos de usuarios.  Los dispositivos que utilicen los miembros de los grupos se evaluarán para determinar su acceso a los datos corporativos en las aplicaciones de destino a través de la protección de aplicaciones de Intune.

## <a name="next-steps"></a>Pasos siguientes

- Más información sobre [Mobile Threat Defense ](mobile-threat-defense.md) en Microsoft Intune.
