---
title: 'Uso de Intune para corregir las vulnerabilidades que encuentra ATP de Microsoft Defender: Azure | Microsoft Docs'
description: Descubra cómo administrar las tareas de seguridad desde Threat & Vulnerability Management, parte de la Protección contra amenazas avanzada (ATP) de Microsoft Defender desde la consola de Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
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
ms.openlocfilehash: a1d410da2cbedb9bcd2418fac1ddb783529ee8c6
ms.sourcegitcommit: a882035696a8cc95c3ef4efdb9f7d0cc7e183a1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87262598"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Uso de Intune para corregir las vulnerabilidades que identifica ATP de Microsoft Defender

Al integrar Intune con la Protección de amenazas avanzada (ATP) de Microsoft Defender, puede aprovechar Threat & Vulnerability Management (TVM) de ATP y usar Intune para corregir los puntos débiles del punto de conexión que TVM identifica. Esta integración ofrece un enfoque basado en riesgos para la detección de vulnerabilidades y la asignación de prioridades de las mismas que puede mejorar el tiempo de respuesta de corrección en todo el entorno.

[Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) forma parte de la [Protección de amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).

## <a name="how-integration-works"></a>Funcionamiento de la integración

Una vez que conecta Intune con la Protección contra amenazas avanzada de Microsoft Defender, ATP recibe detalles de amenazas y vulnerabilidades desde los dispositivos administrados.

En la consola del Centro de seguridad de Microsoft Defender, los administradores de seguridad de ATP revisan los datos sobre las vulnerabilidades del punto de conexión. Los administradores luego usan un solo clic para crear tareas de seguridad que marcan los dispositivos vulnerables para corregirlos. Las tareas de seguridad se pasan de inmediato a la consola de Intune, donde los administradores de Intune pueden verlas. La tarea de seguridad identifica el tipo de vulnerabilidad, la prioridad, el estado y los pasos que hay que tomar para corregirla. El administrador de Intune elige aceptar o rechazar la tarea.

Una vez que se acepta una tarea, el administrador de Intune actúa para corregir la vulnerabilidad a través de Intune, con las instrucciones que se proporcionan como parte de la tarea de seguridad.

Entre las acciones de corrección comunes se incluye:

- **Bloquear** la ejecución de una aplicación.
- **Implementar** una actualización del sistema operativo para mitigar la vulnerabilidad.
- **Modificar** un valor del Registro.
- **Deshabilitar** o **habilitar** una configuración para afectar la vulnerabilidad.
- **Requerir atención** alerta al administrador sobre la amenaza cuando no hay ninguna recomendación adecuada que proporcionar.

Un flujo de trabajo de ejemplo:

- Dentro de ATP de Microsoft Defender, se detecta una vulnerabilidad en una aplicación denominada Contoso Media Player v4 y un administrador crea una tarea de seguridad para actualizar dicha aplicación. Contoso Media Player es una aplicación no administrada que se implementó con Intune.

  Esta tarea de seguridad aparece en la consola de Intune con el estado Pending (Pendiente):

  ![Visualización de la lista de tareas de seguridad en la consola de Intune](./media/atp-manage-vulnerabilities/temp-security-tasks.png)

- El administrador de Intune selecciona la tarea de seguridad para ver los detalles de la tarea.  Luego, el administrador seleccionar **Aceptar**, con lo que se actualiza el estado en Intune y en ATP cambia a *Accepted* (Aceptado).

  ![Aceptación o rechazo de una tarea de seguridad](./media/atp-manage-vulnerabilities/temp-accept-task.png)

- Luego, el administrador corrige la tarea según las instrucciones proporcionadas. Las instrucciones varían según el tipo de corrección que se necesita. Cuando sea posible, las instrucciones de corrección incluyen vínculos que abren paneles pertinentes para las configuraciones en Intune.

  Como el reproductor multimedia de este ejemplo no es una aplicación administrada, Intune solo puede proporcionar instrucciones de texto. Si la aplicación fuese administrada, Intune podría entregar instrucciones para descargar una versión actualizada y proporcionar un vínculo para abrir la implementación de la aplicación para que los archivos actualizados se puedan agregar a la implementación.

- Una vez que se realiza la corrección, el administrador de Intune abre la tarea de seguridad y selecciona **Completar tarea**.  El estado de la corrección se actualiza para Intune y en ATP, donde los administradores de seguridad confirman el estado revisado de la vulnerabilidad.

## <a name="prerequisites"></a>Requisitos previos  

**Suscripciones**:

- Microsoft Intune  
- Protección contra amenazas avanzada de Microsoft Defender ([Suscríbase para disfrutar de una prueba gratuita](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink)).

**Configuraciones de Intune para ATP**:

- Configure una conexión de servicio a servicio con ATP de Microsoft Defender.
- Implemente una directiva de configuración de dispositivos con un tipo de perfil de **ATP de Microsoft Defender (Windows 10 Escritorio)** en dispositivos en los que ATP evaluará el riesgo.

  Para información sobre cómo configurar Intune para que trabaje junto con ATP, consulte [Aplicación del cumplimiento de ATP de Windows Defender con acceso condicional en Intune](advanced-threat-protection-configure.md#enable-microsoft-defender-atp-in-intune).

## <a name="work-with-security-tasks"></a>Trabajo con tareas de seguridad

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Seleccione **Endpoint security** (Seguridad del punto de conexión)  > **Tareas de seguridad**.

3. Seleccione una tarea de la lista para abrir una ventana de recursos donde se muestren más detalles sobre esa tarea de seguridad.

   Mientras ve la ventana de recursos de la tarea de seguridad, puede seleccionar otros vínculos:

   - MANAGED APPS (Aplicaciones administradas): vea cuál es la aplicación vulnerable. Si la vulnerabilidad se aplica a varias aplicaciones, verá una lista de aplicaciones filtrada.
   - DEVICES (Dispositivos): vea una lista de los *dispositivos vulnerables*, desde donde se pueden incluir vínculos a una entrada con más detalles sobre la vulnerabilidad de ese dispositivo.
   - REQUESTOR (Solicitante): use el vínculo para enviar un correo al administrador que envió esta tarea de seguridad.
   - NOTES (Notas): lea los mensajes personalizados que envió el solicitante al abrir la tarea de seguridad.

4. Seleccione **Aceptar** o **Rechazar** para enviar una notificación a ATP sobre la acción planeada. Cuando acepta o rechaza una tarea, puede enviar notas, las que se envían a ATP.

5. Después de aceptar una tarea, vuelva a abrir la tarea de seguridad (si está cerrada) y siga los detalles de CORRECCIÓN para corregir la vulnerabilidad. Las instrucciones que ATP proporciona en los detalles de la tarea de seguridad varían según la vulnerabilidad en cuestión.

   Cuando sea posible, las instrucciones de corrección incluyen vínculos que abren los objetos de configuración pertinentes en la consola de Intune.

6. Después de completar los pasos de corrección, abra la tarea de seguridad y seleccione **Completar tarea**.  Con esta acción se actualiza el estado de la tarea de seguridad tanto en Intune como en ATP.

Una vez que la corrección se realiza correctamente, la puntuación de exposición a riesgos puede disminuir en función de la información nueva proveniente de los dispositivos corregidos.

## <a name="next-steps"></a>Pasos siguientes

Más información sobre Intune y [ATP de Microsoft Defender](advanced-threat-protection.md).

Revise [Mobile Threat Defense](mobile-threat-defense.md) de Intune.

Revise el [panel de Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) en ATP de Microsoft Defender.
