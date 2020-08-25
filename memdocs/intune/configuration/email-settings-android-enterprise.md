---
title: 'Configuración del correo electrónico de Android Enterprise en Microsoft Intune: Azure | Microsoft Docs'
description: Cree perfiles de correo electrónico de configuración de dispositivos que usen servidores de Exchange y recupere los atributos de Azure Active Directory. Habilite SSL o SMIME, autentique a los usuarios con certificados o con el nombre de usuario y la contraseña y sincronice el correo electrónico y las programaciones en dispositivos de perfil de trabajo Android con Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/11/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 99e4e037faf5253f92b4907f9b8746dbd58038eb
ms.sourcegitcommit: 8999e197f10fb72d1b82f30a599d1e588db237b7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "88146072"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Configuración del dispositivo Android Enterprise para definir el correo electrónico, la autenticación y la sincronización en Intune

En este artículo se enumeran y describen las diferentes opciones de configuración de correo electrónico que puede controlar en los dispositivos Android Enterprise. Como parte de su solución de administración de dispositivos móviles (MDM), use estos valores de configuración para configurar un servidor de correo electrónico, usar SSL para cifrar correos electrónicos y mucho más.

Como administrador de Intune, puede crear y asignar configuraciones de correo electrónico a dispositivos Android Enterprise en el perfil de trabajo.

Para más información sobre los perfiles de correo electrónico en Intune, consulte la [configuración de correo electrónico](email-settings-configure.md).

## <a name="before-you-begin"></a>Antes de comenzar

Cree un [perfil de configuración de dispositivo](email-settings-configure.md) (elija el perfil de trabajo) o cree una [directiva de configuración de aplicaciones](../apps/app-configuration-policies-use-android.md).

## <a name="android-enterprise"></a>Android Enterprise

- **Aplicación de correo electrónico**: seleccione **Gmail** o **Nine Work**.
- **Servidor de correo electrónico**: escriba el nombre de host del servidor de Exchange. Por ejemplo, escriba `outlook.office365.com`.
- **Atributo de nombre de usuario de AAD**: este nombre es el atributo que Intune obtiene de Azure Active Directory (Azure AD). Intune genera dinámicamente el nombre de usuario que usa este perfil. Las opciones son:

  - **Nombre principal de usuario**: obtiene el nombre, como `user1` o `user1@contoso.com`.
  - **Nombre de usuario**: obtiene solo el nombre, como `user1`.

- **Atributo de dirección de correo electrónico de AAD**: este nombre es el atributo de correo electrónico que Intune obtiene de Azure AD. Intune genera dinámicamente la dirección de correo electrónico que este perfil usa. Las opciones son:
  - **Nombre principal de usuario**:  usa el nombre principal completo, como `user1@contoso.com` o `user1`, como dirección de correo electrónico.
  - **Dirección SMTP principal**: use la dirección SMTP principal, como `user1@contoso.com`, para iniciar sesión en Exchange.

- **Método de autenticación**: Seleccione **Nombre de usuario y contraseña** o **Certificados** como método de autenticación que el perfil de correo electrónico usa.
  - Si seleccionó **Certificado**, seleccione un SCEP cliente o un perfil de certificado PKCS que haya creado anteriormente para autenticar la conexión de Exchange.
- **SSL**: elija **Habilitar** para usar la comunicación de Capa de sockets seguros (SSL) al enviar y recibir correos electrónicos y comunicarse con el servidor Exchange.
- **Cantidad de correo electrónico para sincronizar**: elija la cantidad de tiempo de correo electrónico que desea sincronizar. También puede seleccionar **Ilimitado** para sincronizar todo el correo electrónico disponible.
- **Tipo de contenido para sincronizar** (solo Nine Work): elija qué datos desea sincronizar en los dispositivos. Las opciones son:
  - **Contactos**: elija **Habilitar** para permitir que los usuarios finales sincronicen contactos con sus dispositivos.
  - **Calendario**: elija **Habilitar** para permitir que los usuarios finales sincronicen el calendario con sus dispositivos.
  - **Tareas**: elija **Habilitar** para permitir que los usuarios finales sincronicen todas las tareas con sus dispositivos.

## <a name="next-steps"></a>Pasos siguientes

[Asigne el perfil](device-profile-assign.md) y [supervise el estado](device-profile-monitor.md).

También puede crear perfiles de correo electrónico para dispositivos [Android Samsung Knox](email-settings-android.md), [iOS y iPadOS](email-settings-ios.md) y [Windows 10 y versiones posteriores](email-settings-windows-10.md).
