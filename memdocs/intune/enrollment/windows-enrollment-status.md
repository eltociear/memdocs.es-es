---
title: Configuración de la página de estado de la inscripción
titleSuffix: Microsoft Intune
description: Configure una página de saludo para los usuarios que inscriban dispositivos Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/10/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: ericor
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure;seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2fc05ced647e8784333c2a20bc13c27aa2bf3447
ms.sourcegitcommit: e2deac196e5e79a183aaf8327b606055efcecc82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90076131"
---
# <a name="set-up-the-enrollment-status-page"></a>Configuración de la página de estado de la inscripción
 
[!INCLUDE [azure_portal](../includes/azure_portal.md)]
 
La página de estado de la inscripción (ESP) muestra el progreso de aprovisionamiento después de que se haya inscrito un nuevo dispositivo, así como tras el inicio de sesión de un nuevo usuario en el dispositivo.  Esto permite a los administradores de TI impedir (bloquear) de forma opcional el acceso al dispositivo hasta que se haya aprovisionado por completo, al mismo tiempo que proporciona a los usuarios información sobre las tareas pendientes del proceso de aprovisionamiento.

ESP se puede usar como parte de cualquier escenario de aprovisionamiento de [Windows Autopilot](../../autopilot/index.yml) y también se puede usar por separado de Windows Autopilot como parte de la configuración rápida (OOBE) predeterminada para la Unión a Azure AD, así como para cualquier usuario nuevo que inicie sesión por primera vez en el dispositivo.

Puede crear varios perfiles de la página de estado de la inscripción con diferentes configuraciones que especifiquen lo siguiente:

- Visualización del progreso de la instalación
- Bloqueo del acceso hasta que se complete el proceso de aprovisionamiento
- Límites de tiempo
- Operaciones permitidas de solución de problemas

Estos perfiles se especifican en orden de prioridad; la prioridad más alta será la que se aplique.  Cada perfil de ESP puede destinarse a grupos que contengan dispositivos o usuarios.  A la hora de determinar el perfil que se va a usar, se seguirán los siguientes criterios:

- Se usará primero el perfil de prioridad más alta destinado al dispositivo.
- Si no hay perfiles destinados al dispositivo, se usará el perfil de prioridad más alta destinado al usuario actual.  (Esto solo se aplica en los escenarios en los que hay un usuario. En los escenarios preferenciales y de autoimplementación, solo se pueden usar dispositivos como destino).
- Si no hay ningún perfil destinado a grupos específicos, se usará el perfil de ESP predeterminado.

## <a name="available-settings"></a>Opciones de configuración disponibles

Se pueden configurar los siguientes valores para personalizar el comportamiento de la página de estado de la inscripción:

