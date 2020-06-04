---
title: 'Configuración de dispositivos compartidos o multiusuario de Microsoft Intune: Azure | Microsoft Docs'
description: Agregue y use dispositivos Windows 10 y Windows Holographic for Business compartidos o con varios usuarios en Microsoft Intune. Vea una lista de todas las opciones de configuración y lo que hacen en los dispositivos, incluido Microsoft HoloLens. Controle cuentas de invitado, administre cuentas y elimine cuentas inactivas, permita o impida guardar en el almacenamiento local, configure las opciones de energía y suspensión, seleccione cuándo se instalarán las actualizaciones y use dispositivos en entornos educativos en un perfil de configuración de dispositivos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/13/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4f85c30c9472849d26802c8cdccd7a95006a3e4a
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83984016"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Control del acceso, las cuentas y las características de energía en dispositivos con varios usuarios o equipos compartidos mediante Intune

Los dispositivos con varios usuarios se denominan dispositivos compartidos y son una parte común de las soluciones de administración de dispositivos móviles (MDM). Con Microsoft Intune puede personalizar dispositivos compartidos que se ejecuten en las plataformas siguientes:

- Windows 10 Professional y versiones más recientes
- Windows 10 Enterprise y versiones más recientes
- Windows Holographic for Business, como HoloLens

Por ejemplo, los centros educativos tienen dispositivos que suele usar un gran número de alumnos. Con esta configuración, el administrador de Intune del centro educativo puede activar la característica de equipos compartidos para permitir solo un usuario cada vez. Los alumnos no pueden cambiar entre las distintas cuentas que hayan iniciado sesión en el dispositivo. Cuando el alumno cierra sesión, también puede seleccionar la opción pertinente para quitar toda la configuración específica del usuario.

Los usuarios finales pueden iniciar sesión en estos dispositivos compartidos con una cuenta de invitado. Cuando los usuarios inicien la sesión, las credenciales se almacenarán en la caché. Cuando usen el dispositivo, los usuarios finales solo podrán acceder a las características que les permita. Por ejemplo, puede elegir el momento en el que el dispositivo pasará al modo de suspensión, si los usuarios pueden ver y guardar archivos localmente, habilitar o deshabilitar la configuración de administración de energía, y mucho más. También puede controlar si la cuenta de invitado se elimina cuando el usuario cierra la sesión, o bien si se eliminan las cuentas inactivas cuando se alcanza el umbral.

En este artículo se muestra cómo crear un perfil de configuración y se incluyen vínculos a las opciones de configuración disponibles, además de sus descripciones.

Al crear el perfil en Intune, se implementa o asigna el perfil a grupos de dispositivos en la organización. También puede asignar este perfil a grupos de dispositivos con tipos de dispositivo y versiones del sistema operativo (SO) mixtos.

## <a name="create-the-profile"></a>Creación del perfil

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba las propiedades siguientes:

   - **Plataforma**: seleccione **Windows 10 y versiones posteriores**.
   - **Perfil**: seleccione **Dispositivo multiusuario compartido**.

4. Seleccione **Crear**.
5. En **Básico**, escriba las propiedades siguientes:

   - **Nombre**: escriba un nombre descriptivo para el nuevo perfil.
   - **Descripción**: escriba una descripción para el perfil. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.
7. En **Opciones de configuración**, las opciones que puede configurar serán diferentes, según la plataforma que haya elegido. Elija la plataforma para la configuración detallada:

    - [Windows 10 y versiones posteriores](shared-user-device-settings-windows.md)
    - [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md)

8. Seleccione **Siguiente**.

9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

    Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione los grupos de dispositivos que van a recibir el perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](device-profile-assign.md).

    Seleccione **Siguiente**.

    > [!NOTE]
    > Asegúrese de asignar el perfil a grupos de dispositivos de la organización.

11. En **Revisar y crear**, revise la configuración. Si selecciona **Crear**, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.

La próxima vez que cada dispositivo se registre, se aplicará la directiva.

## <a name="next-steps"></a>Pasos siguientes

- Vea todas las opciones de configuración para [Windows 10 y versiones posteriores](shared-user-device-settings-windows.md) y [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- Una vez [asignado el perfil](device-profile-assign.md), [supervise su estado](device-profile-monitor.md).
