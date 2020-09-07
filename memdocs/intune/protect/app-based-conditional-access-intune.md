---
title: Acceso condicional basado en aplicación con Intune
titleSuffix: Microsoft Intune
description: Obtenga información sobre el acceso condicional basado en la aplicación con Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1619f3dde57b002ce8884e4af7d4a02e3d71b9f
ms.sourcegitcommit: fde92731a7e27c892d32c63f515cf19545e02ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992766"
---
# <a name="app-based-conditional-access-with-intune"></a>Acceso condicional basado en aplicación con Intune

Las [directivas de protección de aplicaciones de Intune](../apps/app-protection-policy.md) ayudan a proteger los datos de la empresa en dispositivos inscritos en Intune. También puede usar directivas de protección de aplicaciones en dispositivos que poseen los empleados que no están inscritos para administración en Intune. En este caso, aunque la empresa no administre el dispositivo, deberá asegurarse de que los datos y los recursos de la empresa están protegidos.

El acceso condicional basado en la aplicación y la administración de aplicaciones cliente agregan una capa de seguridad al garantizar que solo las aplicaciones cliente que admiten las directivas de protección de aplicaciones de Intune pueden acceder a Exchange Online y a otros servicios de Microsoft 365.

> [!NOTE]
> Una aplicación administrada es aquella que tiene las directivas de protección de aplicaciones aplicadas y puede administrarse mediante Intune.

Puede bloquear las aplicaciones de correo electrónico integradas en iOS/iPadOS y Android cuando solo permita a la aplicación Microsoft Outlook acceder a Exchange Online. Además, puede bloquear las aplicaciones que no tienen directivas de protección de aplicaciones de Intune aplicadas para que no puedan acceder a SharePoint Online.

## <a name="prerequisites"></a>Requisitos previos

Antes de crear una directiva de acceso condicional basado en la aplicación, debe tener:

- **Enterprise Mobility + Security (EMS)** o una **suscripción Premium de Azure Active Directory (AD)**
- Licencia para EMS o Azure AD por parte de los usuarios

Para obtener más información, consulte los [precios de Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) o los [precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

## <a name="supported-apps"></a>Aplicaciones compatibles

Puede encontrar una lista de las aplicaciones que admiten el acceso condicional basado en la aplicación en la [Documentación de referencia técnica sobre el acceso condicional de Azure Active Directory](/azure/active-directory/active-directory-conditional-access-technical-reference).

El acceso condicional basado en la aplicación [también admite aplicaciones de línea de negocio (LOB)](app-modern-authentication-block.md), pero dichas aplicaciones deben usar la [autenticación moderna de Microsoft 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a). 

## <a name="how-app-based-conditional-access-works"></a>Funcionamiento del acceso condicional basado en aplicación

En este ejemplo, el administrador ha aplicado directivas de protección de aplicaciones a la aplicación Outlook, seguidas de una regla de acceso condicional que agrega la aplicación Outlook a una lista aprobada de aplicaciones que pueden usarse al obtener acceso al correo electrónico corporativo.

> [!NOTE]
> El siguiente diagrama de flujo se puede usar con otras aplicaciones administradas.

![Proceso del acceso condicional basado en la aplicación ilustrado en un gráfico de flujo](./media/app-based-conditional-access-intune/ca-intune-common-ways-3.png)

1. El usuario intenta autenticarse en Azure AD desde la aplicación Outlook.

2. Al usuario se le redirige a la tienda de aplicaciones para instalar una aplicación de agente al intentar autenticarse por primera vez. La aplicación de agente puede ser Microsoft Authenticator para iOS o el Portal de empresa de Microsoft para dispositivos Android.

   Si los usuarios intentan usar una aplicación nativa de correo electrónico, se les redirige a la tienda de aplicaciones para instalar la aplicación Outlook.

3. La aplicación de agente se instala en el dispositivo.

4. La aplicación de agente inicia el proceso de registro de Azure AD que crea un registro de dispositivo en Azure AD. No se trata del mismo proceso que para la inscripción de administración de dispositivos móviles (MDM), pero este registro resulta necesario para que las directivas de acceso condicional se puedan aplicar en el dispositivo.

5. La aplicación de agente verifica la identidad de la aplicación. Hay un nivel de seguridad para que la aplicación de agente pueda validar si la aplicación está autorizada para que el usuario la utilice.

6. La aplicación de agente envía el identificador de cliente de la aplicación a Azure AD como parte del proceso de autenticación de usuario para comprobar si se encuentra en la lista aprobada de directivas.

7. Azure AD permite al usuario autenticarse y usar la aplicación en función de la lista aprobada de directivas. Si la aplicación no se encuentra en la lista, Azure AD deniega el acceso a la aplicación.

8. La aplicación Outlook se comunica con el servicio en la nube de Outlook para iniciar la comunicación con Exchange Online.

9. El servicio en la nube de Outlook se comunica con Azure AD para recuperar el token de acceso al servicio Exchange Online para el usuario.

10. La aplicación Outlook se comunica con Exchange Online para recuperar el correo electrónico corporativo del usuario.

11. El correo electrónico corporativo se entrega en el buzón de correo del usuario.

## <a name="next-steps"></a>Pasos siguientes
[Creación de una directiva de acceso condicional basado en la aplicación](app-based-conditional-access-intune-create.md)

[Bloqueo de aplicaciones que no usan la autenticación moderna](app-modern-authentication-block.md)