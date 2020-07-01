---
title: Bloqueo de aplicaciones sin autenticación moderna en Intune
titleSuffix: Microsoft Intune
description: Obtenga información sobre la autenticación moderna (ADAL) y de aplicaciones con Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, has-adal-ref
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a8e61f30cfc21d6dfebef2315296e60dadcb7f1
ms.sourcegitcommit: e2ef7231d3abaf3c925b0e5ee9f66156260e3c71
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85382822"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Bloqueo de aplicaciones que no usan la autenticación moderna (ADAL)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

El acceso condicional basado en la aplicación con directivas de protección de aplicaciones depende de aplicaciones que usan la [autenticación moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) que es una implementación de OAuth2. Las aplicaciones de escritorio y móviles de Office más recientes usan la autenticación moderna. Si bien, hay aplicaciones de terceros y aplicaciones de Office más antiguas que usan otros métodos de autenticación, como la autenticación básica y la autenticación basada en formularios.

## <a name="block-access-to-apps"></a>Bloqueo del acceso a las aplicaciones

Para bloquear el acceso a las aplicaciones que no usan la autenticación moderna, use las directivas de protección de aplicación de Intune para implementar acceso condicional. Para más información, consulte [Acceso condicional basado en aplicación con Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Información adicional

Para más información sobre el acceso condicional de Azure AD, consulte estos temas:
- [¿Qué es el acceso condicional en Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Funcionamiento del acceso condicional basado en aplicación](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Procedimientos para configurar SharePoint Online y Exchange Online para el acceso condicional de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Pasos siguientes

- [Acceso condicional basado en aplicación con Intune](app-based-conditional-access-intune.md)
