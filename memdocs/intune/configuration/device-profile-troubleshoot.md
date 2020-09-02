---
title: Solucionar problemas de perfiles de dispositivo en Microsoft Intune - Azure | Microsoft Docs
description: Preguntas y respuestas comunes con perfiles y directivas de dispositivo, como los cambios de perfil que no se aplican a usuarios o dispositivos, cuánto tiempo tarda una directiva nueva en enviarse a los dispositivos, qué configuración se aplica cuando hay varias directivas, qué ocurre cuando se elimina o quita un perfil y más con Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/20/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 849be91ccedab1f97b68b14e5bc2a51bc5a62f19
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88915303"
---
# <a name="common-questions-and-answers-with-device-policies-and-profiles-in-microsoft-intune"></a>Preguntas y respuestas habituales sobre los perfiles y las directivas de los dispositivos en Microsoft Intune

Obtenga respuestas a preguntas comunes al trabajar con directivas y perfiles de dispositivo en Intune. En este artículo también se muestran los intervalos de tiempo de sincronización, se proporcionan más detalles sobre los conflictos, etc.

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>¿Cuánto tiempo tardan los dispositivos en obtener una directiva, un perfil o una aplicación después de que se hayan asignado?

Intune notifica al dispositivo que se sincronice con el servicio de Intune. Los tiempos de notificación varían y van desde inmediatamente hasta unas horas. Estos tiempos de notificación también varían según la plataforma.

Si un dispositivo no se sincroniza para recibir la directiva o el perfil después de la primera notificación, Intune hace tres intentos más. Es posible que un dispositivo sin conexión, como apagado o no conectado a una red, no reciba las notificaciones. En ese caso, el dispositivo obtiene la directiva o el perfil en la próxima sincronización programada con el servicio Intune. Lo mismo se aplica a las comprobaciones de no cumplimiento, incluidos los dispositivos que pasan de un estado compatible a un estado de no cumplimiento.

Frecuencias **estimadas**:

| Plataforma | Ciclo de actualización|
| --- | --- |
| iOS/iPadOS | Aproximadamente cada 8 horas |
| macOS | Aproximadamente cada 8 horas |
| Android | Aproximadamente cada 8 horas |
| Equipos Windows 10 inscritos como dispositivos | Aproximadamente cada 8 horas |
| Windows Phone | Aproximadamente cada 8 horas |
| Windows 8.1 | Aproximadamente cada 8 horas |

Si el dispositivo se ha inscrito recientemente, la comprobación de cumplimiento, no cumplimiento y configuración se ejecuta con más frecuencia y **se estima** en:

| Plataforma | Frecuencia |
| --- | --- |
| iOS/iPadOS | Cada 15 minutos durante 1 hora y, luego, cada 8 horas |  
| macOS | Cada 15 minutos durante 1 hora y, luego, cada 8 horas | 
| Android | Cada 3 minutos durante 15 minutos, luego cada 15 minutos durante 2 horas y, luego, cada 8 horas | 
| Equipos Windows 10 inscritos como dispositivos | Cada 3 minutos durante 15 minutos, luego cada 15 minutos durante 2 horas y, luego, cada 8 horas | 
| Windows Phone | Cada 5 minutos durante 15 minutos, luego cada 15 minutos durante 2 horas y, luego, cada 8 horas | 
| Windows 8.1 | Cada 5 minutos durante 15 minutos, luego cada 15 minutos durante 2 horas y, luego, cada 8 horas | 

En cualquier momento, los usuarios pueden abrir la aplicación Portal de empresa. **Configuración** > **Sincronizar** para comprobar de inmediato las actualizaciones de la directiva o del perfil.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>¿Qué acciones provocan que Intune envíe inmediatamente una notificación a un dispositivo?

Hay distintas acciones que desencadenan una notificación, por ejemplo, cuando se asigna (o anula la asignación), actualiza, elimina, etc. una directiva, un perfil o una aplicación. Estos tiempos de acción varían según la plataforma.

Los dispositivos se sincronizan con Intune cuando reciben una notificación para sincronizarse o durante la sincronización programada. Cuando el destino es un dispositivo o usuario con una acción (por ejemplo, bloqueo, restablecimiento de código de acceso o asignación de aplicaciones, perfiles o directivas), Intune lo notifica inmediatamente al dispositivo para que se sincronice y reciba estas actualizaciones.

Otros cambios, como la revisión de la información de contacto de la aplicación Portal de empresa, no provocan una notificación inmediata a los dispositivos.

