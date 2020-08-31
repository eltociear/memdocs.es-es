---
title: Proceso de la incorporación de Intune
titleSuffix: Microsoft Intune
description: Este artículo ayuda con todos los detalles que se deben tener en cuenta a la hora de incorporar una solución solo en la nube de Microsoft Intune al entorno.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19de56bfab6e4f4cf2f1243c6cbaf98053e6ba5e
ms.sourcegitcommit: 46d4bc4fa73b22ae2a6a17a2d1cc6ec933a50e89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88663266"
---
# <a name="implement-your-microsoft-intune-plan"></a>Implementar el plan de Microsoft Intune

Durante la fase de incorporación, implementará Intune en su entorno de producción. El proceso de implementación consiste en la instalación y configuración de Intune y de las dependencias externas (si es necesario) en función de sus [requisitos de casos de uso](planning-guide-requirements.md).

En la siguiente sección se proporciona una información general del proceso de implementación de Intune que incluye requisitos y tareas de alto nivel.

## <a name="intune-requirements"></a>Requisitos de Intune

Los requisitos principales de Intune independiente son los siguientes:

- Suscripción a Enterprise Mobility + Security (EMS)/Intune

- Suscripción a Office 365 (para aplicaciones de Office y aplicaciones administradas de directivas de protección de aplicaciones)

- Certificado de APNs de Apple (para habilitar la administración de la plataforma de dispositivos iOS/iPadOS)

- Azure AD Connect (para la sincronización de directorios)

- Conector local de Intune para Exchange (para acceso condicional para Exchange local, si es necesario)

- Conector de certificado de Intune (para la implementación de certificado SCEP, si es necesario)

>[!TIP]
> Consulte la lista de [dispositivos compatibles](supported-devices-browsers.md) para ver todos los dispositivos que se pueden administrar con Intune.

## <a name="intune-implementation-process"></a>Proceso de implementación de Intune

Hemos identificado 13 tareas discretas para llevar a cabo una implementación de Intune. En función de sus requisitos empresariales, de la infraestructura existente y de la estrategia de administración de dispositivos, es posible que algunas de estas tareas ya se hayan llevado a cabo, mientras que otras podrían no ser aplicables a su plan.

### <a name="task-1-get-an-intune-subscription"></a>Tarea 1: Obtener una suscripción a Intune

Como se indica en la anterior sección de requisitos de Intune, se necesita una suscripción a EMS o a Intune. Si su organización no dispone de ella, póngase en contacto con Microsoft o con el equipo de cuentas de Microsoft con respecto a su interés en comprar Enterprise Mobility + Security (EMS) o Intune.

