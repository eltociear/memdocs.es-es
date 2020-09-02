---
title: 'Auditoría de cambios y eventos en Microsoft Intune: Azure | Microsoft Docs'
description: Obtenga información acerca de cómo revisar los registros de auditoría que registran las actividades de Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1808743685c6907c11da23f92c5e263860098bea
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88909693"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Uso de registros de auditoría para realizar un seguimiento y supervisar eventos en Microsoft Intune

Los registros de auditoría incluyen un registro de las actividades que generan un cambio en Microsoft Intune. Las acciones de creación, actualización (edición), eliminación, asignación y remotas crean eventos de auditoría que los administradores pueden revisar para la mayoría de las cargas de trabajo de Intune. La auditoría está habilitada de forma predeterminada para todos los clientes. No se puede deshabilitar.

> [!NOTE]
> Los eventos de auditoría comenzaron a registrarse en la versión de características de diciembre de 2017. Los eventos anteriores no están disponibles.

## <a name="who-can-access-the-data"></a>¿Quién puede tener acceso a los datos?

Los usuarios con los siguientes permisos pueden revisar los registros de auditoría:

- Administrador global
- Administrador del servicio de Intune
- Administradores asignados a un rol de Intune con los permisos **Datos de auditoría** - **Lectura**

## <a name="audit-logs-for-intune-workloads"></a>Registros de auditoría para cargas de trabajo de Intune

Puede revisar los registros de auditoría en el grupo de supervisión para cada carga de trabajo de Intune:

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Administración de inquilinos** > **Registros de auditoría**.
3. Para filtrar los resultados, seleccione **Filtro** y restrinja los resultados con las opciones siguientes.
    - **Categoría**: como, por ejemplo, **Cumplimiento**, **Dispositivo** y **Rol**.
    - **Actividad**: las opciones que se muestran aquí están restringidas por la opción elegida en **Categoría**.
    - **Intervalo de fechas**: puede elegir registros para el mes, semana o día anteriores.
4. Elija **Aplicar**.
4. Seleccione un elemento de la lista para ver los detalles de la actividad.

## <a name="route-logs-to-azure-monitor"></a>Enrutamiento de registros a Azure Monitor

También se pueden enrutar registros de auditoría y registros operativos a Azure Monitor. En **Registros de auditoría**, seleccione **Exportar configuración de datos**:

![Exportación de datos de registro en Azure Monitor seleccionando Exportar configuración de datos en Intune](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

> [!NOTE]
> Para obtener más información sobre esta característica y revisar los requisitos previos para usarla, vea [Envío de datos de registro a almacenamiento, centro de eventos o análisis de registros](review-logs-using-azure-monitor.md).

> [!NOTE]
> **Iniciado por (actor)** incluye información sobre quién ejecutó la tarea y sobre dónde se ejecutó. Por ejemplo, si ejecuta la actividad en Intune en Azure Portal, como **Aplicación** siempre figura **Extensión del portal de Microsoft Intune** y como **Id. de aplicación** siempre se usa el mismo GUID.
>
> La sección **Destinos** muestra varios destinos y las propiedades que cambiaron.  

## <a name="use-graph-api-to-retrieve-audit-events"></a>Uso de API Graph para recuperar eventos de auditoría

Para más información sobre el uso de Graph API para recuperar hasta un año de eventos de auditoría, vea [Enumerar auditEvents](/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Pasos siguientes

[Envío de datos de registro a Storage, Event Hubs o Log Analytics](review-logs-using-azure-monitor.md).

[Revisión de los registros de protección de aplicaciones cliente](../apps/app-protection-policy-settings-log.md).