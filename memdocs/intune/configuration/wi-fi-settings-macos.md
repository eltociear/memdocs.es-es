---
title: Configuración de Wi-Fi para dispositivos macOS en Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Cree o agregue un perfil de configuración de dispositivos Wi-Fi para dispositivos macOS. Vea las diferentes configuraciones, agregue certificados, elija un tipo EAP y seleccione un método de autenticación en Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/10/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1cd60b8a9a8612034972e8357d2e346d194ca3a
ms.sourcegitcommit: 387706b2304451e548d6d9c68f18e4764a466a2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85092887"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Incorporación de la configuración de Wi-Fi para dispositivos macOS en Microsoft Intune

Puede crear un perfil con una configuración específica de Wi-Fi y después implementarlo en los dispositivos macOS. Microsoft Intune ofrece muchas características, incluidas la autenticación en la red, agregar un certificado PKCS o SCEP y muchas más.

Esta configuración de Wi-Fi se divide en dos categorías: configuración Básica y configuración Enterprise.

Ambas se describen en este artículo.

## <a name="before-you-begin"></a>Antes de comenzar

[Creación de un perfil de dispositivo en Microsoft Intune](wi-fi-settings-configure.md).

> [!NOTE]
> Estas configuraciones están disponibles para todos los tipos de inscripción. Para más información sobre los tipos de inscripción, consulte [Inscripción de macOS](../enrollment/macos-enroll.md).

## <a name="basic-profiles"></a>Perfiles básicos

Los perfiles personales o básicos usan WPA/WPA2 para proteger la conexión Wi-Fi en los dispositivos. Normalmente, WPA/WPA2 se usa en redes domésticas o redes personales. También puede agregar una clave previamente compartida para autenticar la conexión.

- **Tipo de Wi-Fi**: Elija **Básica**.
- **Nombre de red**: escriba un nombre para esta conexión Wi-Fi. Este valor es el nombre que ven los usuarios cuando exploran la lista de conexiones disponibles en sus dispositivos.
- **SSID**: abreviatura de **identificador de conjunto de servicios**. Esta propiedad es el nombre real de la red inalámbrica a la que se conectan los dispositivos. Con todo, los usuarios solo ven el nombre de red que ha configurado al elegir la conexión.
- **Conectar automáticamente**: elija **Habilitar** para conectarse automáticamente a esta red cuando el dispositivo está en el intervalo. Elija **Deshabilitar** para impedir que los dispositivos se conecten automáticamente.
- **Red oculta**: elija **Habilitar** para ocultar esta red en la lista de redes disponibles en el dispositivo. No se difunde el SSID. Elija **Deshabilitar** para mostrar esta red en la lista de redes disponibles en el dispositivo.
- **Tipo de seguridad**: seleccione el protocolo de seguridad para autenticarse en la red Wi-Fi. Las opciones son:

  - **Abierta (sin autenticación)** : use esta opción solo si la red no es segura.
  - **WPA o WPA2 - Personal**: escriba la contraseña en **Clave precompartida**. Una vez configurada la red de su organización, también se configuran una contraseña o una clave de red. Escriba esta contraseña o clave de red para el valor PSK.
  - **WEP**

- **Configuración de proxy**: Las opciones son:
  - **Ninguna**: no se ha configurado ningún valor de proxy.
  - **Manual**: especifique la **dirección del servidor proxy** como una dirección IP y su **número de puerto**.
  - **Automático**: use un archivo para configurar el servidor proxy. Escriba la **URL del servidor proxy** (por ejemplo, `http://proxy.contoso.com`) que contiene el archivo de configuración.

## <a name="enterprise-profiles"></a>Perfiles de empresa

Los perfiles Enterprise usan el Protocolo de autenticación extensible (EAP) para autenticar las conexiones Wi-Fi. EAP se suele usar en empresas, ya que puede utilizar certificados para autenticar y proteger las conexiones, y configurar más opciones de seguridad.

- **Tipo de Wi-Fi**: elija **Empresa**.
- **SSID**: abreviatura de **identificador de conjunto de servicios**. Esta propiedad es el nombre real de la red inalámbrica a la que se conectan los dispositivos. Con todo, los usuarios solo ven el nombre de red que ha configurado al elegir la conexión.
- **Conectar automáticamente**: elija **Habilitar** para conectarse automáticamente a esta red cuando el dispositivo está en el intervalo. Elija **Deshabilitar** para impedir que los dispositivos se conecten automáticamente.
- **Red oculta**: elija **Habilitar** para ocultar esta red en la lista de redes disponibles en el dispositivo. No se difunde el SSID. Elija **Deshabilitar** para mostrar esta red en la lista de redes disponibles en el dispositivo.

