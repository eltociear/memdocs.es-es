---
title: 'Tutorial: Protección del correo electrónico de Exchange Online en dispositivos administrados'
titleSuffix: Microsoft Intune
description: Aprenda a proteger Exchange Online con las directivas de cumplimiento de Intune para iOS y el acceso condicional de Azure AD para exigir dispositivos administrados y la aplicación Outlook.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: feabc9f889d0bce83c96df92f8154784e31b84e4
ms.sourcegitcommit: fde92731a7e27c892d32c63f515cf19545e02ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88996714"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Tutorial: Protección del correo electrónico de Exchange Online en dispositivos administrados

Obtenga información sobre cómo usar las directivas de cumplimiento de dispositivos con acceso condicional para asegurarse de que los dispositivos iOS pueden acceder al correo electrónico de Exchange Online solo si se administran mediante Intune y con una aplicación de correo electrónico aprobada.

En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Crear una directiva de cumplimiento para dispositivos iOS para establecer las condiciones que debe cumplir un dispositivo para que se considere compatible.
> * Crear una directiva de acceso condicional de Azure Active Directory (Azure AD) que exige que los dispositivos iOS se inscriban en Intune, cumplan las directivas de Intune y usen la aplicación móvil de Outlook aprobada para acceder al correo electrónico de Exchange Online.

