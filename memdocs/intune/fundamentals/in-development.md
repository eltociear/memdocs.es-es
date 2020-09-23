---
title: 'En desarrollo: Microsoft Intune'
titleSuffix: ''
description: Características de Microsoft Intune en desarrollo
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/28/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1f261d8d61fc2c4273ae8f137a43bb6c607430d
ms.sourcegitcommit: fdd6d3c4b906e895ebec2856ebc38b0656296d2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "91002705"
---
# <a name="in-development-for-microsoft-intune"></a>En desarrollo para Microsoft Intune

Para ayudarle con la preparación y planeación, en esta página se enumeran las actualizaciones y características de la interfaz de usuario de Intune que están en desarrollo, pero que aún no se han publicado. Además de la información de esta página: 

- Si prevemos que tendrá que tomar medidas antes de realizar un cambio, haremos una publicación complementaria en el Centro de mensajes de Office.
- Cuando una característica entra en producción, ya sea una versión preliminar o disponible con carácter general, la descripción de la característica pasa de esta página a [Novedades](whats-new.md).
- Esta página y la página [Novedades](whats-new.md) se actualizan periódicamente. Compruebe si hay actualizaciones adicionales.
- Consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para conocer los plazos de tiempo y los productos estratégicos.

> [!NOTE]
> Esta página refleja las expectativas actuales sobre las funciones de Intune en una versión futura. Las fechas y las características individuales pueden cambiar. En esta página no se describen todas las características en desarrollo.

**Fuente RSS**: para recibir notificaciones cuando esta página se actualice, copie y pegue la dirección URL siguiente en el lector de fuentes: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

**Este artículo se actualizó por última vez en la fecha que aparece bajo el título anterior.**

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Administración de aplicaciones

