---
title: Administración de aplicaciones Win32 en Microsoft Intune
titleSuffix: ''
description: Aprenda a administrar aplicaciones Win32 con Microsoft Intune. En este tema se proporciona información general sobre las funcionalidades de entrega y administración de aplicaciones Win32 de Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: contperfq1
ms.collection: M365-identity-device-management
ms.openlocfilehash: db28653207d7bf4341d614aeecb769dcc145caaa
ms.sourcegitcommit: 4b8c317c71535c2d464f336c03b5bebdd2c6d4c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90083937"
---
# <a name="win32-app-management-in-microsoft-intune"></a>Administración de aplicaciones Win32 en Microsoft Intune

Microsoft Intune permite funcionalidades de administración de aplicaciones Win32. Aunque es posible que los clientes conectados a la nube usen Microsoft Endpoint Configuration Manager para la administración de aplicaciones Win32, aquellos que solo utilicen Intune tendrán mayores funcionalidades de administración para sus aplicaciones Win32 de línea de negocio (LOB). En este tema se proporciona información general sobre las características de administración de aplicaciones Win32 de Intune e información relacionada.

> [!NOTE]
> Esta capacidad de administración de aplicaciones admite la arquitectura del sistema operativo de 32 bits y 64 bits para las aplicaciones Windows.

> [!IMPORTANT]
> Al implementar aplicaciones Win32, considere la posibilidad de usar el enfoque de la [extensión de administración de Intune](../apps/intune-management-extension.md) de forma exclusiva, especialmente cuando tenga un instalador de aplicaciones Win32 de varios archivos. Si mezcla la instalación de aplicaciones Win32 y aplicaciones de línea de negocio durante la inscripción de AutoPilot, puede producirse un error en la instalación de la aplicación. Se instalará la extensión de administración de Intune automáticamente cuando se asigne un script de PowerShell o una aplicación Win32 al usuario o al dispositivo.

## <a name="prerequisites"></a>Requisitos previos

Para usar la administración de aplicaciones Win32, asegúrese de cumplir los criterios siguientes:

- Use Windows 10 versión 1607 o posteriores (versiones Enterprise, Pro y Education).
- Los dispositivos deben estar unidos a Azure Active Directory (Azure AD) y haberse inscrito automáticamente. La extensión de administración de Intune admite dispositivos unidos a Azure AD, unidos a un dominio híbrido e inscritos en una directiva de grupo. 
  > [!NOTE]
  > En el escenario de inscripción en una directiva de grupo, el usuario usa la cuenta de usuario local para unir a Azure AD su dispositivo Windows 10. El usuario debe iniciar sesión en el dispositivo con su cuenta de usuario de Azure AD e inscribirse en Intune. Intune instalará la extensión de administración de Intune en el dispositivo si un script de PowerShell o una aplicación Win32 tiene como destino el usuario o dispositivo.
- El tamaño de la aplicación Windows está limitado a 8 GB por aplicación.

## <a name="prepare-the-win32-app-content-for-upload"></a>Preparar el contenido de la aplicación Win32 para la carga

Antes de poder agregar una aplicación Win32 a Microsoft Intune, debe prepararla mediante la herramienta de preparación de contenido de Microsoft Win32. Use esta herramienta para procesar previamente las aplicaciones clásicas de Windows (Win32). La herramienta convierte los archivos de instalación de la aplicación al formato *.intunewin*. Para más información y conocer los pasos, consulte [Preparación del contenido de una aplicación Win32 para la carga](apps-win32-prepare.md). 

## <a name="add-assign-and-monitor-a-win32-app"></a>Adición, asignación y supervisión de aplicaciones Win32

Después de haber [preparado una aplicación Win32 para su carga en Intune](apps-win32-prepare.md) mediante la herramienta de preparación de contenido de Microsoft Win32, puede agregarla a Intune. Para más información y conocer los pasos, consulte [Adición, asignación y supervisión de una aplicación Win32 en Microsoft Intune](apps-win32-add.md).

