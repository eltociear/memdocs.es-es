---
title: Configuración de dispositivos Android Enterprise en Microsoft Intune - Azure | Microsoft Docs
description: Vea una lista de todas las opciones que puede usar al configurar el cumplimiento de dispositivos Android Enterprise en Microsoft Intune. Configure reglas de contraseña, elija una versión mínima o máxima de sistema operativo, restrinja aplicaciones específicas, evite reutilizar contraseñas y mucho más.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9897f824bb1bd13c1d12ff0c705b42cea275b9d4
ms.sourcegitcommit: eccf83dc41f2764675d4fd6b6e9f02e6631792d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2020
ms.locfileid: "86462089"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configuración de Android Enterprise para marcar dispositivos como compatibles o no compatibles con Intune

En este artículo se enumeran y describen las distintas opciones de configuración de cumplimiento que se pueden establecer en dispositivos Android Enterprise y versiones posteriores en Intune. Como parte de la solución de administración de dispositivos móviles (MDM), use estas opciones para marcar los dispositivos liberados (descodificados) como no compatibles, establecer un nivel de amenaza permitido, habilitar Google Play Protect y mucho más.

Esta característica se aplica a:

- Android Enterprise

Como administrador del servicio Intune, use esta configuración de cumplimiento para proteger mejor los recursos de la organización. Para más información sobre las directivas de cumplimiento y lo que hacen, vea [Introducción a las directivas de cumplimiento](device-compliance-get-started.md).

> [!IMPORTANT]
> Las directivas de cumplimiento también se aplican a dispositivos Android Enterprise dedicados. Si se asigna una directiva de cumplimiento a un dispositivo dedicado, es posible que el dispositivo se muestre como **No es compatible**. El acceso condicional y la exigencia del cumplimiento no está disponible en dispositivos dedicados. Asegúrese de completar las tareas o acciones para obtener dispositivos dedicados compatibles con las directivas asignadas.

## <a name="before-you-begin"></a>Antes de comenzar

