---
title: Auditoría, exportación o eliminación de datos personales
titleSuffix: Microsoft Intune
description: Obtenga más información sobre cómo auditar, exportar o eliminar datos personales.
keywords: RGPD, datos personales y privacidad
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 9/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5d792df5a4a8690751d7d140aa7fa89191aedb1b
ms.sourcegitcommit: d6cbd1a1c2926064e074e3431471534eb142c905
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2020
ms.locfileid: "90012636"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Auditoría, exportación o eliminación de datos personales en Intune

Los administradores de Intune pueden usar los registros de auditoría para realizar un seguimiento de las actividades en torno a los datos personales. Los administradores también pueden exportar y eliminar los datos personales.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Auditoría de los datos personales

Los registros de auditoría proporcionan a los administradores de inquilinos un registro de las actividades que generan un cambio en Microsoft Intune. Los registros de auditoría están disponibles para muchas tareas de administración y normalmente permiten crear, actualizar (editar), eliminar y asignar acciones. También se pueden revisar las tareas remotas que generan eventos de auditoría. Estos registros de auditoría pueden contener datos personales de los usuarios cuyos dispositivos estén inscritos en Intune.  

Por motivos de seguridad, Intune podrá mantener los registros de auditoría para las acciones de usuario y de dispositivo durante un período de un año. Estos registros se eliminan automáticamente tras el período de retención de un año.

Para revisar los registros de auditoría, vea [Registros de auditoría para actividades de Intune](../fundamentals/monitor-audit-logs.md). 

Los administradores no pueden eliminar los registros de auditoría.

Estos eventos de auditoría se conservan durante un año. Los administradores de inquilinos pueden solicitar registros de auditoría mediante [este formulario de solicitud de soporte técnico](https://privacy.microsoft.com/en-US/privacy-questions?).

## <a name="export-personal-data"></a>Exportación de los datos personales

Los administradores pueden exportar los datos personales del usuario final, incluidas las cuentas, los datos del servicio y los registros asociados para cumplir con las solicitudes de derechos del interesado. Depende de usted y de su organización decidir si se debe proporcionar al titular una copia de los datos personales o si existe algún motivo comercial legítimo para retenerlos. Si decide proporcionarlos, puede hacerlo mediante una copia del documento real, una versión redactada adecuadamente o una captura de pantalla de las partes que considere oportuno compartir.

Para exportar datos personales de un usuario, puede usar: 
- la hoja de dispositivos de MDM de Intune para exportar una lista de dispositivos. También puede copiar los datos del dispositivo directamente.
- el [script Export-IntuneData.ps1](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Eliminación de los datos personales del usuario final

Hay tres formas de eliminar los datos personales de la administración de Intune:
- Eliminación del usuario de Azure Active Directory
- Restablecimiento de los valores de fábrica del dispositivo
- Eliminación automática del usuario

### <a name="delete-a-user-from-intune"></a>Eliminación de un usuario de Intune

Para eliminar de Intune los datos personales de un usuario final, un administrador debe [eliminar el usuario de Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Cuando se elimina el usuario de Azure AD (eliminación permanente), Intune recibe la señal de eliminación de Azure AD y, después, comienza a purgar automáticamente todos los datos personales del usuario del servicio Intune. La información del usuario se eliminará del servicio de Intune en un plazo de 30 días a partir de la acción de eliminación.

### <a name="reset-device-to-factory-settings"></a>Restablecimiento de los valores de fábrica del dispositivo
La restauración de los valores de fábrica permite restaurar todos los datos personales y de empresa, así como las opciones de configuración, a los valores originales de fábrica. Resulta una opción muy útil para proporcionar un dispositivo a otro empleado. Los archivos de usuario, las aplicaciones instaladas por el usuario y la configuración no predeterminada se eliminan y estos datos se quitan del servicio Intune al cabo de 30 días tras la acción de eliminación.

### <a name="user-self-removal-from-intune-management"></a>Eliminación automática de usuarios desde la administración de Intune
Los usuarios pueden quitar sus dispositivos [Android, Apple o Windows](../user-help/unenroll-your-device-from-intune-android.md) personales desde la administración de Intune sin la asistencia del administrador.   

### <a name="retire"></a>Retirar
La acción **Retirar** quita los datos aprovisionados por Intune, como las aplicaciones de empresa, los datos sobre las aplicaciones que administra Intune, la configuración de directivas y los perfiles de correo electrónico que se aprovisionan mediante Intune. Esta acción deja los datos personales del usuario en el dispositivo.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Eliminación de un inquilino de Microsoft Intune

Si un cliente de inquilino de Intune cancela su cuenta de Intune, todos los datos del inquilino se eliminan en los 180 días posteriores al cierre de la cuenta de Intune. Si el inquilino de Azure AD está asociado a otras suscripciones empresariales de Microsoft (Azure, Microsoft 365), solo se eliminan los datos del cliente de Intune. El recurso de inquilino de Azure AD se mantiene para su uso en otras suscripciones. Si la cuenta de Intune es la única suscripción asociada al inquilino de Azure AD, se elimina el inquilino, así como todos los recursos y datos del cliente.

## <a name="next-steps"></a>Pasos siguientes

Descubra cómo [ver y corregir los datos personales](privacy-data-view-correct.md) en Intune.
