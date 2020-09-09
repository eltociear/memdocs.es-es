---
title: Retirada o borrado de los dispositivos mediante Microsoft Intune - Azure | Microsoft Docs
description: Retire o borre un dispositivo en un dispositivo con Android, perfil de trabajo Android, iOS/iPadOS, macOS o Windows mediante Microsoft Intune. Elimine también un dispositivo de Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/27/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c36b46cedb69ae0ce9d5559797fba78f5f7ab7f6
ms.sourcegitcommit: 7f71d6f776df3ac28e5da3f8c926c88626483ce9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "89564285"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Eliminación de dispositivos mediante el borrado, la retirada o la anulación manual de la inscripción del dispositivo

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Mediante las acciones **Retirar** o **Borrar**, puede quitar de Intune los dispositivos que ya no son necesarios, que se van a reasignar o que han desaparecido. Los usuarios también pueden emitir un comando remoto desde el Portal de empresa de Intune para los dispositivos que están inscritos en Intune.

> [!NOTE]
> Antes de eliminar un usuario de Azure Active Directory (Azure AD), use la acción **Borrar** o **Retirar** para todos los dispositivos asociados a ese usuario. Si elimina usuarios que tienen dispositivos administrados desde Azure AD, Intune ya no podrá borrar o retirar esos dispositivos.

## <a name="wipe"></a>Eliminación de datos

La acción **Borrar** restaura un dispositivo a su configuración de fábrica predeterminada. Los datos de usuario se conservan si decide activar la casilla **Conservar el estado de inscripción y la cuenta de usuario**. De lo contrario, se quitarán todos los datos, las aplicaciones y las configuraciones.

|Acción de borrado|**Conservar el estado de inscripción y la cuenta de usuario**|Quitado de la administración de Intune|Descripción|
|:-------------:|:------------:|:------------:|------------|
|**Borrar**| No activada | Sí | Borra todas las cuentas de usuario, los datos, las directivas de MDM y la configuración. Restablece el sistema operativo a su configuración y estado predeterminados.|
|**Borrar**| Activada | No | Borra todas las directivas de MDM. Conserva los datos y las cuentas de usuario. Restablece la configuración del usuario a los valores predeterminados. Restablece el sistema operativo a su configuración y estado predeterminados.|


> [!NOTE]
> La acción de borrado no está disponible para los dispositivos iOS/iPadOS inscritos con la inscripción de usuario.

La opción **Conservar el estado de inscripción y la cuenta de usuario** solo está disponible para Windows 10 versión 1709 o posterior.

Las directivas de MDM se volverán a aplicar la próxima vez que el dispositivo se conecte a Intune.

Un borrado es útil para restablecer un dispositivo antes de dárselo a otro usuario o en el caso de que el dispositivo se haya perdido o lo hayan robado. Tenga cuidado al seleccionar **Borrar**. Los datos del dispositivo no se pueden recuperar.

### <a name="wiping-a-device"></a>Borrado de un dispositivo

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Seleccione **Dispositivos** > **Todos los dispositivos**.
4. Seleccione el nombre del dispositivo que quiere borrar.
5. En el panel en el que se muestra el nombre del dispositivo, haga clic en **Borrar**.
6. Para Windows 10 versión 1709 y posteriores, también tiene la opción **Borrar el dispositivo, pero mantener el estado de inscripción y la cuenta de usuario asociada**. 
    
    |Se conserva durante un borrado |No se conserva|
    | -------------|------------|
    |Cuentas de usuario asociadas con el dispositivo|Archivos de usuario|
    |Estado del equipo \(unión a un dominio, unido a Azure AD)| Aplicaciones instaladas por el usuario \(tienda y aplicaciones de Win32)|
    |Inscripción de la Administración de dispositivos móviles (MDM)|Configuración del dispositivo no predeterminada|
    |Aplicaciones instaladas por OEM \(tienda y aplicaciones de Win32)||
    |Perfil de usuario||
    |Datos de usuario que se encuentran fuera del perfil de usuario||
    |Inicio de sesión automático del usuario|| 
    
