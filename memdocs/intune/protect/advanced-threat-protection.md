---
title: Uso de ATP de Microsoft Defender en Microsoft Intune (Azure) | Microsoft Docs
description: Use Advanced Threat Protection de Microsoft Defender (ATP de Microsoft Defender) con Intune. Puede instalar, configurar e incorporar ATP en sus dispositivos de Intune, y usar una evaluación de riesgos de ATP de dispositivos con las directivas de cumplimiento y acceso condicional de los dispositivos de Intune para proteger los recursos de red.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/24/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35871aba60d45719b9a6da50184a6113f72e6044
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83989302"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Aplicación del cumplimiento de ATP de Microsoft Defender con acceso condicional en Intune

Puede integrar Advanced Threat Protection de Microsoft Defender (ATP de Microsoft Defender) con Microsoft Intune como solución de Mobile Threat Defense. Esta integración puede ayudarle a evitar infracciones de seguridad y a limitar su impacto en una organización. ATP de Microsoft Defender funciona con dispositivos que ejecutan Windows 10 o una versión posterior y con dispositivos Android.

Para que funcione correctamente, se usan las siguientes tareas de configuración de manera conjunta:

- **Establecer una conexión de servicio a servicio entre Intune y ATP de Microsoft Defender**. Esta conexión permite que ATP de Microsoft Defender recopile datos sobre el riesgo de la máquina de los dispositivos Windows 10 y Android que se administran con Intune.
- **Usar un perfil de configuración de dispositivo para incorporar dispositivos con ATP de Microsoft Defender**. Los dispositivos se incorporan para configurarlos y que se comuniquen con ATP de Microsoft Defender y para proporcionar datos que ayuden a evaluar su nivel de riesgo.
- **Usar una directiva de cumplimiento de dispositivos para establecer el nivel de riesgo que quiere permitir**. ATP de Microsoft Defender notifica los niveles de riesgo. Los dispositivos que superan el nivel de riesgo permitido se identifican como no compatibles.
- **Usar una directiva de acceso condicional** para impedir que los usuarios accedan a los recursos corporativos desde dispositivos no compatibles.

