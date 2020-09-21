---
title: Administradores sin licencia en Microsoft Intune
description: Obtenga información sobre cómo conceder a los administradores sin licencia permiso para acceder a Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a5f479dcad0c293c547edec24f0f835a4fc987e1
ms.sourcegitcommit: cba06c182646cb6dceef304b35230bf728d5133e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90574837"
---
# <a name="unlicensed-admins"></a>Administradores sin licencia

> [!Important]
> Esta opción solo elimina para los administradores el requisito de tener una licencia para acceder a Microsoft Endpoint Manager. Para usar otras características o servicios, como Azure Active Directory Premium, puede seguir siendo necesaria una licencia para el administrador.

Puede conceder acceso al centro de administración de Microsoft Endpoint Manager/Intune a los administradores sin licencias de Intune.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Administración de inquilinos** > **Roles** > **Licencias de administrador**.
2. Seleccione **Permitir el acceso a administradores sin licencia** > **Sí**.
    >[!WARNING]
    >No se puede deshacer esta configuración después de hacer clic en **Sí**.

3. A partir de ahora, los usuarios que inicien sesión en el centro de administración de Microsoft Endpoint Manager no necesitarán una licencia de Intune. Su ámbito de acceso se definirá mediante los roles que tengan asignados.

Intune admite hasta 350 administradores sin licencia por grupo de seguridad y solo se aplica a los miembros directos. Los administradores que superen este límite experimentarán un comportamiento imprevisible.




