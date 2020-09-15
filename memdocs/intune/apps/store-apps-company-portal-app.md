---
title: Adición manual de la aplicación Portal de empresa para Windows 10
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo los empleados pueden agregar manualmente la aplicación Portal de empresa de Windows 10 a sus PC desde Microsoft Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/01/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4dca7e5b790cd932841211b04cf463602df55a57
ms.sourcegitcommit: cf7cdd0e66e155ac153392468799732eafbb0744
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89390779"
---
# <a name="add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Adición de la aplicación Portal de empresa de Windows 10 con Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Para administrar dispositivos e instalar aplicaciones, los usuarios pueden instalar la aplicación Portal de empresa por sí mismos desde Microsoft Store. Sin embargo, si las necesidades empresariales exigen que les asigne la aplicación Portal de empresa, puede asignar esa aplicación para Windows 10 directamente desde Intune. Puede hacerlo aun cuando no haya integrado Intune con Microsoft Store para Empresas.

 > [!IMPORTANT]
 > Si descarga la aplicación Portal de empresa, la opción descrita en este artículo exige que asigne actualizaciones manuales cada vez que se publica la actualización de una aplicación. Para implementar la aplicación Portal de empresa para dispositivos Windows 10 aprovisionados con Autopilot, vea [Adición de dispositivos Autopilot con la aplicación Portal de empresa de Windows 10](store-apps-company-portal-autopilot.md).

> [!NOTE]
> El Portal de empresa admite aplicaciones de Configuration Manager. Esta característica permite a los usuarios finales ver las aplicaciones implementadas de Configuration Manager y de Intune en el Portal de empresa de los clientes administrados conjuntamente. Esta nueva versión del portal de empresa mostrará las aplicaciones implementadas por Configuration Manager para todos los clientes administrados conjuntamente. Esta compatibilidad ayuda a los administradores a consolidar sus diferentes experiencias del portal de usuario final. Para más información, consulte [Uso de la aplicación Portal de empresa en dispositivos administrados conjuntamente](/mem/configmgr/comanage/company-portal).