Al integrar Intune con ATP de Microsoft Defender, puede aprovechar las ventajas de Threat & Vulnerability Management (TVM) de ATP y [usar Intune para corregir las debilidades de los puntos de conexión que ha identificado TVM](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Ejemplo de uso de ATP de Microsoft Defender con Intune

En el siguiente ejemplo se explica cómo funcionan conjuntamente estas soluciones para ayudar a proteger la organización. En este ejemplo, ATP de Microsoft Defender e Intune ya están integrados.

Considere el caso en que alguien envía datos adjuntos de Word con código malintencionado insertado a un usuario de la organización.

- El usuario abre los datos adjuntos y habilita el contenido.
- Se inicia un ataque con privilegios elevados y un atacante desde una máquina remota tiene derechos de administrador al dispositivo de la víctima.
- Después, el atacante, accede remotamente a otros dispositivos del usuario. Esta infracción de seguridad puede afectar a toda la organización.

ATP de Microsoft Defender puede ayudar a resolver eventos de seguridad como el de este escenario.

- En nuestro ejemplo, ATP de Microsoft Defender detecta que el dispositivo ejecutó código anómalo, experimentó una elevación de privilegios de proceso, inyectó código malintencionado y emitió un shell remoto sospechoso.
- En función de estas acciones del dispositivo, ATP de Microsoft Defender [clasifica el dispositivo como de alto riesgo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) e incluye un informe detallado de actividad sospechosa en el portal de Security Center de Microsoft Defender.

Como tiene una directiva de cumplimiento de dispositivos de Intune para clasificar los dispositivos con un nivel de riesgo *Medio* o *Alto* como no compatibles, el dispositivo en peligro se clasifica como no compatible. Esta clasificación permite que se inicie la directiva de acceso condicional y que bloquee el acceso a los recursos corporativos desde ese dispositivo.

## <a name="prerequisites"></a>Requisitos previos

Para usar ATP de Microsoft Defender con Intune, asegúrese de que tiene configurados los siguientes requisitos previos y listos para su uso:

- Inquilino con licencia para Enterprise Mobility + Security E3 y Windows E5 (o Microsoft 365 Enterprise E5)
- Entorno de Microsoft Intune, con dispositivos Windows 10 [administrados por Intune](../enrollment/windows-enroll.md) o dispositivos Android que también estén unidos a Azure AD.
- [ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) y acceso al Centro de seguridad de Microsoft Defender (portal de ATP)

> [!NOTE]
> ATP de Microsoft Defender no es compatible con las directivas de protección de aplicaciones de Intune de iOS/iPadOS y Android.

## <a name="enable-microsoft-defender-atp-in-intune"></a>Habilitación de ATP de Microsoft Defender en Intune

El primer paso que debe realizar es configurar la conexión de servicio a servicio entre Intune y ATP de Microsoft Defender. Para ello es necesario acceso administrativo a Security Center de Microsoft Defender y a Intune.

### <a name="to-enable-defender-atp"></a>Para habilitar ATP de Defender

Solo tiene que habilitar ATP de Defender una vez por inquilino.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Endpoint security** (Seguridad del punto de conexión)  > **ATP de Microsoft Defender** y, luego, seleccione **Abrir el Centro de seguridad de Microsoft Defender**.

   ![Seleccionar para abrir el Centro de seguridad de Microsoft Defender](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

3. En el **Centro de seguridad de Microsoft Defender**, siga estos pasos:
   1. Seleccione **Configuración** > **Características avanzadas**.
   2. Para **Microsoft Intune connection** (Conexión con Intune), elija **Activado**:

      ![Habilitar la conexión a Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

   3. Seleccione **Guardar preferencias**.

4. Vuelva a **ATP de Microsoft Defender** en el Centro de administración de Microsoft Endpoint Manager. En **Configuración de la directiva de cumplimiento de MDM**, en función de las necesidades de su organización, haga lo siguiente:
   - Establezca **Conectar dispositivos Windows de la versión 10.0.15063 y posteriores a ATP de Microsoft Defender** en **Activado** y/o
   - Establezca **Conectar dispositivos Android de la versión 6.0.0 y posteriores a ATP de Microsoft Defender** en **Activado**.

5. Seleccione **Guardar**.

> [!TIP]
> Al integrar una nueva aplicación en Intune Mobile Threat Defense y habilitar la conexión con Intune, este servicio crea una directiva de acceso condicional clásica en Azure Active Directory. Todas las aplicaciones de MTD que integre, incluido [ATP de Defender](advanced-threat-protection.md) o cualquiera de nuestros [asociados de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionales, crean una directiva de acceso condicional clásica. Estas directivas se pueden omitir, pero no se deben editar, eliminar ni deshabilitar.
>
> Si se elimina la directiva clásica, deberá eliminar la conexión a Intune que era responsable de su creación y, a continuación, configurarla de nuevo. Esto vuelve a crear la directiva clásica. No se admite la migración de directivas clásicas para aplicaciones de MTD al nuevo tipo de directiva para el acceso condicional.
>
> Directivas de acceso condicional clásicas para aplicaciones de MTD:
>
> - Las usa Intune MTD para requerir que los dispositivos estén registrados en Azure AD, de modo que dispongan de un id. de dispositivo antes de comunicarse con los asociados de MTD. El id. es necesario para que los dispositivos puedan informar de su estado correctamente a Intune.
> - No tiene ningún efecto en otros recursos o aplicaciones en la nube.
> - Son diferentes a las directivas de acceso condicional que puede crear para ayudarle con la administración de MTD.
> - No interactúan de forma predeterminada con otras directivas de acceso condicional usadas para la evaluación.
>
> Para ver las directivas de acceso condicional clásicas, en [Azure](https://portal.azure.com/#home), vaya a **Azure Active Directory** > **Acceso condicional** > **Directivas clásicas**.

## <a name="onboard-windows-devices-by-using-a-configuration-profile"></a>Incorporación de dispositivos Windows mediante un perfil de configuración 

En el caso de la plataforma Windows, después de establecer la conexión de servicio a servicio entre Intune y ATP de Microsoft Defender, se incorporan los dispositivos administrados por Intune a ATP para que se puedan recopilar y usar los datos sobre su nivel de riesgo. Para incorporar los dispositivos, se usa un perfil de configuración de dispositivo para ATP de Microsoft Defender.

Cuando estableció la conexión a ATP de Microsoft Defender, Intune recibió un paquete de configuración de incorporación de ATP de Microsoft Defender de ATP de Microsoft Defender. Este paquete se implementa en los dispositivos con el perfil de configuración de dispositivo. El paquete de configuración configura los dispositivos para que se comuniquen con los [servicios de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar archivos, detectar amenazas e informar del riesgo a ATP de Microsoft Defender. Después de incorporar un dispositivo mediante el paquete de configuración, no es necesario hacerlo de nuevo. También puede incorporar dispositivos mediante una [directiva de grupo o Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-device-configuration-profile"></a>Creación de un perfil de configuración de dispositivo

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba la información que desee en **Nombre** y **Descripción**.
4. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**. 
5. En **Tipo de perfil**, seleccione **ATP de Microsoft Defender (Windows 10 Desktop)** .
6. Defina la configuración:

   - **Tipo de paquete de configuración del cliente ATP de Microsoft Defender**: seleccione **Incorporar** para agregar el paquete de configuración al perfil. Seleccione **Cesar** para quitar el paquete de configuración del perfil.
  
     > [!NOTE]
     > Si ha establecido correctamente una conexión con ATP de Microsoft Defender, Intune **incorporará** automáticamente el perfil de configuración, mientras que la configuración **Tipo de paquete de configuración del cliente ATP de Microsoft Defender** no estará disponible.
  
   - **Uso compartido de muestras para todos los archivos**: la opción **Habilitar** permite recopilar muestras y compartirlas con ATP de Microsoft Defender. Por ejemplo, si ve un archivo sospechoso, puede enviarlo a ATP de Microsoft Defender para un análisis profundo. **No configurado**: no se comparte ninguna muestra con ATP de Microsoft Defender.
   - **Frecuencia de informes de telemetría urgentes**: para los dispositivos que presentan un riesgo alto, **habilite** esta opción para informar de la telemetría al servicio de ATP de Microsoft Defender con más frecuencia.

     [Incorporar máquinas Windows 10 con Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) tiene más detalles sobre estas configuraciones de ATP de Microsoft Defender.

7. Seleccione **Aceptar** y **Crear** para guardar los cambios, lo que crea el perfil.
8. [Asigne el perfil de configuración de dispositivo](../configuration/device-profile-assign.md) a los dispositivos que quiera evaluar con ATP de Microsoft Defender.

## <a name="create-and-assign-the-compliance-policy"></a>Creación y asignación de la directiva de cumplimiento

Para los dispositivos Windows y Android, la directiva de cumplimiento determina el nivel de riesgo que se considera aceptable para un dispositivo.

Si no está familiarizado con la creación de una directiva de cumplimiento, consulte el procedimiento [Creación de una directiva](../protect/create-compliance-policy.md#create-the-policy) del artículo *Creación de una directiva de cumplimiento en Microsoft Intune*. La siguiente información es específica de la configuración de ATP de Defender como parte de una directiva de cumplimiento.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Dispositivos** > **Directivas de cumplimiento** > **Directivas** > **Crear directiva**.

3. En **Plataforma**, seleccione *Windows 10 y versiones posteriores*, **Administrador de dispositivos Android** o **Android Enterprise**. Luego, seleccione **Crear** para abrir la ventana de configuración **Crear directiva**.

4. Rellene el campo **Nombre** para que le ayude a identificarla más tarde. También puede especificar una descripción en **Descripción**.
  
5. En la pestaña **Compliance settings** (Configuración de cumplimiento), expanda el grupo **Microsoft Defender ATP** (ATP de Microsoft Defender) y establezca **Require the device to be at or under the machine risk score** (Requerir que el dispositivo tenga la misma puntuación de riesgo de la máquina o inferior) en su nivel preferido.

   Las clasificaciones de nivel de amenaza vienen [determinadas por ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Borrar**: este nivel es el más seguro. El dispositivo no puede tener ninguna amenaza existente y aún puede acceder a los recursos de la empresa. Si se encuentra alguna amenaza, el dispositivo se clasificará como no conforme. (ATP de Microsoft Defender usa el valor *Seguro*).
   - **Bajo**: el dispositivo se evalúa como compatible si solo hay amenazas de nivel bajo. Los dispositivos con niveles de amenaza medio o alto no son compatibles.
   - **Media**: el dispositivo se evalúa como compatible si las amenazas que se encuentran en él son de nivel bajo o medio. Si se detectan amenazas de nivel alto, se determinará que el dispositivo no es compatible.
   - **Alta**: este nivel es el menos seguro, ya que permite todos los niveles de amenaza. Por tanto, los dispositivos con niveles de amenaza alto, medio o bajo se consideran compatibles.

6. Complete la configuración de la directiva, incluida la asignación de esta a los grupos correspondientes.

## <a name="create-a-conditional-access-policy"></a>Creación de una directiva de acceso condicional

La directiva de acceso condicional bloquea el acceso a los recursos de los dispositivos que superan el nivel de amenaza establecido en la directiva de cumplimiento. Puede bloquear el acceso del dispositivo a los recursos corporativos, como SharePoint o Exchange Online.

> [!TIP]
> Acceso condicional es una tecnología de Azure Active Directory (Azure AD). El nodo de acceso condicional al que se accede desde el Centro de administración de Microsoft Endpoint Manager es el mismo nodo que al que se accede desde *Azure AD*.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Endpoint security** (Seguridad del punto de conexión)  > **Acceso condicional** > **Nueva directiva**.

3. En **Nombre**, escriba un nombre de directiva y seleccione **Usuarios y grupos**. Utilice las opciones Incluir o Excluir para agregar los grupos para la directiva y seleccione **Listo**.

4. Seleccione **Aplicaciones en la nube** y elija las aplicaciones que desea proteger. Por ejemplo, elija **Seleccionar aplicaciones** y seleccione **Office 365 SharePoint Online** y **Office 365 Exchange Online**.

   Haga clic en **Listo** para guardar los cambios.

5. Seleccione **Condiciones** > **Aplicaciones cliente** para aplicar la directiva a las aplicaciones y los exploradores. Por ejemplo, seleccione **Sí** y habilite **Explorador** y **Aplicaciones móviles y aplicaciones de escritorio**.

   Haga clic en **Listo** para guardar los cambios.

6. Seleccione **Conceder** para aplicar el acceso condicional basado en el cumplimiento del dispositivo. Por ejemplo, seleccione **Conceder acceso** > **requieren que el dispositivo se marquen como compatibles**.

    Elija **Seleccionar** para guardar los cambios.

7. Seleccione **Habilitar directiva** y luego **crear** para guardar los cambios.

## <a name="monitor-device-compliance"></a>Supervisión del cumplimiento del dispositivo

A continuación, supervise el estado de los dispositivos que tienen la directiva de cumplimiento de ATP de Microsoft Defender.

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Dispositivos** > **Supervisar** > **Cumplimiento de directiva**.

3. Busque la directiva de ATP de Microsoft Defender en la lista y vea qué dispositivos son compatibles o no compatibles.

También puede usar el informe *Operativo* en dispositivos no conformes desde la misma ubicación:

1. Seleccione **Dispositivos** > **Monitor** > **Dispositivos no conformes**.

Para más información sobre los informes, consulte [Informes de Intune](../fundamentals/reports.md).

## <a name="view-onboarding-status"></a>Ver estado de incorporación

Para ver el estado de incorporación de todos los dispositivos Windows 10 administrados por Intune, puede ir a **Seguridad de punto de conexión** > **ATP de Microsoft Defender**. En esta página, también puede iniciar la creación de un perfil de configuración de dispositivo para incorporar más dispositivos a ATP de Microsoft Defender.

## <a name="next-steps"></a>Pasos siguientes

[Acceso condicional de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)

[Panel de riesgo de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)

[Uso de tareas de seguridad con la administración de vulnerabilidades de ATP para corregir problemas de los dispositivos](atp-manage-vulnerabilities.md).

[Introducción a las directivas de cumplimiento de dispositivos de Intune](device-compliance-get-started.md)
