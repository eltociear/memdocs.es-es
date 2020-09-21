---
title: Escenarios y funcionalidades de Windows AutoPilot
description: Siga con varios escenarios típicos de implementación de Windows AutoPilot, como volver a implementar un dispositivo en un estado listo para la empresa.
keywords: MDM, configurar, Windows, Windows 10, Oobe, administrar, implementar, AutoPilot, ZTD, cero-Touch, Partner, msfb, Intune
ms.reviewer: mniehaus
manager: laurawi
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.sitesec: library
ms.pagetype: deploy
audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: 1755399ad67cd073c71f2a26ef4305bec5a53f51
ms.sourcegitcommit: 7037d2cd6b4e3d3e75471db33f22d475dfd89f5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "90814877"
---
# <a name="windows-autopilot-scenarios-and-capabilities"></a>Escenarios y funcionalidades de Windows AutoPilot

**Se aplica a: Windows 10**

## <a name="scenarios"></a>Escenarios

Windows AutoPilot admite una lista cada vez mayor de escenarios que las organizaciones suelen necesitar. Estas necesidades varían en función de lo siguiente:
- Tipo de organización.
- Progreso al pasar a Windows 10.
- Hasta qué punto han [pasado a la administración moderna](/windows/client-management/manage-windows-10-in-your-organization-modern-management).

En esta guía se describen los siguientes escenarios de Windows AutoPilot:

| Escenario | Más información |
| --- | --- |
| Implementar y configurar dispositivos para que un usuario final pueda configurarlo por sí mismo | [Modo controlado por el usuario de Windows Autopilot](user-driven.md) |
| Implementar dispositivos para su configuración automática para uso compartido, como un quiosco, o como un dispositivo de anuncios digitales.| [Modo autoimplementado de Windows AutoPilot](self-deploying.md) |
| Volver a implementar un dispositivo en un estado listo para la empresa.| [Restablecimiento de Windows AutoPilot](windows-autopilot-reset.md) |
| Aprovisione el aprovisionamiento de un dispositivo con las aplicaciones, las directivas y la configuración actualizadas.| [Preferencial](white-glove.md) |
| Implementación de Windows 10 en un dispositivo Windows 7 o 8,1 existente | [Windows Autopilot para dispositivos existentes](existing-devices.md) |

Estos escenarios se resumen en el vídeo siguiente.

&nbsp;

> [!video https://www.microsoft.com/videoplayer/embed/RE4Ci1b?autoplay=false]

## <a name="windows-autopilot-capabilities"></a>Capacidades de Windows AutoPilot

### <a name="windows-autopilot-is-self-updating-during-oobe"></a>Windows AutoPilot se actualiza automáticamente durante OOBE

En el caso de los dispositivos Windows 10, versión 1903 y versiones posteriores, las actualizaciones funcionales y críticas del piloto automático se descargan automáticamente en OOBE después de:
- El dispositivo está conectado a una red.
- El [controlador crítico y las actualizaciones de la revisión de cero días de Windows (ZDP)](/windows-hardware/customize/desktop/windows-updates-during-oobe) se han completado.

No puede rechazar estas actualizaciones de AutoPilot porque son necesarias para la implementación de Windows AutoPilot. Windows avisa al usuario de que el dispositivo está comprobando, descargando e instalando las actualizaciones.

Para obtener más información, consulte [actualización de Windows AutoPilot](autopilot-update.md).

### <a name="cortana-voiceover-and-speech-recognition-during-oobe"></a>Reconocimiento de voz y VoiceOver de Cortana durante OOBE

En Windows 10, versión 1903 y posteriores, Cortana VoiceOver y reconocimiento de voz durante OOBE está deshabilitado de forma predeterminada. Este valor predeterminado se aplica a todas las SKU de Windows 10 Pro, Education y Enterprise.

También puede habilitar el reconocimiento de voz y VoiceOver de Cortana durante OOBE mediante la creación de la siguiente clave del registro. Esta clave no existe de forma predeterminada:

HKLM\Software\Microsoft\Windows\CurrentVersion\OOBE\EnableVoiceForAllEditions

El valor de clave es un DWORD con **0** = deshabilitado y **1** = habilitado.

| Value | Descripción |
| --- | --- |
| 0 | La VoiceOver de Cortana está deshabilitada |
| 1 | La VoiceOver de Cortana está habilitada |
| No hay ningún valor | El dispositivo revertirá al comportamiento predeterminado de la edición |

Para cambiar este valor de clave, utilice la herramienta WCD para crear como PPKG como se documenta [aquí](/windows/configuration/wcd/wcd-oobe#nforce).

### <a name="bitlocker-encryption"></a>Cifrado de BitLocker

Con Windows AutoPilot, puede configurar las opciones de cifrado de BitLocker que se aplicarán antes de que se inicie el cifrado automático. Para obtener más información, vea [establecer el algoritmo de cifrado de BitLocker para dispositivos AutoPilot](bitlocker.md) .

## <a name="related-topics"></a>Temas relacionados

[Windows AutoPilot: novedades](windows-autopilot-whats-new.md)