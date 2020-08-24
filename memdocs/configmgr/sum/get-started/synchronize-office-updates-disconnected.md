---
title: Sincronización de actualizaciones de Aplicaciones de Microsoft 365 sin conexión a Internet
titleSuffix: Configuration Manager
description: Sincronice las actualizaciones de Aplicaciones de Microsoft 365 en el punto de actualización de software de nivel superior que está desconectado de Internet.
ms.date: 08/11/2020
ms.topic: conceptual
ms.prod: configuration-manager
ms.technology: configmgr-sum
ms.assetid: a8fa7e7a-bf55-42de-b0c2-c56777dc1508
manager: dougeby
author: mestew
ms.author: mstewart
ms.openlocfilehash: 49e0f5e1dff466e62cdba0def917dd34510e48ee
ms.sourcegitcommit: 99084d70c032c4db109328a4ca100cd3f5759433
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88696776"
---
# <a name="synchronize-microsoft-365-apps-updates-from-a-disconnected-software-update-point"></a><a name="bkmk_O365"></a> Sincronización de actualizaciones de Aplicaciones de Microsoft 365 desde un punto de actualización de software desconectado

*Se aplica a: Configuration Manager (rama actual)*
<!--4065163-->
A partir de la versión 2002 de Configuration Manager, puede usar una nueva herramienta para importar actualizaciones de Aplicaciones de Microsoft 365 desde un servidor de WSUS conectado a Internet en un entorno de Configuration Manager desconectado. Anteriormente, cuando exportaba e importaba metadatos de software actualizado en entornos desconectados, no podía implementar actualizaciones de Aplicaciones de Microsoft 365. Las actualizaciones de Aplicaciones de Microsoft 365 requieren la descarga de metadatos adicionales de una API de Office y la red CDN de Office, lo cual no es posible en entornos desconectados.

> [!Note]
> A partir del 21 de abril de 2020, el nombre de Office 365 ProPlus cambia a **Aplicaciones de Microsoft 365 para empresas**. Para obtener más información, vea [Cambio de nombre para Office 365 ProPlus](/deployoffice/name-change). Es posible que siga viendo referencias al nombre anterior en la consola de Configuration Manager y la documentación complementaria mientras se está actualizando la consola.

## <a name="prerequisites"></a>Requisitos previos

- Un servidor WSUS conectado a Internet que ejecute al menos Windows Server 2012.
- El servidor WSUS necesita conectividad para estos dos puntos de conexión de Internet:
   - `officecdn.microsoft.com`
   - `config.office.com`
- Copie la herramienta OfflineUpdateExporter y sus dependencias en el servidor WSUS conectado a Internet.
  - La herramienta y sus dependencias se encuentran en el directorio **&lt;ConfigMgrInstallDir>/tools/OfflineUpdateExporter**.
- El usuario que ejecuta la herramienta debe formar parte del grupo **administradores de WSUS**.
- El directorio creado para almacenar los metadatos y el contenido de las actualizaciones de Aplicaciones de Microsoft 365 debe tener listas de control de acceso (ACL) adecuadas para proteger los archivos.
    - Este directorio también debe estar vacío.
- Los datos que se trasladan desde el servidor WSUS en línea al entorno desconectado deben moverse de forma segura.

> [!IMPORTANT]
> El contenido se descargará en todos los idiomas de Aplicaciones de Microsoft 365. Cada actualización puede tener aproximadamente 10 GB de contenido.

## <a name="synchronize-then-decline-unneeded-microsoft-365-apps-updates"></a>Sincronización y rechazo posterior de las actualizaciones de Aplicaciones de Microsoft 365 innecesarias

