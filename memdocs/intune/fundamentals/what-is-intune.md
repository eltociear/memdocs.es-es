---
title: ¿Qué es Microsoft Intune? - Azure | Microsoft Docs
description: Obtenga información sobre cómo Microsoft Intune es el componente de administración de dispositivos móviles (MDM) y de administración de aplicaciones móviles (MAM) de la solución Enterprise Mobility + Security y sobre cómo ayuda a proteger los datos de la empresa.
keywords: ¿Qué es Intune?
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/23/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28a5bc7a1ee00e9595c50d274605af1b33c1ea90
ms.sourcegitcommit: 411e9d93cbafc7585f5a0f9a05097fe589de804f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85332811"
---
# <a name="microsoft-intune-is-an-mdm-and-mam-provider-for-your-devices"></a>Microsoft Intune es un proveedor de MDM y MAM para los dispositivos.

Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Puede controlar cómo se usan los dispositivos de la organización, incluidos los teléfonos móviles, las tabletas y los equipos portátiles. También puede configurar directivas específicas para controlar las aplicaciones. Por ejemplo, puede evitar que se envíen mensajes de correo electrónico a personas ajenas a la organización. Intune también permite que las personas de la organización usen sus dispositivos personales para la escuela o el trabajo. En los dispositivos personales, Intune ayuda a que los datos de la organización permanezcan protegidos., y puede aislar los datos de la organización de los datos personales.

Intune es parte del [conjunto de aplicaciones Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) de Microsoft. Intune se integra con Azure Active Directory (Azure AD) para controlar quién tiene acceso y a qué se puede tener acceso. También se integra con Azure Information Protection para la protección de los datos. Se puede usar con el conjunto de productos de Microsoft 365. Por ejemplo, puede implementar Microsoft Teams, OneNote y otras aplicaciones de Microsoft 365 en los dispositivos. Esta característica permite que las personas de su organización sean productivas en todos sus dispositivos, a la vez que mantiene protegida la información de la organización con las directivas que crea.

