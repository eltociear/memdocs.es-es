---
title: 'Adición de scripts de PowerShell para dispositivos Windows 10 en Microsoft Intune: Azure | Microsoft Docs'
description: Cree y ejecute scripts de PowerShell, asigne la directiva de script a grupos de Active Directory de Azure, use informes para supervisar los scripts y vea los pasos para eliminar scripts que se agregan en dispositivos Windows 10 en Microsoft Intune. Vea también algunos problemas comunes y sus soluciones.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/06/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f4080c5cfcc6635478bd88b7d9edf42dd3d8576
ms.sourcegitcommit: d1bfd5b8481439babc7eae43493f28edaebe647a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "88179492"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Uso de scripts de PowerShell para dispositivos Windows 10 en Intune

Use la extensión de administración de Microsoft Intune para cargar los scripts de PowerShell en Intune y ejecutarlos en dispositivos Windows 10. La extensión de administración mejora la administración de dispositivos móviles (MDM) de Windows y facilita el paso a una administración moderna.

Esta característica se aplica a:

- Windows 10 y versiones posteriores (excepto Windows 10 Home)

> [!NOTE]
> Una vez que se hayan cumplido los requisitos previos de la extensión de administración de Intune, se instala la extensión de administración de Intune automáticamente cuando se asigne un script de PowerShell o una aplicación Win32 al usuario o al dispositivo. Para más información, vea los [requisitos previos](../apps/intune-management-extension.md#prerequisites) de las extensiones de administración de Intune.

## <a name="move-to-modern-management"></a>Transición hacia una administración moderna

La informática de usuario final está experimentando una transformación digital. La TI clásica y tradicional se centra en una plataforma de dispositivo único, en dispositivos propiedad de la empresa, en usuarios que trabajan desde la oficina y en distintos procesos de TI manuales y proactivos. En el área de trabajo moderno se usan muchas plataformas que son propiedad del usuario o la empresa, permite a los usuarios trabajar desde cualquier lugar y proporciona procesos de TI automatizados y proactivos.

Los servicios MDM, como Microsoft Intune, pueden administrar dispositivos móviles y de escritorio que ejecutan Windows 10. El cliente de administración integrado de Windows 10 se comunica con Intune para realizar tareas de administración empresariales. Hay algunas tareas que puede necesitar, como configuración avanzada de dispositivos y solución de problemas. Para la administración de aplicaciones Win32, puede usar la característica de [administración de aplicaciones Win32](app-management.md) en sus dispositivos Windows 10.

La extensión de administración de Intune complementa las características de administración de dispositivos móviles (MDM) que Windows 10 incluye de fábrica. Puede crear scripts de PowerShell para ejecutar en dispositivos Windows 10. Por ejemplo, cree un script de PowerShell que realice configuraciones avanzadas del dispositivo. Después, cargue el script en Intune, asígnelo a un grupo de Azure Active Directory (AAD) y ejecútelo. Luego, puede supervisar de principio a fin el estado de ejecución del script.

## <a name="prerequisites"></a>Requisitos previos

La extensión de administración de Intune tiene los siguientes requisitos previos. Una vez que se hayan cumplido, se instala la extensión de administración de Intune automáticamente cuando se asigne un script de PowerShell o una aplicación Win32 al usuario o al dispositivo.

- Dispositivos que ejecutan Windows 10 versión 1607 o una posterior. Si el dispositivo se inscribe mediante la [inscripción automática masiva](../enrollment/windows-bulk-enroll.md), los dispositivos deben ejecutar Windows 10, versión 1709 o posteriores. La extensión de administración de Intune no se admite en Windows 10 en modo S, ya que este no permite la ejecución de aplicaciones de fuera de la tienda. 
  
- Dispositivos unidos a Azure Active Directory (AD), incluidos los siguientes:  
  
  - Unidos a Azure AD híbrido: dispositivos unidos a Azure Active Directory (AD) y que también están unidos a Active Directory (AD) local. Vea [Planeamiento de la implementación de la unión a Azure Active Directory híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) para obtener instrucciones.
  
  > [!TIP]
  > Asegúrese de que los dispositivos estén [unidos](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) a Azure AD. Los dispositivos que solo están [registrados](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) en Azure AD no recibirán los scripts.  

- Dispositivos inscritos en Intune, incluidos los siguientes:

  - Dispositivos inscritos en una directiva de grupo (GPO). Vea [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) (Inscripción automática de un dispositivo Windows 10 con Directiva de grupo) para obtener instrucciones.
  
  - Dispositivos inscritos manualmente en Intune, que son los que encajan con una de las siguientes descripciones:
  
    - La opción [Auto-enrollment to Intune](../enrollment/quickstart-setup-auto-enrollment.md) (Inscripción automática en Intune) está habilitada en Azure AD. El usuario final inicia sesión en el dispositivo mediante una cuenta de usuario local, une manualmente el dispositivo a Azure AD y, luego, inicia sesión en el dispositivo con su cuenta de Azure AD.
    
    O BIEN  
    
    - El usuario inicia sesión en el dispositivo con su cuenta de Azure AD y, posteriormente, se inscribe en Intune.

  - Dispositivos administrados conjuntamente que usan Configuration Manager e Intune. Al instalar las aplicaciones Win32, asegúrese de que la carga de trabajo **Aplicaciones** esté establecida en **Intune piloto** o **Intune**. Los scripts de PowerShell se ejecutarán incluso si la carga de trabajo de **Aplicaciones** está establecida en **Configuration Manager**. La extensión de administración de Intune se implementará en un dispositivo cuando el destino sea un script de PowerShell en el dispositivo. Sin embargo, como se indicó anteriormente, el dispositivo debe ser un dispositivo Azure AD o un dispositivo unido a Azure AD híbrido y debe ejecutar Windows 10 versión 1607 o posterior. Consulte los artículos siguientes para obtener instrucciones: 
  
    - [¿Qué es la administración conjunta?](https://docs.microsoft.com/configmgr/comanage/overview) 
    - [Carga de trabajo de aplicaciones cliente](https://docs.microsoft.com/configmgr/comanage/workloads#client-apps)
    - [Cambio de las cargas de trabajo de Configuration Manager a Intune](https://docs.microsoft.com/configmgr/comanage/how-to-switch-workloads)
  
> [!NOTE]
> Para obtener información sobre el uso de máquinas virtuales Windows 10, vea [Uso de máquinas virtuales Windows 10 con Intune](../fundamentals/windows-10-virtual-machines.md).

## <a name="create-a-script-policy-and-assign-it"></a>Creación y asignación de una directiva de script

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Scripts de PowerShell** > **Agregar**.

    ![Adición y uso de scripts de PowerShell en Microsoft Intune](./media/intune-management-extension/mgmt-extension-add-script.png)

3. En **Datos básicos**, escriba las propiedades siguientes y seleccione **Siguiente**:
    - **Nombre**: Escriba un nombre para el script de PowerShell. 
    - **Descripción**: Escriba una descripción para el script de PowerShell. Esta configuración es opcional pero recomendada.
4. En **Configuración de script**, escriba las propiedades siguientes y seleccione **Siguiente**:
    - **Ubicación del script**: Vaya al script de PowerShell. El script debe ser inferior a 200 KB (ASCII).
    - **Ejecutar este script con las credenciales de inicio de sesión**: Seleccione **Sí** para ejecutar el script con las credenciales del usuario en el dispositivo. Elija **No** (valor predeterminado) para ejecutar el script en el contexto del sistema. Muchos administradores eligen **Sí**. Si es necesario que el script se ejecute en el contexto del sistema, elija **No**.
    - **Exigir comprobación de firma del script**: Elija **Sí** en caso de que el script lo deba firmar un editor de confianza. Seleccione **No** (valor predeterminado) si no es necesario que el script esté firmado. 
    - **Ejecutar script en host de PowerShell de 64 bits**: Seleccione **Sí** para ejecutar el script en un host de PowerShell (PS) de 64 bits en una arquitectura de cliente de 64 bits. Si selecciona **No** (valor predeterminado) el script se ejecutará en un host de PowerShell de 32 bits.

      Cuando la establezca en **Sí** o **No**, use la tabla siguiente para los comportamientos de la directiva nuevos y existentes:

      | Ejecución de script en host de PS de 64 bits | Arquitectura de cliente | Nuevo script de PS | Script de PS de directiva existente |
      | --- | --- | --- | --- | 
      | No | 32 bits  | Host de PS de 32 bits compatible | Se ejecuta solo en host de PS de 32 bits, que funciona en arquitecturas de 32 y 64 bits. |
      | Sí | 64 bits | Se ejecuta el script en un host de PS de 64 bits para arquitecturas de 64 bits. Si se ejecuta en 32 bits, el script se ejecutará en un host de PS de 32 bits. | Se ejecuta el script en un host de PS de 32 bits. Si esta configuración cambia a 64 bits, el script se abrirá (no se ejecutará) en un host de PS de 64 bits y se notificarán los resultados. Si se ejecuta en 32 bits, el script se ejecutará en un host de PS de 32 bits. |

5. Seleccione **Etiquetas de ámbito**. Las etiquetas de ámbito son opcionales. En la sección [Uso de control de acceso basado en rol (RBAC) y etiquetas de ámbito para TI distribuida](../fundamentals/scope-tags.md) encontrará más información.

    Para agregar una etiqueta de ámbito, realice lo siguiente:

    1. Elija **Seleccionar etiquetas de ámbito** > seleccione una etiqueta de ámbito existente en la lista > **Seleccionar**.

    2. Cuando termine, seleccione **Siguiente**.

6. Seleccione **Asignaciones** > **Seleccionar grupos para incluir**. Se muestra una lista existente de grupos de Azure AD.

    1. Seleccione uno o varios grupos que incluyan los usuarios cuyos dispositivos reciben el script. Elija **Seleccionar**. Los grupos que ha elegido se muestran en la lista y recibirán la directiva.

        > [!NOTE]
        > Los scripts de PowerShell en Intune pueden estar dirigidos a grupos de seguridad de dispositivos de Azure AD ni a grupo de seguridad de usuarios de Azure AD.

    2. Seleccione **Siguiente**.

        ![Asignación o implementación del script de PowerShell para grupos de dispositivos en Microsoft Intune](./media/intune-management-extension/mgmt-extension-assignments.png)

7. En **Revisar y agregar**, se muestra un resumen de la configuración. Seleccione **Agregar** para guardar el script. Al seleccionar **Agregar**, la directiva se implementa en los grupos elegidos.

## <a name="important-considerations"></a>Consideraciones importantes

- Cuando los scripts están establecidos en el contexto del usuario y el usuario final tiene derechos de administración, de manera predeterminada, el script de PowerShell se ejecuta bajo el privilegio de administrador.

- No es necesario que los usuarios finales inicien sesión en el dispositivo para ejecutar scripts de PowerShell.

- El agente de extensión de administración de Intune comprueba con Intune nuevos scripts o cambios una vez cada hora y tras cada reinicio. Después de asignar la directiva a los grupos de Azure AD, se ejecuta el script de PowerShell y se notifican los resultados de la ejecución. Una vez que se ejecuta el script, no se ejecuta de nuevo a menos que haya un cambio en el script o en la directiva. Si se produce un error en el script, el agente de extensión de administración de Intune intentará aplicar el script de nuevo tres veces durante las tres siguientes sincronizaciones consecutivas del agente de extensión de administración de Intune.

- En el caso de los dispositivos compartidos, el script de PowerShell se ejecutará para cada usuario nuevo que inicie sesión.

### <a name="failure-to-run-script-example"></a>Ejemplo de error al ejecutar el script
8 a.m.
  -  Sincronización
  -  Ejecución del script **ConfigScript01**
  -  Error de script

9 a.m.
  -  Sincronización
  -  Ejecución del script **ConfigScript01**
  -  Error de script (número de reintentos = 1)

10 a.m.
  -  Sincronización
  -  Ejecución del script **ConfigScript01**
  -  Error de script (número de reintentos = 2)
  
11 a.m.
  -  Sincronización
  -  Ejecución del script **ConfigScript01**
  -  Error de script (número de reintentos = 3)

12 p.m.
  -  Sincronización
  - No se realizan más intentos de ejecutar el script **ConfigScript01**.
  - En el futuro, si no se realizan cambios adicionales en el script, no se realizará ningún intento adicional para ejecutar el script.


## <a name="monitor-run-status"></a>Supervisión del estado de ejecución

Puede supervisar el estado de ejecución de scripts de PowerShell para usuarios y dispositivos en Azure Portal.

En **Scripts de PowerShell**, seleccione el script que quiere supervisar y, después, elija **Supervisar** y uno de estos informes:

- **Estado del dispositivo**
- **Estado del usuario**

## <a name="intune-management-extension-logs"></a>Registros de extensión de administración de Intune

Habitualmente, los registros de agente en la máquina cliente se encuentran en `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Puede usar [CMTrace.exe](https://docs.microsoft.com/configmgr/core/support/cmtrace) para ver estos archivos de registro.

![Captura de pantalla o registros de agente de CMTrace de muestra en Microsoft Intune](./media/apps-win32-app-management/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Eliminación de un script

En **Scripts de PowerShell**, haga clic con el botón derecho en el script y seleccione **Eliminar**.

## <a name="common-issues-and-resolutions"></a>Problemas comunes y sus soluciones

### <a name="issue-intune-management-extension-doesnt-download"></a>Problema: La extensión de administración de Intune no se descarga

**Soluciones posibles**:

- El dispositivo no está unido a Azure AD. Asegúrese de que los dispositivos cumplen con los [requisitos previos](#prerequisites) (en este artículo). 
- No hay ningún script de PowerShell ni ninguna aplicación Win32 asignados a los grupos a los que pertenece el usuario o el dispositivo.
- El dispositivo no puede ponerse en contacto con el servicio de Intune, bien porque no dispone de acceso a Internet o a Windows Push Notification Services (WNS), bien por un motivo similar.
- El dispositivo está en modo S. La extensión de administración de Intune no se admite en dispositivos que se ejecutan en modo S. 

Para ver si el dispositivo se ha inscrito automáticamente, puede hacer lo siguiente:

  1. Vaya a **Configuración** > **Cuentas** > **Obtener acceso a trabajo o escuela**.
  2. Seleccione la cuenta combinada > **Información**.
  3. En **Advanced Diagnostic Report** (Informe de diagnóstico avanzado), seleccione **Crear informe**.
  4. Abra `MDMDiagReport` en un explorador web.
  5. Busque la propiedad **MDMDeviceWithAAD**. Si la propiedad existe, el dispositivo se ha inscrito automáticamente. Si esta propiedad no existe, el dispositivo no se ha inscrito automáticamente.

En [Habilitar la inscripción automática de Windows 10](../enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) se describen los pasos para configurar la inscripción automática en Intune.

### <a name="issue-powershell-scripts-do-not-run"></a>Problema: Los scripts de PowerShell no se ejecutan.

**Soluciones posibles**:

- Los scripts de PowerShell no se ejecutan en cada inicio de sesión. Se ejecuta en los siguientes casos:

  - Cuando se asigna el script a un dispositivo.
  - Si cambia el script, lo carga y asigna el script a un usuario o dispositivo.
  
    > [!TIP]
    > La **extensión de administración de Microsoft Intune** es un servicio que se ejecuta en el dispositivo, al igual que cualquier otro servicio que aparezca en la aplicación Servicios (services.msc). Después de reiniciar un dispositivo, es posible que el servicio también lo haga y compruebe si hay algún script de PowerShell asignado con el servicio de Intune. Si el servicio de **extensión de administración de Microsoft Intune** está establecido en Manual, es posible que el servicio no se reinicie después del reinicio del dispositivo.

- Asegúrese de que los dispositivos estén [unidos a Azure AD](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Los dispositivos que solo están unidos al área de trabajo o a la organización ([registrados](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) en Azure AD) no recibirán los scripts.
- El cliente de la extensión de administración de Intune comprueba con Intune cada hora si se han producido cambios en el script o la directiva.
- Confirme que la extensión de administración de Intune se ha descargado en `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Los scripts no se ejecutan en dispositivos Surface Hub ni con Windows 10 en modo S.
- Mire si hay errores en los registros. Consulte, en este artículo, [Registros de extensión de administración de Intune](#intune-management-extension-logs).
- Para comprobar si existen problemas de permisos, asegúrese de que las propiedades del script de PowerShell estén establecidas en `Run this script using the logged on credentials`. Compruebe también que el usuario que ha iniciado sesión tenga los permisos adecuados para ejecutar el script.

- Para aislar los problemas de scripts, haga lo siguiente:

  - Revise la configuración de ejecución de PowerShell de los dispositivos. Vea la [directiva de ejecución de PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) para obtener instrucciones.
  - Ejecute un script de ejemplo con la extensión de administración de Intune. Por ejemplo, cree el directorio `C:\Scripts` y proporcione a todos control total. Ejecute el siguiente script:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Si se ejecuta correctamente, se creará un archivo output.txt e incluirá el texto "Script Worked" (El script funcionó).

  - Para probar la ejecución del script sin Intune, ejecute los scripts en la cuenta del sistema mediante el uso local de la [herramienta psexec](https://docs.microsoft.com/sysinternals/downloads/psexec):

    `psexec -i -s`  
    
  - Si el script informa de que se ha realizado correctamente, pero no ha sido así en realidad, es posible que el servicio antivirus se encuentre en un espacio aislado por AgentExecutor. El siguiente script siempre informa de un error en Intune. Como prueba, puede usar este script:
  
    ```powershell
    Write-Error -Message "Forced Fail" -Category OperationStopped
    mkdir "c:\temp" 
    echo "Forced Fail" | out-file c:\temp\Fail.txt
    ```

    Si el script informa de que se ha realizado correctamente, consulte `AgentExecutor.log` para confirmar la salida de error. Si se ejecuta el script, la longitud debe ser > 2.

  - Para capturar los archivos .error y .output, el fragmento de código siguiente ejecuta el script a través de AgentExecutor en PSx86 (`C:\Windows\SysWOW64\WindowsPowerShell\v1.0`). Mantiene los registros para su revisión. Recuerde que la extensión de administración de Intune limpia los registros después de que se ejecute el script:
  
    ```powershell
    $scriptPath = read-host "Enter the path to the script file to execute"
    $logFolder = read-host "Enter the path to a folder to output the logs to"
    $outputPath = $logFolder+"\output.output"
    $errorPath =  $logFolder+"\error.error"
    $timeoutPath =  $logFolder+"\timeout.timeout"
    $timeoutVal = 60000 
    $PSFolder = "C:\Windows\SysWOW64\WindowsPowerShell\v1.0"
    $AgentExec = "C:\Program Files (x86)\Microsoft Intune Management Extension\agentexecutor.exe"
    &$AgentExec -powershell  $scriptPath $outputPath $errorPath $timeoutPath $timeoutVal $PSFolder 0 0
    ```

## <a name="next-steps"></a>Pasos siguientes

[Supervise](../configuration/device-profile-monitor.md) y [solucione los problemas](../configuration/device-profile-troubleshoot.md) de sus perfiles.
