---
title: Administración de dispositivos de forma remota en Microsoft Intune - Azure | Microsoft Docs
description: Consulte los roles necesarios para usar TeamViewer, cómo instalar el conector de TeamViewer y una guía paso a paso para administrar dispositivos de forma remota usando Microsoft Intune en Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3031e909b5bd330f9ec84f05f2c83c504022d50e
ms.sourcegitcommit: 7a099ff53668f50b37adab97ecd7ba98c5324676
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2020
ms.locfileid: "84746602"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Uso de TeamViewer para administrar dispositivos de Intune de forma remota

Los dispositivos administrados por Intune pueden administrarse de forma remota con [TeamViewer](https://www.teamviewer.com). TeamViewer es un programa de terceros que se adquiere por separado. En este tema se muestra cómo configurar TeamViewer en Intune y cómo administrar un dispositivo de forma remota. 

## <a name="prerequisites"></a>Requisitos previos

- Use un dispositivo compatible. Los dispositivos con Administrador de dispositivos Android, Perfil de trabajo Android, Windows, iOS/iPadOS y macOS administrados por Intune se pueden administrar de forma remota. Es posible que TeamViewer no sea compatible con Windows Holographic (HoloLens), Windows Team (Surface Hub) o Windows 10 S. Si tiene dudas sobre la compatibilidad, consulte [TeamViewer](https://www.teamviewer.com) para ver las actualizaciones.

> [!NOTE]
> Los dispositivos totalmente administrados y dedicados de Android no se admiten.

- El administrador de Intune en Azure Portal debe tener los siguientes [roles de Intune](../fundamentals/role-based-access-control.md):  

  - **Actualizar asistencia remota**: Permite a los administradores modificar la configuración del conector de TeamViewer.
  - **Solicitar asistencia remota**: Permite a los administradores iniciar una nueva sesión de asistencia remota para cualquier usuario. Los usuarios con este rol no están limitados por ningún rol de Intune dentro de un ámbito. Además, los grupos de dispositivos o usuarios a los que se ha asignado un rol de Intune dentro de un ámbito también pueden solicitar asistencia remota. 

- Cuenta de [TeamViewer](https://www.teamviewer.com) con las credenciales de inicio de sesión. Solo algunas licencias TeamViewer pueden admitir la integración con Intune. Para las necesidades específicas de TeamViewer, consulte [Partner de integración de TeamViewer: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/).

Al usar TeamViewer, permite que el conector de TeamViewer para Intune cree sesiones de TeamViewer, lea datos de Active Directory y guarde el token de acceso de la cuenta de TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Configuración del conector de TeamViewer

Para proporcionar asistencia remota a los dispositivos, configure el conector de TeamViewer para Intune siguiendo estos pasos:

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Administración de inquilinos** > **Conectores y tokens** > **Conector de TeamViewer**.
3. Seleccione **Conectar** y acepte el contrato de licencia.
4. Seleccione **Inicie sesión en TeamViewer para autorizar**.
5. Se abre una página web en el sitio de TeamViewer. Escriba sus credenciales de la licencia de TeamViewer y haga clic en **Iniciar sesión**.

## <a name="remotely-administer-a-device"></a>Administración remota de un dispositivo

Una vez configurado el conector, estará listo para administrar un dispositivo de forma remota. Use los pasos siguientes: 

1. Vaya al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** y, después, **Todos los dispositivos**.
3. En la lista, seleccione el dispositivo que quiere administrar de forma remota> **...**  > **Nueva sesión de Asistencia remota**.
4. Cuando Intune se conecte al servicio TeamViewer, verá información sobre el dispositivo. Elija **Conectar** para iniciar la sesión remota.

![Ejemplo de uso de TeamViewer para administrar un dispositivo Android de forma remota](./media/teamviewer-support/android-teamviewer.png)

Al iniciar una sesión remota, los usuarios verán una marca de notificación en el icono de la aplicación Portal de empresa de su dispositivo. También se mostrará una notificación cuando abra la aplicación. Los usuarios pueden aceptar la solicitud de asistencia remota.

> [!NOTE]
> Los dispositivos Windows inscritos con métodos "sin usuarios", como Administrador de inscripción de dispositivos (DEM) o Windows Configuration Designer (WCD), no muestran la notificación de TeamViewer en la aplicación Portal de empresa. En estos casos, se recomienda usar el portal de TeamViewer para generar la sesión.

En TeamViewer, puede completar una serie de acciones en el dispositivo, incluida la toma del control de este. Para obtener más detalles sobre lo que puede hacer, consulte la [página de la comunidad de TeamViewer](https://community.teamviewer.com/).

Cuando haya finalizado, cierre la ventana de TeamViewer.
