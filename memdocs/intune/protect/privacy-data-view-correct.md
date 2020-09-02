---
title: Visualización y corrección de datos personales
titleSuffix: Microsoft Intune
description: Obtenga más información sobre cómo visualizar y corregir los datos personales.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 865a6f33053d9e1fe011d6c2cddf94d0e3995148
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88914978"
---
# <a name="view-and-correct-personal-data"></a>Visualización y corrección de datos personales

Los administradores de Intune pueden ver algunos datos personales en función de sus permisos de acceso, pero solo los usuarios finales pueden cambiar los datos personales de su dispositivo.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Consulta de los datos personales

Los administradores pueden ver la información personal del usuario final en varias hojas en la interfaz de usuario de Intune. En los siguientes artículos se explica a qué información tienen o no acceso los administradores:
- En la sección [Visualización de los detalles del dispositivo](../remote-actions/device-inventory.md) en Intune se explica cómo puede revisar los detalles del dispositivo de un usuario final.
- En [Supervisión de información y asignaciones de aplicaciones](../apps/apps-monitor.md) se explica cómo ver los detalles de las aplicaciones instaladas en el dispositivo de un usuario final.
- En el artículo [¿Qué información puede ver mi empresa cuando inscribo mi dispositivo?](../user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) se proporciona a los usuarios finales una lista con los datos que su empresa puede y no puede ver. Es mejor decir claramente a los usuarios qué tipo de datos se van a recopilar y por qué. Este artículo puede ser el primer paso para hacerlo.

### <a name="who-can-view-the-data"></a>¿Quién puede ver los datos?

Microsoft usa controles estrictos para controlar el acceso a los datos de los clientes, para lo que concede el nivel más bajo de acceso necesario para completar las tareas clave y revoca el acceso cuando ya no se necesita. 

Puede proteger y controlar el acceso a los datos personales del usuario final mediante el uso del control de administración basada en roles (RBAC). Para obtener más información, vea [RBAC con Microsoft Intune](../fundamentals/role-based-access-control.md).

Para obtener más información sobre las prácticas de datos de Microsoft, lea los términos de los servicios en línea y la [declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Corrección de los datos personales del usuario final

Los administradores no pueden actualizar la información específica del dispositivo o la aplicación. Si un usuario final quiere corregir algún dato personal (por ejemplo, el nombre del dispositivo), debe hacerlo directamente en su dispositivo. Estos cambios se sincronizan la siguiente vez que se conecten a Intune.


## <a name="next-steps"></a>Pasos siguientes

Obtenga más información sobre cómo [auditar, exportar o eliminar](privacy-data-audit-export-delete.md) datos personales en Intune.