## <a name="delivery-optimization"></a>Optimización de entrega

Los clientes de Windows 10 1709 y versiones posteriores descargarán contenido de aplicaciones Win32 de Intune mediante un componente de optimización de distribución del cliente Windows 10. La optimización de distribución proporciona funcionalidad punto a punto que está activada de manera predeterminada. 

Se puede configurar el agente de Optimización de distribución para descargar contenido de aplicaciones Win32 en primer o segundo plano en función de la asignación. La optimización de distribución se puede configurar mediante la directiva de grupo y a través de la configuración de dispositivos de Intune. Para más información, consulte el artículo sobre la [Optimización de distribución para Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

> [!NOTE]
> También puede instalar un servidor de caché con conexión de Microsoft en los puntos de distribución de Configuration Manager para almacenar en caché el contenido de la aplicación Win32 de Intune. Para más información, vea [Caché con conexión de Microsoft en Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

## <a name="install-required-and-available-apps-on-devices"></a>Instalar aplicaciones obligatorias y disponibles en dispositivos

El usuario verá las notificaciones de Windows durante las instalaciones de aplicaciones obligatorias y disponibles. En la siguiente imagen se muestra una notificación de ejemplo donde la instalación de la aplicación no finaliza hasta que se reinicia el dispositivo. 

![Captura de pantalla de notificaciones de Windows para la instalación de una aplicación.](./media/apps-win32-app-management/apps-win32-app-08.png)    

La siguiente imagen notifica al usuario que se están realizando cambios de la aplicación en el dispositivo.

![Captura de pantalla que notifica al usuario que se están realizando cambios en la aplicación.](./media/apps-win32-app-management/apps-win32-app-09.png)    

Además, en la aplicación del Portal de empresa se muestra a los usuarios más mensajes de estado de la instalación de la aplicación. Las condiciones siguientes se aplican a las características de dependencia de Win32:
- La aplicación no se pudo instalar. No se cumplieron las dependencias definidas por el administrador.
- La aplicación se ha instalado correctamente, pero requiere un reinicio.
- La aplicación está en proceso de instalación, pero se requiere un reinicio para continuar.

## <a name="set-win32-app-availability-and-notifications"></a>Establecimiento de la disponibilidad y las notificaciones de las aplicaciones Win32
Puede configurar la hora de inicio y la hora de la fecha límite para una aplicación Win32. A la hora de inicio, la extensión de administración de Intune iniciará la descarga del contenido de la aplicación y lo almacenará en caché según la intención necesaria. La aplicación se instalará a la hora de la fecha límite. 

En las aplicaciones disponibles, la hora de inicio determina cuándo la aplicación está visible en el Portal de empresa, y el contenido se descarga cuando el usuario solicita la aplicación desde el Portal de empresa. También puede habilitar un período de gracia de reinicio. 

> [!IMPORTANT]
> La opción **Período de gracia de reinicio** de la sección **Asignación** solo está disponible cuando **Comportamiento de reinicio de dispositivo** de la sección **Programa** se establece en una de las opciones siguientes:
> - **Determinar comportamiento en función de códigos de retorno**
> - **Intune forzará un reinicio obligatorio del dispositivo**

Establezca la disponibilidad de la aplicación en función de la fecha y la hora de una aplicación necesaria mediante los pasos siguientes:

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Aplicaciones** > **Todas las aplicaciones**.
3. En la lista **Aplicación de Windows (Win32)** , seleccione una aplicación. 
4. En el panel de la aplicación, seleccione **Propiedades** > **Editar** junto a la sección **Asignaciones**. Luego, seleccione **Agregar grupo** debajo del tipo de asignación **Requerido**. 
   
   Tenga en cuenta que la disponibilidad de la aplicación se puede establecer en función del tipo de asignación. La opción **Tipo de asignación** puede tener los valores **Requerido**, **Disponible para dispositivos inscritos** o **Desinstalar**.
5. Seleccione un grupo en el panel **Seleccionar grupo** para especificar a qué grupo de usuarios se le asignará la aplicación. 

    > [!NOTE]
    > Las opciones de **Tipo de asignación** incluyen las siguientes:<br>
    > - **Requerido**: puede elegir entre **Hacer que esta aplicación sea obligatoria para todos los usuarios** o **Hacer que esta aplicación sea obligatoria en todos los dispositivos**.<br>
    > - **Disponible para dispositivos inscritos**: puede elegir **Hacer que esta aplicación esté disponible para todos los usuarios con dispositivos inscritos**.<br>
    > - **Desinstalar**: puede optar por **Desinstalar esta aplicación para todos los usuarios** o **Desinstalar esta aplicación para todos los dispositivos**.

6. Para modificar las opciones de **Notificación para el usuario final**, seleccione **Mostrar todas las notificaciones del sistema**.
7. En el panel **Editar asignación**, establezca **Notificaciones del usuario final** en **Mostrar todas las notificaciones del sistema**. Tenga en cuenta que puede establecer **Notificaciones de usuario final** en **Mostrar todas las notificaciones del sistema**, **Mostrar notificaciones del sistema para reinicios de equipo** o en **Ocultar todas las notificaciones del sistema**.
8. Establezca **Disponibilidad de la aplicación** en **Fecha y hora específicas** y seleccione la fecha y hora. Esta fecha y hora especifican cuándo se descarga la aplicación en el dispositivo del usuario. 
9. Establezca **Fecha límite de instalación de la aplicación** en **Fecha y hora específicas** y seleccione la fecha y hora. Esta fecha y hora especifica cuándo se instala la aplicación en el dispositivo del usuario. Cuando se realiza más de una asignación para el mismo usuario o dispositivo, la hora de la fecha límite de instalación de la aplicación se elige en función de la fecha más temprana posible.

10. Junto a **Período de gracia de reinicio**, seleccione **Habilitado**. El período de gracia de reinicio se inicia en cuanto finaliza la instalación de la aplicación en el dispositivo. Cuando esta opción está deshabilitada, el dispositivo puede reiniciarse sin previo aviso. 

    Puede personalizar las opciones siguientes:
    
    - **Periodo de gracia de reinicio del dispositivo (minutos)** : El valor predeterminado es 1440 minutos (24 horas). Este valor puede ser un máximo de dos semanas.
    - **Seleccionar cuándo debe mostrarse el cuadro de diálogo de cuenta regresiva de reinicio antes de producirse el reinicio (minutos)** : El valor predeterminado es 15 minutos.
    - **Permitir al usuario posponer la notificación de reinicio**: Puede elegir entre **Sí** o **No**.
        - **Seleccionar la duración del aplazamiento (minutos)** : El valor predeterminado es 240 minutos (4 horas). El valor de aplazamiento no puede ser mayor que el período de gracia de reinicio.

11. Seleccione **Revisar y guardar**.

## <a name="notifications-for-win32-apps"></a>Notificaciones para aplicaciones Win32 
Si es necesario, puede suprimir que se muestren notificaciones al usuario por asignación de aplicaciones. En Intune, seleccione **Aplicaciones** > **Todas las aplicaciones** > *la aplicación* > **Asignaciones** > **Incluir grupos**. 

> [!NOTE]
> Las aplicaciones Win32 instaladas mediante la extensión de administración de Intune no se desinstalarán en dispositivos no inscritos. Los administradores pueden usar la exclusión de asignaciones para no ofrecer aplicaciones Win32 a los dispositivos con el programa Bring Your Own Device (BYOD).

## <a name="next-steps"></a>Pasos siguientes

- Para obtener más información sobre agregar aplicaciones en Intune, vea [Incorporación de aplicaciones a Microsoft Intune](apps-add.md).
