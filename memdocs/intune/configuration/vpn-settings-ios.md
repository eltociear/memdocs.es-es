---
title: 'Configuración de VPN para dispositivos iOS/iPadOS en Microsoft Intune: Azure | Microsoft Docs'
description: Agregue o cree un perfil de configuración de VPN en dispositivos iOS o iPadOS mediante la configuración de red privada virtual (VPN). Configure los detalles de la conexión, los métodos de autenticación, el túnel dividido, la configuración de VPN personalizada con el identificador y los pares de clave-valor, la configuración de VPN por aplicación que incluye direcciones URL de Safari y VPN a petición con SSID o dominios de búsqueda DNS, la configuración del proxy para incluir un script de configuración, la dirección IP o FQDN y el puerto TCP en Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/17/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8aeab9ba7f6b6abd42793bf2af9452b4482edf4
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88911835"
---
# <a name="add-vpn-settings-on-ios-and-ipados-devices-in-microsoft-intune"></a>Adición de la configuración de VPN en dispositivos iOS y iPadOS en Microsoft Intune

Microsoft Intune incluye muchas opciones de configuración de VPN que se pueden implementar en los dispositivos iOS/iPadOS. Estas opciones se usan para crear y configurar conexiones VPN a la red de su organización. Ambas se describen en este artículo. Algunas opciones solo están disponibles para algunos clientes VPN, como Citrix, Zscaler y otros.

## <a name="before-you-begin"></a>Antes de comenzar

[Cree un perfil de configuración de dispositivo](vpn-settings-configure.md).

> [!NOTE]
> Esta configuración está disponible para todos los tipos de inscripción, excepto para la inscripción de usuarios. La inscripción de usuarios está limitada a [VPN por aplicación](./vpn-setting-configure-per-app.md). Para más información sobre los tipos de inscripción, consulte [Inscripción en iOS/iPadOS ](../enrollment/ios-enroll.md).

## <a name="connection-type"></a>Tipo de conexión

