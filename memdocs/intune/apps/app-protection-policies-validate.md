---
title: Validación de la configuración de la directiva de protección de aplicaciones
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo probar si su directiva de protección de aplicaciones está configurada y funciona correctamente en Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/31/2020
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.topic: how-to
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02266ce355d4fc4b74487840a91b503d69bf7b2e
ms.sourcegitcommit: fde92731a7e27c892d32c63f515cf19545e02ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88996510"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>Validación de la configuración de la directiva de protección de aplicaciones en Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Compruebe que su directiva de protección de aplicaciones esté configurada y funcione correctamente. Esta guía se aplica a las directivas de protección de aplicaciones de Azure Portal.

## <a name="checking-for-symptoms"></a>Examinar los síntomas
Los usuarios no suelen notificar problemas, ya que la protección de aplicaciones es una herramienta de protección de datos. Si hay algún problema con la configuración de la protección de aplicaciones, el usuario tendrá acceso ilimitado, del mismo modo que si no tuviera protección de aplicaciones, y no podrá detectar que hay un problema. Por este motivo, se recomienda que valide la configuración de la protección de aplicaciones efectuando una prueba piloto de las directivas de protección de aplicaciones con un pequeño grupo de usuarios que puedan probar deliberadamente las restricciones de la protección de aplicaciones.

## <a name="what-to-check"></a>Elementos que se deben comprobar

Si las pruebas muestran que el comportamiento de la directiva de protección de aplicaciones no funciona según lo previsto, compruebe lo siguiente:

- ¿Tienen licencia los usuarios para la protección de aplicaciones?
- ¿Los usuarios tienen licencia para Microsoft 365?
- ¿El estado de protección de cada una de las aplicaciones de los usuarios no es el esperado? Los estados posibles de las aplicaciones son **Protegido** y **No protegido**.

### <a name="user-app-protection-status"></a>Estado de protección de las aplicaciones de los usuarios
1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Seleccione **Aplicaciones** > **Supervisar** >  **Estado de protección de la aplicación** y, luego, el icono **Usuarios asignados**. 
4. En la página **Informes de aplicaciones**, seleccione **Seleccionar usuario** para abrir una lista de usuarios y grupos. 
5. Busque y seleccione un usuario de la lista y luego elija **Seleccionar usuario**. En la parte superior del panel **Informes de aplicaciones**, verá si el usuario tiene licencia para la protección de aplicaciones. También puede consultar si el usuario tiene licencia para Microsoft 365, así como el estado de la aplicación para todos los dispositivos del usuario.

## <a name="what-to-do"></a>Qué hacer
Aquí se muestran las acciones que se deben tomar en función del estado del usuario:

- Si el usuario no tiene licencia para la protección de aplicaciones, asigne una [licencia de Intune](../fundamentals/licenses.md) al usuario.
- Si el usuario no tiene licencia para Microsoft 365, [obtenga una](../fundamentals/licenses.md).
- Si la aplicación de un usuario aparece como **No protegida**, compruebe si ha configurado correctamente una [directiva de protección de aplicaciones](app-protection-policies-validate.md) para esa aplicación.
- Asegúrese de que estas condiciones se aplican a todos los usuarios a los que quiera aplicar [directivas de protección de aplicaciones](app-protection-policies-monitor.md).

## <a name="see-also"></a>Vea también

- [¿Qué es la directiva de protección de aplicaciones de Intune?](app-protection-policies.md)
- [Licencias que incluyen Intune](../fundamentals/licenses.md)
- [Asignar licencias a los usuarios para que puedan inscribir dispositivos en Intune](../fundamentals/licenses-assign.md)
- [Validación de la configuración de la directiva de protección de aplicaciones](app-protection-policies-validate.md)
- [Supervisión de las directivas de protección de aplicaciones](app-protection-policies-monitor.md)