1. En WSUS conectado a Internet, abra la consola de WSUS.
1. Seleccione **Opciones** y luego **Productos y clasificaciones**.
1. En la pestaña **Productos**, seleccione **Cliente de Office 365** y seleccione **Actualizaciones** en la pestaña **Clasificaciones**. [![Productos y clasificaciones de actualizaciones de Aplicaciones de Microsoft 365 en WSUS](./media/4065163-o365-updates-product-classification.png)](./media/4065163-o365-updates-product-classification.png#lightbox)
1. Vaya a **Sincronizaciones** y seleccione **Sincronizar ahora** para obtener las actualizaciones de Aplicaciones de Microsoft 365 en WSUS.
1. Una vez finalizada la sincronización, rechace cualquier actualización de Aplicaciones de Microsoft 365 que no desee implementar con Configuration Manager. No es necesario aprobar las actualizaciones de Aplicaciones de Microsoft 365 para poder descargarlas.  
   - El rechazo de las actualizaciones de Aplicaciones de Microsoft 365 no deseadas en WSUS no impide que se exporten durante una exportación de WsusUtil.exe, pero sí impide que la herramienta OfflineUpdateExporter descargue su contenido.
   - La herramienta OfflineUpdateExporter realiza la descarga de las actualizaciones de Aplicaciones de Microsoft 365 automáticamente. Se deberá seguir aprobando la descarga de otros productos si se exportan actualizaciones para ellos.
    - Cree una [vista de actualización en WSUS](/windows-server/administration/windows-server-update-services/manage/viewing-and-managing-updates#to-create-a-new-update-view-on-wsus) para ver y rechazar fácilmente las actualizaciones innecesarias de Aplicaciones de Microsoft 365.
1. Si va a aprobar otras actualizaciones de productos para su descarga y exportación, espere a que se complete la descarga de contenido antes de ejecutar WsusUtil.exe y copiar el contenido de la carpeta WSUSContent. Para obtener más información, consulte [Sincronizar actualizaciones de software desde un punto de actualización de software desconectado](synchronize-software-updates-disconnected.md).

## <a name="exporting-the-microsoft-365-apps-updates"></a>Exportación de las actualizaciones de Aplicaciones de Microsoft 365

1. Copie la carpeta OfflineUpdateExporter de Configuration Manager en el servidor WSUS conectado a Internet.
    - La herramienta y sus dependencias se encuentran en el directorio **&lt;ConfigMgrInstallDir>/tools/OfflineUpdateExporter**.
1. Desde un símbolo del sistema en el servidor WSUS conectado a Internet, ejecute la herramienta con el siguiente uso: **OfflineUpdateExporter.exe -O -D &lt;ruta de acceso de destino>**

   |Parámetro OfflineUpdateExporter|Descripción|
   |---|---|
   |**-O**|  **-Office**. Especifica que el producto para la exportación de actualizaciones es Office 365 o Aplicaciones de Microsoft 365.|
   |**-D**|**-Destination**. Destination es un parámetro necesario y se necesita la ruta de acceso completa a la carpeta de destino.|

   - La herramienta **OfflineUpdateExporter** hace lo siguiente:
      - Se conecta a WSUS.
      - Lee los metadatos de actualización de Aplicaciones de Microsoft 365 en WSUS.
      - Descarga el contenido y los metadatos adicionales que necesiten las actualizaciones de Aplicaciones de Microsoft 365 en la carpeta de destino.

1. En el símbolo del sistema del servidor WSUS conectado a Internet, vaya a la carpeta que contiene WsusUtil.exe. De forma predeterminada, la herramienta se encuentra en %*ProgramFiles*%\Update Services\Tools. Por ejemplo, si la herramienta se encuentra en la ubicación predeterminada, escriba **cd %ProgramFiles%\Update Services\Tools**.
   - Si usa Windows Server 2012, asegúrese de que la actualización [KB 2819484](https://support.microsoft.com/help/2819484/cab-file-that-is-exported-by-using-the-wsusutil-exe-command-is-display) está instalada en los servidores WSUS.
   - El usuario que ejecuta la herramienta WsusUtil debe ser miembro del grupo de administradores local en el servidor.

1. Escriba lo siguiente para exportar los metadatos de las actualizaciones de software a un archivo GZIP:  

    **WsusUtil.exe export**  *packagename*  *logfile*  

    Por ejemplo:  

    **WsusUtil.exe export export.xml.gz export.log**

1. Copie el archivo **Export. Xml. gz** en el servidor WSUS de nivel superior de la red desconectada.
1. Si ha aprobado actualizaciones para otros productos, copie el contenido de la carpeta WSUSContent en la carpeta WSUSContent del servidor WSUS desconectado de nivel superior.
1. Copie la carpeta de destino utilizada para **OfflineUpdateExporter** en el servidor de sitio de Configuration Manager de nivel superior en la red desconectada.

## <a name="import-the-microsoft-365-apps-updates"></a>Importación de las actualizaciones de Aplicaciones de Microsoft 365

1. En el servidor WSUS desconectado de nivel superior, importe los metadatos de actualización desde el archivo **export.xml.gz** generado en el servidor WSUS conectado a Internet.
   
    Por ejemplo:  

    **WsusUtil.exe import export.xml.gz import.log**
    
    De forma predeterminada, la herramienta WsusUtil.exe se encuentra en %*ProgramFiles*%\Update Services\Tools.

1. Una vez completada la importación, deberá configurar una propiedad de control de sitio en el servidor de sitio de Configuration Manager de nivel superior desconectado. Este cambio de configuración hace que Configuration Manager apunte al contenido de Aplicaciones de Microsoft 365. Para cambiar la configuración de la propiedad:
   1. Copie el [script de PowerShell de O365OflBaseUrlConfigured](#bkmk_o365_script) en el servidor de sitio de Configuration Manager de nivel superior desconectado.
   1. Cambie `"D:\Office365updates\content"` por la ruta de acceso completa del directorio copiado que contiene el contenido y los metadatos de Aplicaciones de Microsoft 365 generados por OfflineUpdateExporter.
      > [!IMPORTANT]
      > Solo las rutas de acceso locales funcionan para la propiedad O365OflBaseUrlConfigured.
   1. Guarde el script como `O365OflBaseUrlConfigured.ps1`
   1. En una ventana de PowerShell con privilegios elevados en el servidor de sitio de Configuration Manager de nivel superior desconectado, ejecute `.\O365OflBaseUrlConfigured.ps1`.
   1. Reinicie el servicio **SMS_Executive** en el servidor de sitio.
1. En la consola de **Configuration Manager**, vaya a **Administración** > **Configuración del sitio** > **Sitios**.
1. Haga clic con el botón derecho en el sitio de nivel superior, seleccione **Configurar componentes de sitio** > **Punto de actualización de software**.
1. En la pestaña **Clasificaciones**, seleccione *Actualizaciones*. En la pestaña **Productos**, seleccione *Cliente de Office 365*.
1. [Sincronice las actualizaciones de software](synchronize-software-updates.md#manually-start-software-updates-synchronization) para Configuration Manager.
1. Cuando finalice la sincronización, use el proceso normal para implementar las actualizaciones de Aplicaciones de Microsoft 365.

## <a name="proxy-configuration"></a><a name="bkmk_O365_ki"></a> Configuración del proxy

- La configuración del proxy no se integra de forma nativa en la herramienta. Si el proxy se establece en las opciones de Internet en el servidor en el que se ejecuta la herramienta, en teoría se usará y debería funcionar correctamente.
   - En un símbolo del sistema, ejecute `netsh winhttp show proxy` para ver el proxy configurado.



## <a name="modify-o365oflbaseurlconfigured-property"></a><a name="bkmk_o365_script"></a> Modificación de la propiedad O365OflBaseUrlConfigured

```powershell
# Name: O365OflBaseUrlConfigured.ps1
#
# Description: This sample sets the O365OflBaseUrlConfigured property for the SMS_WSUS_CONFIGURATION_MANAGER component on the top-level site.
# This script must be run on the disconnected top-level Configuration Manager site server
#
# Replace "D:\Office365updates\content" with the full path to the copied directory containing all the Office metadata and content generated by the OfflineUpdateExporter tool.
# Only local paths work for the O365OflBaseUrlConfigured property.

$PropertyValue = "D:\Office365updates\content"

# Don't change any of the lines below
$PropertyName = "O365OflBaseUrlConfigured"

# Get provider instance
$providerMachine = Get-WmiObject -namespace "root\sms" -class "SMS_ProviderLocation"

if($providerMachine -is [system.array])
{
    $providerMachine=$providerMachine[0]
}

$SiteCode = $providerMachine.SiteCode

$component = gwmi -ComputerName $providerMachine.Machine -namespace root\sms\site_$SiteCode -query 'select comp.* from sms_sci_component comp join SMS_SCI_SiteDefinition sdef on sdef.SiteCode=comp.SiteCode where sdef.ParentSiteCode="" and comp.componentname="SMS_WSUS_CONFIGURATION_MANAGER"'
$properties = $component.props

Write-host "Updating $PropertyName property for site " $SiteCode

foreach ($property in $properties)
{
  if ($property.propertyname -eq $PropertyName) 
  {
    Write-host "Current value for $PropertyName is $($property.value2)"
    $property.value2 = $PropertyValue
    Write-host "Updating value for $PropertyName to $($property.value2)"
    break
  }
}

$component.props = $properties
$component.put()
```

## <a name="next-steps"></a>Pasos siguientes

[Agregar actualizaciones de software a un grupo de actualizaciones](../deploy-use/add-software-updates-to-an-update-group.md)