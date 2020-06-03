---
title: Usar el Almacenamiento de datos de Intune
titleSuffix: Microsoft Intune
description: Use el Almacenamiento de datos de Intune para generar informes que proporcionen una visión general del entorno móvil de la empresa.
keywords: Almacenamiento de datos de Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/28/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3c6440b800b3bf652cb9adc8c565efcb48ef334
ms.sourcegitcommit: 118587ddb31ce26b27801839db9b3b59f1177f0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84165964"
---
# <a name="use-the-microsoft-intune-data-warehouse"></a>Usar Data Warehouse de Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use el Almacenamiento de datos de Intune para generar informes que proporcionen una visión general del entorno móvil de la empresa. Por ejemplo, algunos de los informes incluyen:
- Tendencia de los usuarios que se inscriben en Intune para que pueda optimizar las compras de licencias.
- Desglose de las versiones de las aplicaciones y del sistema operativo para que pueda revisar el estado de los dispositivos móviles.
- Tendencias de inscripción y cumplimiento de dispositivos para que pueda aplicar fácilmente actualizaciones de directivas.

## <a name="data-warehouse-benefits"></a>Ventajas de Data Warehouse

El Almacenamiento de datos proporciona acceso a más información sobre el entorno móvil que Azure Portal. Con el Almacenamiento de datos de Intune puede tener acceso a lo siguiente:

- Datos históricos de Intune
- Datos actualizados diariamente
- Un modelo de datos mediante el estándar OData

> [!Note]
> Si usa administración de dispositivos móviles (MDM) administrados conjuntamente con Microsoft Endpoint Configuration Manager y Microsoft Intune, tiene que recuperar los datos de Configuration Manager. El Almacenamiento de datos de Intune solo contiene datos de Intune. Puede usar un panel de Power BI de Configuration Manager para los informes personalizados. Para obtener más información, vea "[Presentación de la plantilla de solución de Power BI para Configuration Manager](https://powerbi.microsoft.com/blog/sccm-solution-template)" y "[Contenido de Power BI para Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page)".

> [!Important]  
> Ahora puede usar la versión v1.0 del almacenamiento de datos de Intune mediante la configuración del parámetro de consulta  `api-version=v1.0`. Las actualizaciones de las colecciones en el almacenamiento de datos son aditivas por naturaleza y no interrumpen los escenarios existentes.<br><br>
> Puede probar las funciones más recientes del Almacenamiento de datos mediante la versión beta. Para usar la versión beta, la dirección URL debe contener el parámetro de consulta  `api-version=beta`. La versión beta permite usar ciertas características antes de que estén disponibles con carácter general como servicio admitido. A medida que Intune agrega nuevas características, la versión beta puede cambiar el comportamiento y los contratos de datos. El código personalizado o las herramientas de informes que dependan de la versión beta podrían degradarse con las actualizaciones continuas.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga un vínculo y use Power BI para aprender más. Para obtener instrucciones, vea [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md) (Conectarse al Almacenamiento de datos de Intune con Power BI).
- Con el enlace, podrá crear un informe personalizado con Power BI. Para obtener instrucciones, consulte [Crear un informe desde la fuente OData con Power BI](reports-proc-create-with-odata.md).
- Para más información sobre la API Data Warehouse de Intune, el modelo de datos y las relaciones entre las entidades,<!-- , and an example of creating a custom client to retrieve data,--> vea [API Data Warehouse de Intune](reports-nav-intune-data-warehouse.md).
