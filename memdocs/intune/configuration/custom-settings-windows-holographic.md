---
title: 'Configuración personalizada: dispositivos Windows Holographic for Business | Microsoft Docs'
description: Agregue o cree un perfil personalizado para usar la configuración OMA-URI para dispositivos con Windows Holographic for Business en Microsoft Intune, incluido Microsoft Hololens. Puede establecer las opciones de los proveedores de servicios de configuración (CSP) de directivas AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates y ApplicationLaunchRestrictions.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/18/2020
ms.article: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.topic: reference
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f37550bcfd8105b9cf5ea51c1bfa0d9305721348
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83990073"
---
# <a name="use-custom-settings-for-windows-holographic-for-business-devices-in-intune"></a>Uso de la configuración personalizada para dispositivos Windows Holographic for Business en Intune

Con Microsoft Intune, puede agregar o crear una configuración personalizada para los dispositivos Windows Holographic for Business mediante "perfiles personalizados". Los perfiles personalizados son una característica de Intune diseñada para agregar una configuración de dispositivo y características que no están integradas Intune.

Los perfiles personalizados de Windows Holographic for Business usan la configuración OMA-URI (identificador uniforme de recursos de Open Mobile Alliance) para configurar diferentes características. Esta configuración la suelen usar los fabricantes de dispositivos móviles para controlar las características en el dispositivo.

