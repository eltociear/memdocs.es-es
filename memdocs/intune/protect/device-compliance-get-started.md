---
title: Directivas de cumplimiento de dispositivos en Microsoft Intune - Azure | Microsoft Docs
description: Introducción al uso de directivas de cumplimiento de dispositivos, información general de los estados y los niveles de gravedad, uso del estado InGracePeriod, trabajo con el acceso condicional y control de los dispositivos sin una directiva asignada.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/21/2020
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 559d9a704f0b33e3fda3adf628626b56ff263de3
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83989725"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Establecimiento de reglas en los dispositivos para permitir el acceso a recursos de su organización con Intune

Muchas soluciones de administración de dispositivos móviles (MDM) ayudan a proteger los datos de la organización exigiendo a los usuarios y dispositivos que cumplan algunos requisitos. En Intune, esta característica se denomina "directivas de cumplimiento". Las directivas de cumplimiento definen las reglas y la configuración que los usuarios y los dispositivos deben cumplir para ser conformes. Cuando se combinan con el acceso condicional, los administradores pueden bloquear a los usuarios y dispositivos que no cumplan las reglas.

Por ejemplo, un administrador de Intune puede exigir:

- Que los usuarios finales usen una contraseña para acceder a los datos de la organización en dispositivos móviles
- Que el dispositivo no esté descodificado o descifrado
- Una versión máxima o mínima del sistema operativo en el dispositivo
- Que el dispositivo esté en un nivel de amenaza o bajo el mismo

También puede usar esta característica para supervisar el estado del cumplimiento de los dispositivos de su organización.

> [!IMPORTANT]
> Intune sigue el programa de inserción en el repositorio del dispositivo para todas las evaluaciones de cumplimiento del dispositivo. En el artículo sobre [ciclos de actualización de directivas y perfiles](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) se indican los tiempos de actualización estimados.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

- When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

- 3 days after initial noncompliance state, a follow up reminder is sent to the user.

- 5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

- 7 days after initial noncompliance state, access to company resources is blocked. This requires that you have Conditional Access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement Conditional Access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="device-compliance-policies-work-with-azure-ad"></a>Funcionamiento de las directivas de cumplimiento de dispositivos con Azure AD

Intune usa [acceso condicional](../protect/conditional-access.md) para ayudar a aplicar el cumplimiento. Acceso condicional es una tecnología de Azure Active Directory (Azure AD).

Cuando un dispositivo se inscribe en Intune, se inicia el proceso de registro de Azure AD y la información del dispositivo se actualiza en Azure AD. Una parte clave de la información es el estado de cumplimiento del dispositivo. Este estado de cumplimiento lo usan las directivas de acceso condicional para bloquear o permitir el acceso al correo electrónico y otros recursos de la organización.

Más información sobre el acceso condicional e Intune:

- [Formas habituales de usar el acceso condicional con Intune](conditional-access-intune-common-ways-use.md)