[Crear una directiva de cumplimiento](create-compliance-policy.md#create-the-policy). Para **Plataforma**, seleccione **Android Enterprise**.


## <a name="fully-managed-dedicated-and-corporate-owned-work-profile"></a>Perfil de trabajo de propiedad corporativa, dedicado y totalmente administrado

### <a name="microsoft-defender-atp"></a>ATP de Microsoft Defender

- **Solicitar que el dispositivo tenga o esté por debajo de la puntuación de riesgo de la máquina**  

  Seleccione la puntuación de riesgo de la máquina máxima permitida para los dispositivos evaluados por ATP de Microsoft Defender. Los dispositivos que superan esta puntuación se marcan como no compatibles.
  - **Sin configurar** (*valor predeterminado*).
  - **Borrar**
  - **Baja**
  - **Media**
  - **Alta**

### <a name="device-health"></a>Estado del dispositivo

- **Requerir que el dispositivo tenga el nivel de amenaza del dispositivo**  
  Seleccione el máximo nivel de amenaza del dispositivo permitido evaluado por el [servicio de defensa frente a amenazas para dispositivos móviles](mobile-threat-defense.md). Los dispositivos que superan este nivel de amenaza se marcan como no compatibles. Para usar esta configuración, elija el nivel de amenaza permitido:

  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Protegido**: esta opción es la más segura y significa que el dispositivo no puede tener ninguna amenaza. Si se detecta cualquier nivel de amenaza en el dispositivo, se evaluará como no conforme.
  - **Bajo**: el dispositivo se evalúa como conforme si solo hay amenazas de nivel bajo. Cualquier valor por encima coloca al dispositivo en un estado de no conformidad.
  - **Medio**: el dispositivo se evalúa como conforme si las amenazas presentes en él son de nivel bajo o medio. Si se detecta que el dispositivo tiene amenazas de nivel alto, se determina como no conforme.
  - **Alto**: esta opción es la menos segura, ya que permite que todos los niveles de amenaza. Quizás sea útil si utiliza esta solución solo con fines informativos.
  
> [!NOTE]
> Todos los proveedores de Mobile Threat Defense (MTD) se admiten en las implementaciones Perfil de trabajo de propiedad corporativa, dedicado y totalmente administrado de Android Enterprise mediante la configuración de la aplicación. Consulte con el proveedor de MTD la configuración exacta necesaria para admitir las plataformas del Perfil de trabajo de propiedad corporativa, dedicado y totalmente administrado de Android Enterprise en Intune.

#### <a name="google-play-protect"></a>Google Play Protect

- **Atestación de dispositivo SafetyNet**  
  especifique el nivel de [atestación de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que se debe cumplir. Las opciones son:
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Comprobar integridad básica**
  - **Comprobar integridad básica y dispositivos certificados**

### <a name="device-properties"></a>Propiedades de dispositivos

#### <a name="operating-system-version"></a>Versión de sistema operativo

- **Versión de SO mínima**  
  Cuando un dispositivo no cumple el requisito de versión mínima del sistema operativo, se notifica como no compatible. Además, se mostrará un vínculo con información sobre cómo actualizar el sistema. El usuario final puede actualizar el dispositivo y luego acceder a los recursos de la organización.

  *De forma predeterminada, no se configura ninguna versión*.

- **Versión de SO máxima**  
  si un dispositivo usa una versión del sistema operativo posterior a la de la regla, se bloquea el acceso a los recursos de la organización. Se pide al usuario que se ponga en contacto con el administrador de TI. El dispositivo no podrá acceder a los recursos de la empresa mientras no se cambie la regla para permitir la versión de sistema operativo.

  *De forma predeterminada, no se configura ninguna versión*.

- **Nivel mínimo de revisión de seguridad**  
  seleccione el nivel de revisión de seguridad más antiguo que puede tener un dispositivo. Los dispositivos que no estén al menos en este nivel de revisión se consideran no conformes. La fecha debe especificarse en el formato AAAA-MM-DD.

  *De forma predeterminada, no se configura ninguna fecha*.

### <a name="system-security"></a>Seguridad del sistema

- **Requerir una contraseña para desbloquear dispositivos móviles**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: los usuarios deben introducir una contraseña para poder acceder al dispositivo.

- **Tipo de contraseña requerida**  
  elija si una contraseña debe incluir solo caracteres numéricos o una combinación de números y otros caracteres. Las opciones son:
  - **Dispositivo predeterminado**: para evaluar el cumplimiento de las contraseñas, asegúrese de seleccionar una seguridad de contraseña distinta de *Predeterminada del dispositivo*.
  - **Contraseña necesaria, sin restricciones**
  - **Biométrica deficiente** - [Biométricas eficientes frente a deficientes](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (abre el sitio web de Android).
  - **Numérica** (*valor predeterminado*): la contraseña solo debe contener números, por ejemplo, `123456789`. Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Complejo numérico**: no se permiten números repetidos ni consecutivos, como "1111" o "1234". Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Alfabético**: son necesarias letras del alfabeto. No son necesarios números ni símbolos. Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Alfanumérica**: incluye letras mayúsculas, minúsculas y caracteres numéricos. Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Alfanumérica con símbolos**: incluye letras mayúsculas, minúsculas, caracteres numéricos, signos de puntuación y símbolos.

  En función del *tipo de contraseña* que seleccione, están disponibles las opciones siguientes:
  - **Longitud mínima de la contraseña**  
    escriba la longitud mínima que debe tener la contraseña, entre 4 y 16 caracteres.  

  - **Número de caracteres requeridos**  
    escriba el número de caracteres que debe tener la contraseña, entre 0 y 16 caracteres.

  - **Número de caracteres en minúscula requeridos**  
    escriba el número de caracteres en minúscula que debe tener la contraseña, entre 0 y 16.

  - **Número de caracteres en mayúscula requeridos**  
    escriba el número de caracteres en mayúscula que debe tener la contraseña, entre 0 y 16.

  - **Número de caracteres que no sean letras requeridos**  
    escriba el número de caracteres que no son letras del alfabeto que debe tener la contraseña, entre 0 y 16 caracteres.

  - **Número de caracteres numéricos requeridos**  
    escriba el número de caracteres numéricos (`1`, `2`, `3`, etc.) que debe tener la contraseña, entre 0 y 16.

  - **Número de caracteres de símbolo requeridos**  
    escriba el número de caracteres de símbolo (`&`, `#`, `%`, etc.) que debe tener la contraseña, entre 0 y 16.

  - **Máximo de minutos de inactividad antes de solicitar la contraseña**  
    especifique el tiempo de inactividad antes de que el usuario deba volver a escribir la contraseña. Las opciones incluyen el valor predeterminado *Sin configurar* y entre *1 minuto* y *8 horas*.

  - **Número de días hasta que expire la contraseña**  
    especifique el número de días, entre 1 y 365, hasta que se deba cambiar la contraseña del dispositivo. Por ejemplo, para cambiar la contraseña después de 60 días, escriba `60`. Cuando la contraseña expire, se le solicitará a los usuarios que creen una nueva contraseña.

    *De forma predeterminada, no se configura ningún valor*.

  - **Número de contraseñas requeridas antes de que el usuario pueda reusar una**  
    indique el número de contraseñas recientes que no se pueden volver a usar, entre 1 y 24. Utilice esta configuración para impedir que el usuario cree contraseñas usadas anteriormente.  

    *De forma predeterminada, no se configura ninguna versión*.

#### <a name="encryption"></a>Cifrado

- **Cifrado de almacenamiento de datos en el dispositivo**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: se cifra el almacenamiento de datos en los dispositivos.

  No tiene que configurar este valor ya que los dispositivos Android Enterprise fuerzan el cifrado.

## <a name="work-profile"></a>Perfil de trabajo

### <a name="microsoft-defender-atp---for-work-profile"></a>ATP de Microsoft Defender: *para perfil de trabajo*

- **Solicitar que el dispositivo tenga o esté por debajo de la puntuación de riesgo de la máquina**  
  Seleccione la puntuación de riesgo de la máquina máxima permitida para los dispositivos evaluados por ATP de Microsoft Defender. Los dispositivos que superan esta puntuación se marcan como no compatibles.
  - **Sin configurar** (*valor predeterminado*).
  - **Borrar**
  - **Baja**
  - **Media**
  - **Alta**

### <a name="device-health---for-work-profile"></a>Estado del dispositivo: *para perfil de trabajo*

- **Dispositivos con acceso "root"**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Bloquear**: marcar los dispositivos raíz (con jailbreak) como no conformes.

- **Requerir que el dispositivo tenga el nivel de amenaza del dispositivo**  
  Seleccione el máximo nivel de amenaza del dispositivo permitido evaluado por el [servicio de defensa frente a amenazas para dispositivos móviles](mobile-threat-defense.md). Los dispositivos que superan este nivel de amenaza se marcan como no compatibles. Para usar esta configuración, elija el nivel de amenaza permitido:
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Protegido**: esta opción es la más segura y significa que el dispositivo no puede tener ninguna amenaza. Si se detecta cualquier nivel de amenaza en el dispositivo, se evaluará como no conforme.
  - **Bajo**: el dispositivo se evalúa como conforme si solo hay amenazas de nivel bajo. Cualquier valor por encima coloca al dispositivo en un estado de no conformidad.
  - **Medio**: el dispositivo se evalúa como conforme si las amenazas presentes en él son de nivel bajo o medio. Si se detecta que el dispositivo tiene amenazas de nivel alto, se determina como no conforme.
  - **Alto**: esta opción es la menos segura, ya que permite que todos los niveles de amenaza. Quizás sea útil si utiliza esta solución solo con fines informativos.

#### <a name="google-play-protect---for-work-profile"></a>Google Play Protect: *para perfil de trabajo*

- **Google Play Services está configurado**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: se requiere que la aplicación Google Play Services esté instalada y habilitada. Google Play Services permite actualizaciones de seguridad y es una dependencia de nivel base para muchas características de seguridad en los dispositivos de Google certificados.
  
- **Proveedor de seguridad actualizada**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: se requiere que un proveedor de seguridad actualizado pueda proteger un dispositivo frente a vulnerabilidades conocidas.
  
- **Atestación de dispositivo SafetyNet**  
  especifique el nivel de [atestación de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que se debe cumplir. Las opciones son:
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Comprobar integridad básica**
  - **Comprobar integridad básica y dispositivos certificados**

> [!NOTE]
> En los dispositivos Android Enterprise, **Examen de amenazas en las aplicaciones** es una directiva de configuración de dispositivos. Con una directiva de configuración, los administradores pueden habilitar la configuración en un dispositivo. Vea [Configuración de las restricciones de dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties---for-work-profile"></a>Propiedades del dispositivo: *para perfil de trabajo*

#### <a name="operating-system-version---for-work-profile"></a>Versión del sistema operativo: *para perfil de trabajo*

- **Versión de SO mínima**  
Cuando un dispositivo no cumple el requisito de versión mínima del sistema operativo, se notifica como no compatible. Además, se mostrará un vínculo con información sobre cómo actualizar el sistema. El usuario final puede actualizar el dispositivo y luego acceder a los recursos de la organización.

  *De forma predeterminada, no se configura ninguna versión*.

- **Versión de SO máxima**  
si un dispositivo usa una versión del sistema operativo posterior a la de la regla, se bloquea el acceso a los recursos de la organización. Se pide al usuario que se ponga en contacto con el administrador de TI. El dispositivo no podrá acceder a los recursos de la empresa mientras no se cambie la regla para permitir la versión de sistema operativo.

  *De forma predeterminada, no se configura ninguna versión*.

### <a name="system-security---for-work-profile"></a>Seguridad del sistema: *para perfil de trabajo*

- **Requerir una contraseña para desbloquear dispositivos móviles**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: los usuarios deben introducir una contraseña para poder acceder al dispositivo.  

  Esta configuración se aplica en el nivel de dispositivo. Si solo tiene que solicitar una contraseña en el nivel de perfil de trabajo, entonces use una directiva de configuración. Vea [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md).

- **Tipo de contraseña requerida**  
  elija si una contraseña debe incluir solo caracteres numéricos o una combinación de números y otros caracteres. Las opciones son:
  - **Valor predeterminado del dispositivo**
  - **Biométrico de seguridad baja**
  - **Al menos numérica** (*valor predeterminado*): Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Numérica compleja**: Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Al menos alfabética**: Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Al menos alfanumérica**: Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.
  - **Al menos alfanumérica con símbolos**: Escriba la **longitud mínima de la contraseña** que un usuario debe escribir, entre 4 y 16 caracteres.

  En función del *tipo de contraseña* que seleccione, están disponibles las opciones siguientes:

  - **Máximo de minutos de inactividad antes de solicitar la contraseña**  
    especifique el tiempo de inactividad antes de que el usuario deba volver a escribir la contraseña. Las opciones incluyen el valor predeterminado *Sin configurar* y entre *1 minuto* y *8 horas*.

  - **Número de días hasta que expire la contraseña**  
    especifique el número de días, entre 1 y 365, hasta que se deba cambiar la contraseña del dispositivo. Por ejemplo, para cambiar la contraseña después de 60 días, escriba `60`. Cuando la contraseña expire, se le solicitará a los usuarios que creen una nueva contraseña.

  - **Longitud mínima de la contraseña**  
    escriba la longitud mínima que debe tener la contraseña, entre 4 y 16 caracteres.

  - **Número de contraseñas anteriores que no se pueden reutilizar**  
    indique el número de contraseñas recientes que no se pueden volver a usar. Utilice esta configuración para impedir que el usuario cree contraseñas usadas anteriormente.

#### <a name="encryption---for-work-profile"></a>Cifrado: *para perfil de trabajo*

- **Cifrado de almacenamiento de datos en el dispositivo**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: se cifra el almacenamiento de datos en los dispositivos.  

  No tiene que configurar este valor ya que los dispositivos Android Enterprise fuerzan el cifrado.

#### <a name="device-security---for-work-profile"></a>Seguridad de dispositivos: *para perfil de trabajo*

- **Bloquear aplicaciones de orígenes desconocidos**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Bloquear**: bloquee los dispositivos con orígenes habilitados mediante **Seguridad** > **Orígenes desconocidos** (*admitidos en Android 4.0 a Android 7.x. No se admite en Android 8.0 y versiones posteriores*).  

  Para realizar instalaciones de prueba de las aplicaciones, se deben permitir los orígenes desconocidos. Si no realiza instalaciones de prueba de las aplicaciones Android, establezca esta característica en **Bloquear** para habilitar esta directiva de cumplimiento.

  > [!IMPORTANT]
  > Las aplicaciones de instalación de prueba requieren que se habilite la opción **Bloquear aplicaciones de orígenes desconocidos**. Aplique esta directiva de cumplimiento solo si no realiza instalaciones de prueba de las aplicaciones Android en dispositivos.

  No tiene que configurar este valor ya que los dispositivos Android Enterprise siempre restringen la instalación desde orígenes desconocidos.

- **Integridad en tiempo de ejecución de la aplicación Portal de empresa**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: elija *Requerir* para confirmar que la aplicación Portal de empresa cumple los siguientes requisitos:
    - Tiene instalado el entorno de tiempo de ejecución predeterminado.
    - Está firmada correctamente.
    - No se encuentra en modo de depuración.
    - Se ha instalado desde un origen conocido.

- **Bloquear depuración USB en el dispositivo**  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Bloquear**: evita que los dispositivos usen la característica de depuración USB.  

  No es necesario configurar esta opción porque la depuración USB ya está deshabilitada en los dispositivos Android Enterprise.

- **Nivel mínimo de revisión de seguridad**  
  seleccione el nivel de revisión de seguridad más antiguo que puede tener un dispositivo. Los dispositivos que no estén al menos en este nivel de revisión se consideran no conformes. La fecha debe especificarse en el formato AAAA-MM-DD.

  *De forma predeterminada, no se configura ninguna fecha*.

## <a name="next-steps"></a>Pasos siguientes

- [Agregar acciones para dispositivos no compatibles](actions-for-noncompliance.md) y [usar etiquetas de ámbito para filtrar directivas](../fundamentals/scope-tags.md).
- [Supervisar las directivas de cumplimiento](compliance-policy-monitor.md).
- Vea [Configuración de directivas de cumplimiento para dispositivos Android](compliance-policy-create-android.md).
