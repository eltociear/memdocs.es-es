---
title: Ver los detalles de un dispositivo con Microsoft Intune - Azure | Microsoft Docs
description: Vea los detalles del dispositivo, incluidos los sistemas operativos, el espacio de almacenamiento, el fabricante y el modelo. Obtenga una lista de las aplicaciones instaladas, compruebe las directivas de cumplimiento y configure TeamViewer con Microsoft Intune en Azure. El procedimiento es similar a ver el inventario de los dispositivos que administra.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/11/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cc9cf0bdba9a6dea77955a6b88d3221053ea50f
ms.sourcegitcommit: e2deac196e5e79a183aaf8327b606055efcecc82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90076148"
---
# <a name="see-device-details-in-intune"></a>Ver detalles del dispositivo en Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

La característica **Dispositivos** proporciona detalles adicionales sobre los dispositivos que administra, incluido el hardware, y sobre las aplicaciones instaladas.

En este artículo se explica cómo se pueden ver todos los dispositivos y sus propiedades en el portal de Azure.

## <a name="view-the-device-details"></a>Ver los detalles del dispositivo

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Seleccione **Dispositivos** > **Todos los dispositivos** > seleccione uno de los dispositivos que aparecen para que se muestren los detalles correspondientes:

   - En **Información general** se indica el nombre del dispositivo y algunas de sus propiedades clave, como, por ejemplo, si se trata de un dispositivo personal o corporativo, el número de serie, el usuario principal, etc. Puede realizar lo siguiente en el dispositivo:
      - [Retirar](devices-wipe.md#retire)
      - [Borrar](devices-wipe.md#wipe)
      - [Eliminar](devices-wipe.md#delete-devices-from-the-intune-portal)
      - [Bloqueo remoto](device-remote-lock.md)
      - [Sincronización](device-sync.md)
      - [Restablecer el código de acceso](device-passcode-reset.md)
      - [Reiniciar](device-restart.md) (solo para Windows)
      - [Comienzo de cero](device-fresh-start.md) (solo para Windows)
      - [Restablecimiento de Autopilot](/windows/deployment/windows-autopilot/windows-autopilot-reset#reset-devices-with-remote-windows-autopilot-reset) (solo Windows)
      - [Examen rápido](../configuration/device-restrictions-windows-10.md) (solo Windows 10)
      - [Examen completo](../configuration/device-restrictions-windows-10.md) (solo Windows 10)
      - [Actualización de la inteligencia de seguridad de Windows Defender](/windows/security/threat-protection/microsoft-defender-antivirus/manage-protection-updates-microsoft-defender-antivirus)
      - [Rotación de clave de BitLocker](../protect/encrypt-devices.md#to-rotate-the-bitlocker-recovery-key)
      - [Cambio de nombre de un dispositivo](device-rename.md)
      - [Nueva sesión de Asistencia remota](./teamviewer-support.md)
   - Use **Propiedades** para asignar una [categoría de dispositivo que cree](../enrollment/device-group-mapping.md) y cambie la propiedad del dispositivo a un dispositivo personal o a un dispositivo de empresa.
   - **Hardware** incluye muchos detalles sobre el dispositivo, como el identificador del dispositivo, el sistema operativo y la versión, el espacio de almacenamiento y más detalles.
   - **Aplicaciones detectadas**: muestra todas las aplicaciones que Intune encuentra instaladas en el dispositivo, así como las versiones de las aplicaciones. Para más información, consulte [Aplicaciones descubiertas de Intune](../apps/app-discovered-apps.md).
   - En **Conformidad de dispositivos** figuran todas las directivas de cumplimiento asignadas y se indica si el dispositivo es compatible o no.
   - En **Configuración del dispositivo** se muestran todas las directivas de configuración de dispositivos asignadas al dispositivo. También se indica si la directiva se ha aplicado correctamente o no.
   - **Configuración de aplicaciones** 
   - **Configuración de seguridad del punto de conexión**
   - En **Claves de recuperación** se muestran las claves de BitLocker disponibles para el dispositivo.
   - En **Aplicaciones administradas** se enumeran todas las aplicaciones administradas que Intune configuró y que se han implementado en el dispositivo. 

## <a name="hardware-device-details"></a>Estado del dispositivo de hardware
En función del operador que usen los dispositivos, puede que no se recopilen todos los detalles.

> [!Note]  
> El inventario de hardware y de software se actualiza cada 7 días en el servicio de Intune.

|Detalle|Descripción|Plataforma| 
|--------------|----------------------|----|  
|Nombre|Nombre del dispositivo.|Windows, iOS|
|Nombre de administración|Nombre de dispositivo usado solo en la consola. Si se cambia, el nombre del dispositivo permanece inalterado.|Windows, iOS|
|UDID|Identificador de dispositivo único del dispositivo.|Windows, iOS|
|Identificador de dispositivo de Intune|GUID que identifica el dispositivo de forma única.|Windows, iOS|
|Número de serie|Número de serie del dispositivo del fabricante.|Windows, iOS|
|Dispositivo compartido|Si se establece en **Sí**, el dispositivo se comparte con más de un usuario.|Windows, iOS|
|Inscripción de usuario aprobada|Si se establece en **Sí**, el dispositivo dispondrá de una inscripción de usuario aprobada que permite a los administradores administrar determinadas opciones de seguridad en el dispositivo.|Windows, iOS|
|Sistema operativo|Sistema operativo usado en el dispositivo.|Windows, iOS|
|Versión del sistema operativo|La versión del sistema operativo en el dispositivo.|Windows, iOS|
|Idioma del sistema operativo|Idioma configurado en el sistema operativo del dispositivo.|Windows, iOS|
|Número de compilación|Número de compilación del sistema operativo.|Android|
|Nivel de revisión de seguridad|Nivel de revisión de seguridad del dispositivo.|Android|
|Espacio de almacenamiento total|Espacio de almacenamiento total del dispositivo (en gigabytes).|Windows, iOS|
|Espacio de almacenamiento libre|Espacio de almacenamiento sin usar en el dispositivo (en gigabytes).|Windows, iOS|
|IMEI|Identidad de equipo móvil internacional del dispositivo.|Windows, iOS/iPadOS y Android|
|MEID|Identificador de equipo móvil del dispositivo.|Windows, iOS/iPadOS y Android|
|Fabricante|Fabricante del dispositivo.|Windows, iOS/iPadOS y Android|
|Modelo|Modelo del dispositivo.|Windows, iOS/iPadOS y Android|
|Número de teléfono|Número de teléfono asignado al perfil.|Windows, iOS/iPadOS y Android*|
|Operador del suscriptor|Operador de red inalámbrica del dispositivo.|Windows, iOS/iPadOS y Android|
|Tecnología de datos móviles|Sistema de radio usado en el dispositivo.|Windows, iOS/iPadOS y Android|
|MAC Wi-Fi|Dirección de Media Access Control del dispositivo.|Windows, iOS/iPadOS y Android|
|ICCID|Identificador de tarjeta de circuitos integrados, que es el número de identificación único de una tarjeta SIM.|Windows, iOS/iPadOS y Android|
|Fecha de inscripción|Fecha y hora en que el dispositivo se inscribió en Intune.|Windows, iOS/iPadOS y Android|
|Último contacto|Fecha y hora en que el dispositivo se conectó a Intune por última vez.|Windows, iOS/iPadOS y Android|
|Código de omisión del bloqueo de activación|Código que se puede usar para deshabilitar el bloqueo de activación.|iOS|
|Registrado en Azure AD|Si se establece en **Sí**, el dispositivo se registra en Azure Directory.|Windows, iOS/iPadOS y Android|
|Registrado en Intune|Si se establece en **Sí**, el dispositivo se registra en Intune.|Windows, iOS/iPadOS y Android|
|Cumplimiento|Estado de cumplimiento del dispositivo.|Windows, iOS/iPadOS y Android|
|EAS activada|Si se establece en **Sí**, el dispositivo se sincroniza con un buzón de Exchange.|Windows, iOS/iPadOS y Android|
|Id. de activación de EAS|Identificador de Exchange ActiveSync del dispositivo.|Windows, iOS/iPadOS y Android|
|Supervisado|Si se establece en **Sí**, los administradores han mejorado el control sobre el dispositivo.|Windows, iOS/iPadOS y Android|
|Cifrado|Si se establece en **Sí**, los datos almacenados en el dispositivo se cifran.|Windows, iOS/iPadOS y Android|

> [!Note]  
> El número de teléfono no forma parte del inventario de dispositivos Android Enterprise dedicados, totalmente administrados o corporativos con perfil de trabajo.

## <a name="next-steps"></a>Pasos siguientes
Vea qué más puede hacer para [administrar sus dispositivos](device-management.md) con Intune.
