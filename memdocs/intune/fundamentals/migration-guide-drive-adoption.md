---
title: Impulso de la adopción de usuarios finales con acceso condicional
titleSuffix: Microsoft Intune
description: Sepa cómo usar el acceso condicional para impulsar la inscripción de Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 07/17/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca64791256acbdcd124ee79401d116962671dd71
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88909710"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Impulso de la adopción de usuarios finales con acceso condicional en Microsoft Intune

La habilitación de las características de acceso condicional con Intune, como el bloqueo de correo electrónico para dispositivos no inscritos, puede contribuir a impulsar la inscripción y el cumplimiento, pero no son necesarios para una correcta migración. Los requisitos de seguridad y los objetivos de adopción de la migración deben determinar el éxito.

## <a name="migration-campaign-with-conditional-access"></a>Campaña de migración con acceso condicional

Este es un método típico para mejorar una campaña de migración con acceso condicional:

1. Establezca reglas de acceso condicional que se apliquen a todos los usuarios, pero excluya específicamente los usuarios que tengan que migrar desde el proveedor de MDM antiguo. Puede crear un grupo de usuarios de Azure AD con todos los usuarios excluidos del acceso condicional.

2. A medida que se migren, quite los usuarios del grupo de exclusión de acceso condicional.

3. Una vez finalizada la migración, configure todas las directivas de acceso condicional para que se bloqueen de forma predeterminada a menos que Intune permita el acceso.

### <a name="advantages"></a>Ventajas

- Ofrece control de acceso para nuevas cuentas de usuario o cuentas de usuario que no se administraban mediante la solución anterior.

- Ofrece un período de gracia para los usuarios de la solución anterior a la migración.

- Minimiza la pérdida de productividad.

### <a name="disadvantages"></a>Desventajas

- Los usuarios de la solución anterior posiblemente puedan obtener acceso a recursos mediante dispositivos no administrados hasta que se habilite el acceso condicional para esos usuarios.


Se trata de un método entre otros. Es posible elegir un proceso más sencillo que aplace todo el acceso condicional hasta después de que se dé orden de inscripción a cada fase o un proceso más estricto que exija el acceso condicional desde el mismo principio y requiera compatibilidad completa para todos los accesos.

- Más información sobre el [acceso condicional](../protect/conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Lista de tareas para acceso condicional

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Tarea 1: determinación de cómo se va a implementar el acceso condicional

[Formas comunes de usar el acceso condicional](../protect/conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>Tarea 2: configuración del acceso condicional de Intune

Elija una de las siguientes opciones:

- [Configurar el acceso condicional en Azure Active Directory](/azure/active-directory/active-directory-conditional-access-azure-portal)

- [Configuración de la autenticación moderna híbrida](/office365/enterprise/hybrid-modern-auth-overview)

- [Configurar directivas de acceso condicional basado en la aplicación para Exchange Online](../protect/app-based-conditional-access-intune-create.md)

- [Configurar directivas de acceso condicional basado en la aplicación para SharePoint Online](../protect/app-based-conditional-access-intune-create.md)

- [Bloquear las aplicaciones que no usan la autenticación moderna (ADAL o MSAL)](../protect/app-modern-authentication-block.md) 

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre el [ciclo de migración habitual](migration-guide-cycle.md).