<table>
<th align="left">Setting<th align="left">Sí<th align="left">No
<tr><td>Mostrar el progreso de la instalación de la aplicación y el perfil<td>Se muestra la página de estado de la inscripción.<td>No se muestra la página de estado de la inscripción.
<tr><td>Bloquear el uso del dispositivo hasta que todos los perfiles y aplicaciones estén instalados<td>La configuración de esta tabla está disponible para personalizar el comportamiento de la página de estado de la inscripción, de modo que el usuario pueda resolver posibles problemas de instalación.
<td>La página de estado de la inscripción se muestra sin opciones adicionales para solucionar los errores de instalación.
<tr><td>Permitir a los usuarios restablecer el dispositivo si se produce un error de instalación<td>Si se produce un error de instalación, se muestra un botón <b>Restablecer dispositivo</b>.<td>El botón <b>Restablecer dispositivo</b> no se muestra si se produce un error de instalación.
<tr><td>Permitir a los usuarios utilizar el dispositivo si se produce un error de instalación<td>Si se produce un error de instalación, se muestra un botón <b>Continuar de todos modos</b>.<td>El botón <b>Continuar de todos modos</b> no se muestra si se produce un error de instalación.
<tr><td>Show timeout error when installation takes longer than specified number of minutes (Mostrar error de tiempo de expiración cuando la instalación tarda más de un número especificado de minutos)<td colspan="2">Especifique el número de minutos de espera para finalizar la instalación. Se especifica un valor predeterminado de 60 minutos.
<tr><td>Mostrar un mensaje personalizado cuando se produce un error<td>Se proporciona un cuadro de texto en el que puede especificar un mensaje personalizado que se mostrará si se produce un error de instalación.<td>Se muestra el mensaje predeterminado: <br><b>La instalación superó el límite de tiempo establecido por su organización. Vuelva a intentarlo o póngase en contacto con la persona de soporte de TI para obtener ayuda.<b>
.<tr><td>Permitir a los usuarios recopilar los registros acerca de los errores de instalación<td>Si se produce un error de instalación, se muestra el botón registros <b>Recopilar registros</b>. <br>Si el usuario hace clic en este botón, se le pedirá que elija una ubicación para guardar el archivo de registro <b>MDMDiagReport.cab</b>.<td>El botón <b>Recopilar registros</b> no se muestra si hay un error de instalación.
<tr><td>Block device use until these required apps are installed if they are assigned to the user/device (Bloquear dispositivo hasta que las aplicaciones necesarias estén instaladas si están asignadas al usuario o dispositivo).<td colspan="2">Elija <b>Todo</b> o <b>Seleccionado</b>. <br><br>Si se elige <b>Seleccionado</b>, aparece un botón <b>Seleccionar aplicaciones</b> que permite elegir qué aplicaciones deben instalarse antes de habilitar el dispositivo.
</table>

## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Turn on default Enrollment Status Page for all users (Activar la página de estado de la inscripción predeterminada para todos los usuarios)

Para activar la página de estado de la inscripción, siga estos pasos.
 
1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Windows** > **Inscripción de Windows** > **Página de estado de la inscripción**.
2. En la hoja **Página de estado de inscripción**, elija **Predeterminado** > **Configuración**.
3. Para **Show app and profile installation progress** (Mostrar progreso de instalación de la aplicación y el perfil), elija **Sí**.
4. Elija las demás opciones de configuración que desee activar y seleccione **Guardar**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Creación de un perfil de la página de estado de la inscripción y asignación a un grupo

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Windows** > **Inscripción de Windows** > **Página de estado de la inscripción** > **Crear perfil**.
2. Proporcione un **Nombre** y una **Descripción**.
3. Elija **Crear**.
4. Elija el nuevo perfil en la lista **Página de estado de inscripción**.
5. Elija **Asignaciones** > **Seleccionar grupos** > elija los grupos que quiera que adopten este perfil > **Seleccionar** > **Guardar**.
6. Elija **Configuración** > elija la configuración que quiera aplicar a este perfil > **Guardar**.

## <a name="set-the-enrollment-status-page-priority"></a>Establecimiento de la prioridad de la página de estado de inscripción

Un dispositivo o un usuario pueden estar en varios grupos y tener como destino varios perfiles de página de estado de la inscripción. Para controlar qué perfiles se consideran primero, puede establecer las prioridades de cada perfil; se considerarán primero los que tengan prioridades más altas.

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Windows** > **Inscripción de Windows** > **Página de estado de la inscripción**.
2. Mantenga el mouse sobre el perfil en la lista.
3. Use los tres puntos verticales para arrastrar el perfil a la posición que quiera en la lista.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Bloqueo del acceso a un dispositivo a menos que haya instalada una aplicación específica

Puede especificar qué aplicaciones deben instalarse antes de que se complete la página de estado de la inscripción (ESP).

1. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Windows** > **Inscripción de Windows** > **Página de estado de la inscripción**.
2. Elija un perfil > **Configuración**.
3. Elija **Sí** en **Show app and profile installation progress** (Mostrar progreso de instalación de la aplicación y el perfil).
4. Elija **Sí** en **Block device use until all apps and profiles are installed** (Bloquear dispositivo hasta que todas estas aplicaciones y perfiles estén instalados).
5. Elija **Seleccionado** en **Block device use until these required apps are installed if they are assigned to the user/device** (Bloquear dispositivo hasta que las aplicaciones necesarias estén instaladas si están asignadas al usuario o dispositivo).
6. Elija **Seleccionar aplicaciones** > elija las aplicaciones > **Seleccionar** > **Guardar**.

