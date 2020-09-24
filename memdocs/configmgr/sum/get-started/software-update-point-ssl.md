---
title: Configuración de un punto de actualización de software para usar TLS/SSL con un certificado PKI
titleSuffix: Configuration Manager
description: 'Tutorial: Configuración de servidores de Windows Server Update Services (WSUS) y los puntos de actualización de software para usar TLS/SSL con un certificado PKI'
author: mestew
ms.author: mstewart
manager: dougeby
ms.date: 09/16/2020
ms.topic: tutorial
ms.prod: configuration-manager
ms.technology: configmgr-sum
ms.assetid: bd9989b8-ccaf-4d51-8262-b4a99b600d12
ms.openlocfilehash: e8359077ac363d2d732b2ffa6712c9b938a2c709
ms.sourcegitcommit: 6176a7825d6c663faa318a6818b7764bc70f08fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90718950"
---
# <a name="tutorial-configure-a-software-update-point-to-use-tlsssl-with-a-pki-certificate"></a>Tutorial: Configuración de un punto de actualización de software para usar TLS/SSL con un certificado PKI

*Se aplica a: Configuration Manager (rama actual)*

La configuración de servidores de Windows Server Update Services (WSUS) y sus puntos de actualización de software (SUP) correspondientes para usar TLS/SSL puede reducir la capacidad de un atacante potencial de poner en peligro a un cliente de forma remota y elevar los privilegios. Para asegurarse de que se han implementado los mejores protocolos de seguridad, se recomienda encarecidamente usar el protocolo TLS/SSL para proteger la infraestructura de actualización de software. Este artículo le guía por los pasos necesarios para configurar cada uno de los servidores de WSUS y el punto de actualización de software para usar HTTPS. Para más información sobre cómo proteger WSUS, vea el artículo [Proteger WSUS con el protocolo de Capa de sockets seguros](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#25-secure-wsus-with-the-secure-sockets-layer-protocol) en la documentación de WSUS.

En este tutorial, aprenderá lo siguiente:
> [!div class="checklist"]
> * Obtención de un certificado PKI, si es necesario
> * Enlace del certificado con el sitio web de administración de WSUS
> * Configuración de los servicios web de WSUS para que requieran SSL
> * Configuración de la aplicación de WSUS para usar SSL
> * Comprobación de que la conexión de la consola de WSUS puede usar SSL
> * Configuración del punto de actualización de software para requerir la comunicación SSL con el servidor de WSUS
> * Comprobación de la funcionalidad con Configuration Manager

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

WSUS utiliza TLS/SSL para autenticar en el servidor de WSUS ascendente los equipos cliente y los servidores de WSUS que siguen en la cadena. WSUS también utiliza TLS/SSL para cifrar los metadatos de las actualizaciones. WSUS no usa TLS/SSL para los archivos de contenido de una actualización. Los archivos de contenido se firman, y el hash del archivo se incluye en los metadatos de la actualización. Antes de que el cliente descargue e instale los archivos, se comprueban la firma digital y el hash. Si se produce un error en cualquiera de las comprobaciones, no se instalará la actualización.

Tenga en cuenta las siguientes limitaciones cuando use TLS/SSL para proteger una implementación de WSUS:

- El uso de TLS/SSL aumenta la carga de trabajo del servidor. Debe esperar una pequeña pérdida de rendimiento por el cifrado de todos los metadatos que se envían a través de la red.
- Si usa WSUS con una base de datos de SQL Server remota, la conexión entre el servidor de WSUS y el servidor de base de datos no está protegida mediante TLS/SSL. Si la conexión de base de datos debe estar protegida, tenga en cuenta las siguientes recomendaciones:
   - Mueva la base de datos WSUS al servidor WSUS.
   - Mueva el servidor de la base de datos remota y el servidor WSUS a una red privada.
   - Implemente el protocolo de seguridad de Internet (IPsec) para ayudar a proteger el tráfico de la red.

Al configurar los servidores de WSUS y sus puntos de actualización de software para que usen TLS/SSL, es posible que desee introducir gradualmente los cambios en las jerarquías grandes de Configuration Manager. Si elige introducir gradualmente estos cambios, empiece en la parte inferior de la jerarquía y desplácese hacia arriba hasta llegar al sitio de administración central.

## <a name="prerequisites"></a>Requisitos previos

En este tutorial se trata el método más común para obtener un certificado para su uso con Internet Information Services (IIS). Sea cual sea el método que use su organización, asegúrese de que el certificado cumple los [requisitos de los certificados PKI](../../core/plan-design/network/pki-certificate-requirements.md) para un punto de actualización de software de Configuration Manager. Como con cualquier certificado, la entidad de certificación debe ser de confianza para los dispositivos que se comunican con el servidor de WSUS.

- Un servidor de WSUS con el rol de punto de actualización de software instalado.
- Compruebe que ha seguido los [procedimientos recomendados](/troubleshoot/mem/configmgr/windows-server-update-services-best-practices#disable-recycling-and-configure-memory-limits) para deshabilitar el reciclaje y configurar los límites de memoria para WSUS antes de habilitar TLS/SSL.
- Una de las dos opciones siguientes:
   - Ya existe un certificado PKI adecuado en el almacén de certificados **Personal** del servidor de WSUS.
   - La capacidad de solicitar y obtener un certificado PKI adecuado para el servidor de WSUS de la entidad de certificación (CA) raíz de la empresa.
      - De forma predeterminada, la mayoría de las plantillas de certificado, incluida la plantilla de certificado WebServer, solo se emitirán a los administradores del dominio. Si el usuario que ha iniciado sesión no es un administrador de dominio, será necesario conceder a su cuenta de usuario el permiso **Inscribir** en la plantilla de certificado.

## <a name="obtain-the-certificate-from-the-ca-if-needed"></a><a name="bkmk_pki"></a> Obtención del certificado de la CA si es necesario

Si ya tiene un certificado adecuado en el almacén de certificados **Personal** del servidor de WSUS, omita esta sección y comience con la sección [Enlace del certificado](#bkmk_bind). Para enviar una solicitud de certificado a la entidad de certificación interna para instalar un nuevo certificado, siga las instrucciones de esta sección.
 
1. Desde el servidor de WSUS, abra un símbolo del sistema administrativo y ejecute `certlm.msc`. Su cuenta de usuario debe ser un administrador local para administrar certificados en el equipo local.

   Aparece la herramienta Administrador de certificados para el dispositivo local.

1. Expanda **Personal** y, después, haga clic con el botón derecho en **Certificados**.
1. Seleccione **Todas las tareas** y, después, **Solicitar un nuevo certificado**.
1. Elija **Siguiente** para iniciar la inscripción de certificado.
1. Elija el tipo de certificado que se va a inscribir. El propósito del certificado es **Autenticación de servidor** y la plantilla de certificado de Microsoft que se va a usar es **Servidor web** o una plantilla personalizada que tenga la opción **Autenticación de servidor** configurada como **Uso mejorado de claves**. Es posible que se le pida información adicional para inscribir el certificado. Normalmente, especificará la siguiente información como mínimo:
   - **Nombre común**: en la pestaña **Firmante**, establezca el valor del FQDN del servidor de WSUS.
   - **Nombre descriptivo**: en la pestaña **General**, establezca el valor en un nombre descriptivo que le ayude a identificar el certificado más adelante.
:::image type="content" source="media/certificate-properties.png" alt-text="Ventana Propiedades de certificado para especificar más información para la inscripción":::
1. Seleccione **Inscribir** y, después, **Finalizar** para completar la inscripción.
1. Abra el certificado si desea ver los detalles sobre él, como la huella digital del certificado.

> [!TIP]
> Si se puede acceder al servidor de WSUS desde Internet, necesitará el FQDN externo del firmante o el nombre alternativo del titular (SAN) del certificado.

## <a name="bind-the-certificate-to-the-wsus-administration-site"></a><a name="bkmk_bind"></a> Enlace del certificado con el sitio de administración de WSUS

Una vez que tenga el certificado en el almacén de certificados personal del servidor de WSUS, enlácelo con el sitio de administración de WSUS en IIS.

1. En el servidor WSUS, abra el Administrador de Internet Information Services (IIS).
1. Vaya a **Sitios** > **Administración de WSUS**.
1. Seleccione **Enlaces** en el menú Acción o haciendo clic con el botón derecho en el sitio.
1. En la ventana **Enlaces de sitios**, seleccione la línea para **https** y, después, seleccione **Editar...** .
   - No quite el enlace del sitio HTTP. WSUS usa HTTP para los archivos de contenido de actualización.
1. En la opción **Certificado SSL**, elija el certificado que se va a enlazar con el sitio de administración de WSUS. El nombre descriptivo del certificado se muestra en el menú desplegable. Si no se especificó un nombre descriptivo, se muestra el campo `IssuedTo` del certificado. Si no está seguro de qué certificado usar, seleccione **Ver** y compruebe que la huella digital coincide con la que ha obtenido.  
   :::image type="content" source="media/edit-site-binding.png" alt-text="Ventana Modificar enlace de sitio con la selección del certificado SSL":::
1. Seleccione **Aceptar** cuando haya terminado, y **Cerrar** para salir de los enlaces del sitio. Mantenga abierto el Administrador de Internet Information Services (IIS) para los pasos siguientes.



## <a name="configure-the-wsus-web-services-to-require-ssl"></a><a name="bkmk_webserv"></a> Configuración de los servicios web de WSUS para que requieran SSL

1. En el Administrador de IIS en el servidor de WSUS, vaya a **Sitios** > **Administración de WSUS**.
1. Expanda el sitio de administración de WSUS para ver la lista de servicios web y directorios virtuales de WSUS.
1. Para cada uno de los servicios web de WSUS siguientes:
   - ApiRemoting30
   - ClientWebService
   - DSSAuthWebService
   - ServerSyncWebService
   - SimpleAuthWebService

   Se han realizado los siguientes cambios:

      1. Seleccione **Configuración de SSL**.
      1. Habilite la opción **Requerir SSL**.
      1. Compruebe que la opción **Certificados de cliente** está establecida en **Omitir**.
      1. Seleccione **Aplicar**.

No establezca la configuración de SSL en el sitio de administración de WSUS de nivel superior, ya que determinadas funciones, como el contenido, deben usar HTTP.

## <a name="configure-the-wsus-application-to-use-ssl"></a><a name="bkmk_wsusutil"></a> Configuración de la aplicación de WSUS para usar SSL

Una vez que los servicios web estén configurados para requerir SSL, se debe notificar a la aplicación de WSUS para que pueda realizar alguna configuración adicional para admitir el cambio.

1. Abra un símbolo del sistema de administrador en el servidor de WSUS. La cuenta de usuario que ejecuta este comando debe ser miembro del grupo de administradores de WSUS o del grupo de administradores local.
1. Cambie el directorio a la carpeta Tools de WSUS:  
   `cd "c:\Program Files\Update Services\Tools"`
1. Configure WSUS para usar SSL con el siguiente comando:

    `WsusUtil.exe configuressl server.contoso.com`
   
   Donde *server.contoso.com* es el FQDN del servidor de WSUS.
1. WsusUtil devuelve la dirección URL del servidor de WSUS con el número de puerto especificado al final. El puerto será 8531 (predeterminado) o 443. Compruebe que la dirección URL devuelta es la esperada. Si hay algún tipo de error, puede volver a ejecutar el comando.

   :::image type="content" source="media/wsusutil.png" alt-text="El comando wsusutil configuressl que devuelve la dirección URL HTTPS para WSUS":::

> [!TIP] 
> Si se puede acceder al servidor de WSUS desde Internet, especifique el nombre de dominio completo externo al ejecutar `WsusUtil.exe configuressl`.

## <a name="verify-the-wsus-console-can-connect-using-ssl"></a><a name="bkmk_wsus_console"></a> Comprobación de que la consola de WSUS se puede conectar con SSL

La consola de WSUS usa el servicio web ApiRemoting30 para la conexión. El punto de actualización de software (SUP) de Configuration Manager también usa este mismo servicio web para indicar a WSUS que realice determinadas acciones, como:

- Iniciar la sincronización de actualizaciones de software.
- Configurar el servidor ascendente para WSUS, que depende del lugar en el que reside el sitio del SUP en la jerarquía de Configuration Manager.
- Agregar o eliminar productos y clasificaciones para la sincronización desde el servidor de WSUS de nivel superior de la jerarquía.
- Eliminar actualizaciones expiradas.

Abra la consola de WSUS para comprobar que puede usar una conexión SSL con el servicio web ApiRemoting30 del servidor de WSUS. Probaremos algunos de los otros servicios web más adelante.

1. Abra la consola de WSUS y seleccione **Acción** > **Conectar al servidor**.
1. Escriba el FQDN del servidor de WSUS para la opción **Nombre de servidor**.
1. Elija el **Número de puerto** devuelto en la dirección URL de WSUSutil.
1. La opción **Usar la Capa de sockets seguros (SSL) para conectarse a este servidor** se habilita automáticamente cuando se eligen los puertos 8531 (predeterminado) o 443.
       :::image type="content" source="media/connect-wsus-console.png" alt-text="Conectarse a la consola de WSUS a través del puerto HTTPS":::
1. Si el servidor de sitio de Configuration Manager es remoto desde el punto de actualización de software, inicie la consola de WSUS desde el servidor de sitio y compruebe que la consola de WSUS puede conectarse a través de SSL.
   - Si la consola remota de WSUS no se puede conectar, es probable que se deba a un problema con la confianza en el certificado, la resolución de nombres o el puerto que se está bloqueando.

## <a name="configure-the-software-update-point-to-require-ssl-communication-to-the-wsus-server"></a><a name="bkmk_cm_sup"></a> Configuración del punto de actualización de software para requerir la comunicación SSL con el servidor de WSUS

Una vez que WSUS está configurado para usar TLS/SSL, deberá actualizar el punto de actualización de software de Configuration Manager correspondiente para que también se requiera SSL. Al hacer este cambio, Configuration Manager:

- Comprobará que puede configurar el servidor de WSUS para el punto de actualización de software.
- Remitirá a los clientes para que usen el puerto SSL cuando se les indique que realicen el análisis en este servidor de WSUS.

Para configurar el punto de actualización de software para requerir la comunicación SSL con el servidor de WSUS, siga estos pasos: 

1. Abra la consola de Configuration Manager y conéctese al sitio de administración central o al servidor de sitio principal para el punto de actualización de software que necesita editar.
1. Vaya a **Administración** > **General** > **Configuración de sitio** > **Servidores y roles de sistema de sitio**.
1. Seleccione el servidor de sistema de sitio en el que está instalado WSUS y, a continuación, seleccione el rol de sistema de sitio del punto de actualización de software.
1. En la cinta de opciones, elija **Propiedades**.
1. Habilite la opción **Requerir comunicación de SSL con el servidor de WSUS**.

   :::image type="content" source="media/sup-properties.png" alt-text="Propiedades de SUP que muestran la opción Requerir comunicación de SSL con el servidor de WSUS":::
1. En el archivo [**WCM.log**](../../core/plan-design/hierarchy/log-files.md#BKMK_SUPLog) del sitio, verá las siguientes entradas cuando aplique el cambio:

   ```
   SCF change notification triggered.
   Populating config from SCF
   Setting new configuration state to 1 (WSUS_CONFIG_PENDING)
   ...
   Attempting connection to local WSUS server
   Successfully connected to local WSUS server
   ...
   Setting new configuration state to 2 (WSUS_CONFIG_SUCCESS)
   ```

Los ejemplos de archivos de registro se han editado para quitar información innecesaria para este escenario.  

## <a name="verify-functionality-with-configuration-manager"></a><a name="bkmk_cm_verify"></a> Comprobación de la funcionalidad con Configuration Manager

### <a name="verify-the-site-server-can-sync-updates"></a>Comprobación de que el servidor de sitio puede sincronizar actualizaciones

1. Conecte la consola de Configuration Manager al sitio de nivel superior.
1. Vaya a **Biblioteca de software** > **Información general** > **Actualización de software** > **Todas las actualizaciones de software**.
1. En la cinta de opciones, seleccione **Sincronizar actualizaciones de software**.
1. Seleccione **Sí** en la notificación que le pregunta si desea iniciar una sincronización en todo el sitio con las actualizaciones de software.
   - Como la configuración de WSUS ha cambiado, se producirá una sincronización completa de las actualizaciones de software en lugar de una sincronización diferencial.
1. Abra el archivo **wsyncmgr.log** del sitio. Si va a supervisar un sitio secundario, deberá esperar primero a que el sitio principal termine la sincronización. Compruebe que el servidor se sincroniza correctamente revisando el registro en busca de entradas similares a las siguientes:

   ```
   Starting Sync
   ...
   Full sync required due to changes in main WSUS server location.
   ...
   Found active SUP SERVER.CONTOSO.COM from SCF File.
   ...
   https://SERVER.CONTOSO.COM:8531
   ...
   Done synchronizing WSUS Server SERVER.CONTOSO.COM
   ...
   sync: Starting SMS database synchronization
   ...
   Done synchronizing SMS with WSUS Server SERVER.CONTOSO.COM
   ```

### <a name="verify-a-client-can-scan-for-updates"></a>Comprobación de que un cliente pueda buscar actualizaciones

Al cambiar el punto de actualización de software para que requiera SSL, los clientes de Configuration Manager reciben la dirección URL de WSUS actualizada cuando realiza una solicitud de ubicación para un punto de actualización de software. Al probar un cliente, podemos:
-  Determinar si el cliente confía en el certificado del servidor de WSUS. 
- Comprobar si SimpleAuthWebService y ClientWebService para WSUS son funcionales.
-  Comprobar que el directorio virtual de contenido de WSUS sea funcional, si el cliente ha tenido que obtener un CLUF durante el examen.

1. Identifique un cliente que examina el punto de actualización de software cambiado recientemente para usar TLS/SSL. Use [Ejecutar scripts](../..//apps/deploy-use/create-deploy-scripts.md) con el siguiente script de PowerShell si necesita ayuda con la identificación de un cliente:

   ```powershell
   $Last = (Get-CIMInstance -Namespace "root\CCM\Scanagent" -Class "CCM_SUPLocationList").LastSuccessScanPath
   $Current= Write-Output (Get-CIMInstance -Namespace "root\CCM\Scanagent" -Class "CCM_SUPLocationList").CurrentScanPath
   Write-Host "LastGoodSUP- $last"
   Write-Host "CurrentSUP- $current"
   ```

1. Ejecute un ciclo de examen de actualizaciones de software en el cliente de prueba. Puede forzar un examen con el siguiente script de PowerShell:

   ```powershell
   Invoke-WMIMethod -Namespace root\ccm -Class SMS_CLIENT -Name TriggerSchedule "{00000000-0000-0000-0000-000000000113}"
   ```

1. Revise el archivo **ScanAgent.log** del cliente para comprobar que se ha recibido el mensaje que se va a examinar en el punto de actualización de software.

   ```
   Message received: '<?xml version='1.0' ?>
   <UpdateSourceMessage MessageType='ScanByUpdateSource'>
      <ForceScan>TRUE</ForceScan>
      <UpdateSourceIDs>
            <ID>{A1B2C3D4-1234-1234-A1B2-A1B2C3D41234}</ID>
      </UpdateSourceIDs>
    </UpdateSourceMessage>'
   ```

1. Revise el archivo **LocationServices.log** para comprobar si el cliente ve la dirección URL correcta de WSUS.
**LocationServices.log**
   ```
   WSUSLocationReply : <WSUSLocationReply SchemaVersion="1
   ...
   <LocationRecord WSUSURL="https://SERVER.CONTOSO.COM:8531" ServerName="SERVER.CONTOSO.COM"
   ...
   </WSUSLocationReply>
   ```

1. Revise el archivo **WUAHandler.log** para comprobar que el cliente puede realizar un análisis correcto.

   ```
   Enabling WUA Managed server policy to use server: https://SERVER.CONTOSO.COM:8531
   ...
   Successfully completed scan.
   ```

## <a name="next-steps"></a>Pasos siguientes

[Implementar actualizaciones de software](../deploy-use/deploy-software-updates.md)