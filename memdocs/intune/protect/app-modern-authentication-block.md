---
title: Bloqueo de aplicaciones sin autenticación moderna en Intune
titleSuffix: Microsoft Intune
description: Obtenga información sobre la autenticación moderna (ADAL) y de aplicaciones con Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/22/2020
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
ms.openlocfilehash: bd8070dd1584beac0744ebfae63aa4fd066fa2bf
ms.sourcegitcommit: b90d51f7ce09750e024b97baf6950a87902a727c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86022252"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Bloqueo de aplicaciones que no usan la autenticación moderna (ADAL)

> [!NOTE]
> Azure Active Directory (Azure AD) Authentication Library (ADAL) y Azure AD Graph API quedarán obsoletos próximamente. Para obtener más información, consulte [Actualización de aplicaciones para el uso de la biblioteca de autenticación de Microsoft (MSAL) y Microsoft Graph API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/update-your-applications-to-use-microsoft-authentication-library/ba-p/1257363).

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