Más información sobre el acceso condicional en la documentación de Azure AD:
  - [¿Qué es el acceso condicional?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
  - [¿Qué es una identidad de dispositivo?](https://docs.microsoft.com/azure/active-directory/device-management-introduction)

## <a name="ways-to-use-device-compliance-policies"></a>Formas de usar las directivas de cumplimiento de dispositivos

### <a name="with-conditional-access"></a>Con acceso condicional

Para los dispositivos que cumplan las reglas de directiva, puede concederles acceso al correo electrónico y a otros recursos de la organización. Si los dispositivos no cumplen las reglas de directiva, no obtendrán acceso a los recursos de la organización. Se trata del acceso condicional.

### <a name="without-conditional-access"></a>Sin acceso condicional

También puede usar las directivas de cumplimiento de dispositivos sin ningún acceso condicional. Cuando se usan directivas de cumplimiento de forma independiente, los dispositivos de destino se evalúan y su estado se cumplimiento se notifica. Por ejemplo, puede obtener un informe sobre cuántos dispositivos no están cifrados o qué dispositivos están descodificados o descifrados. Cuando se usan directivas de cumplimiento sin acceso condicional, no hay ninguna restricción de acceso a los recursos de la organización.

## <a name="ways-to-deploy-device-compliance-policies"></a>Formas de implementar las directivas de cumplimiento de dispositivos

Puede implementar directivas de cumplimiento en los usuarios de grupos de usuarios o en dispositivos de grupos de dispositivos. Cuando se implementa una directiva de cumplimiento en un usuario, se comprueba el cumplimiento de todos los dispositivos del usuario. El uso de grupos de dispositivos en este escenario ayuda con los informes de cumplimiento.

Intune también incluye un conjunto de configuraciones de directivas de cumplimiento integradas. Las directivas integradas siguientes se evalúan en todos los dispositivos inscritos en Intune:

- **Marcar los dispositivos que no tienen asignada una directiva de cumplimiento como**: Se trata de una acción predeterminada para el no cumplimiento. esta propiedad tiene dos valores:

  - **Compatible** (*valor predeterminado*): característica de seguridad desactivada
  - **No compatible**: característica de seguridad activada

  Si un dispositivo no tiene asignada una directiva de cumplimiento, se considerará compatible de forma predeterminada. Si se usa el acceso condicional con directivas de cumplimiento, se recomienda cambiar la configuración predeterminada a **No compatible**. Si un usuario final no es compatible porque no se asignó ninguna directiva, en la [aplicación Portal de empresa de Intune](../apps/company-portal-app.md) se muestra `No compliance policies have been assigned`.

- **Detección de jailbreak mejorada** (*se aplica a iOS/iPadOS*): cuando se habilita, esta configuración hace que el estado del dispositivo con Jailbreak se realice con más frecuencia en dispositivos iOS/iPadOS. Esta configuración solo afecta a los dispositivos a los que se destina una directiva de cumplimiento que bloquea los dispositivos con Jailbreak. Para habilitar esta propiedad se usan los servicios de ubicación del dispositivo y puede afectar al uso de la batería. Intune no almacena los datos de ubicación del usuario y solo los usa para desencadenar la detección de jailbreak con mayor frecuencia en segundo plano. 

  Para habilitar esta configuración, los dispositivos deben:
  - Habilitar los servicios de ubicación en el nivel de sistema operativo.
  - Permitir siempre que el Portal de empresa use los servicios de ubicación.

  La detección mejorada funciona a través de los servicios de ubicación. La evaluación se desencadena al abrir la aplicación Portal de empresa o al mover físicamente el dispositivo a una distancia de unos 500 metros o más. En iOS 13 y versiones posteriores, esta característica requiere que los usuarios seleccionen Permitir siempre cada vez que el dispositivo les pida que sigan permitiendo al Portal de empresa usar su ubicación en segundo plano. Si los usuarios no permiten siempre el acceso a la ubicación y tienen configurada una directiva con esta opción, el dispositivo se marcará como no conforme. Tenga en cuenta que Intune no puede garantizar que cada cambio de ubicación significativo garantice una comprobación de detección de jailbreak, ya que esto depende de la conexión de red de un dispositivo en ese momento.

- **Período de validez del estado de cumplimiento (días)** : especifique el período en que los dispositivos informan del estado de todas las directivas de cumplimiento recibidas. Los dispositivos que no proporcionen el estado dentro de este período se tratarán como no conformes. El valor predeterminado es 30 días. El valor máximo es de 120 días. El valor mínimo es 1 día.

  Esta configuración se muestra como la directiva de cumplimiento predeterminada **Activa** (**Dispositivos** > **Monitor** > **Configuración de cumplimiento**). La tarea en segundo plano para esta directiva se ejecuta una vez al día.

Puede usar estas directivas integradas para supervisar estas configuraciones. Intune también [se actualiza o comprueba si hay actualizaciones](create-compliance-policy.md#refresh-cycle-times) en distintos intervalos, dependiendo de la plataforma del dispositivo. [Preguntas comunes, problemas y su solución con perfiles y directivas de dispositivos en Microsoft Intune](../configuration/device-profile-troubleshoot.md) es un recurso útil.

Los informes de cumplimiento son una excelente manera de comprobar el estado de los dispositivos. [Supervisión de las directivas de cumplimiento](compliance-policy-monitor.md) incluye algunas instrucciones.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Incumplimiento y acceso condicional en las distintas plataformas

En la tabla siguiente se describe cómo administrar la configuración de no conformidad cuando se usa una directiva de cumplimiento con una directiva de acceso condicional.

---------------------------

|**Configuración de directiva**| **Plataforma** |
| --- | ----|
| **Configuración de PIN o contraseña** | - **Android 4.0 y versiones posteriores**: En cuarentena<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: En cuarentena<br>- **Android Enterprise**: En cuarentena  <br>  <br>- **iOS 8.0 y versiones posteriores**: Corregido<br>- **macOS 10.11 y versiones posteriores**: Corregido  <br>  <br>- **Windows 8.1 y versiones posteriores**: Corregido<br>- **Windows Phone 8.1 y versiones posteriores**: Corregido|
| **Cifrado del dispositivo** | - **Android 4.0 y versiones posteriores**: En cuarentena<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: En cuarentena<br>- **Android Enterprise**: En cuarentena<br><br>- **iOS 8.0 y versiones posteriores**: Corregido (estableciendo PIN)<br>- **macOS 10.11 y versiones posteriores**: Corregido (estableciendo PIN)<br><br>- **Windows 8.1 y versiones posteriores**: No disponible<br>- **Windows Phone 8.1 y versiones posteriores**: Corregido |
| **Dispositivo liberado o modificado** | - **Android 4.0 y versiones posteriores**: En cuarentena (no es una configuración)<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: En cuarentena (no es una configuración)<br>- **Android Enterprise**: En cuarentena (no es una configuración)<br><br>- **iOS 8.0 y versiones posteriores**: En cuarentena (no es una configuración)<br>- **macOS 10.11 y versiones posteriores**: No disponible<br><br>- **Windows 8.1 y versiones posteriores**: No disponible<br>- **Windows Phone 8.1 y versiones posteriores**: No disponible |
| **Perfil de correo electrónico** | - **Android 4.0 y versiones posteriores**: No disponible<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: No disponible<br>- **Android Enterprise**: No disponible<br><br>- **iOS 8.0 y versiones posteriores**: En cuarentena<br>- **macOS 10.11 y versiones posteriores**: En cuarentena<br><br>- **Windows 8.1 y versiones posteriores**: No disponible<br>- **Windows Phone 8.1 y versiones posteriores**: No disponible |
| **Versión de SO mínima** | - **Android 4.0 y versiones posteriores**: En cuarentena<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: En cuarentena<br>- **Android Enterprise**: En cuarentena<br><br>- **iOS 8.0 y versiones posteriores**: En cuarentena<br>- **macOS 10.11 y versiones posteriores**: En cuarentena<br><br>- **Windows 8.1 y versiones posteriores**: En cuarentena<br>- **Windows Phone 8.1 y versiones posteriores**: En cuarentena |
| **Versión de SO máxima** | - **Android 4.0 y versiones posteriores**: En cuarentena<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: En cuarentena<br>- **Android Enterprise**: En cuarentena<br><br>- **iOS 8.0 y versiones posteriores**: En cuarentena<br>- **macOS 10.11 y versiones posteriores**: En cuarentena<br><br>- **Windows 8.1 y versiones posteriores**: En cuarentena<br>- **Windows Phone 8.1 y versiones posteriores**: En cuarentena |
| **Atestación de estado de Windows** | - **Android 4.0 y versiones posteriores**: No disponible<br>- **Samsung Knox Standard 4.0 y versiones posteriores**: No disponible<br>- **Android Enterprise**: No disponible<br><br>- **iOS 8.0 y versiones posteriores**: No disponible<br>- **macOS 10.11 y versiones posteriores**: No disponible<br><br>- **Windows 10 y Windows 10 Mobile**: En cuarentena<br>- **Windows 8.1 y versiones posteriores**: En cuarentena<br>- **Windows Phone 8.1 y versiones posteriores**: No disponible |

---------------------------

**Corregido**: el sistema operativo del dispositivo exige compatibilidad. Por ejemplo, se obliga al usuario a establecer un PIN.

**En cuarentena**: el sistema operativo del dispositivo no exige cumplimiento. Por ejemplo, los dispositivos Android y Android Enterprise no obligan al usuario a cifrar el dispositivo. Si el dispositivo no es conforme, se emprenden las acciones siguientes:

- El dispositivo se bloquea si se aplica una directiva de acceso condicional al usuario.
- La aplicación Portal de empresa de Intune notifica al usuario sobre cualquier problema de cumplimiento.

## <a name="next-steps"></a>Pasos siguientes

- [Cree una directiva](create-compliance-policy.md) y vea los requisitos previos.
- Consulte la configuración de cumplimiento para las distintas plataformas de dispositivos:

  - [Android](compliance-policy-create-android.md)
  - [Android Enterprise](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows Holographic for Business](compliance-policy-create-windows.md#windows-holographic-for-business)
  - [Windows Phone 8.1](compliance-policy-create-windows-8-1.md)
  - [Windows 8.1 y versiones posteriores](compliance-policy-create-windows-8-1.md)
  - [Windows 10 y versiones posteriores](compliance-policy-create-windows.md)

- En [Referencia de entidades de directivas](../developer/reports-ref-policy.md) se brinda información sobre las entidades de directivas de almacenamiento de datos de Intune.
