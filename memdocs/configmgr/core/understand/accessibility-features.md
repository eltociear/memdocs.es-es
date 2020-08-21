---
title: Accesibilidad
titleSuffix: Configuration Manager
description: Conozca las características que permiten que Configuration Manager sea accesible para todo el mundo.
ms.date: 05/15/2020
ms.prod: configuration-manager
ms.technology: configmgr-core
ms.topic: conceptual
ms.assetid: 1cb96666-98bf-49a9-85ca-dbb53f0655e9
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: a6e406d55524caca71bf75b087c9fd78a470c939
ms.sourcegitcommit: 99084d70c032c4db109328a4ca100cd3f5759433
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88699388"
---
# <a name="accessibility-features-in-configuration-manager"></a>Características de accesibilidad de Configuration Manager

*Se aplica a: Configuration Manager (rama actual)*


Configuration Manager incluye características que ayudan a que sea accesible para todo el mundo.

> [!Note]  
> A partir de la versión 1902, para mejorar las características de accesibilidad de la consola de Configuration Manager, actualice .NET a la versión 4.7 o posterior en el equipo que ejecuta la consola. <!-- SCCMDocs-pr issue #3228 -->  
> 
> Para más información sobre los cambios de accesibilidad realizados en .NET 4.7.1 y 4.7.2, consulte [Novedades de accesibilidad en .NET Framework](/dotnet/framework/whats-new/whats-new-in-accessibility).  



## <a name="keyboard-shortcuts"></a>Métodos abreviados de teclado

### <a name="console-workspaces"></a>Áreas de trabajo de la consola

Para tener acceso a un área de trabajo, utilice los siguientes métodos abreviados de teclado:  

|Método abreviado de teclado| Área de trabajo|
|--------|--------|  
|Ctrl + 1| Activos y compatibilidad|
|Ctrl+2|  Biblioteca de software|
|Ctrl+3|  monitoring|
|Ctrl+4|  Administración|


### <a name="other-console-shortcuts"></a>Otros accesos directos de la consola

|Método abreviado de teclado|  Finalidad|
|--------|--------|  
|Ctrl+M|Establece el foco en el panel principal (central).|
|Ctrl+T|Establece el foco en el nodo superior del panel de navegación. Si el foco ya estaba en dicho panel, este se establece en el último nodo que visitó.|
|Ctrl+I|Establece el foco en la barra de ruta de navegación, debajo de la cinta de opciones.|
|Ctrl+L|Establece el foco en el campo **Búsqueda**, si está disponible.|
|Ctrl+D|Establece el foco en el panel Detalles, si está disponible.|
|Alt     |Cambia el foco dentro y fuera de la cinta de opciones.|

### <a name="cmpivot-shortcuts"></a><a name="bkmk_cmpshortcuts"></a> Accesos directos de CMPivot

La mayoría de los [métodos abreviados de teclado del explorador web](https://support.microsoft.com/help/17456/windows-internet-explorer-ease-of-access-options) funcionarán en CMPivot.

|Método abreviado de teclado|Finalidad|
|--------|--------|  
|Ctrl + 1|Establecer el foco en la primera pestaña.|
|Alt + &lt;|Para volver a la dirección|


## <a name="other-accessibility-features"></a>Otras características de accesibilidad

- Para desplazarse por el panel de navegación, escriba las letras de un nombre de nodo.

- La navegación con el teclado por la vista principal y la cinta de opciones es circular.

- La navegación con el teclado en el panel de detalles es circular. Para volver al objeto o panel anterior, utilice Ctrl + D y luego Mayús + Tab.

- Después de actualizar una vista del área de trabajo, se establece el foco en el panel principal de esa área de trabajo.

- Para acceder a un menú del área de trabajo, presione la tecla TAB hasta que el foco esté en el icono Expandir o contraer. Después, presione la tecla de flecha abajo para acceder al menú del área de trabajo.  

- Para navegar por un menú de área de trabajo, utilice las teclas de dirección.  

- Para acceder a diferentes áreas del área de trabajo, utilice las teclas Tab y Mayús+Tab. Para navegar dentro de un área de trabajo, como la cinta, utilice las teclas de dirección.  

- Para acceder a la barra de direcciones cuando el foco está en el nodo de árbol, presione tres veces Mayús+TAB.  

- En una página de asistente o de propiedades, puede desplazarse entre los diferentes cuadros utilizando los métodos abreviados de teclado. Presione la tecla Alt y el carácter subrayado (Alt+_) para seleccionar un cuadro específico.     

- Para desplazarse a los diferentes nodos de un área de trabajo, escriba la primera letra del nombre de un nodo. Cada presión de tecla mueve el cursor al siguiente nodo que comience con esa letra. Para los usuarios que tengan un lector de pantalla, el lector leerá el nombre del nodo.



## <a name="see-also"></a>Vea también

Para más información sobre los fundamentos de navegar por las interfaces de usuario de Configuration Manager, consulte los artículos siguientes:
- [Uso de la consola de Configuration Manager](../servers/manage/admin-console.md)
- [Manual del usuario del Centro de software](software-center.md)

> [!NOTE]  
> Es posible que la información de este artículo solo sea válida para los usuarios con licencia de productos de Microsoft en Estados Unidos. Si ha obtenido este producto fuera de los Estados Unidos, puede usar la tarjeta de información de filiales incluida en el paquete de software o visitar el [sitio web de accesibilidad de Microsoft](https://www.microsoft.com/accessibility/) para obtener la información de contacto de los servicios de soporte técnico de Microsoft. Puede ponerse en contacto con su distribuidor para conocer si el tipo de productos y servicios que se describen en esta sección están disponibles en su área. La información acerca de la accesibilidad está disponible en otros idiomas, incluido el japonés y el francés.