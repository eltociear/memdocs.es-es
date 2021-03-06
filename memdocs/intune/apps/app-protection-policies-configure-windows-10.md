---
title: Configuración de directivas de protección de aplicaciones para Windows 10
titleSuffix: Microsoft Intune
description: En este tema se describe cómo configurar directivas de protección de aplicación (APP) para dispositivos Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83eccdddd1cc38f72c949c80c4a1488b09920f94
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83988699"
---
# <a name="get-ready-for-windows-information-protection-in-windows-10"></a>Preparación de Windows Information Protection en Windows 10 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Habilite la administración de aplicaciones móviles (MAM) para Windows 10. Para ello, establezca el proveedor de MAM en Azure AD. Establecer un proveedor de MAM en Azure AD permite definir el estado de la inscripción al crear una nueva directiva de Windows Information Protection con Intune. El estado de la inscripción puede ser MAM o administración de dispositivos móviles (MDM).

## <a name="to-configure-the-mam-provider"></a>Para configurar el proveedor de MAM

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Todos los servicios** y elija **Azure Active Directory de M365** para cambiar los paneles.
3. Seleccione **Azure Active Directory**.
4. Elija **Movilidad (MDM y MAM)** en el grupo **Administrar**.
5. Haga clic en **Microsoft Intune**.
6. Configure los valores en el grupo **Restaurar las URL de MAM predeterminadas** en el panel **Configurar**.

   **Ámbito de usuario de MAM**  
   Use la inscripción automática de MAM para administrar los datos de la empresa en los dispositivos Windows de sus empleados. La inscripción automática de MAM se configurará para traer sus propios escenarios de dispositivo.<ul><li>**Ninguno**<br>Seleccione si ningún usuario se puede inscribir en MAM.</li><li>**Algunos**<br>Seleccione los grupos de Azure AD que incluyen los usuarios que se inscribirán en MAM.</li><li>**Todos**<br>Seleccione si todos los usuarios se pueden inscribir en MAM.</li></ul>

   **URL de las condiciones de uso de MAM**  
   Microsoft Intune no admite la URL de los términos de uso de MAM. Este cuadro de entrada se debe dejar en blanco para que se apliquen las directivas de protección.

   **URL de detección de MAM**  
   La dirección URL del punto de conexión de la inscripción del servicio MAM. El punto de conexión de inscripción se usa para inscribir dispositivos para administración con el servicio MAM.

   **URL de cumplimiento de MAM**  
   Microsoft Intune no admite la URL de cumplimiento de MAM. Este cuadro de entrada se debe dejar en blanco para que se apliquen las directivas de protección. 

7. Haga clic en **Guardar**.

## <a name="next-steps"></a>Pasos siguientes

[Creación de una directiva de WIP](windows-information-protection-policy-create.md)