Intune usa las aplicaciones que se incluyen en esta lista para filtrar la lista cuyo bloqueo se debe considerar.  No especifica qué aplicaciones deben instalarse.  Por ejemplo, si configura esta lista para incluir "aplicación 1", "aplicación 2" y "aplicación 3", y "aplicación 3" y "aplicación 4" se destinan al dispositivo o usuario, la Página de estado de inscripción solo realizará el seguimiento de "aplicación 3".  "Aplicación 4" todavía se instalará, pero la Página de estado de inscripción no esperará a que se complete.

Se puede especificar un máximo de 100 aplicaciones.

## <a name="enrollment-status-page-tracking-information"></a>Información de seguimiento de la página de estado de la inscripción

Hay tres fases en las que la página de estado de la inscripción realiza un seguimiento de la información: durante la preparación del dispositivo, la instalación del dispositivo y la configuración de la cuenta.

### <a name="device-preparation"></a>Preparación del dispositivo

Durante la preparación del dispositivo, la página de estado de la inscripción realiza un seguimiento de lo siguiente:

- Atestación de clave del Módulo de plataforma segura (TPM) (cuando proceda)
- Proceso de unión a Azure Active Directory
- Inscripción en Intune (MDM)
- Instalación de las extensiones de administración de Intune (usadas para instalar aplicaciones Win32)

### <a name="device-setup"></a>Configuración del dispositivo

La página de estado de la inscripción realiza el seguimiento de los siguientes elementos de configuración del dispositivo:

- Directivas de seguridad
  - Actualmente se realiza un seguimiento de las directivas de Microsoft Edge, Acceso asignado y Kiosk Browser.
  - No se realiza el seguimiento de otras directivas.
- Aplicaciones
  - Aplicaciones MSI de línea de negocio (LoB) por equipo.
  - Aplicaciones de almacén de LoB con contexto de instalación = Dispositivo.
  - Aplicaciones de almacén de LoB y almacén sin conexión con contexto de instalación = Dispositivo.
  - Aplicaciones Win32 (solo Windows 10 versión 1903 y versiones más recientes) 
- Perfiles de conectividad
  - Perfiles de Wi-Fi o VPN que están asignados a **Todos los dispositivos** o a un grupo de dispositivos en el que el dispositivo de inscripción es un miembro, pero solo para dispositivos Autopilot
- Perfiles de certificado que están asignados a **Todos los dispositivos** o a un grupo de dispositivos en el que el dispositivo de inscripción es un miembro, pero solo para dispositivos Autopilot

### <a name="account-setup"></a>Configuración de la cuenta

Para la configuración de la cuenta, la página de estado de la inscripción realiza un seguimiento de estos elementos si están asignados al usuario con sesión iniciada en ese momento:

- Directivas de seguridad
  - Actualmente se realiza un seguimiento de las directivas de Microsoft Edge, Acceso asignado y Kiosk Browser.
  - No se realiza el seguimiento de otras directivas.
- Aplicaciones
  - Aplicaciones de MSI de LoB por usuario que están asignadas a todos los dispositivos, a todos los usuarios a un grupo de usuarios del que es miembro el usuario que está inscribiendo el dispositivo.
  - Aplicaciones de MSI de LoB por equipo que están asignadas a todos los usuarios o a un grupo de usuarios del que es miembro el usuario que está inscribiendo el dispositivo.
  - Aplicaciones LoB de la tienda, aplicaciones de la tienda en línea y aplicaciones de la tienda sin conexión que se asignan a cualquiera de los siguientes objetos:
    - Todos los dispositivos
    - Todos los usuarios
    - Un grupo de usuarios del que es miembro el usuario que inscribe el dispositivo con el contexto de instalación establecido en Usuario.
  - Aplicaciones Win32 (solo Windows 10 versión 1903 y versiones más recientes) 
- Perfiles de conectividad
  - Perfiles de VPN o Wi-Fi que están asignados a todos los usuarios o a un grupo de usuarios del que es miembro el usuario que está inscribiendo el dispositivo.
