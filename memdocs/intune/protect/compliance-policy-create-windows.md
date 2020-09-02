---
title: 'Configuración de cumplimiento de Windows 10 en Microsoft Intune: Azure | Microsoft Docs'
description: Vea una lista de todas las opciones que puede usar al establecer el cumplimiento de los dispositivos Windows 10, Windows Holographic y Surface Hub en Microsoft Intune. Compruebe el cumplimiento de los requisitos mínimo y máximo de sistema operativo, establezca restricciones de contraseña y longitud, busque soluciones antivirus de asociados, habilite el cifrado en almacenamiento de datos y mucho más.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/19/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 20d3f3967fa77ab90229915afc8b05043004b125
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88909353"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configuración de Windows 10 y versiones posteriores para marcar dispositivos como compatibles o no compatibles con Intune

En este artículo se enumeran y describen las distintas opciones de configuración de cumplimiento que se pueden establecer en dispositivos con Windows 10 y versiones posteriores en Intune. Como parte de la solución de administración de dispositivos móviles (MDM), use esta configuración para exigir BitLocker, establecer un sistema operativo mínimo y máximo, establecer un nivel de riesgo con Protección contra amenazas avanzada (ATP) de Microsoft Defender y mucho más.

Esta característica se aplica a:

- Windows 10 y versiones posteriores
- Windows Holographic for Business
- Surface Hub