- Más información sobre [cómo comprar Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

### <a name="task-2-add-office-365-subscription"></a>Tarea 2: Agregar una suscripción a Office 365

Este paso es opcional. Necesita una suscripción a Office 365 si tiene pensado usar Exchange Online y administrar aplicaciones móviles de Office con las directivas de protección de aplicaciones. Si su organización no tiene ninguna suscripción a Office 365, póngase en contacto con Microsoft o con el equipo de cuentas de Microsoft con respecto a su interés en comprar Office 365.

- Más información sobre [cómo comprar Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

### <a name="task-3-add-users-groups-in-azure-ad"></a>Tarea 3: Agregar grupos de usuarios en Azure AD

Puede que necesite agregar usuarios o grupos de seguridad en Active Directory o Azure Active Directory en función de sus requisitos y escenarios de casos de uso de implementación de Intune. Revise sus usuarios y grupos de seguridad actuales en Active Directory o Azure Active Directory y determine si cumplen completamente sus necesidades. Al agregar usuarios y grupos de seguridad nuevos, se recomienda agregarlos en Active Directory y sincronizarlos con Azure Active Directory mediante Azure AD Connect.

- Más información sobre [cómo agregar usuarios o grupos en Intune](users-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect--->


### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Tarea 4: Asignar licencias de usuario de Office 365 e Intune

Todos los usuarios destinados a la implementación de Office 365 y EMS o Intune necesitarán una licencia asignada. Puede asignar licencias de Office 365 y de EMS o Intune en el Centro de administración de Microsoft 365.

- Más información sobre [cómo asignar licencias de Intune](licenses-assign.md).

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Tarea 5: Establecer Intune como entidad de administración de dispositivos móviles

Antes de que pueda comenzar la instalación, configuración, administración e inscripción de dispositivos con Intune, debe establecer Intune como entidad de administración de dispositivos.

- Obtenga más información sobre [cómo establecer la entidad de administración de dispositivos](mdm-authority-set.md).

### <a name="task-6-enable-device-platforms"></a>Tarea 6: Habilitar plataformas de dispositivos

De manera predeterminada, la mayoría de las plataformas de dispositivos están habilitadas, excepto para los dispositivos de Apple (iOS/iPadOS y Mac). Antes de que los dispositivos iOS/iPadOS se puedan inscribir y administrar en Intune, se debe habilitar la plataforma de dispositivos. Para ello, debe crear un certificado de inserción de MDM y agregarlo a Intune.

- Obtenga más información sobre [cómo habilitar la inscripción en los dispositivos de Apple](../enrollment/apple-mdm-push-certificate-get.md).

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Tarea 7: Agregar e implementar directivas de términos y condiciones

Intune admite las directivas de términos y condiciones. Agregue directivas de términos y condiciones según corresponda e impleméntelas en los grupos de destino en función de los requisitos y los casos de uso de la implementación de Intune.

- Más información sobre [cómo agregar e implementar directivas de términos y condiciones](../enrollment/terms-and-conditions-create.md).

### <a name="task-8-add-and-deploy-configuration-policies"></a>Tarea 8: Agregar e implementar directivas de configuración

Intune admite dos tipos de directivas de configuración: general y personalizada. Agregue directivas de configuración según corresponda e impleméntelas en los grupos de destino en función de los requisitos y los casos de uso de la implementación de Intune.

- Más información sobre [cómo agregar e implementar directivas de configuración](../configuration/device-profiles.md).

### <a name="task-9-add-and-deploy-resource-profiles"></a>Tarea 9: Agregar e implementar perfiles de recursos

Intune admite los perfiles de VPN, Wi-Fi y correo electrónico. Agregue estos perfiles según corresponda e impleméntelos en los grupos de destino en función de los requisitos y los casos de uso de la implementación de Intune.

- Obtenga más información sobre cómo [habilitar el acceso a los recursos de la empresa con Intune](../configuration/device-profiles.md).

### <a name="task-10-add-and-deploy-apps"></a>Tarea 10: Agregar e implementar aplicaciones

Intune admite la implementación de aplicaciones de almacén público, aplicaciones de línea de negocio y aplicaciones web. También puede administrar aplicaciones que tienen el SDK de Intune integrado si las asocia con directivas de protección de aplicaciones. Agregue aplicaciones según corresponda e impleméntelas en los grupos de destino en función de los requisitos y los casos de uso de la implementación de Intune.

- Obtenga más información sobre cómo [agregar e implementar aplicaciones](../apps/app-management.md).

### <a name="task-11-add-and-deploy-compliance-policies"></a>Tarea 11: Agregar e implementar directivas de cumplimiento

Intune admite las directivas de cumplimiento. Agregue directivas de cumplimiento según corresponda e impleméntelas en los grupos de destino en función de los requisitos y los casos de uso de la implementación de Intune.

- Más información sobre las [directivas de cumplimiento](../protect/device-compliance-get-started.md).

### <a name="task-12-enable-conditional-access-policies"></a>Tarea 12: Habilitar directivas de acceso condicional

Intune admite el acceso condicional para Exchange Online, Exchange local, SharePoint Online, Skype Empresarial Online y Dynamics CRM Online. Habilite y configure el acceso condicional según corresponda en función de los requisitos y los casos de uso de la implementación de Intune.

- Más información sobre el [acceso condicional](../protect/conditional-access.md).

### <a name="task-13-enroll-devices"></a>Tarea 13: Inscribir dispositivos

Intune admite iOS/iPadOS, Mac OS, Android, el escritorio de Windows y las plataformas de dispositivos de escritorio de Windows. Inscriba plataformas de dispositivos móviles según corresponda en función de los requisitos y los casos de uso de la implementación de Intune.

- Más información sobre [cómo inscribir dispositivos](../enrollment/device-enrollment.md).


## <a name="next-steps"></a>Pasos siguientes
Consulte instrucciones sobre las [pruebas y la validación de la implementación de Intune](planning-guide-test-validation.md).