- Certificados
  - Perfiles de certificado que están asignados a todos los usuarios o a un grupo de usuarios del que es miembro el usuario que está inscribiendo el dispositivo.

### <a name="known-issues"></a>Problemas conocidos

A continuación se indican los problemas conocidos relacionados con la página de estado de la inscripción.

- Al deshabilitar el perfil de ESP no se quita la directiva de ESP de los dispositivos, y los usuarios siguen viendo la ESP cuando inician sesión en el dispositivo por primera vez. La directiva no se quita cuando se deshabilita el perfil de ESP. Debe implementar OMA-URI para deshabilitar la ESP. Consulte anteriormente las instrucciones para deshabilitar ESP mediante OMA-URI. 
- ya que obligará al usuario a escribir sus credenciales antes de pasar a la fase de configuración de la cuenta. Las credenciales de usuario no se conservan durante el reinicio. Haga que el usuario escriba sus credenciales; de este modo, la página de estado de la inscripción puede continuar. 
- La página de estado de la inscripción siempre agotará el tiempo de expiración durante una inscripción mediante la opción para agregar una cuenta profesional o educativa en versiones de Windows 10 inferiores a la 1903. La página de estado de la inscripción espera a que finalice el registro de Azure AD. El problema se corrigió en Windows 10 versión 1903 y posteriores.  
- La implementación de Autopilot de Azure AD híbrido con ESP tarda más tiempo que la duración del tiempo de expiración definida en el perfil de ESP. En implementaciones de Autopilot de Azure AD híbrido, ESP tardará 40 minutos más que el valor establecido en el perfil de ESP. Este retraso proporciona tiempo para que el conector de AD local cree el registro del dispositivo en Azure AD. 
- La página de inicio de sesión de Windows no se rellena previamente con el nombre de usuario en el modo controlado por el usuario de Autopilot. Si se ha producido un reinicio durante la fase de instalación del dispositivo de ESP:
  - No se conservan las credenciales de usuario.
  - El usuario debe volver a escribir las credenciales antes de pasar de la fase de instalación del dispositivo a la fase de configuración de la cuenta.
- ESP se queda bloqueado durante mucho tiempo o nunca completa la fase de identificación. Intune calcula las directivas de ESP durante la fase de identificación. Puede que un dispositivo no complete nunca las directivas de ESP si el usuario actual no tiene asignada una licencia de Intune.  
- La configuración de Microsoft Defender Application Control provoca que se reinicie el sistema durante la fase de Autopilot. La configuración de Microsoft Defender Application Control (CSP de AppLocker) requiere un reinicio. Cuando se configura esta directiva, es posible que el dispositivo se reinicie durante la fase de Autopilot. Actualmente, no hay ninguna manera de suprimir o posponer el reinicio.
- Cuando la directiva DeviceLock (https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) ) está habilitada como parte de un perfil de ESP, la configuración rápida del sistema (OOBE) o el inicio de sesión automático en el escritorio del usuario podrían producir un error inesperado por dos motivos.
  - Si el dispositivo no se reinició antes de salir de la fase de instalación del dispositivo de ESP, es posible que se le pida al usuario que escriba sus credenciales de Azure AD. Este mensaje se muestra en lugar de un inicio de sesión automático correcto en el que el usuario ve la animación del primer inicio de sesión de Windows.
  - El inicio de sesión automático no se realizará correctamente si el dispositivo se reinicia después de que el usuario haya escrito sus credenciales de Azure AD, pero antes de salir de la fase de instalación del dispositivo de ESP. Este error se produce porque la fase de instalación del dispositivo de ESP nunca se ha completado. La solución alternativa es restablecer el dispositivo.

## <a name="next-steps"></a>Pasos siguientes

Tras configurar las páginas de inscripción de Windows, aprenda a [administrar los dispositivos Windows](../remote-actions/device-management.md).

[Solución de problemas de la página de estado de la inscripción de Windows](https://docs.microsoft.com/troubleshoot/mem/intune/understand-troubleshoot-esp#troubleshooting)