### <a name="update-to-device-icons-in-company-portal-and-intune-apps-on-android---6057023----"></a>Actualización de iconos de dispositivos en aplicaciones del Portal de empresa y de Intune en Android<!-- 6057023  -->
Vamos a actualizar los iconos de dispositivos de las aplicaciones del Portal de empresa y de Intune de los dispositivos Android para crear una apariencia más moderna y en consonancia con el sistema de diseño de Microsoft Fluent. Puede encontrar información relacionada en [Actualizaciones de los iconos de la aplicación del Portal de empresa para iOS o iPadOS y macOS](../fundamentals/whats-new-app-ui.md#update-to-icons-in-company-portal-app-for-iosipados-and-macos-). 

### <a name="ios-company-portal-will-support-apples-automated-device-enrollment-without-user-affinity---7282707----"></a>El Portal de empresa de iOS admitirá la Inscripción de dispositivos automatizada de Apple sin afinidad de usuario<!-- 7282707  --> 
Este portal se admitirá en los dispositivos inscritos con la Inscripción de dispositivos automatizada de Apple sin necesidad de un usuario asignado. Un usuario final puede iniciar sesión en el Portal de empresa de iOS para establecerse como usuario primario de un dispositivo iOS o iPad inscrito sin afinidad de dispositivo. Para más información sobre la Inscripción de dispositivos automatizada, consulte [Inscripción automática de dispositivos iOS/iPadOS con Inscripción de dispositivos automatizada de Apple](../enrollment/device-enrollment-program-enroll-ios.md).


<!-- ***********************************************-->
## <a name="device-configuration"></a>Configuración del dispositivo

### <a name="create-pkcs-certificate-profiles-for-android-enterprise-fully-managed-devices-cobo---4839686---"></a>Creación de perfiles de certificado de PKCS para dispositivos Android Enterprise totalmente administrados (COBO)<!-- 4839686 -->
Puede crear perfiles de certificado de PKCS para implementar certificados en dispositivos de perfil de trabajo y propietario del dispositivo Android Enterprise (**Dispositivos** > **Perfiles de configuración** > **Crear perfil** > **Android Enterprise > solo propietario del dispositivo** o **Android Enterprise > solo perfil de trabajo** para plataforma > **PKCS** para perfil).

Pronto podrá crear perfiles de certificado PKCS para dispositivos Android Enterprise totalmente administrados. Se requiere el conector de certificado PFX de Intune. Si no usa SCEP y solo usa PKCS, puede quitar el conector NDES después de instalar el nuevo conector PFX. El nuevo conector PFX importa los archivos PFX e implementa los certificados PKCS en todas las plataformas.

Para más información sobre certificados PKCS, consulte [Configuración y uso de certificados PKCS con Intune](../protect/certficates-pfx-configure.md).

Se aplica a:
- Android Enterprise totalmente administrado (COBO)

### <a name="use-netmotion-as-a-vpn-connection-type-for-android-enterprise-work-profile-devices---7764263---"></a>Uso de NetMotion como tipo de conexión VPN para dispositivos de perfil de trabajo de Android Enterprise<!-- 7764263 -->
Al crear un perfil de VPN, NetMotion está disponible como tipo de conexión VPN (**Dispositivos** > **Configuración de dispositivos** > **Crear perfil** > **perfil de trabajo de Android Enterprise** para la plataforma > **VPN** para el perfil > **NetMotion** para el tipo de conexión).

Para obtener más información sobre los perfiles de VPN en Intune, consulte [Creación de perfiles de VPN para conectarse a servidores VPN](../configuration/vpn-settings-configure.md).

Se aplica a:
- Perfil de trabajo de Android Enterprise

### <a name="changes-for-password-settings-in-device-restriction-profiles-for-android-device-administrator---7662279----"></a>Cambios en la configuración de contraseñas en los perfiles de restricción de dispositivos para el administrador de dispositivos Android<!-- 7662279  --> 
Estamos introduciendo algunos cambios en la configuración de contraseñas para las directivas de *restricción de dispositivos* y *cumplimiento* para el *administrador de dispositivos Android*. (**Dispositivos** > **Perfiles de configuración** > **Crear perfil** > **Restricciones de dispositivos** y **Dispositivos** > **Directivas de cumplimiento** > **Crear directiva**). Estos cambios ayudan a Intune a adaptarse a los cambios en Android 10 y versiones posteriores, para asegurarse de que la configuración de contraseñas siga aplicándose a los dispositivos según lo previsto.
 
Los cambios incluyen:
- La eliminación de la opción de nivel superior para **Contraseña**.  
- La configuración se reorganizará en secciones basadas en los dispositivos a los que se apliquen.
- La opción **Longitud mínima de contraseña** se deshabilitará para su uso a menos que **Tipo de contraseña** se configure en un valor al que se le aplique la longitud de contraseña.
- Actualizaciones adicionales de etiquetas y texto de ejemplo.

Estos cambios se aplican a la interfaz de usuario para la configuración y no afectarán a los perfiles existentes. 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Inscripción de dispositivos

### <a name="ending-support-for-ios-11--7327321---"></a>Fin de la compatibilidad con iOS 11<!--7327321 -->
A partir de iOS 14, la inscripción de Intune y la aplicación Portal de empresa serán compatibles con iOS 12 y versiones posteriores. No se admitirán versiones anteriores, pero seguirán recibiendo directivas.

### <a name="ending-support-for-macos-1012--7327326---"></a>Fin de la compatibilidad con macOS 10.12<!--7327326 -->
A partir de macOS 11, la inscripción de Intune y la aplicación Portal de empresa serán compatibles con macOS 10.13 y versiones posteriores. No se admitirán versiones anteriores.


<!-- ***********************************************-->
## <a name="device-management"></a>Administración de dispositivos

### <a name="powershell-scripts-support-for-byod-devices---1862833----"></a>Compatibilidad de scripts de PowerShell con dispositivos BYOD<!-- 1862833  -->
Los scripts de PowerShell admitirán dispositivos registrados de Azure AD en Intune. Para más información sobre PowerShell, vea [Uso de scripts de PowerShell para dispositivos Windows 10 en Intune](../apps/intune-management-extension.md). Esta funcionalidad no es compatible con dispositivos que ejecutan Windows 10 Home Edition.

### <a name="log-analytics-will-include-device-details-log--6014987----"></a>Log Analytics incluirá registros de detalles del dispositivo<!--6014987  -->
Habrá disponibles registros detallados del dispositivo de Intune en **Informes** > **Log Analytics**. Puede correlacionar los detalles del dispositivo para compilar consultas personalizadas y libros de Azure.

### <a name="tenant-attach-run-scripts-from-the-admin-center--7220536-cm6234688---"></a>Asociación de inquilinos: ejecución de scripts desde el centro de administración<!--7220536, CM6234688 -->
Podrá incorporar la eficacia de la característica [Ejecutar scripts](../../configmgr/apps/deploy-use/create-deploy-scripts.md) local de Configuration Manager al centro de administración de Microsoft Endpoint Manager. Permita que otros roles, como el de Departamento de soporte técnico, ejecuten scripts de PowerShell desde la nube en un dispositivo administrado de Configuration Manager individual. Esto proporciona todas las ventajas tradicionales de los scripts de PowerShell que ya se han definido y aprobado por el administrador de Configuration Manager en este nuevo entorno. Para más información, consulte [Technical Preview 2005 para Configuration Manager](../../configmgr/core/get-started/2020/technical-preview-2005.md#bkmk_scripts). 

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Implementación de actualizaciones de software en dispositivos macOS <!-- 3194876 -->
Podrá implementar actualizaciones de software en grupos de dispositivos macOS. Esta característica incluye, entre otras, actualizaciones de archivos críticos, de archivos de configuración y del firmware. Podrá enviar actualizaciones en la siguiente sincronización de dispositivos o seleccionar una programación semanal para implementar actualizaciones dentro o fuera de los períodos que establezca. De esta manera, podrá actualizar los dispositivos fuera de las horas de trabajo estándar o cuando el departamento de soporte técnico tiene a todo el personal ocupado. También obtendrá un informe detallado de todos los dispositivos macOS con actualizaciones implementadas. Puede profundizar en el informe en función de cada dispositivo para ver los estados de determinadas actualizaciones.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Aplicaciones de Intune

### <a name="unified-delivery-of-azure-ad-enterprise-and-office-online-applications-in-the-windows-company-portal---1817861----"></a>Entrega unificada de aplicaciones de Azure AD Enterprise y Office Online en el Portal de empresa de Windows<!-- 1817861  -->
En la versión de 2006, anunciamos la [entrega unificada de aplicaciones de Azure AD Enterprise y Office Online en el Portal de empresa](../fundamentals/whats-new.md). Esta característica se admitirá en el Portal de empresa de Windows. En el panel **Personalización** de Intune, puede seleccionar **Ocultar** o **Mostrar** **Aplicaciones de Azure AD Enterprise** y **Aplicaciones de Office Online** en el Portal de empresa de Windows. Cada usuario final ve todo el catálogo de aplicaciones desde el servicio de Microsoft elegido. De forma predeterminada, cada origen de aplicación adicional se establecerá en **Ocultar**. Para encontrar esta opción de configuración, seleccione **Administración de inquilinos** > **Personalización** en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Para obtener información relacionada, vea [Personalización de las aplicaciones del Portal de empresa de Intune, el sitio web del Portal de empresa y la aplicación de Intune](../apps/company-portal-app.md).
 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
## <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

### <a name="power-bi-compliance-report-template-v20---636958----"></a>Plantilla de informe de cumplimiento de Power BI V2.0<!-- 636958  -->
Los administradores podrán actualizar la versión de la plantilla de informe de cumplimiento de Power BI de V1.0 a V2.0. En V2.0 se incluirá un diseño mejorado, así como cambios en los cálculos y los datos que se muestran como parte de la plantilla. Para obtener información relacionada, vea [Conexión con el almacenamiento de datos con Power BI](../developer/reports-proc-get-a-link-powerbi.md).



<!-- ***********************************************-->
<!--
## Role-based access control
-->

<!-- ***********************************************-->
## <a name="security"></a>Seguridad

### <a name="app-protection-policy-support-for-symantec-endpoint-security-and-check-point-sandblast----4452423-4731168---"></a>Compatibilidad de la directiva de protección de aplicaciones con Symantec Endpoint Security y Check Point Sandblast<!--  4452423, 4731168 -->

En octubre de 2019, la directiva de protección de aplicaciones de Intune agregó la capacidad de usar datos de algunos de nuestros asociados de Microsoft Threat Defense (MTD). Estamos agregando compatibilidad con los siguientes asociados para usar una directiva de protección de aplicaciones que bloquee o elimine de forma selectiva los datos corporativos de los usuarios en función del estado de un dispositivo:

- **Check Point Sandblast** en Android, iOS y iPadOS
- **Symantec Endpoint Security** en Android, iOS y iPadOS

Para más información sobre el uso de la directiva de protección de aplicaciones con asociados de MTD, consulte [Creación de una directiva de protección de aplicaciones de Mobile Threat Defense con Intune](../protect/mtd-app-protection-policy.md).

### <a name="microsoft-defender-atp-creates-endpoint-manager-security-task-with-vulnerability-details---5568193----"></a>ATP de Microsoft Defender crea una tarea de seguridad de Endpoint Manager con detalles de la vulnerabilidad<!-- 5568193  -->
La administración de amenazas y vulnerabilidades (TVM) de ATP de Microsoft Defender detecta una configuración de seguridad incorrecta en los dispositivos. Los administradores usan esta información para actualizar los dispositivos vulnerables.

Pronto, ATP de Microsoft Defender podrá generar una tarea de seguridad de Endpoint Manager (**Endpoint Manager** > **Seguridad de los puntos de conexión** > **Tareas de seguridad**) con los detalles de la vulnerabilidad y mostrar los dispositivos afectados. Los administradores de TI pueden aceptar la tarea de seguridad e implementar la configuración necesaria. 

Para más información sobre cómo las tareas de seguridad, vea [Uso de Intune para corregir las vulnerabilidades que identifica ATP de Microsoft Defender](../protect/atp-manage-vulnerabilities.md).



<!-- ***********************************************-->
## <a name="notices"></a>Notificaciones

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Vea también

Consulte [Novedades de Microsoft Intune](whats-new.md) para obtener más información sobre los desarrollos recientes.
