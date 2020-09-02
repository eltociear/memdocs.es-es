---
title: Inscripción del dispositivo iOS en la administración de gastos de telecomunicaciones con Intune
description: Obtenga información sobre cómo inscribir un dispositivo iOS en la administración de gastos de telecomunicaciones.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2017
ms.topic: end-user-help
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 1c43d2c4ae7ccda2cd0cf9283586a980eb166d22
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88912090"
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a>Inscripción del dispositivo iOS en la administración de gastos de telecomunicaciones

Su organización puede estar usando software de administración de gastos de telecomunicaciones para asegurarse de que sus planes de voz y datos se utilizan dentro de límites aceptables. Cuando haya completado la inscripción del dispositivo, se le pedirá que seleccione la categoría más apropiada para dicho dispositivo.

  ![Captura de la pantalla "selección de la categoría más apropiada para un dispositivo" en un dispositivo iOS. Muestra una selección de inscripciones personales o corporativas.](./media/ios-enroll-10-tem-select-best-category.png)

Seleccione la opción adecuada y recibirá una notificación para instalar la aplicación [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) en App Store. Con la aplicación Datalert su organización puede medir el uso de datos. Si la organización configuró la opción de inscripción profesional o educativa de Microsoft, se le pedirá que inicie sesión con su cuenta profesional o educativa. Si no se ha habilitado, deberá proporcionar información, como su número de teléfono, y verificar el dispositivo con un código para inscribirse en el servicio Datalert desde la aplicación.

  ![Captura de la pantalla de bienvenida de la aplicación Datalert, que le pregunta si desea pasar a la siguiente pantalla después de proporcionar una breve explicación sobre cómo Datalert puede ayudarle a sacar el máximo provecho de su plan de datos.](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a>Inscripción en Datalert con su cuenta profesional o educativa de Microsoft

> [!NOTE]
> Debe tener la aplicación [Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) instalada y activa en el teléfono para inscribirse de esta manera.

1. Seleccione __Enroll with Microsoft account__ (Inscribirse con cuenta Microsoft).

   ![Una imagen de la pantalla Configuración de la aplicación Datalert, que ofrece un campo de número de teléfono para inscribir un dispositivo en la mitad superior de la pantalla e "Inscribirse con cuenta Microsoft" en la parte inferior, siempre que tenga una cuenta de Microsoft Office 365 y una suscripción de Intune.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. Recibirá una notificación que indica que __"Datalert" desea abrir "Authenticator"__ . Seleccione __Abrir__.

   ![Una imagen de la ventana emergente que le pide al usuario que abra la aplicación Authenticator a solicitud de la aplicación Datalert.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. Inicie sesión con su __cuenta profesional o educativa de Microsoft__. La configuración de Datalert se ejecutará durante unos momentos y, luego, se debe completar. Pulse __Finalizar__ cuando se complete.

## <a name="enroll-into-datalert-using-your-phone-number"></a>Inscripción en Datalert con su número de teléfono

1. Indique el número de teléfono de su dispositivo.

   ![Captura de pantalla de la aplicación Datalert donde se solicita el número de teléfono.](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. Después, recibirá un código de verificación a través de un mensaje SMS. Escriba el código y pulse __Aceptar__.

   ![Captura de pantalla de la aplicación Datalert donde se solicita el código de verificación SMS.](./media/ios-enroll-13-tem-datalert-sms.png)

3. Una vez que haya proporcionado el código de verificación, se completará la instalación de Datalert. Pulse __Finalizar__ y podrá supervisar los datos desde la aplicación Datalert.

   ![Captura de pantalla de la aplicación Datalert con la supervisión del uso de datos de hoy en día.](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

Una vez inscrito, puede empezar a ver su uso de datos en la aplicación Datalert.

¿Aún necesita ayuda? Póngase en contacto con el departamento de soporte técnico de la empresa. Para averiguar su información de contacto, vaya al [sitio web del portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980).