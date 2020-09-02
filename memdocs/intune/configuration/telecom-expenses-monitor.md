---
title: Configuración de un servicio de administración de gastos de telecomunicaciones en Microsoft Intune | Microsoft Docs
titleSuffix: ''
description: Integre Microsoft Intune con el servicio de administración de gastos de telecomunicaciones Saaswedo para supervisar el uso de datos y establecer umbrales o límites sobre el administrador de dispositivos Android y dispositivo iOS e iPadOS.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/08/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cabf3bad447ef3db8250d14fcb376cb86aefad3
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88907556"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Configuración de un servicio de administración de gastos de telecomunicaciones en Intune

Con Intune, puede administrar gastos de telecomunicaciones a partir del uso de datos en los dispositivos móviles propiedad de la organización. Intune se integra con el servicio de [administración de gastos de telecomunicaciones Datalert](http://datalert.biz/get-started) de Saaswedo. Datalert es una solución de administración de gastos de telecomunicaciones en tiempo real que le permite administrar el uso de datos de telecomunicaciones. Esta solución puede ayudarlo a evitar cargos inesperados por datos e itinerancia en sus dispositivos administrados por Intune.

La integración con Datalert le permite establecer, supervisar y aplicar límites sobre el uso de datos nacionales y de itinerancia. Cuando los límites superan los umbrales, se desencadenan alertas automáticamente. También se puede configurar el servicio para que aplique diferentes acciones a usuarios o grupos, como deshabilitar la itinerancia o superar el umbral. La consola de administración de Datalert incluye informes que muestran información sobre la supervisión y el uso de datos.

La siguiente imagen muestra cómo se integra Intune con Datalert:

> [!div class="mx-imgBorder"]
> ![Diagrama de integración de Intune y Datalert](./media/telecom-expenses-monitor/tem-datalert-intune-solution-diagram.png)

Para usar el servicio Datalert con Intune, hay algunas opciones de configuración en Datalert e Intune. En este artículo se muestra cómo:

- Configurar las opciones de la consola de Datalert para conectar el servicio Datalert a Intune
- Confirmar que esta conexión está activa y habilitada en Intune
- Usar Intune para agregar la aplicación Datalert a los dispositivos
- Desactivar el servicio Datalert e Intune (opcional)

## <a name="supported-platforms"></a>Plataformas compatibles

- Dispositivos del administrador de dispositivos Android 4.4 y versiones posteriores que sean compatibles con Knox (Samsung)
- iOS 8.0 y versiones posteriores
- IPadOS 13.0 y versiones más recientes

## <a name="prerequisites"></a>Requisitos previos

- Una suscripción a Microsoft Intune y acceso al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)
- Una suscripción a [Datalert](http://www.datalert.biz/) (se abre el sitio web de Datalert)

## <a name="telecom-expense-management-providers"></a>Proveedores de administración de gastos de telecomunicaciones

Intune se integra con los siguientes proveedores de administración de gastos de telecomunicaciones:

- [Servicio de administración de gastos de telecomunicaciones Datalert de Saaswedo](http://www.datalert.biz/) (se abre el sitio web de Datalert)

## <a name="deploy-the-intune-and-datalert-solution"></a>Implementación de la solución integrada de Intune y Datalert

### <a name="step-1-connect-the-datalert-service-to-intune"></a>Paso 1: Conexión del servicio Datalert a Intune

1. Inicie sesión en la consola de administración de Datalert con sus credenciales de administrador.

2. En la consola, vaya a la pestaña **Settings** (Configuración) > **MDM configuration** (Configuración de MDM).

3. Seleccione **Unblock** (Desbloquear). Esta opción le permite cambiar o actualizar la configuración de la página.

4. En **Intune / Datalert Connection** (Conexión de Intune/Datalert) > **Server MDM** (MDM del servidor), seleccione **Microsoft Intune**.

5. En **Azure AD domain** (Dominio de Azure AD), escriba su identificador de inquilino de Azure. Seleccione **Connection** (Conexión).

    Al seleccionar esta opción, el servicio Datalert se registra en Intune y confirma que no hay ninguna conexión a Datalert existente. Después de unos momentos, aparece una página de inicio de sesión de Microsoft, seguida de la autenticación de Azure para Datalert.

6. En la página de autenticación de Microsoft, seleccione **Aceptar**.

    Se le redirigirá a una página de **agradecimiento** de Datalert que se cierra transcurridos unos minutos. Datalert valida la conexión y muestra marcas de verificación verdes junto a los elementos que se han validado. Si se produce un error en la validación, verá un mensaje en rojo. Póngase en contacto con el soporte técnico de Datalert para solicitar ayuda.

    En la imagen siguiente se muestran las marcas de verificación verdes cuando la conexión se realiza correctamente:

      > [!div class="mx-imgBorder"]
      > ![Página de Datalert en la que se muestra una conexión correcta](./media/telecom-expenses-monitor/tem-datalert-connection.png)

7. En **Datalert App / ADAL Consent** (Aplicación Datalert/Consentimiento ADAL), establezca el conmutador en **On** (Activo). En la página de autenticación de Microsoft, seleccione **Aceptar**.

    Se le redirigirá a una página de **agradecimiento** de Datalert que se cierra transcurridos unos minutos. Datalert valida la conexión y muestra marcas de verificación verdes junto a los elementos que se han validado. Si se produce un error en la validación, verá un mensaje en rojo. Póngase en contacto con el soporte técnico de Datalert para solicitar ayuda.

    En la imagen siguiente se muestran las marcas de verificación verdes cuando la conexión se realiza correctamente:

      > [!div class="mx-imgBorder"]
      > ![Página de Datalert en la que se muestra una conexión correcta](./media/telecom-expenses-monitor/tem-datalert-adal-consent.png)

8. En **MDM Profiles management (optional)** (Administración de perfiles de MDM [opcional]), establezca el modificador en **On** (Activo). Esta configuración permite a Datalert leer los perfiles disponibles en Intune para ayudarle a configurar las directivas. 

    En la página de autenticación de Microsoft, seleccione **Aceptar**.

    Se le redirigirá a una página de **agradecimiento** de Datalert que se cierra transcurridos unos minutos. Datalert valida la conexión y muestra marcas de verificación verdes junto a los elementos que se han validado. Si se produce un error en la validación, verá un mensaje en rojo. Póngase en contacto con el soporte técnico de Datalert para solicitar ayuda.

    En la imagen siguiente se muestran las marcas de verificación verdes cuando la conexión se realiza correctamente:

    > [!div class="mx-imgBorder"]
    > ![Página de Datalert en la que se muestra una conexión correcta](./media/telecom-expenses-monitor/tem-datalert-mdm-profiles.png)

### <a name="step-2-confirm-telecom-expense-management-is-active-in-intune"></a>Paso 2: Confirmación de que la administración de gastos de telecomunicaciones está activa en Intune

Después de completar el paso 1, la conexión se habilita automáticamente. En Intune, el estado de la conexión muestra **Activo**. Para confirmar que el estado es activo, siga estos pasos:

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Administración de inquilinos** > **Conectores y tokens** > **Administración de gastos de telecomunicaciones**. Busque el estado de conexión **Activo**:

    > [!div class="mx-imgBorder"]
    > ![Página de Intune en la que se muestra el estado de conexión Activo de Datalert](./media/telecom-expenses-monitor/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-devices"></a>Paso 3: Implementación de la aplicación Datalert en los dispositivos

Para confirmar que solo se recopila el uso de datos de líneas propiedad de la organización, asegúrese de:

- Crear categorías de dispositivos en Intune
- Dirigir la aplicación Datalert solo a teléfonos de la organización

En esta sección se indican estos pasos.

#### <a name="create-device-categories-and-device-groups-mapped-to-your-categories"></a>Creación de categorías de dispositivos y grupos de dispositivos asignados a las categorías

En función de las necesidades de su organización, cree al menos dos categorías de dispositivos (tales como Organización y Personal). Después, cree grupos de dispositivos dinámicos para cada categoría. Puede crear más categorías para su organización, según resulte necesario.

Para crear categorías de dispositivos en Intune, consulte el artículo sobre [asignación de dispositivos a grupos](../enrollment/device-group-mapping.md).

Estas categorías se muestran a los usuarios durante la inscripción (consulte el artículo sobre la [inscripción de dispositivos Android](../enrollment/android-enroll.md)). Dependiendo de la categoría que elijan los usuarios, el dispositivo inscrito se trasladará al grupo de dispositivos correspondiente.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del panel Agregar directiva](./media/telecom-expenses-monitor/tem-dynamic-membership-rules.png)

#### <a name="add-the-datalert-app-to-intune"></a>Incorporación de la aplicación Datalert a Intune

En los pasos siguientes se agrega la aplicación Datalert. Como ejemplo, se usa iOS/iPadOS. En los artículos sobre la [incorporación de aplicaciones](../apps/apps-add.md) y el [uso de etiquetas de ámbito](../fundamentals/scope-tags.md) se incluye información más específica sobre estos pasos.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Aplicaciones** > **Todas las aplicaciones** > **Agregar**.

2. Seleccione el **tipo de aplicación**. Por ejemplo, para iOS/iPadOS, seleccione **Aplicación de la Tienda: iOS/iPadOS**.

3. En **Buscar en App Store**, escriba **Datalert** para encontrar la aplicación Datalert.

4. Elija la aplicación **Datalert** > **Seleccionar**:

    > [!div class="mx-imgBorder"]
    > ![Incorporación de la aplicación Datalert desde App Store a las aplicaciones cliente de Intune](./media/telecom-expenses-monitor/tem-select-app-from-apple-app-store.png)

5. Escriba las propiedades adicionales, como información de la aplicación y etiquetas de ámbito:

    > [!div class="mx-imgBorder"]
    > ![Escriba las propiedades de la aplicación, incluido el nombre y la descripción, elija el sistema operativo y otras opciones de configuración para la aplicación en Intune](./media/telecom-expenses-monitor/tem-steps-to-create-the-app.png).

6. Seleccione **Aceptar** > **Agregar** para guardar los cambios. La aplicación Datalert se muestra en la lista.

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Asignar la aplicación Datalert al grupo de dispositivos empresariales

1. En **Aplicaciones** > **Todas las aplicaciones**, seleccione la aplicación Datalert que agregó en el paso anterior.

2. Seleccione **Asignaciones** > **Agregar grupo**. Elija cómo se asigna la aplicación. En el artículo sobre [asignación de aplicaciones a grupos en Intune](../apps/apps-deploy.md) se incluyen más detalles sobre esta configuración.

    En estos pasos, elegirá si quiere que sea obligatorio u opcional para el grupo instalar la aplicación. En el ejemplo siguiente se muestra la instalación como obligatoria. Cuando sea necesario, los usuarios deben instalar la aplicación Datalert después de inscribir el dispositivo.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla del panel Agregar directiva](./media/telecom-expenses-monitor/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-organization-phone-lines-to-the-datalert-console"></a>Paso 4: Incorporación de líneas de teléfono de la organización a la consola de Datalert

Los servicios Intune y Datalert están ahora configurados para comunicarse entre sí. A continuación, agregue las líneas de teléfono de pago de la organización a la consola de Datalert. Especifique umbrales y acciones para las infracciones de uso de telefonía móvil o itinerancia. Puede agregar manualmente líneas telefónicas de pago corporativas a la consola de Datalert o puede agregarlas automáticamente una vez que el dispositivo se inscriba en Intune.

Para establecer estos elementos, vaya a la página de [configuración de Datalert para Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (se abre el sitio web de Datalert). En la pestaña **Settings** (Configuración), siga los pasos que se indican en el asistente de instalación.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del panel Agregar directiva](./media/telecom-expenses-monitor/tem-add-phone-lines-to-datalert-console.png)

El servicio Datalert ya está activo. Ahora comienza a supervisar el uso de datos y a deshabilitar los datos móviles y de itinerancia en los dispositivos que superan los límites de uso configurados.

## <a name="end-user-enrollment"></a>Inscripción de usuarios finales

En cuanto a la experiencia del usuario final, los siguientes artículos pueden resultar de ayuda:

- [Inscripción del dispositivo iOS/iPadOS en la administración de gastos de telecomunicaciones](../user-help/enroll-your-device-with-telecom-expense-management-ios.md)
- [Inscripción del dispositivo Android en la administración de gastos de telecomunicaciones](../user-help/enroll-your-device-with-telecom-expense-management-android.md)

## <a name="turn-off-the-datalert-service"></a>Desactivación del servicio Datalert

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Administración de inquilinos** > **Conectores y tokens** > **Administración de gastos de telecomunicaciones**.
2. Establezca **Habilitar la administración de gastos de telecomunicaciones y bloquear los datos móviles o de itinerancia en dispositivos que hayan excedido las cuotas de uso configuradas.** en **Deshabilitar**.
3. Guarde los cambios mediante **Guardar**.

> [!IMPORTANT]
> Si deshabilita el servicio Datalert en Intune:
>
> - Se anulan todas las acciones que se aplicaron a los dispositivos debido a infracciones anteriores de los límites de uso.
> - Ya no se bloqueará para los usuarios el acceso a los datos y la itinerancia.
> - Intune seguirá recibiendo señales del servicio, pero las ignorará.

## <a name="next-steps"></a>Pasos siguientes

Los informes de uso de datos están disponibles en la consola de administración de Datalert de Saaswedo.