7. Realiza un **borrado del dispositivo y sigue borrando incluso en caso de que este pierda energía.** La opción garantiza que no se pueda eludir la acción de borrado mediante la desactivación del dispositivo. Esta opción seguirá intentando restablecer el dispositivo hasta que se complete de forma correcta. En algunas configuraciones, esta acción puede hacer que el dispositivo [no se pueda reiniciar](troubleshoot-device-actions.md#wipe-action).        
8. Para confirmar el borrado, haga clic en **Sí**.

Si el dispositivo está encendido y conectado, la acción **Borrar** se propaga por todos los tipos de dispositivos en menos de 15 minutos.

## <a name="retire"></a>Retirar

La acción **Retirar** elimina los datos de las aplicaciones administradas (si procede), la configuración y los perfiles de correo electrónico asignados con Intune. El dispositivo se quita de la administración de Intune. Esto sucede la próxima vez que el dispositivo se registra y recibe la acción remota **Retirar**. El dispositivo seguirá apareciendo en Intune hasta que se registra. Si quiere quitar dispositivos obsoletos de inmediato, use en su lugar la [acción Eliminar](devices-wipe.md#delete-devices-from-the-intune-portal).

**Retirar** deja los datos personales del usuario en el dispositivo.  

En las tablas siguientes se describen los datos que se eliminan y el efecto de la acción **Retirar** en los datos que permanecen en el dispositivo después de eliminar los datos de la empresa.

### <a name="ios"></a>iOS

|Tipo de datos|iOS|
|-------------|-------|
|Aplicaciones de empresa y datos asociados instalados por Intune.|**Aplicaciones instaladas mediante el Portal de empresa:** Para las aplicaciones que están ancladas al perfil de administración, se eliminan todas las aplicaciones y los datos de la aplicación. Estas aplicaciones incluyen aplicaciones instaladas originalmente desde App Store y que posteriormente se administran como aplicaciones de empresa, a menos que la aplicación esté configurada para no desinstalarse al quitar el dispositivo. <br /><br /> **Aplicaciones de Microsoft que usan la administración de aplicaciones móviles y se instalaron desde App Store:** Para las aplicaciones que no están administradas por el Portal de empresa, se quitan los datos de la aplicación de empresa que están protegidos por cifrado de la administración de aplicaciones móviles (MAM) en el almacenamiento local de la aplicación. Los datos que están protegidos mediante el cifrado de MAM fuera de la aplicación permanecen cifrados e inutilizables, pero no se quitan. No se quitarán las aplicaciones ni los datos de la aplicación personales.|
|Configuración|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|
|Configuración de perfil de Wi-Fi y VPN|Quitado.|
|Configuración de perfil de certificado|Certificados eliminados y revocados.|
|Agente de administración|Se quitará el perfil de administración.|
|Correo electrónico|Se borran los perfiles de correo electrónico que se aprovisionan mediante Intune. Se elimina el correo electrónico almacenado en caché en el dispositivo.|
|Separación de Azure AD|Se quita el registro de Azure AD.|

### <a name="android-device-administrator"></a>Administrador de dispositivos Android

|Tipo de datos|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Vínculos web|Quitado.|Quitado.|
|Aplicaciones no administradas de Google Play|Se mantendrán instalados los datos y las aplicaciones. <br /> <br />Se quitan los datos de la aplicación de empresa que están protegidos por cifrado de la administración de aplicaciones móviles (MAM) en el almacenamiento local de la aplicación. Los datos que están protegidos mediante el cifrado de MAM fuera de la aplicación permanecen cifrados e inutilizables, pero no se quitan. |Se mantendrán instalados los datos y las aplicaciones. <br /> <br />Se quitan los datos de la aplicación de empresa que están protegidos por cifrado de la administración de aplicaciones móviles (MAM) en el almacenamiento local de la aplicación. Los datos que están protegidos mediante el cifrado de MAM fuera de la aplicación permanecen cifrados e inutilizables, pero no se quitan.|
|Aplicaciones de línea de negocio no administradas|Se mantendrán instalados los datos y las aplicaciones.|Las aplicaciones se desinstalan y se quitan los datos locales de la aplicación. No se quitan los datos que se encuentran fuera de la aplicación (por ejemplo, en una tarjeta SD).|
|Aplicaciones administradas de Google Play|Se quitan los datos de la aplicación. La aplicación no se elimina. Los datos protegidos mediante el cifrado Administración de aplicaciones móviles (MAM) fuera de la aplicación (por ejemplo, las tarjetas SD) permanecen cifrados e inutilizables, pero no se quitan.|Se quitan los datos de la aplicación. La aplicación no se elimina. Los datos protegidos mediante el cifrado MAM fuera de la aplicación (por ejemplo, las tarjetas SD) permanecen cifrados, pero no se quitan.|
|Aplicaciones de línea de negocio administradas|Se quitan los datos de la aplicación. La aplicación no se elimina. Los datos protegidos mediante el cifrado MAM fuera de la aplicación (por ejemplo, las tarjetas SD) permanecen cifrados e inutilizables, pero no se quitan.|Se quitan los datos de la aplicación. La aplicación no se elimina. Los datos protegidos mediante el cifrado MAM fuera de la aplicación (por ejemplo, las tarjetas SD) permanecen cifrados e inutilizables, pero no se quitan.|
|Configuración|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|
|Configuración de perfil de Wi-Fi y VPN|Quitado.|Quitado.|
|Configuración de perfil de certificado|Los certificados se revocan, pero no se quitan.|Certificados eliminados y revocados.|
|Agente de administración|Se revocarán los privilegios del administrador de dispositivos.|Se revocarán los privilegios del administrador de dispositivos.|
|Correo electrónico|N/D (los dispositivos Android no admiten los perfiles de correo electrónico)|Se borran los perfiles de correo electrónico que se aprovisionan mediante Intune. Se elimina el correo electrónico almacenado en caché en el dispositivo.|
|Separación de Azure AD|Se quita el registro de Azure AD.|Se quita el registro de Azure AD.|

### <a name="android-enterprise-devices-with-a-work-profile"></a>Dispositivos Android Enterprise con un perfil de trabajo

Al eliminar los datos de la compañía de un dispositivo de perfil de trabajo Android, se eliminan todos los datos, las aplicaciones y las configuraciones del perfil de trabajo en dicho dispositivo. El dispositivo se retira de la administración con Intune. No se admite el borrado en los perfiles de trabajo Android.

### <a name="android-enterprise-dedicated-devices"></a>Dispositivos Android Enterprise dedicados

Solo se pueden borrar dispositivos de quiosco. Los dispositivos de quiosco de Android no se pueden retirar.


### <a name="macos"></a>macOS

|Tipo de datos|macOS|
|-------------|-------|
|Configuración|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|
|Configuración de perfil de Wi-Fi y VPN|Quitado.|
|Configuración de perfil de certificado|Se han eliminado y revocado los certificados implementados a través de MDM.|
|Agente de administración|Se quitará el perfil de administración.|
|Outlook|Si el acceso condicional está habilitado, el dispositivo no recibirá ningún correo nuevo.|
|Separación de Azure AD|Se quita el registro de Azure AD.|

### <a name="windows"></a>Windows

|Tipo de datos|Windows 8.1 (MDM) y Windows RT 8.1|Windows RT|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplicaciones de empresa y datos asociados instalados por Intune.|Se revocan las claves de los archivos protegidos con EFS. El usuario no puede abrir los archivos.|No se quitan las aplicaciones de empresa.|Las aplicaciones se desinstalarán. Se quitan las claves de instalación de prueba.<br>Para Windows 10 versión 1709 (Creator Update) y versiones posteriores, no se quitan las aplicaciones de Aplicaciones de Microsoft 365. Las aplicaciones Win32 instaladas en la extensión de administración de Intune no serán dispositivos desinstalados o no inscritos. Los administradores pueden aprovechar la exclusión de asignación para no ofrecer las aplicaciones Win32 en los dispositivos BYOD.|
|Configuración|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|Las configuraciones que estableció la directiva de Intune ya no se aplican y los usuarios pueden cambiar la configuración.|
|Configuración de perfil de Wi-Fi y VPN|Quitado.|Quitado.|Quitado.|
|Configuración de perfil de certificado|Certificados eliminados y revocados.|Certificados eliminados y revocados.|Certificados eliminados y revocados.|
|Correo electrónico|Quita el correo electrónico habilitado para EFS. Se incluyen los mensajes de correo electrónico y los datos adjuntos de la aplicación de correo para Windows.|No compatible.|Quita el correo electrónico habilitado para EFS. Se incluyen los mensajes de correo electrónico y los datos adjuntos de la aplicación de correo para Windows. Se quitan las cuentas de correo aprovisionadas por Intune.|
|Separación de Azure AD|No.|No.|Se quita el registro de Azure AD.|

> [!NOTE]
> En el caso de los dispositivos Windows 10 que se unen a Azure AD durante la configuración rápida (OOBE), el comando de retiro quita todas las cuentas de Azure AD del dispositivo. Siga los pasos que se indican en [Iniciar el PC en modo seguro en Windows 10](https://support.microsoft.com/en-us/help/12376/windows-10-start-your-pc-in-safe-mode) para iniciar sesión como administración local y recuperar el acceso a los datos locales del usuario. 

### <a name="retire"></a>Retirar

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. En el panel **Dispositivos**, seleccione **Todos los dispositivos**.
3. Seleccione el nombre del dispositivo que quiere retirar.
4. En el panel en el que se muestra el nombre del dispositivo, haga clic en **Retirar**. Para confirmar, seleccione **Sí**.

Si el dispositivo está encendido y conectado, la acción **Retirar** se propaga por todos los tipos de dispositivos en menos de 15 minutos.

## <a name="delete-devices-from-the-intune-portal"></a>Eliminación de dispositivos del portal de Intune

Si quiere quitar dispositivos del portal de Intune, puede eliminarlos desde el panel de dispositivos específico. La próxima vez que el dispositivo se registra, se quitan los datos de la compañía que contiene.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Elija **Dispositivos** > **Todos los dispositivos** > elija los dispositivos que quiere eliminar > **Eliminar**.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Eliminar dispositivos automáticamente con reglas de limpieza
Puede configurar Intune para eliminar automáticamente los dispositivos que parecen estar inactivos, obsoletos o que no responden. Estas reglas de limpieza supervisan constantemente el inventario de dispositivos para que los registros de dispositivos se mantengan al día. Los dispositivos eliminados de esta forma se quitan de la administración de Intune. Esta configuración afecta a todos los dispositivos administrados por Intune, no solo a algunos específicos.
1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Elija **Dispositivos** > **Reglas de limpieza de dispositivos** > **Sí**.
3. En el cuadro **Eliminar los dispositivos que no se hayan registrado durante el siguiente número de días**, escriba un número entre 30 y 270.
4. Elija **Guardar**.

> [!NOTE]
> Las reglas de limpieza de dispositivos no están disponibles en escenarios de Android Enterprise de tipo [totalmente administrado](../enrollment/android-fully-managed-enroll.md), [dedicado](../enrollment/android-kiosk-enroll.md) y [propiedad corporativa con perfil de trabajo](../enrollment/android-corporate-owned-work-profile-enroll.md). 

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Eliminación de dispositivos en el portal de Azure Active Directory

Es posible que deba eliminar dispositivos de Azure AD si se producen problemas de comunicación o si faltan dispositivos. Puede usar la acción **Eliminar** para quitar registros de dispositivo de Azure Portal de los dispositivos que sabe que son inaccesibles y que es poco probable que vuelvan a comunicarse con Azure. La acción **Eliminar** no quita ningún dispositivo de la administración.

1. Inicie sesión en [Azure Active Directory en Azure Portal](https://azure.microsoft.com/services/active-directory/) con sus credenciales de administrador. También puede iniciar sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com). En el menú, seleccione **Centros de administración** > **Azure AD**.
2. Si no tiene ninguna, cree una suscripción de Azure. Si tiene una cuenta de pago, no necesitará ninguna tarjeta de crédito ni deberá efectuar ningún pago (seleccione el vínculo de suscripción **Registre su suscripción gratuita de Azure Active Directory**).
3. Seleccione **Azure Active Directory** y, después, seleccione su organización.
4. Seleccione la pestaña **Usuarios** .
5. Seleccione el usuario que está asociado al dispositivo que quiere eliminar.
6. Seleccione **Dispositivos**.
7. Quite los dispositivos según corresponda. Por ejemplo, puede quitar los dispositivos que ya no están en uso o los dispositivos que tienen definiciones inexactas.

## <a name="retire-an-apple-dep-device-from-intune"></a>Retirar un dispositivo DEP de Apple de Intune

Si quiere quitar completamente un dispositivo DEP de Apple de la administración mediante Intune, siga estos pasos:

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Elija **Dispositivos** > **Todos los dispositivos** > elija el dispositivo > **Retirar**.
![Captura de pantalla de Retirar](./media/devices-wipe/retire.png)
3. Visite [business.apple.com](http://business.apple.com) y busque el dispositivo por su número de serie.
4. En el menú **Asignado a**, elija **Sin asignar**.

5. Elija **Reasignar**.

    ![Captura de pantalla de reasignación de Apple](./media/devices-wipe/apple-reassign.png)

## <a name="device-states"></a>Estados del dispositivo
Para obtener una descripción de los estados del dispositivo, vea la [colección managementStates](../developer/intune-data-warehouse-collections.md#managementstates).

## <a name="fresh-start"></a>Empezar de cero

Aplicable a los dispositivos con Windows 10. Obtenga más información sobre [Empezar de cero](device-fresh-start.md).

## <a name="next-steps"></a>Pasos siguientes

Si quiere volver a inscribir un dispositivo eliminado, vea [Opciones de inscripción](../enrollment/enrollment-options.md).