La configuración de la directiva o el perfil de aplica en toda sincronización. La [entrada de blob sobre la actualización de la directiva de Windows 10 MDM](https://www.petervanderwoude.nl/post/windows-10-mdm-policy-refresh/) puede ser útil.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Si varias directivas se asignan al mismo usuario o dispositivo, ¿cómo puedo saber qué configuración se aplica?

Cuando dos o más directivas se asignan al mismo usuario o dispositivo, la configuración que se aplica se hace a nivel de valor individual:

- La configuración de directivas de cumplimiento siempre tiene prioridad respecto a la configuración de perfiles de configuración.

- Si se evalúa una directiva de cumplimiento con el mismo valor en otra directiva de cumplimiento, se aplica el valor de directiva de cumplimiento más restrictivo.

- Si una opción de la directiva de configuración entra en conflicto con una opción de otra directiva de configuración, este conflicto se muestra en Intune. Resuelva estos conflictos de forma manual.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>¿Qué sucede cuando las directivas de protección de aplicaciones entran en conflicto entre sí? ¿Cuál se aplica a la aplicación?

Los valores en conflicto son la configuración más restrictiva disponible en una directiva de protección de aplicaciones, *excepto* para los campos de entrada de números (como intentos de PIN antes del restablecimiento). Los campos de entrada de números se definen con los mismos valores que si crease una directiva de MAM con la opción de configuración recomendada.

Se producen conflictos cuando dos configuraciones de perfil son iguales. Por ejemplo, si configura dos directivas MAM que son idénticas, salvo por la configuración de copiar y pegar. En este escenario, la configuración de copiar y pegar se define con el valor más restrictivo, pero el resto de los parámetros se aplican según la configuración.

Se implementa una directiva en la aplicación y surte efecto. Se implementa una segunda directiva. En este escenario, la primera directiva tiene prioridad y sigue siendo la directiva aplicada. La segunda directiva muestra un conflicto. Si ambas se aplican al mismo tiempo, lo que significa que no hay ninguna directiva precedente, ambas están en conflicto. Cualquier configuración en conflicto se establece en los valores más restrictivos.

## <a name="what-happens-when-iosipados-custom-policies-conflict"></a>¿Qué sucede cuando hay un conflicto de directivas personalizadas de iOS/iPadOS?

Intune no evalúa la carga de archivos de configuración de Apple ni directivas personalizadas de identificador uniforme de recursos de Open Mobile Alliance (OMA-URI). Sencillamente, se usa como mecanismo de entrega.

Al asignar una directiva personalizada, confirme que los valores configurados no entran en conflicto con las directivas de cumplimiento, configuración o personalizadas. Si una directiva personalizada y su configuración entran en conflicto, la configuración se aplicará de forma aleatoria.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>¿Qué ocurre cuando se elimina un perfil o deja de ser aplicable?

Al eliminar un perfil o quitar un dispositivo de un grupo que tiene el perfil, se quitan el perfil y la configuración del dispositivo tal como se describe a continuación:

- Perfiles de correo electrónico, certificado, VPN y Wi-Fi: estos perfiles se quitan de todos los dispositivos inscritos admitidos.
- Todos los demás tipos de perfiles:  

  - **Dispositivos Android y Windows**: la configuración no se quita del dispositivo.
  - **Dispositivos Windows Phone 8.1**: Se han eliminado las siguientes configuraciones:  
  
    - Requerir una contraseña para desbloquear dispositivos móviles
    - Permitir contraseñas sencillas
    - Longitud mínima de la contraseña
    - Tipo de contraseña obligatoria
    - Expiración de contraseña (días)
    - Recordar el historial de contraseñas
    - Número de errores de inicio de sesión repetidos que se permiten antes de que se borre el dispositivo
    - Minutos de inactividad antes de que se pida la contraseña
    - Tipo de contraseña requerida: número mínimo de conjuntos de caracteres
    - Permitir cámara
    - Requerir cifrado en dispositivo móvil
    - Permitir almacenamiento extraíble
    - Permitir explorador web
    - Permitir almacén de aplicaciones
    - Permitir captura de pantalla
    - Permitir geolocalización
    - Permitir cuenta de Microsoft
    - Permitir copiar y pegar
    - Permitir Wi-Fi Tethering
    - Permitir la conexión automática a zonas Wi-Fi gratuitas
    - Permitir informar de zonas Wi-Fi
    - Permitir borrado
    - Permitir Bluetooth
    - Permitir NFC
    - Permitir Wi-Fi

  - **iOS/iPadOS**: se quitan todas las opciones de configuración, excepto las siguientes:
  
    - Permitir itinerancia de voz
    - Permitir itinerancia de datos
    - Permitir la sincronización automática en itinerancia

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>He cambiado un perfil de restricción de dispositivos, pero los cambios no han surtido efecto

Una vez establecidas, los dispositivos Windows Phone no permiten que las directivas de seguridad establecidas a través de MDM o EAS reduzcan su nivel de seguridad. Por ejemplo, puede establecer una **contraseña con un número mínimo de 8 caracteres**. Puede intentar reducirla a 4. El perfil más restrictivo ya está aplicado en el dispositivo.

Para cambiar el perfil a un valor menos seguro, debe restablecer las directivas de seguridad. Por ejemplo, en el escritorio de Windows 8.1, deslice el dedo desde la derecha > seleccione **Configuración** > **Panel de control**. Seleccione el applet **Cuentas de usuario** . En el menú de navegación de la izquierda, hay un vínculo denominado **Restablecer las directivas de seguridad** (hacia la parte inferior). Selecciónelo y, después, elija **Restablecer directivas**.

Es posible que sea necesario retirar otros dispositivos MDM, como Android, Windows Phone 8.1 y versiones posteriores, iOS/iPadOS y Windows 10, y volver a inscribirlos en Intune para aplicar un perfil menos restrictivo.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Algunas opciones de configuración de un perfil de Windows 10 devuelven "No aplicable"

Algunas opciones de configuración de los dispositivos Windows 10 pueden mostrarse como "No aplicable". Esto indica que esa configuración concreta no se admite en la versión o edición de Windows que se esté ejecutando en el dispositivo. Este mensaje puede aparecer por las siguientes razones:

- La configuración solo está disponible para versiones más recientes de Windows, pero no para la versión actual del sistema operativo (SO) del dispositivo.
- La configuración solo está disponible para ediciones de Windows o SKU específicas, como Home, Professional, Enterprise o Education.

Para obtener más información sobre los requisitos de versión y de SKU para las distintas opciones de configuración, vea [Configuration Service Provider (CSP) reference](/windows/client-management/mdm/configuration-service-provider-reference) (Referencia del proveedor de servicios de configuración).

## <a name="next-steps"></a>Pasos siguientes

¿Necesita más ayuda? Consulte [Cómo obtener asistencia para Microsoft Intune](../fundamentals/get-support.md).