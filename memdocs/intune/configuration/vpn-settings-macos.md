---
title: 'Configuración de VPN para dispositivos macOS en Microsoft Intune: Azure | Microsoft Docs'
description: Agregue o cree un perfil de configuración de red privada virtual (VPN), incluidos los detalles de conexión, la tunelización dividida, la configuración de VPN personalizada con el identificador, los pares de clave y valor, la configuración de proxy con un script de configuración, la dirección IP o FQDN y el puerto TCP en Microsoft Intune en dispositivos que ejecutan macOS.
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
ms.openlocfilehash: b7bcb685a33bc8d06226b51aaa051656360b436d
ms.sourcegitcommit: 9408d103e7dff433bd0ace5a9ab8b7bdcf2a9ca2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88819956"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Incorporación de la configuración de VPN en dispositivos macOS en Microsoft Intune

En este artículo, se muestra la configuración de Intune que puede usar para configurar conexiones VPN en dispositivos que ejecutan macOS.

Según la configuración que elija, no todos los valores de la lista siguiente se podrán configurar.

## <a name="before-you-begin"></a>Antes de comenzar

[Cree un perfil de configuración de dispositivo](vpn-settings-configure.md).

> [!NOTE]
> Estas configuraciones están disponibles para todos los tipos de inscripción. Para más información sobre los tipos de inscripción, consulte [Inscripción de macOS](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Configuración de VPN base

**Nombre de la conexión**: escriba un nombre para esta conexión. Los usuarios finales verán este nombre cuando exploren su dispositivo para ver la lista de conexiones VPN disponibles.

- **Dirección IP o FQDN**: escriba la dirección IP o el nombre de dominio completo del servidor VPN al que se conectan los dispositivos. Por ejemplo, escriba `192.168.1.1` o `vpn.contoso.com`.
- **Método de autenticación**: elija cómo se autenticarán los dispositivos en el servidor VPN. Las opciones son:
  - **Certificados**: en **Certificado de autenticación**, elija un perfil de certificado SCEP o PKCS que haya creado anteriormente para autenticar la conexión. Para obtener más información sobre los perfiles de certificado, consulte [Configuración de certificados](../protect/certificates-configure.md).
  - **Nombre de usuario y contraseña**: los usuarios finales deben proporcionar un nombre de usuario y una contraseña para iniciar sesión en el servidor VPN.
- **Tipo de conexión**: Seleccione el tipo de conexión VPN de la siguiente lista de proveedores:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **NetMotion Mobility**
  - **Pulse Secure**
  - **VPN personalizada**: seleccione esta opción si el proveedor de la VPN no aparece en la lista. Configure también:

    - **Identificador de VPN**: escriba un identificador de la aplicación VPN que está usando. Este identificador lo suministra el proveedor de VPN.
    - **Especifique pares clave-valor para los atributos de la VPN personalizada**: agregue o importe **Claves** y **Valores** que personalicen la conexión VPN. Estos valores los suministra normalmente el proveedor de VPN.

- **Tunelización dividida**: puede **Habilitar** o **Deshabilitar** esta opción, que permite que los dispositivos decidan qué conexión usar en función del tráfico. Por ejemplo, un usuario en un hotel usará la conexión VPN para acceder a los archivos de trabajo, pero usará la red normal del hotel para la exploración web habitual.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS/iPadOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="proxy-settings"></a>Configuración del proxy

- **Script de configuración automática**: use un archivo para configurar el servidor proxy. Escriba la **URL del servidor proxy** que contiene el archivo de configuración. Por ejemplo, escriba `http://proxy.contoso.com`.
- **Dirección**: escriba la dirección del servidor proxy (como una dirección IP).
- **Número de puerto**: especifique el número de puerto asociado al servidor proxy.

## <a name="next-steps"></a>Pasos siguientes

El perfil se crea, pero puede que todavía no haga nada. Asegúrese de [asignar el perfil](device-profile-assign.md) y [supervise su estado](device-profile-monitor.md).

Configure las opciones de VPN en dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md) y [Windows 10](vpn-settings-windows-10.md).