Seleccione el tipo de conexión VPN de la siguiente lista de proveedores:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: para la versión 4.0.5x y versiones anteriores de la aplicación [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924).
- **Cisco AnyConnect**: para la versión 4.0.7x y versiones posteriores de la aplicación [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690).
- **SonicWall Mobile Connect**
- **F5 Access heredado**: aplicable a la versión 2.1 de la aplicación F5 Access y versiones anteriores.
- **F5 Access**: aplicable a la versión 3.0 de la aplicación F5 Access y versiones posteriores.
- **GlobalProtect de Palo Alto Networks (heredado)** : aplicable a la aplicación GlobalProtect de Palo Alto Networks, versión 4.1 y anteriores.
- **GlobalProtect de Palo Alto Networks**: aplicable a la aplicación GlobalProtect de Palo Alto Networks, versión 5.0 y posteriores.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: para usar el acceso condicional o permitir a los usuarios que omitan la pantalla de inicio de sesión de Zscaler, debe integrar Zscaler Private Access (ZPA) con la cuenta de Azure AD. Para obtener instrucciones detalladas, vea la [documentación de Zscaler](https://help.zscaler.com/zpa/configuration-guide-microsoft-azure-ad).
- **NetMotion Mobility**
- **IKEv2**: la [configuración de IKEv2](#ikev2-settings) (en este artículo) describe las propiedades.
- **VPN personalizada**

> [!NOTE]
> Cisco, Citrix, F5 y Palo Alto han anunciado que sus clientes heredados no funcionan en iOS 12. Tendrá que migrar a las aplicaciones nuevas tan pronto como sea posible. Para obtener más información, vea el [blog del equipo de soporte técnico de Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Configuración de VPN base

La configuración que se muestra en la siguiente lista se determina según el tipo de conexión VPN que elija.  

- **Nombre de la conexión**: Los usuarios finales verán este nombre cuando exploren su dispositivo para ver una lista de conexiones VPN disponibles.
- **Nombre de dominio personalizado** (solo Zscaler): rellene previamente el campo de inicio de sesión de la aplicación Zscaler con el dominio al que pertenecen los usuarios. Por ejemplo, si un nombre de usuario es `Joe@contoso.net`, el dominio `contoso.net` aparece de forma estática en el campo al abrir la aplicación. Si no escribe un nombre de dominio, se usa la parte del dominio del UPN en Azure Active Directory (AD).
- **Dirección IP o FQDN**: dirección IP o nombre de dominio completo (FQDN) del servidor VPN al que se conectan los dispositivos. Por ejemplo, escriba `192.168.1.1` o `vpn.contoso.com`.
- **Nombre de nube de la organización** (solo Zscaler): escriba el nombre de la nube en la que se aprovisiona la organización. El nombre aparece en la URL que usa para iniciar sesión en Zscaler.  
- **Método de autenticación**: elija cómo se autenticarán los dispositivos en el servidor VPN. 
  - **Certificados**: en **Certificado de autenticación**, seleccione un perfil de certificado SCEP o PKCS existente para autenticar la conexión. En [Configurar certificados](../protect/certificates-configure.md) se proporcionan algunas directrices sobre los perfiles de certificado.
  - **Nombre de usuario y contraseña**: los usuarios finales deben especificar un nombre de usuario y una contraseña para iniciar sesión en el servidor VPN.  

    > [!NOTE]
    > Si el nombre de usuario y la contraseña se usan como método de autenticación para VPN Cisco IPsec, deben entregar la credencial SharedSecret a través de un perfil personalizado de Apple Configurator.

  - **Credencial derivada**: Use un certificado que se derive de la tarjeta inteligente de un usuario. Si no hay ningún emisor de credenciales derivada configurado, Intune le pedirá que agregue uno. Para más información, consulte [Uso de credenciales derivadas en Microsoft Intune](../protect/derived-credentials.md).

- **Direcciones URL excluidas** (solo Zscaler): al conectarse a la VPN de Zscaler, las direcciones URL de la lista son accesibles desde fuera de la nube de Zscaler. 

- **Tunelización dividida**: **Habilitar** o **Deshabilitar** permiten que los dispositivos decidan qué conexión van a usar en función del tráfico. Por ejemplo, un usuario en un hotel usa la conexión VPN para acceder a los archivos de trabajo, pero usa la red normal del hotel para la exploración web habitual.

- **Identificador de VPN** (VPN personalizada, Zscaler y Citrix): identificador de la aplicación VPN que se usa proporcionado por el proveedor de VPN.
- **Especifique pares clave-valor para los atributos de la VPN personalizada de la organización** (VPN personalizada, Zscaler y Citrix): agregue o importe **Claves** y **Valores** que personalicen la conexión VPN. Recuerde que estos valores los suele suministrar el proveedor de VPN.

- **Habilite el control de acceso a la red (NAC)** (Cisco AnyConnect, Citrix SSO, F5 Access): al seleccionar **Acepto**, el identificador de dispositivo se incluye en el perfil de VPN. Este identificador puede usarse con la autenticación en la VPN para permitir o impedir el acceso de red.

  **Si usa Cisco AnyConnect con ISE**, asegúrese de:

  - Si todavía no lo ha hecho, integre ISE con Intune para NAC, tal como se describe en la sección **Configuración de Microsoft Intune como servidor MDM** en la [Guía del administrador de Cisco Identity Services Engine](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html).
  - Habilitar NAC en el perfil de VPN.

  **Si utiliza Citrix SSO con puerta de enlace**, no olvide:

  - Confirmar que utiliza Citrix Gateway 12.0.59 o superior.
  - Confirmar que los usuarios tienen Citrix SSO 1.1.6 o posterior instalado en sus dispositivos.
  - Integrar Citrix Gateway con Intune para el control de acceso de red. Vea la guía de implementación de Citrix sobre [integración de Microsoft Intune/Enterprise Mobility Suite con NetScaler (escenario LDAP+OTP)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - Habilitar NAC en el perfil de VPN.

  **Cuando use F5 Access**, no olvide:

  - Confirme que está usando F5 BIG-IP 13.1.1.5 o una versión posterior. 
  - Integre BIG-IP con Intune para NAC. Vea la guía de F5 [Información general: Configuración de APM para comprobaciones de posición del dispositivo con sistemas de administración de puntos de conexión](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
  - Habilitar NAC en el perfil de VPN.

  En el caso de los asociados de VPN que admiten el identificador de dispositivo, el cliente VPN, como Citrix SSO, puede obtener el identificador. Después, puede consultar a Intune para confirmar que el dispositivo está inscrito y si el perfil de VPN es compatible o no.

  - Para quitar esta configuración, vuelva a crear el perfil y no seleccione **Acepto**. Después, vuelva a asignar el perfil.

### <a name="ikev2-settings"></a>Configuración de IKEv2

Esta configuración se aplica cuando se elige **Tipo de conexión** > **IKEv2**.

- **VPN siempre activa**: **Habilitar** establece un cliente VPN para conectarse y volverse a conectar automáticamente a la VPN. Las conexiones VPN siempre activas permanecen conectadas o se vuelven a conectar inmediatamente cuando el usuario desbloquea su dispositivo, se reinicia el dispositivo o cambia la red inalámbrica. Cuando se establece en **Deshabilitar** (valor predeterminado), se deshabilita la VPN siempre activa para todos los clientes VPN. Cuando esté habilitado, configure también:

  - **Interfaz de red**: toda la configuración de IKEv2 solo se aplica a la interfaz de red que elija. Las opciones son:
    - **Wi-Fi and Cellular** (Wi-Fi y telefonía móvil) (valor predeterminado): la configuración de IKEv2 se aplica a las interfaces de Wi-Fi y telefonía móvil del dispositivo.
    - **Móvil**: la configuración de IKEv2 solo se aplica a la interfaz de telefonía móvil del dispositivo. Seleccione esta opción si va a realizar la implementación en dispositivos con la interfaz Wi-Fi deshabilitada o quitada.
    - **Wi-Fi**: la configuración de IKEv2 solo se aplica a la interfaz Wi-Fi del dispositivo.
  - **User to disable VPN configuration** (Usuario para deshabilitar la configuración de VPN): **Habilitar** permite a los usuarios desactivar la VPN siempre activa. **Deshabilitar** (valor predeterminado) impide que los usuarios la desactiven. El valor predeterminado de esta configuración es la opción más segura.
  - **Correo de voz**: elija lo que sucede con el tráfico de correo de voz cuando está habilitada la VPN siempre activa. Las opciones son:
    - **Force network traffic through VPN** (Forzar el tráfico de red a través de VPN) (valor predeterminado): esta configuración es la opción más segura.
    - **Allow network traffic to pass outside VPN** (Permitir que el tráfico de red pase por fuera de la VPN)
    - **Drop network traffic** (Rechazar tráfico de red)
  - **AirPrint**: elija lo que sucede con el tráfico de AirPrint cuando está habilitada la VPN siempre activa. Las opciones son:
    - **Force network traffic through VPN** (Forzar el tráfico de red a través de VPN) (valor predeterminado): esta configuración es la opción más segura.
    - **Allow network traffic to pass outside VPN** (Permitir que el tráfico de red pase por fuera de la VPN)
    - **Drop network traffic** (Rechazar tráfico de red)
  - **Cellular services** (Servicios de telefonía móvil): en iOS 13.0+, elija lo que sucede con el tráfico de telefonía móvil cuando está habilitada la VPN siempre activa. Las opciones son:
    - **Force network traffic through VPN** (Forzar el tráfico de red a través de VPN) (valor predeterminado): esta configuración es la opción más segura.
    - **Allow network traffic to pass outside VPN** (Permitir que el tráfico de red pase por fuera de la VPN)
    - **Drop network traffic** (Rechazar tráfico de red)
  - **Allow traffic from non-native captive networking apps to pass outside VPN** (Permitir que el tráfico de las aplicaciones de red cautivas no nativas pase por fuera de la VPN): una red cautiva hace referencia a zonas activas Wi-Fi que se encuentran en restaurantes y hoteles. Las opciones son:
    - **No**: fuerza el paso de todo el tráfico de aplicaciones de red cautiva (CN) por el túnel de VPN.
    - **Yes, all apps** (Sí, todas las aplicaciones): permite que todas las aplicaciones de CN omitan la VPN.
    - **Yes, specific apps** (Sí, aplicaciones específicas): elija **Agregar** para agregar una lista de aplicaciones de CN cuyo tráfico pueda omitir la VPN. Especifique los identificadores de conjunto de la aplicación de CN. Por ejemplo, escriba `com.contoso.app.id.package`.

  - **Traffic from Captive Websheet app to pass outside VPN** (Tráfico de la aplicación Captive Websheet que pasará por fuera de la VPN): Captive WebSheet es un explorador web integrado que administra el inicio de sesión único cautivo. **Habilitar** permite que el tráfico de aplicación del explorador omita la VPN. **Deshabilitar** (valor predeterminado) fuerza al tráfico de WebSheet a usar la VPN siempre activa. El valor predeterminado es la opción más segura.
  - **Network address translation (NAT) keepalive interval (seconds)** (Intervalo de mantenimiento de conexiones de traducción de direcciones de red [NAT] [segundos]): para estar conectado a la VPN, el dispositivo envía paquetes de red para permanecer activo. Escriba un valor en segundos de la frecuencia con que se envían estos paquetes, desde 20-1440. Por ejemplo, escriba un valor de `60` para enviar los paquetes de red a la VPN cada 60 segundos. De forma predeterminada, este valor está establecido en `110` segundos.
  - **Offload NAT keepalive to hardware when device is asleep** (Descargar el mantenimiento de conexiones NAT en el hardware cuando el dispositivo esté en suspensión): cuando un dispositivo está en modo de suspensión, **Habilitar** (valor predeterminado) permite que NAT envíe continuamente paquetes de mantenimiento para que el dispositivo permanezca conectado a la VPN. **Deshabilitar** desactiva esta característica.

- **Identificador remoto**: escriba la dirección IP de red, el FQDN, USERFQDN o ASN1DN del servidor IKEv2. Por ejemplo, escriba `10.0.0.3` o `vpn.contoso.com`. Normalmente, se escribe el mismo valor que el [**nombre de la conexión**](#base-vpn-settings) (en este artículo). Sin embargo, depende de la configuración del servidor IKEv2.

- **Tipo de autenticación de cliente**: elija cómo se autentica el cliente VPN en la VPN. Las opciones son:
  - **Autenticación de usuario** (valor predeterminado): las credenciales de usuario se autentican en la VPN.
  - **Autenticación de máquina**: las credenciales de dispositivo se autentican en la VPN.

- **Método de autenticación**: elija el tipo de credenciales de cliente que se van a enviar al servidor. Las opciones son:
  - **Certificados**: usa un perfil de certificado existente para autenticarse en la VPN. Asegúrese de que este perfil de certificado ya está asignado al usuario o al dispositivo. De lo contrario, se produce un error en la conexión VPN.
    - **Tipo de certificado**: seleccione el tipo de cifrado que usa el certificado. Asegúrese de que el servidor VPN está configurado para aceptar este tipo de certificado. Las opciones son:
      - **RSA** (valor predeterminado)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Nombre de usuario y contraseña** (solo autenticación de usuario): cuando los usuarios se conectan a la VPN, se les pide su nombre de usuario y contraseña.
  - **Secreto compartido** (solo autenticación de equipo): permite escribir un secreto compartido para enviarlo al servidor VPN.
    - **Secreto compartido**: escriba el secreto compartido, también conocido como clave precompartida (PSK). Asegúrese de que el valor coincida con el secreto compartido configurado en el servidor VPN.

- **Nombre común del emisor de certificado de servidor**: permite que el servidor VPN se autentique en el cliente VPN. Escriba el nombre común (CN) del emisor de certificado del certificado de servidor VPN que se envía al cliente VPN en el dispositivo. Asegúrese de que el valor de CN coincida con la configuración en el servidor VPN. De lo contrario, se produce un error en la conexión VPN.
- **Nombre común del certificado de servidor**: escriba el nombre común del propio certificado. Si se deja en blanco, se usa el valor del identificador remoto.

- **Tasa de detección de elementos del mismo nivel inactiva**: elija la frecuencia con la que el cliente VPN comprueba si el túnel VPN está activo. Las opciones son:
  - **No configurado**: usa el valor predeterminado del sistema iOS/iPadOS, que puede equivaler a elegir **Media**.
  - **Ninguna**: deshabilita la detección de elementos del mismo nivel inactiva.
  - **Bajo**: envía un mensaje de KeepAlive cada 30 minutos.
  - **Media** (valor predeterminado): envía un mensaje de KeepAlive cada 10 minutos.
  - **Alta**: envía un mensaje de KeepAlive cada 60 segundos.

- **Intervalo mínimo de versiones de TLS**: escriba la versión de TLS mínima que se va a usar. Escriba `1.0`, `1.1` o `1.2`. Si se deja en blanco, se usa el valor predeterminado de `1.0`.
- **Intervalo máximo de versiones de TLS**: escriba la versión de TLS máxima que se va a usar. Escriba `1.0`, `1.1` o `1.2`. Si se deja en blanco, se usa el valor predeterminado de `1.2`.

> [!NOTE]
> Se debe establecer el intervalo mínimo y máximo de versiones de TLS al usar la autenticación de usuario y los certificados.

- **Confidencialidad directa total**: seleccione **Habilitar** para activar la confidencialidad directa total (PFS). PFS es una característica de seguridad IP que reduce el impacto en caso de que una clave de sesión se vea comprometida. **Deshabilitar** (valor predeterminado) no usa PFS.
- **Comprobación de revocación de certificados**: seleccione **Habilitar** para asegurarse de que no se revocan los certificados antes de permitir que la conexión VPN se establezca correctamente. Esta comprobación es la mejor opción. Si el servidor VPN agota el tiempo de espera antes de determinar si el certificado se ha revocado, se concede el acceso. **Deshabilitar** (valor predeterminado) no comprueba los certificados revocados.

- **Configurar parámetros de asociaciones de seguridad**: **Sin configurar** (valor predeterminado) usa el valor predeterminado del sistema iOS/iPadOS. Seleccione **Habilitar** para especificar los parámetros usados al crear asociaciones de seguridad con el servidor VPN:
  - **Algoritmo de cifrado**: seleccione el algoritmo que quiere:
    - DES
    - 3DES
    - AES-128
    - AES-256 (valor predeterminado)
    - AES-128-GCM
    - AES-256-GCM
  - **Algoritmo de integridad**:  seleccione el algoritmo que quiere:
    - SHA1-96
    - SHA1:160
    - SHA2-256 (valor predeterminado)
    - SHA2-384
    - SHA2-512
  - **Grupo Diffie-Hellman**: seleccione el grupo que quiere. El valor predeterminado es el grupo `2`.
  - **Duración** (minutos): elija cuánto tiempo permanece activa la asociación de seguridad hasta que se rotan las claves. Escriba un valor entero entre `10` y `1440` (1440 minutos es 24 horas). El valor predeterminado es `1440`.

- **Configurar un conjunto de parámetros independiente para las asociaciones de seguridad secundarias**: iOS/iPadOS permite configurar parámetros independientes para la conexión IKE y cualquier conexión secundaria. 

  **No configurado** (valor predeterminado) usa los valores especificados en la configuración anterior **Configurar parámetros de asociaciones de seguridad**. Seleccione **Habilitar** para especificar los parámetros que se usan al crear asociaciones de seguridad *secundarias* con el servidor VPN:
  - **Algoritmo de cifrado**: seleccione el algoritmo que quiere:
    - DES
    - 3DES
    - AES-128
    - AES-256 (valor predeterminado)
    - AES-128-GCM
    - AES-256-GCM
  - **Algoritmo de integridad**:  seleccione el algoritmo que quiere:
    - SHA1-96
    - SHA1:160
    - SHA2-256 (valor predeterminado)
    - SHA2-384
    - SHA2-512
  - **Grupo Diffie-Hellman**: seleccione el grupo que quiere. El valor predeterminado es el grupo `2`.
  - **Duración** (minutos): elija cuánto tiempo permanece activa la asociación de seguridad hasta que se rotan las claves. Escriba un valor entero entre `10` y `1440` (1440 minutos es 24 horas). El valor predeterminado es `1440`.

## <a name="automatic-vpn-settings"></a>Configuración automática de VPN

- **VPN por aplicación**: habilita la VPN por aplicación. Permite que la conexión VPN se desencadene de forma automática cuando se abren determinadas aplicaciones. También se asocian las aplicaciones con este perfil de VPN. La VPN por aplicación no se admite en IKEv2. Para más información, consulte las [instrucciones para configurar una VPN por aplicación para iOS/iPadOS](vpn-setting-configure-per-app.md). 
  - **Tipo de proveedor**: solo está disponible para Pulse Secure y VPN personalizada.
  - Al usar perfiles de **VPN por aplicación** de iOS/iPadOS con Pulse Secure o una VPN personalizada, elija la tunelización de la capa de aplicación (app-proxy) o la tunelización de nivel de paquete (packet-tunnel). Establezca el valor **ProviderType** en **app-proxy** para la tunelización de la capa de la aplicación o **packet-tunnel** para la tunelización de la capa de paquetes. Si no tiene claro qué valor usar, consulte la documentación de su proveedor de VPN.
  - **Direcciones URL de Safari que habilitarán esta VPN**: agregue una o más direcciones URL de sitios web. Si se usa el explorador Safari en el dispositivo para ir a estas direcciones URL, la conexión VPN se establece automáticamente.

- **VPN a petición**: configure reglas condicionales que controlen cuándo se inicia la conexión VPN. Por ejemplo, cree una condición en la que la conexión VPN solo se usa cuando un dispositivo no está conectado a una red Wi-Fi de empresa. O bien, cree una nueva condición. Por ejemplo, si un dispositivo no puede acceder a un dominio de búsqueda DNS que escriba, no se iniciará la conexión VPN.

  - **SSID o dominios de búsqueda de DNS**: seleccione si esta condición usa **SSID** de red inalámbrica o **dominios de búsqueda de DNS**. Elija **Agregar** para configurar uno o varios SSID o dominios de búsqueda.
  - **Sondeo de cadena de dirección URL**: Opcional. Escriba una dirección URL que la regla usará como prueba. Si el dispositivo accede a esta dirección URL sin redireccionamiento, se inicia la conexión VPN. Además, el dispositivo se conecta a la dirección URL de destino. El usuario no ve el sitio de sondeo de cadena de dirección URL.

    Por ejemplo, un sondeo de cadena de dirección URL es una dirección URL del servidor web de auditoría que comprueba el cumplimiento del dispositivo antes de conectarse a la VPN. O bien, la dirección URL prueba la capacidad de la VPN para conectarse a un sitio antes de que el dispositivo se conecte a la dirección URL de destino a través de la VPN.

  - **Acción del dominio**: seleccione uno de los elementos siguientes:
    - Conectarse si es necesario
    - No conectarse nunca
  - **Acción**: seleccione uno de los elementos siguientes:
    - Conectar
    - Evaluar conexión
    - Ignorar
    - Desconectar

## <a name="proxy-settings"></a>Configuración del proxy

Si usa un proxy, configure las opciones siguientes. La configuración de proxy no está disponible para las conexiones VPN de Zscaler.  

- **Script de configuración automática**: use un archivo para configurar el servidor proxy. Escriba la **URL del servidor proxy** (por ejemplo, `http://proxy.contoso.com`) que incluye el archivo de configuración.
- **Dirección**: escriba la dirección IP o el nombre de host completo del servidor proxy.
- **Número de puerto**: especifique el número de puerto asociado al servidor proxy.

## <a name="next-steps"></a>Pasos siguientes

Se crea el perfil, pero todavía no hace nada. Después, [asigne el perfil](device-profile-assign.md) y [supervise el estado](device-profile-monitor.md).

Configure las opciones de VPN en dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md) y [Windows 10](vpn-settings-windows-10.md).