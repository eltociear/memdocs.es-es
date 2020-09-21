---
title: Solución de problemas de aplicaciones Win32 en Microsoft Intune
titleSuffix: ''
description: Conozca los métodos más comunes para solucionar los problemas de aplicaciones Win32 con Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bbdc929f5d3a9703f3d299b8e3a68dd624c450c2
ms.sourcegitcommit: 4b8c317c71535c2d464f336c03b5bebdd2c6d4c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90083920"
---
# <a name="troubleshoot-win32-app-issues"></a>Solucionar los problemas de aplicaciones Win32

Para solucionar problemas de las aplicaciones Win32 que se usan en Microsoft Intune, puede emplear varios métodos. En este artículo se proporcionan detalles e información de solución de problemas para ayudarle a resolver los problemas de las aplicaciones Win32. Para más información, consulte los recursos de [Solución de problemas de instalación de aplicaciones Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

> [!NOTE]
> Esta funcionalidad de administración de aplicaciones admite aplicaciones Windows con arquitecturas de sistemas operativos de 32 y 64 bits.

> [!IMPORTANT]
> Al implementar aplicaciones Win32, considere la posibilidad de usar el enfoque de la [extensión de administración de Intune](../apps/intune-management-extension.md) de forma exclusiva, especialmente cuando tenga un instalador de aplicaciones Win32 de varios archivos. Si mezcla la instalación de aplicaciones Win32 y de aplicaciones de línea de negocio durante la inscripción de AutoPilot, puede producirse un error en la operación. Se instalará la extensión de administración de Intune automáticamente cuando se asigne un script de PowerShell o una aplicación Win32 al usuario o al dispositivo.

## <a name="app-troubleshooting-details"></a>Detalles de solución de problemas de aplicaciones

Puede ver problemas de instalación, por ejemplo, al crearse, modificarse, dirigirse y entregarse la aplicación a un dispositivo. El [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) proporciona estos y otros detalles en el panel **Solución de problemas y soporte técnico**. Para más información, consulte [Detalles de solución de problemas de aplicaciones](troubleshoot-app-install.md#app-troubleshooting-details).

## <a name="troubleshooting-app-issues-by-using-logs"></a>Solución de problemas de aplicaciones mediante registros

La visualización de los detalles de los registros puede ayudarle a determinar la causa de los problemas y resolverlos. Puede elegir ver los [registros mostrados en Intune](apps-win32-troubleshoot.md#logs-displayed-in-intune) o los [registros mostrados mediante CMTrace](apps-win32-troubleshoot.md#logs-displayed-through-cmtrace). 

### <a name="logs-displayed-in-intune"></a>Registros mostrados en Intune

Cuando se produce un problema de instalación con una aplicación Win32, puede elegir la opción **Recopilar registros** en el panel **Detalles de la instalación** de la aplicación en Intune. Para más información, consulte [Solución de problemas de instalación de aplicaciones Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

### <a name="logs-displayed-through-cmtrace"></a>Registros mostrados mediante CMTrace

Los registros del agente de la máquina cliente suelen encontrarse en *C:\ProgramData\Microsoft\IntuneManagementExtension\Logs*. Puede usar *CMTrace.exe* para ver estos archivos de registro. Para obtener más información, vea [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace).

![Captura de pantalla de los registros del agente en la máquina cliente](./media/apps-win32-app-management/apps-win32-app-10.png)

> [!IMPORTANT]
> Para permitir la correcta instalación y ejecución de aplicaciones Win32 de línea de negocio, la configuración antimalware debe excluir los directorios siguientes del examen:<p>
> **En máquinas cliente x64**:<br>
> *C:\Archivos de programa (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **En máquinas cliente x86**:<br>
> *C:\Archivos de programa\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>
> Para más información, consulte [Recomendaciones para la detección de virus en equipos de empresa que ejecutan actualmente versiones compatibles de Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers).

## <a name="detecting-the-win32-app-file-version-by-using-powershell"></a>Detección de la versión del archivo de la aplicación Win32 mediante PowerShell

Si tiene problemas para detectar la versión del archivo de la aplicación Win32, considere la posibilidad de usar o modificar el siguiente comando de PowerShell:

``` PowerShell

$FileVersion = [System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion
#The below line trims the spaces before and after the version name
$FileVersion = $FileVersion.Trim();
if ("<file version of successfully detected file>" -eq $FileVersion)
{
#Write the version to STDOUT by default
$FileVersion
exit 0
}
else
{
#Exit with non-zero failure code
exit 1
}
```

En el comando de PowerShell anterior, reemplace la cadena `<path to binary file>` por la ruta de acceso al archivo de la aplicación Win32. Una ruta de acceso de ejemplo sería similar a la siguiente:

`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Además, reemplace la cadena `<file version of successfully detected file>` por la versión del archivo que deba detectar. Una cadena de ejemplo de la versión de archivo sería similar a la siguiente:

`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Si necesita obtener la información de versión de la aplicación Win32, puede usar el siguiente comando de PowerShell:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

En el comando de PowerShell anterior, reemplace `<path to binary file>` por la ruta de acceso del archivo.

## <a name="additional-troubleshooting-areas-to-consider"></a>Otras áreas de la solución de problemas para tener en cuenta
- Compruebe el destino para asegurarse de que el agente está instalado en el dispositivo. Una aplicación Win32 que tenga como destino un grupo o un script de PowerShell dirigido a un grupo crearán una directiva de instalación del agente para un grupo de seguridad.
- Compruebe la versión del sistema operativo: Windows 10 1607 y versiones posteriores.  
- Compruebe la SKU de Windows 10. Windows 10 S o las versiones de Windows que se ejecutan con el modo S habilitado no admiten la instalación de MSI.

Para obtener más información sobre la solución de problemas de aplicaciones Win32, consulte [Win32 app installation troubleshooting](troubleshoot-app-install.md#win32-app-installation-troubleshooting) (Solución de problemas de instalación de aplicaciones Win32). Para obtener información acerca de los tipos de aplicaciones en dispositivos ARM64, consulte el artículo sobre los [tipos de aplicación admitidos en dispositivos ARM64](../apps/troubleshoot-app-install.md#app-types-supported-on-arm64-devices).

## <a name="next-steps"></a>Pasos siguientes

- [Solucionar problemas de instalación de aplicaciones](troubleshoot-app-install.md)