[![Imagen de una arquitectura de Intune](./media/what-is-intune/intunearch_sm.png )](./media/what-is-intune/intunearchitecture.svg#lightbox)

Intune permite:

- Elegir estar al 100 % en una nube con Intune, o aplicar una [administración conjunta](https://docs.microsoft.com/configmgr/comanage/overview) con Configuration Manager e Intune.
- Establecer reglas y configurar los valores de los dispositivos personales y de la organización para tener acceso a los datos y las redes.
- Implementar y autenticar aplicaciones en dispositivos, tanto locales como móviles.
- Proteger la información de su empresa controlando el modo en que los usuarios acceden a la información y la comparten.
- Garantizar que los dispositivos y las aplicaciones sean compatibles con los requisitos de seguridad.

## <a name="manage-devices"></a>Administrar los dispositivos

En Intune, adoptará un enfoque adaptado a sus necesidades para administrar los dispositivos. En el caso de los dispositivos que pertenecen a la organización, puede que desee tener un control total sobre los dispositivos, incluida la configuración, las características y la seguridad. En este enfoque, los dispositivos y los usuarios de estos dispositivos "se inscriben" en Intune. Una vez inscritos, reciben las reglas y los valores de configuración a través de las directivas configuradas en Intune. Por ejemplo, puede establecer requisitos de contraseña y PIN, crear una conexión VPN, configurar la protección contra amenazas y mucho más.

En el caso de dispositivos personales, o bring-your-own device (BYOD), es posible que los usuarios no quieran que los administradores de su organización tengan control total. En este enfoque, proporcione opciones a los usuarios. Por ejemplo, los usuarios [inscriben](../enrollment/device-enrollment.md) sus dispositivos si desean tener acceso completo a los recursos de la organización. O bien, si estos usuarios solo quieren acceder al correo electrónico o a Microsoft Teams, use directivas de protección de aplicaciones que requieran autenticación multifactor (MFA) para usar estas aplicaciones.

Cuando los dispositivos se inscriben y administran en Intune, los administradores pueden:

- Ver los dispositivos inscritos y obtener un inventario de los dispositivos que acceden a los recursos de la organización.
- Configurar los dispositivos para que cumplan los estándares de seguridad y mantenimiento. Por ejemplo, es probable que desee bloquear dispositivos liberados.
- Inserte certificados en los dispositivos para que los usuarios puedan acceder fácilmente a la red Wi-Fi, o usar una VPN para conectarse a la red.
- Vea informes sobre usuarios y dispositivos que son compatibles y no compatibles.
- Quite los datos de la organización si un dispositivo se pierde, lo roban o ya no se usa.

**Recursos en línea**:

- [¿Qué es la inscripción de dispositivos?](../enrollment/device-enrollment.md)

- [Aplicación de la configuración y características en dispositivos con perfiles de dispositivos](../configuration/device-profiles.md)

- [Proteger dispositivos con Microsoft Intune](../protect/device-protect.md)

### <a name="try-the-interactive-guide"></a>Pruebe la guía interactiva
La guía interactiva [Administración de dispositivos con Microsoft Endpoint Manager](https://mslearn.cloudguides.com/en-us/guides/Manage%20devices%20with%20Microsoft%20Endpoint%20Manager) le guiará a través del Centro de administración de Microsoft Endpoint Manager para mostrarle cómo administrar y proteger aplicaciones para dispositivos móviles y de escritorio.</br></br>

> [!VIDEO https://mslearn.cloudguides.com/en-us/guides/Manage%20devices%20with%20Microsoft%20Endpoint%20Manager]

## <a name="manage-apps"></a>Administrar aplicaciones

La administración de aplicaciones móviles (MAM) en Intune está diseñada para proteger los datos de la organización en el nivel de aplicación, incluidas las aplicaciones personalizadas y las aplicaciones de tienda. La administración de aplicaciones se puede usar en dispositivos propiedad de la organización y en dispositivos personales.

Cuando las aplicaciones se administran en Intune, los administradores pueden:

- Agregar y asignar aplicaciones móviles a grupos de usuarios y dispositivos, incluidos usuarios de grupos específicos, dispositivos en grupos específicos, etc.
- Configurar las aplicaciones para que se inicien o ejecuten con la configuración específica habilitada, y actualizar las aplicaciones existentes que ya están en el dispositivo.
- Ver los informes en los que se usan las aplicaciones y realizar un seguimiento de su uso.
- Realizar un borrado selectivo quitando únicamente los datos de la organización de las aplicaciones.

Una de las maneras en que Intune proporciona seguridad de aplicaciones móviles es a través de las **[directivas de protección de aplicaciones](../apps/app-protection-policy.md)** . Las directivas de protección de aplicaciones:

- Utilizan la identidad de Azure AD para aislar los datos de la organización de los datos personales. De este modo, la información personal se mantiene al margen del departamento de TI de la organización. A los datos a los que se accede mediante credenciales de la organización se les proporciona protección de seguridad adicional.
- Ayudan a proteger el acceso a dispositivos personales mediante la restricción de las acciones que los usuarios pueden realizar, como copiar y pegar, guardar y ver.
- Pueden crearse e implementarse en dispositivos que estén inscritos en Intune, que estén inscritos en otro servicio MDM o que no estén inscritos en ningún servicio MDM. En los dispositivos inscritos, las directivas de protección de aplicaciones pueden agregar un nivel de protección adicional.

Por ejemplo, un usuario inicia sesión en un dispositivo con sus credenciales de organización. La identidad de su organización permite el acceso a los datos que se deniegan a su identidad personal. Dado que se usan datos de la organización, las directivas de protección de aplicaciones controlan cómo se guardan y se comparten los datos. Cuando los usuarios inician sesión con su identidad personal, no se aplican las mismas protecciones. De esta manera, el departamento de TI controla los datos de la organización, mientras que los usuarios finales mantienen el control y la privacidad de sus datos personales.

Además, puede usar Intune con los demás servicios de EMS. Esta característica proporciona la seguridad de la aplicación móvil de la organización más allá de lo que se incluye con el sistema operativo y las aplicaciones. Las aplicaciones administradas con EMS tienen acceso a un conjunto más amplio de características de protección de datos y aplicaciones móviles.

![Imagen en la que se muestran los niveles de seguridad de datos de la administración de aplicaciones](./media/what-is-intune/managing-mobile-apps.png)

## <a name="compliance-and-conditional-access"></a>Cumplimiento y acceso condicional

Intune se integra con Azure AD para permitir una amplia gama de escenarios de control de acceso. Por ejemplo, requerir que los dispositivos móviles sean compatibles con los estándares de la organización definidos en Intune antes de tener acceso a los recursos de red, como el correo electrónico o SharePoint. También puede bloquear los servicios para que estén disponibles solo para un conjunto específico de aplicaciones móviles. Por ejemplo, puede bloquear Exchange Online de modo que solo Outlook o Outlook Mobile tengan acceso a él.

**Recursos en línea**:

- [Establecimiento de reglas en los dispositivos para permitir el acceso a recursos de su organización](../protect/device-compliance-get-started.md)

- [Formas habituales de usar el acceso condicional con Intune](../protect/conditional-access-intune-common-ways-use.md)

## <a name="how-to-get-intune"></a>Obtención de Intune

Intune está disponible:

- Como un [servicio de Azure](https://go.microsoft.com/fwlink/?linkid=2090973) independiente.
- Incluido con [Microsoft 365 ](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune) y [Microsoft 365 Government](https://www.microsoft.com/microsoft-365/government).
- Como [administración de dispositivos móviles en Office 365 ](https://support.office.com/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd), que consta de algunas características limitadas de Intune.

Intune se usa en muchos sectores, como el [administrativo](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description) o el [educativo](https://www.microsoft.com/en-us/education/intune), así como en [dispositivos de quiosco o dedicados](../configuration/kiosk-settings.md), para la fabricación, la venta minorista, etc.

## <a name="next-steps"></a>Pasos siguientes

- Estos son algunos de los [problemas empresariales comunes que Intune ayuda a resolver](common-scenarios.md).
- Comience con una [prueba de 30 días de Intune](free-trial-sign-up.md).
- Planifique la [migración a Intune ](migration-guide.md).
- Con la evaluación gratuita o la suscripción, recorra el [Inicio rápido: Crear un perfil de dispositivo de correo para iOS](../configuration/quickstart-email-profile.md).