Windows Holographic for Business ofrece muchas opciones de configuración de proveedores de servicios de configuración (CSP). Para obtener una introducción a CSP, consulte [Introducción a los proveedores de servicios de configuración (CSP) para los profesionales de las TI](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Para conocer los CSP específicos admitidos por Windows Holographic, consulte [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (CSP admitidos en Windows Holographic).

Si busca una configuración determinada, recuerde que el [perfil de restricción de dispositivos de Windows Holographic for Business](device-restrictions-windows-holographic.md) incluye muchas configuraciones integradas. Por lo tanto, es posible que no necesite especificar valores personalizados.

En este artículo se muestra cómo crear un perfil personalizado para dispositivos Windows Holographic for Business. También se incluye una lista de las configuraciones OMA-URI recomendadas.

## <a name="before-you-begin"></a>Antes de comenzar

[Cree un perfil personalizado de Windows 10](custom-settings-configure.md#create-the-profile).

## <a name="custom-oma-uri-settings"></a>Configuración OMA-URI personalizada

**Agregar**: Escriba los valores siguientes:

- **Nombre**: Escriba un nombre único para el valor OMA-URI que le ayude a identificarlo en la lista de valores de configuración.
- **Descripción**: escriba una descripción con información general sobre la configuración y otros detalles importantes.
- **OMA-URI** (distingue mayúsculas de minúsculas): escriba la configuración OMA-URI que quiere usar.
- **Tipo de datos**: seleccione el tipo de datos que se va a usar para esta configuración OMA-URI. Las opciones son:

  - String
  - Cadena (archivo XML)
  - Fecha y hora
  - Integer
  - Punto flotante
  - Boolean
  - Base64 (archivo)

- **Valor**: escriba el valor de datos que quiere asociar con la configuración OMA-URI especificada. El valor depende del tipo de datos que ha seleccionado. Por ejemplo, si selecciona **Fecha y hora**, seleccione el valor en un selector de fecha.

Después de agregar algunos valores de configuración, puede seleccionar **Exportar**. Haga clic en **Exportar** para crear una lista de todos los valores agregados en un archivo de valores separados por comas (.csv).

## <a name="recommended-custom-settings"></a>Configuración personalizada recomendada

La siguiente configuración es útil para dispositivos que ejecuten Windows Holographic for Business:

### <a name="allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Integer<br/>0: no permitido<br/>1: permitido (valor predeterminado)|

### <a name="allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Integer<br/>0: no se permite el servicio de actualización <br/>1: se permite el servicio de actualización (valor predeterminado).|

### <a name="allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Integer<br/>0: no permitido<br/>1: permitido (valor predeterminado)|

### <a name="requireupdateapproval"></a>[RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Esta opción está disponible en RS5 (compilación 17763) y versiones anteriores. A partir de 19H1 (compilación 18362), use [Windows Update para empresas](../protect/windows-update-for-business-configure.md).<br/><br/>Integer<br/>0: no configurado. El dispositivo instala todas las actualizaciones aplicables.<br/>1: el dispositivo solo instala las actualizaciones que son aplicables y que están en la lista Actualizaciones aprobadas. Establezca esta directiva en 1 si el departamento de TI quiere controlar la implementación de actualizaciones en dispositivos, por ejemplo, cuando es necesario realizar pruebas antes de la implementación.|

### <a name="scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Entero 0-23, donde 0 = 12 a.m. y 23 = 11 p.m.<br/>El valor predeterminado es 3.|

### <a name="updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Esta opción está disponible en RS5 (compilación 17763) y versiones anteriores. A partir de 19H1 (compilación 18362), use [Windows Update para empresas](../protect/windows-update-for-business-configure.md).<br/><br/>String<br/>URL: el dispositivo busca actualizaciones desde el servidor de WSUS en la URL especificada.<br/>No configurado: el dispositivo busca actualizaciones desde Microsoft Update.|

### <a name="approvedupdates"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Importante**<br/>Debe leer y aceptar los CLUF de la actualización en nombre de los usuarios finales. Si no lo hace, es un incumplimiento de las obligaciones legales o contractuales.|Nodo para las aprobaciones de actualización y la aceptación de CLUF en nombre del usuario final.<br/><br/>Para más información, consulte [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) (CSP de actualización).|

### <a name="applicationlaunchrestrictions"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Importante**<br/>El artículo de AppLocker CSP usa ejemplos XML con escape. Para configurar los valores con perfiles personalizados de Intune, debe usar XML sin formato.|String<br/>Para más información, consulte [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) (CSP de AppLocker).|

### <a name="deletionpolicy"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Integer<br/>0 - eliminar inmediatamente cuando el dispositivo vuelva a un estado sin usuarios activos<br/>1 - eliminar cuando se alcance el umbral de capacidad de almacenamiento (valor predeterminado)<br/>2 - eliminar cuando se alcancen el umbral de capacidad de almacenamiento y el umbral de inactividad de perfil|

### <a name="enableprofilemanager"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Boolean<br/>True - habilitar<br/>False - deshabilitar (valor predeterminado)|

### <a name="profileinactivitythreshold"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Integer<br/>El valor predeterminado es 30.|

### <a name="storagecapacitystartdeletion"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Integer<br/>El valor predeterminado es 25.|

### <a name="storagecapacitystopdeletion"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Tipo de datos|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Integer<br/>El valor predeterminado es 50.|

## <a name="find-the-policies-you-can-configure"></a>Buscar las directivas que se pueden configurar

Puede encontrar una lista completa de todos los proveedores de servicios de configuración (CSP) que admite Windows Holographic en [CSP admitidos en Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). No todas las configuraciones son compatibles con todas las versiones de Windows Holographic. En la tabla de [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (CSP admitidos en Windows Holographic) se enumeran las versiones compatibles con cada CSP.

Además, Intune no admite todas las configuraciones que aparecen en [CSPs supported in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) (CSP admitidos en Windows Holographic). Para saber si Intune admite la configuración que quiere, abra el artículo correspondiente a dicha configuración. En la página de cada configuración se muestra la operación que admite. Para trabajar con Intune, la configuración debe ser compatible con las operaciones **Add** o **Replace**.

## <a name="next-steps"></a>Pasos siguientes

[Asigne el perfil](device-profile-assign.md) y [supervise su estado](device-profile-monitor.md).

Cree un [perfil personalizado en dispositivos Windows 10](custom-settings-windows-10.md).

Más información sobre los [perfiles personalizados](custom-settings-configure.md) de Intune.