## <a name="configure-settings-to-show-offline-apps"></a>Configuración de las opciones para mostrar las aplicaciones sin conexión
1. Inicie sesión en [Microsoft Store para Empresas](https://www.microsoft.com/business-store) con la cuenta de administrador.
2. Haga clic en la pestaña **Administrar**, situada cerca de la parte superior de la ventana.
3. En el panel de la izquierda, seleccione **Configuración**.
4. En **Experiencia de compra**, establezca **Mostrar aplicaciones sin conexión** en **Activado**.  
    Se muestran las aplicaciones con licencia sin conexión.

## <a name="download-the-offline-company-portal-app"></a>Descarga de la aplicación Portal de empresa sin conexión
1. Busque y seleccione la aplicación **Portal de empresa**.
2. Establezca **Tipo de licencia** en **Sin conexión**.
3. Seleccione **Obtener la aplicación** para adquirir y agregar la aplicación Portal de empresa sin conexión al inventario.
4. En la página de la aplicación **Portal de empresa**, seleccione **Administrar**.
5. En **Plataforma**, seleccione **Todos los dispositivos Windows 10** y luego los valores **Versión mínima**, **Arquitectura** y **Descargar metadatos de la aplicación** correspondientes. 
6. Seleccione **Descargar** en **Detalles del paquete** para guardar el archivo en la máquina local.

    ![Dispositivos Windows 10 donde la arquitectura es igual a x86 (seleccionado)](./media/app-sideload-windows/Win10CP-all-devices.png)

7. Descargue todos los paquetes de "Marcos necesarios" al seleccionar **Descargar**.  

    Esta acción se debe realizar en arquitecturas x86, x64 y ARM:<br> 
    *Hay 9 paquetes de .NET Framework necesarios cuando se selecciona 1507 como la versión mínima del SO, 12 paquetes cuando se selecciona la versión 1511 y 15 cuando se selecciona la versión 1607.*

8. En Microsoft Intune, en Azure Portal, cargue la aplicación Portal de empresa como una nueva aplicación. Para agregar la aplicación, seleccione la aplicación de línea de negocio en **Tipo de aplicación** en el panel **Seleccionar tipo de aplicación**. Después, seleccione el archivo de paquete de aplicación (extensión .AppxBundle).

9. En **Select dependency app files** (Seleccionar archivos de aplicación de dependencia), seleccione todas las dependencias que descargó en el paso 7 con Mayús + clic y compruebe que la columna **Agregado** muestra **Sí** en la arquitectura que se necesita.

     > [!NOTE]
     > Si no se agregan las dependencias, es posible que la aplicación no se instale en los tipos de dispositivo especificados.

10. Haga clic en **Aceptar**, rellene el campo **Información de la aplicación** y haga clic en **Agregar**.

11. Asigne la aplicación Portal de empresa como una aplicación necesaria al conjunto seleccionado de grupos de dispositivos o usuarios.  

Para obtener más información sobre cómo controla Intune las dependencias de las aplicaciones universales, vea [Deploying an appxbundle with dependencies via Microsoft Intune MDM](/archive/blogs/configmgrdogs/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm) (Implementación de appxbundle con dependencias a través de la MDM de Microsoft Intune).  

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>¿Cómo actualizo la aplicación Portal de empresa en los dispositivos de mis usuarios si ya han instalado las aplicaciones anteriores desde la Tienda?
Si los usuarios ya han instalado las aplicaciones del Portal de empresa de Windows 8.1 desde Microsoft Store, estas se actualizarán automáticamente a la nueva versión sin necesidad de hacer nada. Si la actualización no se realiza, pida a los usuarios que confirmen que han habilitado las actualizaciones automáticas de aplicaciones de la Tienda en sus dispositivos.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>¿Cómo puedo actualizar mi aplicación transferida localmente del Portal de empresa para Windows 8.1 a la versión para Windows 10?
La ruta de migración recomendada es eliminar la asignación de la aplicación Portal de empresa de Windows 8.1 al establecer la acción de asignación en **Desinstalar**. Después de seleccionar esta opción, puede asignar la aplicación Portal de empresa de Windows 10 mediante cualquiera de las opciones expuestas anteriormente.  

Si necesita transferir localmente la aplicación y ha asignado el Portal de empresa de Windows 8.1 sin firmarlo con el certificado de Symantec, realice la actualización mediante los pasos de las secciones anteriores de este artículo.

Si necesita transferir localmente la aplicación y ha firmado y asignado la aplicación Portal de empresa de Windows 8.1 con el certificado de firma de código de Symantec, siga los pasos de la siguiente sección.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>¿Cómo puedo actualizar mi aplicación del Portal de empresa firmada y transferida localmente para Windows 8.1 a la versión para Windows 10?
La ruta de migración recomendada es eliminar la asignación existente de la aplicación del Portal de empresa de Windows 8.1 mediante el establecimiento de la acción de asignación en **Desinstalar**. Después de seleccionar esta opción, puede asignar la aplicación Portal de empresa de Windows 10 con normalidad.  

De lo contrario, tiene que actualizar y firmar correctamente la aplicación Portal de empresa de Windows 10 para garantiza que se respete la ruta de actualización.  

Si firma y asigna la aplicación Portal de empresa de Windows 10 de esta manera, debe repetir este proceso para cada nueva actualización de la aplicación cuando esté disponible en la Tienda. La aplicación no se actualiza automáticamente cuando se actualiza la Tienda.  

Así es cómo se tiene que firmar y asignar la aplicación:

1. Descargue el [script de firma de la aplicación Portal de empresa de Windows 10 de Microsoft Intune](https://aka.ms/win10cpscript).  
    Este script requiere instalar Windows SDK para Windows 10 en el equipo host. [Descargar Windows SDK para Windows 10](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Descargue la aplicación Portal de empresa de Windows 10 desde Microsoft Store para Empresas, como se ha explicado anteriormente.  
3. Para firmar la aplicación Portal de empresa de Windows 10, ejecute el script con los parámetros de entrada detallados en el encabezado del script, como se muestra en la siguiente tabla.  
    Las dependencias no tienen que pasarse al script. Solo se necesitan cuando la aplicación va a cargarse en la consola de administración de Intune.

| Parámetro |  Descripción  |
|---|---|
| InputWin10AppxBundle  |  Ruta de acceso al archivo de origen appxbundle. |
| OutputWin10AppxBundle | La ruta de acceso de salida del archivo firmado appxbundle. 
| Win81Appx  | Ruta de acceso al archivo del Portal de empresa de Windows 8.1 (.APPX). |
| PfxFilePath  |  Ruta de acceso al archivo del certificado de firma de código móvil de empresa de Symantec (.PFX).  |
| PfxPassword  | La contraseña del certificado de firma de código móvil de empresa de Symantec. |
| PublisherId | El identificador del publicador de la empresa. Si no hay, se usa el campo Asunto del certificado de firma de código móvil de empresa de Symantec. |
| SdkPath | La ruta de acceso a la carpeta raíz de Windows SDK para Windows 10. Este argumento es opcional y su valor predeterminado es ${env:ProgramFiles(x86)}\Windows Kits\10.  |

Cuando el script termina de ejecutarse, genera la versión firmada de la aplicación Portal de empresa de Windows 10. Luego puede asignar la versión firmada de la aplicación como una aplicación de línea de negocio (LOB) mediante Intune, que actualiza las versiones asignadas actualmente a esta nueva aplicación.  

## <a name="next-steps"></a>Pasos siguientes

- [Asignar aplicaciones a grupos](apps-deploy.md)