- **Tipo de EAP**: elija el tipo Protocolo de autenticación extensible (EAP) que se usa para autenticar conexiones inalámbricas seguras. Las opciones son:

  - **EAP-FAST**: escriba la **Configuración de las credenciales de acceso protegido (PAC)** . Esta opción usa credenciales de acceso protegido para crear un túnel autenticado entre el cliente y el servidor de autenticación. Las opciones son:
    - **No usar (PAC)**
    - **Usar (PAC)** : si existe un archivo PAC, úselo.
    - **Usar y aprovisionar PAC**: cree y agregue el archivo PAC a los dispositivos.
    - **Usar y aprovisionar PAC anónimamente**: cree y agregue el archivo PAC a los dispositivos sin autenticación en el servidor.

  - **EAP-SIM**

  - **EAP-TLS**: Indique también:

    - **Confianza del servidor** - **Nombres de servidor de certificados**: **agregue** uno o varios nombres comunes usados en los certificados emitidos por la entidad de certificación (CA) de confianza. Si escribe esta información, puede omitir la ventana de confianza dinámica que se muestra en los dispositivos de los usuarios cuando se conectan a esta red Wi-Fi.
    - **Certificado raíz para validación del servidor**: elija uno o varios perfiles de certificado raíz de confianza existentes. Cuando el cliente se conecta a la red, estos certificados se presentan al servidor. Autentican la conexión.

    - **Autenticación de cliente** - **Certificado cliente para la autenticación del cliente (certificado de identidad)** : elija el perfil de certificado de cliente SCEP o PKCS que también se implementa en el dispositivo. Este certificado es la identidad presentada por el dispositivo al servidor para autenticar la conexión.

  - **EAP-TTLS**: Indique también:

    - **Confianza del servidor** - **Nombres de servidor de certificados**: **agregue** uno o varios nombres comunes usados en los certificados emitidos por la entidad de certificación (CA) de confianza. Si escribe esta información, puede omitir la ventana de confianza dinámica que se muestra en los dispositivos de los usuarios cuando se conectan a esta red Wi-Fi.
    - **Certificado raíz para validación del servidor**: elija uno o varios perfiles de certificado raíz de confianza existentes. Cuando el cliente se conecta a la red, estos certificados se presentan al servidor. Autentican la conexión.

    - **Autenticación de cliente**: elija un **método de autenticación**. Las opciones son:

      - **Nombre de usuario y contraseña**: pida al usuario un nombre de usuario y una contraseña para autenticar la conexión. Indique también:
        - **Método que no es EAP (identidad interna)** : elija cómo autenticar la conexión. Asegúrese de elegir el mismo protocolo que está configurado en su red Wi-Fi.

          Las opciones son: **Contraseña no cifrada (PAP)** , **Protocolo de autenticación por desafío mutuo (CHAP)** , **Microsoft CHAP (MS-CHAP)** o **Microsoft CHAP versión 2 (MS-CHAP v2)**

      - **Certificados**: elija el perfil de certificado de cliente SCEP o PKCS que también se implementa en el dispositivo. Este certificado es la identidad presentada por el dispositivo al servidor para autenticar la conexión.

      - **Privacidad de identidad (identidad externa)** : escriba el texto que se envía como respuesta a una solicitud de identidad EAP. Este texto puede ser cualquier valor, como `anonymous`. Durante la autenticación, esta identidad anónima se envía inicialmente, seguida de la identificación real enviada en un túnel seguro.

  - **LEAP**

  - **PEAP**: Indique también:

    - **Confianza del servidor** - **Nombres de servidor de certificados**: **agregue** uno o varios nombres comunes usados en los certificados emitidos por la entidad de certificación (CA) de confianza. Si escribe esta información, puede omitir la ventana de confianza dinámica que se muestra en los dispositivos de los usuarios cuando se conectan a esta red Wi-Fi.
    - **Certificado raíz para validación del servidor**: elija uno o varios perfiles de certificado raíz de confianza existentes. Cuando el cliente se conecta a la red, estos certificados se presentan al servidor. Autentican la conexión.

    - **Autenticación de cliente**: elija un **método de autenticación**. Las opciones son:

      - **Nombre de usuario y contraseña**: pida al usuario un nombre de usuario y una contraseña para autenticar la conexión. 

      - **Certificados**: elija el perfil de certificado de cliente SCEP o PKCS que también se implementa en el dispositivo. Este certificado es la identidad presentada por el dispositivo al servidor para autenticar la conexión.

      - **Privacidad de identidad (identidad externa)** : escriba el texto que se envía como respuesta a una solicitud de identidad EAP. Este texto puede ser cualquier valor, como `anonymous`. Durante la autenticación, esta identidad anónima se envía inicialmente, seguida de la identificación real enviada en un túnel seguro.

- **Configuración de proxy**: Las opciones son:
  - **Ninguna**: no se ha configurado ningún valor de proxy.
  - **Manual**: especifique la **dirección del servidor proxy** como una dirección IP y su **número de puerto**.
  - **Automático**: use un archivo para configurar el servidor proxy. Escriba la **URL del servidor proxy** (por ejemplo, `http://proxy.contoso.com`) que contiene el archivo de configuración.

## <a name="next-steps"></a>Pasos siguientes

Se crea el perfil, pero no hacen nada. Después, [asigne este perfil](device-profile-assign.md) y [supervise su estado](device-profile-monitor.md).

Configure las opciones de Wi-Fi en dispositivos [Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [iOS/iPadOS](wi-fi-settings-ios.md) y [Windows 10](wi-fi-settings-windows.md).
