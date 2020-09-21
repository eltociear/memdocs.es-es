---
title: Preparación de una aplicación Win32 para su carga en Microsoft Intune
titleSuffix: ''
description: Aprenda a preparar una aplicación Win32 para cargarse en Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94626b6cc7e9586ff6b9230206c3e57e6b01b86f
ms.sourcegitcommit: 4b8c317c71535c2d464f336c03b5bebdd2c6d4c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90083804"
---
# <a name="prepare-win32-app-content-for-upload"></a>Preparación del contenido de una aplicación Win32 para su carga

Antes de poder agregar una aplicación Win32 a Microsoft Intune, debe prepararla mediante la [herramienta de preparación de contenido de Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730).

## <a name="prerequisites"></a>Requisitos previos

Para usar la administración de aplicaciones Win32, asegúrese de cumplir los criterios siguientes:

- Use Windows 10 versión 1607 o posteriores (versiones Enterprise, Pro y Education).
- Los dispositivos deben estar unidos a Azure Active Directory (Azure AD) y haberse inscrito automáticamente. La extensión de administración de Intune admite dispositivos unidos a Azure AD, unidos a un dominio híbrido e inscritos en una directiva de grupo. 
  > [!NOTE]
  > En el escenario de inscripción en una directiva de grupo, el usuario usa la cuenta de usuario local para unir a Azure AD su dispositivo Windows 10. El usuario debe iniciar sesión en el dispositivo con su cuenta de usuario de Azure AD e inscribirse en Intune. Intune instalará la extensión de administración de Intune en el dispositivo si un script de PowerShell o una aplicación Win32 tiene como destino el usuario o dispositivo.
- El tamaño de la aplicación Windows está limitado a 8 GB por aplicación.

## <a name="convert-the-win32-app-content"></a>Conversión del contenido de las aplicaciones Win32

Use la [herramienta de preparación de contenido de Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) para procesar previamente las aplicaciones clásicas de Windows (Win32). La herramienta convierte los archivos de instalación de la aplicación al formato *.intunewin*. La herramienta también detecta algunos de los atributos que necesita Intune para determinar el estado de instalación de la aplicación. Después de usar esta herramienta en la carpeta del instalador de aplicaciones, podrá crear una aplicación Win32 en la consola de Intune.

> [!IMPORTANT]
> La [Herramienta de preparación de contenido de Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) comprime los archivos y subcarpetas cuando crea el archivo *.intunewin*. Asegúrese de guardar la Herramienta de preparación de contenido de Microsoft Win32 independientemente de los archivos y carpetas del instalador, de modo que en el archivo *.intunewin* no se incluyan la herramienta u otros archivos y carpetas innecesarios.

Puede descargar la [herramienta de preparación de contenido de Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) desde GitHub como un archivo .zip. El archivo comprimido contiene una carpeta llamada *Microsoft-Win32-Content-Prep-Tool-master*. La carpeta contiene la herramienta de preparación, la licencia, un archivo Léame y las notas de la versión. 

### <a name="process-flow-to-create-a-intunewin-file"></a>Flujo del proceso para crear un archivo .intunewin

   <img alt="Flow chart of the process to create a .intunewin file." src="./media/apps-win32-app-management/prepare-win32-app.png" width="700">

### <a name="running-the-microsoft-win32-content-prep-tool"></a>Ejecución de la herramienta de preparación de contenido de Microsoft Win32

Si ejecuta `IntuneWinAppUtil.exe` desde la ventana de comandos sin parámetros, la herramienta le ayudará a escribir los parámetros necesarios paso a paso. También se pueden agregar los parámetros para el comando basándose en los siguientes parámetros de línea de comandos disponibles.

### <a name="available-command-line-parameters"></a>Parámetros de línea de comandos disponibles 

|    **Parámetro de línea de comandos**    |    **Descripción**    |
|--------------------------------|------------------------------------------------------------|
|    `-h`     |    Ayuda    |
|    `-c <setup_folder>`     |    Carpeta para todos los archivos de instalación. Todos los archivos de esta carpeta se comprimirán en un archivo *.intunewin*.    |
|    `-s <setup_file>`     |    Archivo de instalación (como *setup.exe* o *setup.msi*).    |
|    `-o <output_folder>`     |    Carpeta de salida del archivo *.intunewin* generado.    |
|    `-q`       |    Modo silencioso.    |

### <a name="example-commands"></a>Comandos de ejemplo

|    **Comando de ejemplo**    |    **Descripción**    |
|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `IntuneWinAppUtil -h`    |    Este comando muestra información de uso de la herramienta.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Este comando generará el archivo *.intunewin* desde la carpeta de origen y el archivo de instalación especificados. En el archivo de instalación MSI, esta herramienta recupera la información necesaria para Intune. Si se especifica `-q`, el comando se ejecutará en modo silencioso. Si el archivo de salida ya existe, se sobrescribirá. Además, si la carpeta de salida no existe, se creará automáticamente.    |

Al generar un archivo *.intunewin*, coloque los archivos a los que tenga que hacer referencia en una subcarpeta de la carpeta de instalación. Después, utilice una ruta de acceso relativa para hacer referencia al archivo específico que necesita. Por ejemplo:

**Carpeta de origen de la instalación:** *c:\testapp\v1.0*<br>
**Archivo de licencia:** *c:\testapp\v1.0\licenses\license.txt*

Haga referencia al archivo *license.txt* mediante la ruta de acceso relativa *licenses\license.txt*.

## <a name="next-steps"></a>Pasos siguientes

- [Agregar aplicaciones Win32 a Microsoft Intune](apps-win32-add.md)