Si no dispone de ninguna suscripción a Intune, [regístrese para obtener una cuenta de evaluación gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Requisitos previos

Necesitará a un inquilino de prueba con las siguientes suscripciones para este tutorial:

- Azure Active Directory Premium ([evaluación gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))

- Suscripción de Aplicaciones de Microsoft 365 para empresas que incluya Exchange ([evaluación gratuita](https://go.microsoft.com/fwlink/p/?LinkID=510938))

Antes de comenzar, cree un perfil de dispositivo de prueba para dispositivos iOS siguiendo los pasos descritos en [Inicio rápido: Creación de un perfil de dispositivo de correo para iOS/iPadOS](../configuration/quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Iniciar sesión en Intune

Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) como [administrador global](../fundamentals/users-add.md#types-of-administrators) o [administrador del servicio](../fundamentals/users-add.md#types-of-administrators) de Intune. Si ha creado una suscripción de prueba de Intune, la cuenta con la que creó la suscripción es el administrador global.

## <a name="create-the-ios-device-compliance-policy"></a>Creación de una directiva de cumplimiento para dispositivos iOS

Configure una directiva de cumplimiento para dispositivos Intune para establecer las condiciones que debe cumplir un dispositivo para que se considere compatible. Para este tutorial, se creará una directiva de cumplimiento para dispositivos iOS. Las directivas de cumplimiento son específicas de la plataforma, por lo que necesita una directiva de cumplimiento independiente para cada plataforma de dispositivo que va a evaluar.

1. Seleccione **Dispositivos** > **Directivas de cumplimiento** > **Crear directiva**.

2. En **Nombre**, escriba **Prueba de directiva de cumplimiento de iOS**.

3. En **Descripción**, escriba **Prueba de directiva de cumplimiento de iOS**.

4. Para **Plataforma**, seleccione **iOS/iPadOS**.

5. Seleccione **Configuración** > **Correo electrónico**.

   1. Junto a **Requerir que los dispositivos móviles tengan un perfil de correo electrónico administrado**, seleccione **Requerir**.

   2. Seleccione **Aceptar**.

   ![Configuración de la directiva de cumplimiento de correo electrónico para requerir un perfil de correo electrónico administrado](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)

6. Seleccione **Estado del dispositivo**. Junto a **Dispositivos con Jailbreak**, seleccione **Bloquear** y luego **Aceptar**.

7. Seleccione **Seguridad del sistema** y escriba el valor de la **Contraseña**. Para este tutorial, seleccione la siguiente configuración recomendada:

   - En **Requerir una contraseña para desbloquear dispositivos móviles**, seleccione **Requerir**.

   - En **Contraseñas sencillas**, seleccione **Bloquear**.

   - En **Longitud mínima de contraseña**, escriba **4**.

     > [!TIP]
     > Los valores predeterminados que aparecen atenuados y en cursiva son solo recomendaciones. Debe reemplazar los valores que son recomendaciones para configurar una opción.

   - Para **Tipo de contraseña requerida**, elija **Alfanumérica**.

   - En **Máximo de minutos tras bloqueo de pantalla antes de solicitar la contraseña**, elija **Inmediatamente**.

   - En **Expiración de contraseña (días)** , escriba **41**.

   - En **Número de contraseñas anteriores para impedir su reutilización**, escriba **5**.
 
   ![Configuración de la contraseña para la directiva de cumplimiento de correo electrónico](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Seleccione **Aceptar** y, luego, **Aceptar**.

9. Seleccione **Crear**.

## <a name="create-the-conditional-access-policy"></a>Creación de la directiva de acceso condicional

Ahora se va a crear una directiva de acceso condicional que requiere que todas las plataformas de dispositivo se inscriban en Intune y cumplan la directiva de cumplimiento de Intune para que puedan acceder a Exchange Online. También se necesita la aplicación Outlook para el acceso al correo electrónico. Las directivas de acceso condicional se pueden configurar en el portal de Azure AD o en el portal de Intune. Como ya estamos en el portal de Intune, vamos a crear la directiva aquí.

1. En Intune, seleccione **Seguridad de los puntos de conexión** > **Acceso condicional** > **Nueva directiva**.

2. En **Nombre**, escriba **Probar directiva para el correo electrónico de Microsoft 365**.

3. En **Asignaciones**, seleccione **Usuarios y grupos**. En la pestaña **Incluir**, seleccione **Todos los usuarios**, y luego seleccione **Listo**.

4. En **Asignaciones**, seleccione **Acciones o aplicaciones en la nube**. Puesto que queremos proteger el correo electrónico de Microsoft 365 Exchange Online, lo seleccionaremos siguiendo estos pasos:

   1. En la pestaña **Incluir**, elija **Seleccionar aplicaciones**.

   2. Elija **Seleccionar**. 

   3. En la lista de aplicaciones, seleccione **Office 365 Exchange Online** y después elija **Seleccionar**. 

   4. Seleccione **Listo**.
  
   ![Seleccione la aplicación Office 365 Exchange Online](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. En **Asignaciones**, seleccione **Condiciones** > **Plataformas de dispositivo**.

   1. En **Configurar**, seleccione **Sí**.

   2. En la pestaña **Incluir**, seleccione **Cualquier dispositivo** y luego seleccione **Listo**. 

   3. Vuelva a seleccionar **Listo**.

   ![Incluir cualquier dispositivo](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. En **Asignaciones**, seleccione **Condiciones** > **Aplicaciones cliente**.

   1. En **Configurar**, seleccione **Sí**.

   2. Para este tutorial, seleccione **Aplicaciones móviles y clientes de escritorio** y **Clientes de autenticación moderna** (que hace referencia a aplicaciones como Outlook para iOS y Outlook para Android). Desactive todas las demás casillas.

   3. Seleccione **Listo** y después vuelva a seleccionar **Listo**.

   ![Selección de aplicaciones y clientes](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. En **Controles de acceso**, seleccione **Conceder**.

   1. En el panel **Conceder**, seleccione **Conceder acceso**.

   2. Seleccione **Requerir que el dispositivo esté marcado como compatible**.

   3. Seleccione **Requerir aplicación cliente aprobada**.

   4. En **Para varios controles**, seleccione **Requerir todos los controles seleccionados**. Esta configuración garantiza que ambos requisitos que ha seleccionado se aplican cuando un dispositivo intenta acceder al correo electrónico.

   5. Elija **Seleccionar**.

   ![Selección de controles](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. En **Habilitar directiva**, seleccione **Activar**.

   ![Habilitar directiva](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Seleccione **Crear**.

## <a name="try-it-out"></a>Haga la prueba

Con las directivas que se han creado, cualquier dispositivo iOS que intente iniciar sesión en el correo electrónico de Microsoft 365 tendrá que inscribirse en Intune y usar la aplicación móvil de Outlook para iOS/iPadOS. Para probar este escenario en un dispositivo iOS, intente iniciar sesión en Exchange Online con las credenciales de un usuario en su inquilino de prueba. Se le pedirá que inscriba el dispositivo e instale la aplicación móvil de Outlook.

1. Para realizar pruebas en un iPhone, vaya a **Configuración** > **Contraseñas y cuentas** > **Agregar cuenta** > **Exchange** .

2. Escriba la dirección de correo electrónico de un usuario en su inquilino de prueba y después presione **Siguiente**.

3. Presione **Iniciar sesión**.

4. Escriba la contraseña del usuario de prueba y luego presione **Iniciar sesión**.

5. Aparece un mensaje que dice que el dispositivo debe administrarse para tener acceso al recurso, junto con una opción para inscribirlo.

## <a name="clean-up-resources"></a>Limpieza de recursos

Cuando ya no se necesiten las directivas de prueba, puede quitarlas.
1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) como administrador global o administrador de servicios de Intune.

2. Seleccione **Dispositivos** > **Directivas de cumplimiento**.

3. En la lista **Nombre de directiva**, seleccione el menú contextual ( **...** ) de la directiva de prueba y después seleccione **Eliminar**. Seleccione **Aceptar** para confirmar.

4. Seleccione **Seguridad de los puntos de conexión** > **Acceso condicional**.

5. En la lista **Nombre de directiva**, seleccione el menú contextual ( **...** ) de la directiva de prueba y después seleccione **Eliminar**. Seleccione **Sí** para confirmar.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, se han creado las directivas que exigen que los dispositivos iOS se inscriban en Intune y usen la aplicación Outlook para acceder al correo electrónico de Exchange Online. Para obtener información sobre cómo usar Intune con acceso condicional para proteger otras aplicaciones y servicios, incluidos los clientes de Exchange ActiveSync para Microsoft 365 Exchange Online, consulte la [configuración del acceso condicional](conditional-access.md).