Como administrador del servicio Intune, use esta configuración de cumplimiento para proteger mejor los recursos de la organización. Para más información sobre las directivas de cumplimiento y lo que hacen, vea [Introducción a las directivas de cumplimiento](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de comenzar

[Crear una directiva de cumplimiento](create-compliance-policy.md#create-the-policy). En **Plataforma**, seleccione **Windows 10 y versiones posteriores**.

## <a name="device-health"></a>Estado del dispositivo

### <a name="windows-health-attestation-service-evaluation-rules"></a>Reglas de evaluación del servicio Atestación de estado de Windows

- **Requerir BitLocker**:  
   La característica Cifrado de unidad BitLocker de Windows cifra todos los datos almacenados en el volumen del sistema operativo Windows. BitLocker usa el Módulo de plataforma segura (TPM) para ayudar a proteger el sistema operativo Windows y los datos de usuario. También ayuda a confirmar que un equipo no se manipule, incluso si se deja desatendido, se pierde o se lo roban. Si el equipo está equipado con un TPM compatible, BitLocker usa este para bloquear las claves de cifrado que protegen los datos. Como resultado, las claves no son accesibles hasta que el TPM comprueba el estado del equipo.  

  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: el dispositivo puede proteger los datos almacenados en la unidad contra el acceso no autorizado cuando el sistema está apagado o hibernando.
  
  [CSP de HealthAttestation de dispositivo: BitLockerStatus](/windows/client-management/mdm/healthattestation-csp)

- **Debe estar habilitado el arranque seguro en el dispositivo**:  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: se obliga al sistema a arrancar en un estado de fábrica de confianza. Los componentes principales que se usan para arrancar el equipo deben tener las firmas de cifrado correctas que son de confianza para la organización que fabricó el dispositivo. El firmware UEFI comprueba la firma antes de permitir iniciar el equipo. Si los archivos se manipulan, lo que rompe su firma, el sistema no arranca.

  > [!NOTE]
  > La opción **Debe estar habilitado el arranque seguro en el dispositivo** se admite en algunos dispositivos TPM 1.2 y 2.0. Para los dispositivos que no son compatibles con TPM 2.0 o versiones posteriores, el estado de la directiva en Intune se muestra como **No conforme**. Para más información sobre las versiones compatibles, vea [Atestación de estado de dispositivo](/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Requiere integridad de código**:  
  la integridad de código es una característica que valida la integridad de un archivo del sistema o controlador cada vez que se carga en la memoria.
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: requerir la integridad de código, que detecta si se está cargando en el kernel un archivo del sistema o controlador sin firmar. También detecta si se ha modificado un archivo del sistema mediante software malintencionado o si lo ha ejecutado un usuario con privilegios de administrador.

Más recursos:

- Vea [CSP de atestación de mantenimiento](/windows/client-management/mdm/healthattestation-csp) para obtener información sobre cómo funciona el servicio HAS.
- [Sugerencia de soporte: Uso de la configuración de atestación de estado de dispositivo como parte de la directiva de cumplimiento de Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643).

## <a name="device-properties"></a>Propiedades de dispositivos

### <a name="operating-system-version"></a>Versión de sistema operativo

- **Versión mínima del sistema operativo**:  
  escriba la versión mínima permitida, con el formato numérico **major.minor.build.CU**. Para obtener el valor correcto, abra un símbolo del sistema y escriba `ver`. El comando `ver` devuelve la versión en este formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Cuando un dispositivo tiene una versión anterior a la versión del sistema operativo que especifica, se notifica como no conforme. Además, se mostrará un vínculo con información sobre cómo actualizar el sistema. El usuario final puede elegir actualizar su dispositivo. Después de la actualización, puede acceder a los recursos de la empresa.

- **Versión máxima de SO**:  
  escriba la versión máxima permitida, con el formato numérico **major.minor.build.revision**. Para obtener el valor correcto, abra un símbolo del sistema y escriba `ver`. El comando `ver` devuelve la versión en este formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Cuando un dispositivo usa una versión de sistema operativo posterior a la que se ha indicado, se bloquea el acceso a los recursos de la empresa. Se pide al usuario final que se ponga en contacto con el administrador de TI. El dispositivo no podrá acceder a los recursos de la empresa mientras no se cambie la regla para permitir la versión de sistema operativo.

- **Versión mínima del SO requerida para dispositivos móviles**:  
  escriba la versión mínima permitida, con el formato numérico major.minor.build.

  Cuando un dispositivo tiene una versión anterior a la versión del sistema operativo que especifica, se notifica como no conforme. Además, se mostrará un vínculo con información sobre cómo actualizar el sistema. El usuario final puede elegir actualizar su dispositivo. Después de la actualización, puede acceder a los recursos de la empresa.

- **Versión máxima del SO requerida para dispositivos móviles**:  
  escriba la versión máxima permitida, con el formato numérico major.minor.build.

  Cuando un dispositivo usa una versión de sistema operativo posterior a la que se ha indicado, se bloquea el acceso a los recursos de la empresa. Se pide al usuario final que se ponga en contacto con el administrador de TI. El dispositivo no podrá acceder a los recursos de la empresa mientras no se cambie la regla para permitir la versión de sistema operativo.

- **Compilaciones válidas del sistema operativo**:  
  escriba un intervalo para las versiones de sistema operativo aceptables, incluida la mínima y la máxima. También puede **exportar** una lista de archivos de valores separados por comas (CSV) de estos números de compilación aceptables del sistema operativo.

## <a name="configuration-manager-compliance"></a>Comprobación del cumplimiento de Configuration Manager

Solo se aplica a dispositivos administrados conjuntamente en los que se ejecuta Windows 10 y versiones posteriores. Los dispositivos solo de Intune devuelven un estado de no disponible.

- **Requerir cumplimiento del dispositivo de Configuration Manager**:  
  - **Sin configurar** (*valor predeterminado*): Intune no comprueba ninguna configuración de Configuration Manager para el cumplimiento.
  - **Requerir**: exija que toda la configuración (elementos de configuración) de Configuration Manager sea compatible.

    Por ejemplo, exige que todas las actualizaciones de software se instalen en los dispositivos. En Configuration Manager, este requisito tiene el estado "Instalado". Si algún programa del dispositivo se encuentra en un estado desconocido, dicho dispositivo no será conforme en Intune.

  > [!NOTE]
  > Use solo **Require device compliance from Configuration Manager** (Exigir el cumplimiento del dispositivo de Configuration Manager) cuando la carga de trabajo de cumplimiento para la administración conjunta esté establecida en *Configuration Manager*. Cuando se usa esta opción con la carga de trabajo de cumplimiento establecida en *Intune*, las evaluaciones de cumplimiento generales pueden verse afectadas.

## <a name="system-security"></a>Seguridad del sistema

### <a name="password"></a>Contraseña

- **Requerir una contraseña para desbloquear dispositivos móviles**:  
  - **Sin configurar** (*valor predeterminado*): no se evalúa el cumplimiento o incumplimiento de esta opción de configuración.
  - **Requerir**: los usuarios deben introducir una contraseña para poder acceder al dispositivo. 

- **Contraseñas sencillas**:  
  - **Sin configurar** (*valor predeterminado*): los usuarios pueden crear contraseñas sencillas como **1234** o **1111**.
  - **Bloquear**: los usuarios no puedan crear contraseñas sencillas, como **1234** o **1111**.

- **Tipo de contraseña**:  
  elija el tipo de contraseña o PIN requerido. Las opciones son:
  - **Valor predeterminado del dispositivo** (*valor predeterminado*): requiere una contraseña, un PIN numérico o un PIN alfanumérico.
  - **Numérico**: requiere una contraseña o un PIN numérico.
  - **Alfanumérico**: requiere una contraseña o un PIN alfanumérico.  
  
  Cuando se establece en *Alfanumérico*, están disponibles las opciones siguientes:  
  - **Complejidad de la contraseña**:  
    Las opciones son:
    - **Requerir el uso de dígitos y letras minúsculas** (*valor predeterminado*)
    - **Requerir el uso de dígitos, letras minúsculas y mayúsculas**
    - **Requerir dígitos, letras minúsculas, letras mayúsculas y caracteres especiales**

    > [!TIP]
    > Las directivas de contraseña alfanuméricas pueden ser complejas. Se recomienda que los administradores lean los CSP para obtener más información:
    >
    > - [CSP de DeviceLock/AlphanumericDevicePasswordRequired](/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [CSP de DeviceLock/MinDevicePasswordComplexCharacters](/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Longitud mínima de la contraseña**:  
  especifique el número mínimo de dígitos o caracteres que debe tener la contraseña.

- **Máximo de minutos de inactividad antes de solicitar la contraseña**:  
  especifique el tiempo de inactividad antes de que el usuario deba volver a escribir la contraseña.

- **Expiración de la contraseña (días)** :  
  escriba el número de días (entre 1 y 730) que faltan para que expire la contraseña y se deba crear una nueva.

- **Número de contraseñas anteriores que no se pueden reutilizar**:  
  escriba el número de contraseñas usadas previamente que no se pueden volver a usar.

- **Requerir contraseña cuando el dispositivo vuelve de un estado de inactividad (Mobile y Holographic)** :  
  - **Sin configurar** (*valor predeterminado*).
  - **Requerir**: requerir a los usuarios que introduzcan la contraseña cada vez que el dispositivo vuelve de un estado de inactividad.

  > [!IMPORTANT]
  > Cuando el requisito de contraseña se cambia en un escritorio de Windows, los usuarios se ven afectados la próxima vez que inician sesión, porque es entonces cuando el dispositivo pasa de inactivo a activo. Los usuarios con contraseñas que cumplan el requisito de todos modos tendrán que cambiarlas.

### <a name="encryption"></a>Cifrado

- **Cifrado de almacenamiento de datos en un dispositivo**:  
  Esta configuración se aplica a todas las unidades de un dispositivo.
  - **Sin configurar** (*valor predeterminado*).
  - **Requerir**: use *Requerir* para cifrar el almacenamiento de datos en los dispositivos.
  
   [CSP de DeviceStatus: DeviceStatus/Compliance/EncryptionCompliance](/windows/client-management/mdm/devicestatus-csp)

  > [!NOTE]
  > La configuración **Cifrado de almacenamiento de datos en el dispositivo** comprueba de manera genérica la presencia de cifrado en el dispositivo. Para conseguir una configuración de cifrado más sólida, considere la posibilidad de usar **Requerir BitLocker**, que aprovecha la Atestación de estado de dispositivo de Windows para validar el estado de Bitlocker en el nivel de TPM.

### <a name="device-security"></a>Seguridad de dispositivos  

- **Firewall**:  
  - **No configurado** (*valor predeterminado*): Intune no controla el firewall de Microsoft Defender ni cambia la configuración existente.
  - **Requerir**: activa el firewall de Microsoft Defender y evita que los usuarios lo desactiven.

  [CSP del firewall](/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Si el dispositivo se sincroniza inmediatamente después de un reinicio, o lo hace inmediatamente al iniciarse tras una suspensión, es posible que esta configuración informe de ello como un **error**. Es posible que este escenario no afecte al estado general del cumplimiento del dispositivo. Para volver a evaluar el estado de cumplimiento, [sincronice manualmente el dispositivo](../user-help/sync-your-device-manually-windows.md).

- **Módulo de plataforma segura (TPM)** :  
  - **No configurado** (*valor predeterminado*): Intune no comprueba si el dispositivo tiene una versión de chip de TPM.
  - **Requerir**: Intune comprueba el cumplimiento de la versión del chip TPM. El dispositivo es conforme si la versión del chip TPM es mayor que **0** (cero). El dispositivo no es conforme si no hay una versión de TPM en el dispositivo.

  [CSP de DeviceStatus: DeviceStatus/TPM/SpecificationVersion](/windows/client-management/mdm/devicestatus-csp)
  
- **Antivirus**:  
  - **Sin configurar** (*valor predeterminado*): Intune no busca soluciones antivirus instaladas en el dispositivo.
  - **Requerir**: comprobar el cumplimiento mediante soluciones antivirus registradas con el [Centro de seguridad de Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), como Symantec y Microsoft Defender.

  [CSP de DeviceStatus: DeviceStatus/Antivirus/Status](/windows/client-management/mdm/devicestatus-csp)

- **Antiespía**:  
  - **Sin configurar** (*valor predeterminado*): Intune no busca soluciones antiespía instaladas en el dispositivo.
  - **Requerir**: comprobar el cumplimiento mediante soluciones antiespía registradas con el [Centro de seguridad de Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), como Symantec y Microsoft Defender.

  [CSP de DeviceStatus: DeviceStatus/Antispyware/Status](/windows/client-management/mdm/devicestatus-csp)

### <a name="defender"></a>Defender

*La siguiente configuración de cumplimiento es compatible con la versión para escritorio de Windows 10.*

- **Antimalware de Microsoft Defender**:  
  - **No configurado** (*valor predeterminado*): Intune no controla el servicio ni cambia la configuración existente.
  - **Requerir**: activa el servicio antimalware de Microsoft Defender y evita que los usuarios lo desactiven.

- **Versión mínima de Antimalware de Microsoft Defender**:  
  Escriba la versión mínima permitida del servicio antimalware de Microsoft Defender. Por ejemplo, escriba `4.11.0.0`. Cuando se deja en blanco, se puede usar cualquier versión del servicio antimalware de Microsoft Defender.

  *De forma predeterminada, no se configura ninguna versión*.

- **Actualización de la inteligencia de seguridad de Antimalware de Microsoft Defender**:  
  Controla las actualizaciones de protección contra amenazas y virus de seguridad de Windows en los dispositivos.
  - **Sin configurar** (*valor predeterminado*): Intune no aplica estos requisitos.
  - **Requerir**: fuerza a la inteligencia de seguridad de Microsoft Defender a actualizarse.

  [CSP de Defender: CSP de Defender/Health/SignatureOutOfDate](/windows/client-management/mdm/defender-csp)
  
  Para obtener más información, vea [Actualizaciones de inteligencia de seguridad para el antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

- **Protección en tiempo real**:  
  - **No configurado** (*valor predeterminado*): Intune no controla la característica ni cambia la configuración existente.
  - **Requerir**: activa la protección en tiempo real, que detecta malware, spyware y otro tipo de software no deseado.  

  [CSP de directiva: CSP de Defender/AllowRealtimeMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>ATP de Microsoft Defender

### <a name="microsoft-defender-advanced-threat-protection-rules"></a>Reglas de Advanced Threat Protection de Microsoft Defender

- **Require the device to be at or under the machine risk score**: (Requerir que el dispositivo tenga la misma puntuación de riesgo de la máquina o inferior):  
  use este valor de configuración para hacer que la evaluación del riesgo de los servicios de amenazas de defensa sea una condición para el cumplimiento. Elija el máximo nivel de amenaza permitido:
  - **Sin configurar** (*valor predeterminado*).  
  - **Despejado**: esta opción es la más segura y el dispositivo no puede tener ninguna amenaza. Si se detecta cualquier nivel de amenaza en el dispositivo, se evaluará como no conforme.
  - **Bajo**: el dispositivo se evalúa como conforme si solo hay amenazas de nivel bajo. Cualquier valor por encima coloca al dispositivo en un estado de no conformidad.
  - **Medio:** el dispositivo se evalúa como compatible si las amenazas existentes en él son de nivel bajo o medio. Si se detecta que el dispositivo tiene amenazas de nivel alto, se determina como no conforme.
  - **Alto**: esta opción es la menos segura, ya que permite todos los niveles de amenaza. Quizás sea útil si utiliza esta solución solo con fines informativos.
  
  Para configurar ATP (protección contra amenazas avanzada) de Microsoft Defender como servicio de defensa contra amenazas, consulte [Habilitación de ATP de Microsoft Defender con acceso condicional](advanced-threat-protection.md).

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business usa la plataforma **Windows 10 y versiones posteriores**. Windows Holographic for Business es compatible con las siguientes opciones de configuración:

- **Seguridad del sistema** > **Cifrado** > **Cifrado de almacenamiento de datos en el dispositivo**.

Para verificar el cifrado de dispositivo en Microsoft HoloLens, vea [Verificar el cifrado de dispositivo](/hololens/security-encryption-data-protection).

## <a name="surface-hub"></a>Surface Hub

Surface Hub usa la plataforma **Windows 10 y versiones posteriores**. Las instancias de Surface Hub son compatibles tanto con el cumplimiento como con el acceso condicional. Para habilitar estas características en Surface Hubs, le recomendamos que [habilite la inscripción automática de Windows 10 ](../enrollment/windows-enroll.md) en Intune (se necesita Azure Active Directory [Azure AD]) y dirija los dispositivos de Surface Hub como grupos de dispositivos. Se requiere que Surface Hub se una a Azure AD para que el cumplimiento y el acceso condicional funcionen.

Para instrucciones, consulte [Configuración de la inscripción de dispositivos Windows](../enrollment/windows-enroll.md).

## <a name="next-steps"></a>Pasos siguientes

- [Agregar acciones para dispositivos no compatibles](actions-for-noncompliance.md) y [usar etiquetas de ámbito para filtrar directivas](../fundamentals/scope-tags.md).
- [Supervisar las directivas de cumplimiento](compliance-policy-monitor.md).
- Vea la [configuración de directivas de cumplimiento para dispositivos Windows 8.1](compliance-policy-create-windows-8-1.md).