---
title: Agregar aplicaciones de Microsoft Store a Microsoft Intune
titleSuffix: ''
description: Obtenga información sobre cómo agregar aplicaciones de Microsoft Store (Tienda Windows) a Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/13/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c816bf41933346a568ff0419ea8daccbeffebd3d
ms.sourcegitcommit: 1aeb4a11e89f68e8081d76ab013aef6b291c73c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "88217298"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Agregar aplicaciones de Microsoft Store a Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Para poder asignar, supervisar, configurar o proteger las aplicaciones, debe agregarlas a Intune. 

## <a name="add-an-app-to-intune"></a>Agregar una aplicación a Intune
Puede agregar una aplicación de Microsoft Store a Intune si hace lo siguiente:

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Aplicaciones** > **Todas las aplicaciones** > **Agregar**.
3. En el panel **Seleccionar tipo de aplicación**, en los tipos de **Aplicación de la Tienda** disponibles, seleccione **Aplicación de la Tienda Windows**.
4. Haga clic en **Seleccionar**. Se muestran los pasos para **Agregar aplicación**.
5. Para configurar la **Información de la aplicación** para las aplicaciones de la Tienda de Windows, vaya a [Microsoft Store](https://www.microsoft.com/store/apps) y busque la aplicación que quiere implementar. Muestre la página de la aplicación y tome nota de los detalles de la aplicación. 
6. En la página **Información de la aplicación**, agregue los detalles de la aplicación:
    - **Nombre**: escriba el nombre de la aplicación como se va a mostrar en el Portal de empresa. Asegúrese de que cualquier nombre de aplicación que use sea exclusivo. Si hay un nombre de aplicación duplicado, solo se muestra uno a los usuarios del Portal de empresa.
    - **Descripción**: Escriba una descripción de la aplicación. Esta descripción se muestra a los usuarios del Portal de empresa.
    - **Publicador**: Escriba el nombre del publicador de la aplicación.
    - **Dirección URL de Appstore**: escriba la dirección URL de App Store de la aplicación que quiere crear. Para encontrar la dirección URL, busque la aplicación deseada en [Microsoft Store](https://www.microsoft.com/store/apps). Use la dirección URL de la barra de direcciones del explorador.
    - **Categoría**: de manera opcional, seleccione una o varias de las categorías de aplicaciones integradas o una categoría que haya creado. Esto facilita que los usuarios puedan encontrar la aplicación cuando exploran el Portal de empresa.
    - **Mostrar como aplicación destacada en el Portal de empresa**: seleccione esta opción para mostrar el conjunto de aplicaciones de forma destacada en la página principal del Portal de empresa cuando los usuarios busquen aplicaciones.
    - **Dirección URL de información**: Opcionalmente, escriba la dirección URL de un sitio web que contenga información sobre esta aplicación. La dirección URL se muestra a los usuarios en el portal de empresa.
    - **Dirección URL de privacidad**: Opcionalmente, escriba la dirección URL de un sitio web que contenga información de privacidad sobre esta aplicación. La dirección URL se muestra a los usuarios en el portal de empresa.
    - **Desarrollador**: opcionalmente, escriba el nombre del desarrollador de la aplicación.
    - **Propietario**: opcionalmente, escriba un nombre para el propietario de esta aplicación, por ejemplo, *Departamento de Recursos Humanos*.
    - **Notas**: opcionalmente, escriba las notas que desea asociar a esta aplicación.
    - **Logotipo**: opcionalmente, cargue un icono que se asociará con la aplicación. Este icono se muestra con la aplicación cuando los usuarios examinan el portal de empresa.
7. Haga clic en **Siguiente** para mostrar la página **Etiquetas de ámbito**.
8. Si quiere, haga clic en **Seleccionar etiquetas de ámbito** para agregar etiquetas de ámbito para la aplicación. Para más información, consulte [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito para TI distribuida](../fundamentals/scope-tags.md).
9. Haga clic en **Siguiente** para abrir la página **Asignaciones**.
10. Seleccione las asignaciones de grupo para la aplicación. Para más información, consulte [Agregar grupos para organizar usuarios y dispositivos](../fundamentals/groups-add.md). 
11. Elija **Siguiente** para mostrar la página **Revisar y crear**. Revise los valores y la configuración que especificó para la aplicación.
12. Cuando haya terminado, haga clic en **Crear** para agregar la aplicación a Intune.

Se muestra la hoja **Información general** de la aplicación que creó.

La aplicación que ha creado aparece en la lista de aplicaciones, donde puede asignarla a los grupos que seleccione.

> [!IMPORTANT]
> Las aplicaciones de Microsoft Store solo pueden asignarse a grupos con el tipo de asignación **Disponible para dispositivos inscritos** (los usuarios instalan la aplicación desde el sitio web o la aplicación Portal de empresa).

## <a name="next-steps"></a>Pasos siguientes

- [Asignar aplicaciones a grupos](apps-deploy.md)
