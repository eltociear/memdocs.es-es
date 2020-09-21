---
title: Directivas para las aplicaciones de Office
titleSuffix: Microsoft Intune
description: Comprenda las directivas disponibles para aplicaciones de Office.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca558b40ad3d006aa764819a0fbccc16a03fd0e2
ms.sourcegitcommit: d4ed7b4369389fd8ab07d28a7fa507797b6c6e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89644036"
---
# <a name="policies-for-office-apps"></a>Directivas para las aplicaciones de Office

Intune proporciona directivas específicamente para aplicaciones de Microsoft Office. Puede seleccionar opciones concretas para crear directivas de administración de aplicaciones móviles para aplicaciones móviles de Office que se conectan a servicios de Microsoft 365. Hay muchas directivas para aplicaciones de Office que se pueden agregar a Microsoft Intune y aplicar a grupos de usuarios finales.

Estos son ejemplos de algunas de las directivas de aplicaciones de Office:
- Microsoft Word: *Desactivar Vista protegida para los datos adjuntos abiertos en Outlook*
- Microsoft Visio: *Bloquear la ejecución de macros en archivos de Office procedentes de Internet*
- Microsoft Project: *Permitir ubicaciones de confianza en la red*
- Microsoft Publisher: *Nivel de seguridad de la automatización de Publisher*
- Microsoft PowerPoint: *Desactivar Vista protegida para los datos adjuntos abiertos en Outlook*

> [!NOTE]
> Al elegir configurar la directiva de cada aplicación específica, se proporcionan detalles adicionales de la directiva. Puede filtrar la lista de directivas de Office para seleccionar rápidamente las directivas de **Línea de base de seguridad** recomendadas.

También puede proteger el acceso a los buzones locales de Exchange mediante la creación de directivas de protección de aplicaciones de Intune para Outlook para iOS/iPadOS y Android habilitadas con autenticación moderna híbrida. Antes de usar esta característica, debe cumplir los requisitos de uso del servicio de directivas de nube de Office. Las directivas de protección de aplicaciones no son compatibles con otras aplicaciones que se conectan a los servicios de Exchange o SharePoint locales. Puede encontrar información relacionada en [Introducción al servicio de directivas de la nube de Office para las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service).

## <a name="prerequisites"></a>Prerrequisitos

Debe cumplir los requisitos para usar directivas para las aplicaciones de Office. Para más información, consulte [Requisitos para usar el servicio de directiva de la nube de Office](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service#requirements-for-using-the-office-cloud-policy-service).

## <a name="to-add-an-office-app-policy"></a>Adición de una directiva de aplicación de Office

Después de configurar Intune para la organización, puede crear una directiva de aplicación de Office.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Aplicaciones** > **Directivas para las aplicaciones de Office** > **Crear**.
3. Agregue los siguientes valores:
    - **Nombre:** escriba un nombre (necesario) para la nueva directiva.
    - **Descripción:** (opcional) escriba una descripción.
    - **Seleccionar tipo**: seleccione cómo se aplicará esta configuración de directiva.
    - **Seleccionar grupo:** seleccione el grupo para esta configuración de directiva.
    - **Configurar directivas:** seleccione la directiva de Office que quiere aplicar. Puede ordenar la lista proporcionada por la directiva, la plataforma, la aplicación, la recomendación y el estado.
4. Seleccione **Crear**. La directiva se crea y aparece en la tabla del panel **Configuración de directivas**.

   > [!TIP]
   > En el panel **Configuración de directivas** se proporciona el **estado de mantenimiento** de cada directiva.

## <a name="additional-information"></a>Información adicional

- [Información general del servicio de directivas de la nube de Office para las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service)
- [Usar la configuración de directivas para administrar los controles de privacidad de Aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/privacy/manage-privacy-controls)
- [Usar las preferencias para administrar los controles de privacidad de Office para Mac](https://docs.microsoft.com/deployoffice/privacy/mac-privacy-preferences)
- [Usar las preferencias para administrar los controles de privacidad de Office en dispositivos iOS](https://docs.microsoft.com/deployoffice/privacy/ios-privacy-preferences)
- [Usar la configuración de directivas para administrar los controles de privacidad de Office en Android](https://docs.microsoft.com/deployoffice/privacy/android-privacy-controls)

## <a name="next-steps"></a>Pasos siguientes

- [Supervisión de información y asignaciones de aplicaciones con Microsoft Intune](apps-monitor.md)