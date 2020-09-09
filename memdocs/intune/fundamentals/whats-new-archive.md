---
title: 'Novedades de Microsoft Intune en los meses anteriores: Azure | Microsoft Docs'
titleSuffix: ''
description: Revise los anuncios anteriores en la página de novedades de Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/28/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: faabd2656e8b72502c682eaab37a0cc5b484ea03
ms.sourcegitcommit: b95eac00a0cd979dc88be953623c51dbdc9327c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "89423941"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novedades de Microsoft Intune: meses anteriores

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

<!-- ########################## -->
## <a name="january-2020"></a>Enero de 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="intune-support-for-additional-microsoft-edge-version-77-deployment-channel-for-macos---5983950----"></a>Compatibilidad de Intune con el canal de implementación adicional de Microsoft Edge versión 77 para macOS<!-- 5983950  -->
Microsoft Intune ahora admite el canal de implementación **estable** para la aplicación Microsoft Edge para macOS. El canal **estable** es el canal recomendado para la implementación de Microsoft Edge en general en entornos empresariales. Se actualiza cada seis semanas y cada versión incorpora mejoras del canal **beta**. Además de canales **estable** y **beta**, Intune admite un canal de **desarrollo**. La versión preliminar pública ofrece los canales estable y de desarrollo para la versión 77 y posteriores de Microsoft Edge para macOS. Las actualizaciones automáticas del explorador están activadas de forma predeterminada. Para obtener más información, consulte [Adición de Microsoft Edge a dispositivos macOS con Microsoft Intune](../apps/apps-edge-macos.md).

#### <a name="retirement-of-intune-managed-browser--5728447---"></a>Retirada de Intune Managed Browser<!--5728447 -->
Se va a retirar Intune Managed Browser. Use Microsoft Edge para la experiencia de explorador de Intune protegida. 

#### <a name="user-experience-change-when-adding-apps-to-intune---4705829-----"></a>Cambio en la experiencia del usuario al agregar aplicaciones a Intune<!-- 4705829   -->
Verá una nueva experiencia de usuario al agregar aplicaciones a través de Intune. Esta experiencia proporciona la misma configuración y los mismos detalles que ha usado anteriormente, pero la nueva experiencia emplea un proceso similar a un asistente antes de agregar una aplicación a Intune. Esta nueva experiencia también proporciona una página de revisión antes de agregar la aplicación. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Aplicaciones** > **Todas las aplicaciones** > **Agregar**. Para más información, vea [Agregar aplicaciones a Microsoft Intune](../apps/apps-add.md).

#### <a name="require-win32-apps-to-restart----5622282-----"></a>Requisito de reinicio de las aplicaciones Win32 <!-- 5622282   -->
Puede requerir que una aplicación Win 32 se reinicie después de una instalación correcta. Además, puede elegir el tiempo (el período de gracia) que transcurrirá antes de que se produzca el reinicio.

#### <a name="user-experience-change-when-configuring-apps-in-intune---4207990-----"></a>Cambio en la experiencia del usuario al configurar aplicaciones en Intune<!-- 4207990   -->
Verá una nueva experiencia de usuario al crear directivas de configuración de aplicaciones en Intune. Esta experiencia proporciona la misma configuración y los mismos detalles que ha usado anteriormente, pero la nueva experiencia emplea un proceso similar a un asistente antes de agregar una directiva a Intune. En el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Aplicaciones** > **Directivas de configuración de aplicaciones** > **Agregar**. Para obtener más información, vea [Directivas de configuración de aplicaciones para Microsoft Intune](../apps/app-configuration-policies-overview.md). 

#### <a name="intune-support-for-additional-microsoft-edge-for-windows-10-deployment-channel---5861774---"></a>Compatibilidad de Intune con el canal de implementación adicional de Microsoft Edge para Windows 10<!-- 5861774 -->
Microsoft Intune ahora admite el canal de implementación adicional **estable** para la aplicación Microsoft Edge (versión 77 y posteriores) para Windows 10. El canal **estable** es el canal recomendado para la implementación de Microsoft Edge para Windows 10 en general en entornos empresariales. Este canal se actualiza cada seis semanas y cada versión incorpora mejoras del canal **beta**. Además de canales **estable** y **beta**, Intune admite un canal de **desarrollo**. Para obtener más información, vea [Microsoft Edge para Windows 10 - Configuración de aplicaciones](../apps/apps-windows-edge.md#configure-app-settings).

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>Compatibilidad de S/MIME con Microsoft Outlook para iOS<!-- 2669398 -->
Intune admite la entrega de certificados de cifrado y firma S/MIME que se pueden usar con Outlook para iOS en dispositivos iOS. Para más información, consulte [Etiquetado de sensibilidad y protección en Outlook para iOS y Android](https://aka.ms/omsmime).

#### <a name="cache-win32-app-content-using-microsoft-connected-cache-server---6030314---"></a>Almacenamiento en caché del contenido de la aplicación Win32 mediante el servidor de caché con conexión de Microsoft<!-- 6030314 -->
Puede instalar un servidor de caché con conexión de Microsoft en los puntos de distribución de Configuration Manager para almacenar en caché el contenido de la aplicación Win32 de Intune. Para más información, consulte [Caché con conexión de Microsoft en Configuration Manager - Compatibilidad con aplicaciones Win32 de Intune](/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="improved-user-interface-experience-when-configuring-exchange-activesync-on-premises-connector-ui---5695492-----"></a>Mejor experiencia de interfaz de usuario al configurar la interfaz de usuario del conector local de Exchange ActiveSync<!-- 5695492   -->
Hemos actualizado para experiencia para [configurar el conector local de Exchange ActiveSync](../protect/exchange-connector-install.md). La experiencia actualizada usa un solo panel para configurar, editar y resumir los detalles de los conectores locales.

#### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-----"></a>Adición de configuración de proxy automática a perfiles de Wi-Fi para perfiles de trabajo de Android Enterprise<!-- 4490822   -->
En los dispositivos de perfil de trabajo de Android Enterprise, puede crear perfiles de Wi-Fi. Al elegir el tipo Wi-Fi Enterprise, también puede especificar el tipo de protocolo de autenticación extensible (EAP) que se usa en la red Wi-Fi.

Ahora, al elegir el tipo de empresa, también puede especificar la configuración de proxy automática, incluida una dirección URL del servidor proxy, como `proxy.contoso.com`.

Para ver la configuración de Wi-Fi actual que puede establecer, vaya a [Incorporación de la configuración de Wi-Fi en Microsoft Intune para dispositivos que ejecutan Android Enterprise y el Quiosco de Android](../configuration/wi-fi-settings-android-enterprise.md#work-profile-only).

Se aplica a:
- Perfil de trabajo de Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="block-android-enrollments-by-device-manufacturer--5197392----"></a>Bloqueo de las inscripciones de Android por el fabricante del dispositivo<!--5197392  -->
Puede bloquear la inscripción de dispositivos en función del fabricante del dispositivo. Esta característica se aplica al administrador de dispositivos Android y los dispositivos de perfil de trabajo de Android Enterprise. Para ver las restricciones de inscripción, vaya al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **Restricciones de inscripción**.

#### <a name="improvements-to-the-iosipados-create-enrollment-type-profile-ui---6055005---"></a>Mejoras en la interfaz de usuario para Crear un perfil de tipo de inscripción en iOS/iPadOS<!-- 6055005 -->
Para la inscripción de usuarios de iOS/iPadOS, se ha simplificado la página **Crear un perfil de tipo de inscripción** **Configuración** para mejorar el proceso de elección del **Tipo de inscripción** manteniendo la misma funcionalidad. Para ver la interfaz de usuario nueva, vaya a la página [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Dispositivos** > **iOS** > **Inscripción de iOS** > **Tipos de inscripción** > **Crear perfil** > **Configuración**. Para obtener más información, consulte [Creación de un perfil de inscripción de usuario en Intune](../enrollment/ios-user-enrollment.md#create-a-user-enrollment-profile-in-intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="new-information-in-device-details---4471759-5604099----"></a>Nueva información en los detalles del dispositivo<!-- 4471759 5604099  -->
La siguiente información está ahora en la página de **información general** para dispositivos:
- Capacidad de memoria (cantidad de memoria física en el dispositivo)
- Capacidad de almacenamiento (cantidad de almacenamiento físico en el dispositivo) 
- Arquitectura de CPU

#### <a name="ios-bypass-activation-lock-remote-action-renamed-to-disable-activation-lock---5904591----"></a>Cambio de nombre de la acción remota Omisión del bloqueo de activación de iOS a Deshabilitación del bloqueo de activación <!--5904591  -->
Se ha cambiado el nombre de la acción remota **Omisión del bloqueo de activación** a **Deshabilitación del bloqueo de activación**. Para obtener más información, consulte [Deshabilitación del bloqueo de activación de iOS con Intune](../remote-actions/device-activation-lock-disable.md).

#### <a name="windows-10-feature-update-deployment-support-for-autopilot-devices---5948137-----"></a>Compatibilidad con la implementación de actualizaciones de características de Windows 10 para dispositivos AutoPilot<!-- 5948137   -->
Intune ahora admite dispositivos registrados con AutoPilot mediante [implementaciones de actualizaciones de características de Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates).

Las directivas de actualización de características de Windows 10 no se pueden aplicar durante la configuración rápida (OOBE) de Autopilot y solo se aplican en el primer análisis de Windows Update una vez que el dispositivo haya finalizado el aprovisionamiento (que suele ser un día).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="windows-autopilot-deployment-reports-preview----3856172-----"></a>Informes de implementación de Windows Autopilot (versión preliminar) <!-- 3856172   -->
Un nuevo informe detalla cada dispositivo implementado mediante Windows Autopilot. Para más información, vea [Informe de implementaciones de Autopilot](../../autopilot/enrollment-autopilot.md#autopilot-deployments-report).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-----"></a>Nuevo rol de Administrador de seguridad de los puntos de conexión integrado en Intune<!--4253397   -->
Hay un nuevo rol integrado de Intune disponible: el administrador de seguridad de los puntos de conexión. Este nuevo rol concede a los administradores acceso completo al nodo del administrador de puntos de conexión en Intune y acceso de solo lectura a otras áreas. El rol es una expansión del rol "Administrador de seguridad" de Azure AD. Si actualmente solo tiene administradores globales como roles, no es necesario realizar ningún cambio. Si usa roles y desea la granularidad que proporciona el Administrador de seguridad de puntos de conexión, asigne ese rol cuando esté disponible. Para más información acerca de roles integrados, vea [Control de acceso basado en rol](role-based-access-control.md).

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390---"></a>Los perfiles de plantillas administrativas de Windows 10 (ADMX) ahora admiten etiquetas de ámbito <!--5137390 -->
Ahora puede asignar etiquetas de ámbito a los perfiles de plantilla administrativa (ADMX). Para ello, vaya a **Intune** > **Dispositivos** > **Perfiles de configuración** > elija un perfil de plantillas administrativas en la lista > **Propiedades** > **Etiquetas de ámbito**. Para más información sobre las etiquetas de ámbito, vea [Asignar etiquetas de ámbito a otros objetos](../fundamentals/scope-tags.md#assign-scope-tags-to-other-objects).

<!-- ########################## -->
## <a name="december-2019"></a>Diciembre de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Recuperación de una clave de recuperación personal desde dispositivos macOS con cifrado de MEM<!-- 4851745 -->
Los usuarios finales pueden recuperar su clave de recuperación personal (clave de FileVault) mediante la aplicación Portal de empresa de iOS. El dispositivo que tiene la clave de recuperación personal se debe inscribir en Intune y cifrar con FileVault a través de Intune. Con la aplicación Portal de empresa de iOS, un usuario final puede recuperar su clave de recuperación personal en su dispositivo macOS cifrado haciendo clic en **Obtener clave de recuperación**. También puede recuperar la clave de recuperación en Intune si selecciona **Dispositivos** > *el dispositivos macOS cifrado e inscrito* > **Obtener clave de recuperación**. Para más información sobre FileVault, consulte [Cifrado de FileVault para macOS](../protect/encrypt-devices-filevault.md).

#### <a name="ios-and-ipados-user-licensed-vpp-apps---5619268---"></a>Aplicaciones de VPP con licencia de usuario de iOS y iPadOS<!-- 5619268 -->
En el caso de los dispositivos iOS y iPadOS inscritos por el usuario, los usuarios finales ya no verán las aplicaciones de VPP con licencia de dispositivo recién creadas implementadas como disponibles. Sin embargo, los usuarios finales seguirán viendo todas las aplicaciones de VPP con licencia de usuario en el Portal de empresa. Para más información relacionada con las aplicaciones VPP, vea [Administración de aplicaciones de iOS y macOS compradas a través del Programa de Compras por Volumen de Apple con Microsoft Intune](../apps/vpp-apps-ios.md).

#### <a name="notice---windows-10-1703-rs2-will-be-moving-out-of-support----5026679---"></a>Aviso: La compatibilidad de Windows 10 1703 (RS2) finalizará <!-- 5026679 -->
A partir del 9 de octubre de 2018, finalizó la compatibilidad de Windows 10 1703 (RS2) con la plataforma de Microsoft para las ediciones Home, Pro y Pro for Workstations. En el caso de las ediciones Windows 10 Enterprise y Education, la compatibilidad de Windows 10 1703 (RS2) con la plataforma finalizó el 8 de octubre de 2019. A partir del 26 de diciembre de 2019, actualizaremos la versión mínima de la aplicación Portal de empresa de Windows a Windows 10 1709 (RS3). Los equipos que ejecutan versiones anteriores a 1709 dejarán de recibir las versiones actualizadas de la aplicación desde Microsoft Store. Comunicamos anteriormente este cambio a los clientes que administran versiones anteriores de Windows 10 a través del centro de mensajes. Para más información, consulte [Hoja de datos del ciclo de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Migración a Microsoft Edge para escenarios de exploración administrados<!-- 5173762 -->
A medida que se acerca la retirada de Intune Managed Browser, se han realizado cambios en las directivas de protección de aplicaciones para simplificar los pasos necesarios para trasladar a los usuarios a Edge. Se han actualizado las opciones de la configuración de directiva de protección de aplicaciones **Restringir la transferencia de contenido web con otras aplicaciones** para que sea una de las siguientes:

- Cualquier aplicación
- Intune Managed Browser
- Microsoft Edge
- Explorador no administrado 

Al seleccionar **Microsoft Edge**, los usuarios finales verán que la mensajería de acceso condicional les notifica que Microsoft Edge es necesario para escenarios de exploración administrados. Se les pedirá que descarguen e inicien sesión en Microsoft Edge con sus cuentas de Azure AD, si todavía no lo han hecho.  Este será el equivalente a tener como destino las aplicaciones habilitadas para MAM con la configuración de la aplicación `com.microsoft.intune.useEdge` establecida en **true**. Las directivas de protección de aplicaciones existentes en las que se usaba la opción **Exploradores administrados por directivas** ahora tendrán **Intune Managed Browser** seleccionado y no verá ningún cambio de comportamiento. Esto significa que los usuarios verán mensajes para usar Microsoft Edge si ha establecido la opción de configuración de la aplicación **useEdge** en **true**. Animamos a todos los clientes que aprovechan los escenarios de exploración administrados para actualizar sus directivas de protección de aplicaciones con **Restringir la transferencia de contenido web con otras aplicaciones** para asegurarse de que los usuarios vean las instrucciones adecuadas para realizar la transición a Microsoft Edge, con independencia de la aplicación desde la que inicien los vínculos. 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Configuración del contenido de las notificaciones de una aplicación para las cuentas de organización<!-- 2576686  -->
Las directivas de protección de aplicaciones (APP) de Intune en dispositivos iOS y Android permiten controlar el contenido de las notificaciones de una aplicación para las cuentas de organización. Puede seleccionar una opción (permitir, bloquear datos de la organización o bloqueado) para especificar cómo se muestran las notificaciones de las cuentas de la organización para la aplicación seleccionada. Esta característica requiere compatibilidad de las aplicaciones y puede que no esté disponible para todas las aplicaciones habilitadas para la aplicación. Outlook para iOS versión 4.15.0 (o posterior) y Outlook para Android 4.83.0 (o posterior) serán compatibles con esta configuración. La configuración está disponible en la consola, pero la funcionalidad entrará en vigor después del 16 de diciembre de 2019. Consulte [¿Qué son las directivas de protección de aplicaciones?](../apps/app-protection-policy.md) para obtener más información sobre APP.

#### <a name="microsoft-app-icons-update--4677605----"></a>Actualización de los iconos de las aplicaciones de Microsoft<!--4677605  -->
Se han actualizado los iconos que se usan para las aplicaciones de Microsoft en el panel de la aplicación objetivo para las directivas de protección de aplicaciones y las directivas de configuración de aplicaciones.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Requerir el uso de teclados aprobados en Android<!--4761794  -->
Como parte de una directiva de protección de aplicaciones, puede especificar la configuración [**Teclados aprobados**](../apps/app-protection-policy-settings-android.md#data-protection) para administrar los teclados Android que se pueden usar con aplicaciones Android administradas. Cuando un usuario abra la aplicación administrada y aún no use un teclado aprobado para esa aplicación, se le pedirá que cambie a uno de los teclados aprobados que ya están instalados en el dispositivo. Si es necesario, verá un vínculo para descargar un teclado aprobado en Google Play Store, que puede instalar y configurar. El usuario solo puede editar campos de texto en una aplicación administrada cuando su teclado activo no sea uno de los teclados aprobados.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="updates-to-administrative-templates-for-windows-10-devices----5941568---"></a>Actualizaciones de Plantillas administrativas para dispositivos Windows 10 <!-- 5941568 -->

Puede usar plantillas ADMX en Microsoft Intune para controlar y administrar la configuración de Microsoft Edge, Office y Windows. Las Plantillas administrativas en Intune realizaron estas actualizaciones en la configuración de las directivas:

- Se agregó compatibilidad con las versiones 78 y 79 de Microsoft Edge.
- Incluye los archivos ADMX del 11 de noviembre de 2019 en [Archivos de Plantillas administrativas (ADMX/ADML) y la Herramienta de personalización de Office para Aplicaciones de Microsoft 365 para empresas, Office 2019 y Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Para más información sobre las plantillas ADMX en Intune, consulte [Usar plantillas de Windows 10 para configurar opciones de directiva de grupo en Microsoft Intune](../configuration/administrative-templates-windows.md).

Se aplica a:

- Windows 10 y versiones posteriores

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>Experiencia de inicio de sesión único actualizada para aplicaciones y sitios web en dispositivos iOS, iPadOS y macOS<!-- 4999578  -->
Intune agregó una configuración de inicio de sesión único (SSO) para dispositivos iOS, iPadOS y macOS. Ahora puede configurar las extensiones de aplicación de SSO de redireccionamiento escritas por su organización o por el proveedor de identidades. Use estas opciones para configurar una experiencia de inicio de sesión único sin problemas para aplicaciones y sitios web que usan métodos de autenticación modernos, como OAuth y SAML2. 

Estas nuevas opciones expanden la configuración anterior de las extensiones de aplicación SSO y la extensión Kerberos integrada de Apple (**Dispositivos** > **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS/iPadOS** o **macOS** para el tipo de plataforma > **Características del dispositivo** para el tipo de perfil). 

Para ver todas las opciones de la extensión de aplicación SSO que puede configurar, vaya a [SSO en iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) y [SSO en macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Se aplica a:

- iOS/iPadOS
- macOS

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352------"></a>Actualizamos dos opciones de restricción de dispositivos para dispositivos iOS e iPados para corregir su comportamiento<!-- 5701352    -->
En los dispositivos iOS, puede crear los perfiles de restricción de dispositivos **Permitir actualizaciones móviles de PKI** y **Bloqueo del modo restringido de USB** (**Dispositivos** > **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS/iPadOS** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil). Antes de esta versión, la configuración de la interfaz de usuario y las descripciones de las siguientes opciones no eran correctas, algo que ahora se corrigió. A partir de esta versión, el comportamiento de la configuración es el siguiente:

**Bloquear actualizaciones móviles de PKI**: **Bloquear** impide que los usuarios reciban actualizaciones de software, a menos que el dispositivo esté conectado a un equipo. **No configurado** (valor predeterminado): permite que un dispositivo reciba actualizaciones de software sin estar conectado a un equipo.
- Anteriormente, esta configuración le permitía configurarla como: **Permitir**, que permite a los usuarios recibir actualizaciones de software sin tener que conectar los dispositivos a un equipo.
**Permitir accesorios USB con el dispositivo bloqueado**: **Permitir** permite que los accesorios USB intercambien datos con un dispositivo que ha estado bloqueado durante más de una hora. **No configurado** (valor predeterminado) no actualiza el modo restringido de USB en el dispositivo y los accesorios USB no podrán transferir datos del dispositivo si están bloqueados durante más de una hora.
- Anteriormente, esta configuración le permitía configurarla como: **Bloquear** para deshabilitar el modo restringido de USB en los dispositivos supervisados.

Para más información sobre los valores que puede configurar, consulte [Configuración de dispositivos iOS e iPadOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md).

Esta característica se aplica a:

- OS/iPadOS

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Impedir que los usuarios configuren las credenciales de certificado en el almacén de claves administrado en dispositivos propietarios de dispositivos Android Enterprise<!-- 3311998 -->
En dispositivos propietarios de dispositivos Android Enterprise, puede establecer una nueva configuración que impide que los usuarios configuren sus credenciales de certificado en el almacén de claves administrado (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Solo el propietario del dispositivo > Restricciones de dispositivos** para el tipo de perfil > **Users + Accounts** [Usuarios y cuentas]).

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Nueva licencia de administración conjunta de Microsoft Endpoint Configuration Manager<!--5027281-->
Los clientes de Configuration Manager con Software Assurance pueden obtener la administración conjunta de Intune para equipos con Windows 10 sin tener que comprar una licencia de Intune adicional para la administración conjunta. Los clientes ya no necesitan asignar licencias de Intune y EMS individuales a los usuarios finales para la administración conjunta de Windows 10.
- Los dispositivos administrados por Configuration Manager e inscritos en la administración conjunta tienen casi los mismos derechos que los equipos administrados por MDM de Intune independiente. Pero después de restablecerlos, no se pueden volver a aprovisionar con Autopilot.
- Los dispositivos Windows 10 inscritos en Intune mediante otros medios requieren licencias completas de Intune.
- Los dispositivos de otras plataformas siguen requiriendo licencias de Intune completas.

Para más información, vea [Términos de Licencia](https://www.microsoft.com/en-us/Licensing/product-licensing/products).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="protected-wipe-action-now-available--51150000---"></a>La acción de borrado protegido ya está disponible<!--51150000 -->
Ahora tiene la opción de usar la acción Borrar dispositivo para realizar el borrado protegido de un dispositivo. Los borradores protegidos equivalen a los borrados estándar, salvo que no se pueden eludir apagando el dispositivo. Un borrado protegido seguirá intentando restablecer el dispositivo hasta que se complete de forma correcta. En algunas configuraciones, esta acción puede hacer que el dispositivo no se pueda reiniciar. Para más información, consulte [Retirada o borrado de los dispositivos](../remote-actions/devices-wipe.md).

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Dirección MAC de Ethernet de un dispositivo agregada a la página Información general del dispositivo<!--5562275 -->
Ahora puede ver la dirección MAC de Ethernet de un dispositivo en la página de detalles del dispositivo (**Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **Información general**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Seguridad de dispositivos

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Experiencia mejorada en un dispositivo compartido cuando se habilitan las directivas de acceso condicional basadas en el dispositivo<!-- 1734096  -->
Mejoramos la experiencia en un dispositivo compartido con varios usuarios a los que se les aplica la directiva de acceso condicional basada en los dispositivos mediante la comprobación de la evaluación de cumplimiento más reciente para el usuario al aplicar la directiva. Para más información, consulte estos artículos de información general:
- [Información general de Azure sobre el Acceso condicional](/azure/active-directory/conditional-access/overview)
- [Información general sobre el cumplimiento de los dispositivos de Intune](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>Uso de perfiles de certificado PKCS para aprovisionar dispositivos con certificados<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
Ahora puede usar perfiles de certificado PKCS para emitir certificados a *dispositivos* que ejecuten Android for Work, iOS/iPadOS y Windows, cuando estén asociados a perfiles como los de Wi-Fi y VPN. Anteriormente, estas tres plataformas solo admitían certificados basados en el usuario, con la compatibilidad basada en dispositivos limitada a macOS.

> [!NOTE]
> No se admiten los perfiles de certificado PKCS con perfiles Wi-FI. En su lugar, use perfiles de certificado SCEP cuando use un [tipo EAP](../configuration/wi-fi-settings-windows.md#enterprise-profile).

Para usar un certificado basado en dispositivos, al [crear un perfil de certificado PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) para las plataformas admitidas, seleccione **Configuración**. Ahora verá el valor de **Tipo de certificado**, que admite las opciones de dispositivo o usuario.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Registros de auditoría centralizados<!--5603185, 5697164 -->
Una nueva experiencia de registros de auditoría centralizados ahora recopila los registros de auditoría de todas las categorías en una sola página. Puede filtrar los registros para obtener los datos que está buscando. Para ver los registros de auditoría, vaya a **Administración de inquilinos** > **Registros de auditoría**. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Información de etiqueta de ámbito incluida en los detalles de la actividad de registro de auditoría<!--5763534 -->
Los detalles de la actividad de registro de auditoría ahora incluyen información de etiqueta de ámbito (para los objetos de Intune que admiten etiquetas de ámbito). Para más información sobre los registros de auditoría, consulte [Uso de registros de auditoría para realizar un seguimiento de los eventos y supervisarlos](monitor-audit-logs.md).





<!-- ########################## -->
## <a name="november-2019"></a>Noviembre de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Actualización de la interfaz de usuario al borrar datos de la aplicación de forma selectiva<!-- 4102028 -->
La interfaz de usuario para borrar selectivamente los datos de la aplicación en Intune se ha actualizado. Los cambios de la UI son:
- Una experiencia más sencilla, dado el uso de un formato de tipo asistente condensado dentro de un panel.
- Una actualización del flujo de creación para incluir asignaciones.
- Una página de resumen de todos los elementos establecidos al ver las propiedades, antes de crear una nueva directiva o al editar una propiedad. Además, al editar las propiedades, el resumen solo mostrará una lista de elementos de la categoría de propiedades que se están editando.

Para obtener más información, consulte [Borrado solo de datos corporativos de aplicaciones administradas por Intune](../apps/apps-selective-wipe.md).

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Compatibilidad con el teclado de terceros de iOS y iPadOS<!-- 4922950 -->
En marzo de 2019, anunciamos el fin del la compatibilidad del parámetro de la directiva de protección de aplicaciones de iOS "Teclados de terceros". La característica está de vuelta en Intune con compatibilidad tanto con iOS como con iPadOS. Para habilitar esta configuración, visite la pestaña **Protección de datos** de una directiva de protección de aplicaciones iOS/iPadOS nueva o existente y busque la opción **Teclados de terceros** en **Transferencia de datos**.

El comportamiento de esta configuración de directiva difiere ligeramente de la implementación anterior. En las aplicaciones de varias identidades que usan la versión de SDK 12.0.16 y versiones posteriores que son el destino de directivas de protección de aplicaciones con esta opción configurada en **Bloquear**, los usuarios finales no podrán elegir los teclados de terceros en sus cuentas personales y de organización. Las aplicaciones que usan versiones de SDK 12.0.12 y anteriores seguirán mostrando el comportamiento documentado en la entrada de blog que lleva por título [Problema conocido: Los teclados de terceros no se bloquean en iOS para cuentas personales](https://aka.ms/3rdparty_iOS_Intune).


#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Experiencia mejorada de inscripción de macOS en el Portal de empresa <!-- 5074349  -->  
La experiencia de inscripción del Portal de empresa para macOS cuenta con un proceso de inscripción más sencillo que es más coherente con la experiencia de inscripción en el Portal de empresa para iOS. Los usuarios del dispositivo ahora ven lo siguiente:  

- Una interfaz de usuario más elegante.  
- Una lista de comprobación de inscripción mejorada.  
- Instrucciones más claras sobre cómo inscribir sus dispositivos.  
- Mejores opciones de solución de problemas.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Aplicaciones web iniciadas desde la aplicación Portal de empresa de Windows<!-- 5030972 -->
Los usuarios finales ahora pueden iniciar aplicaciones web directamente desde la aplicación Portal de empresa de Windows. Los usuarios finales pueden seleccionar la aplicación web y, a continuación, elegir la opción **Abrir en el explorador**. La dirección URL web publicada se abre directamente en un explorador web. Esta funcionalidad se implementará durante la próxima semana. Para más información sobre las aplicaciones web, consulte[Agregar aplicaciones web a Microsoft Intune](../apps/web-app.md).  

#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Nueva columna de tipo de asignación en el Portal de empresa para Windows 10 <!-- 5459950  -->
Se ha cambiado el nombre de la columna Portal de empresa > **Aplicaciones instaladas** > **Tipo de asignación** a **Requerida por la organización**.  En esa columna, los usuarios verán un valor de **Sí** o **No** para indicar si una aplicación es obligatoria o es opcional para su organización. La razón de estos cambios es la confusión que despertaba en los usuarios de los dispositivos el concepto de aplicaciones disponibles. Los usuarios pueden obtener más información sobre cómo instalar aplicaciones en el Portal de empresa en [Instalar y compartir aplicaciones en el dispositivo](../user-help/install-apps-cpapp-windows.md). Para obtener más información sobre cómo configurar la aplicación Portal de empresa para sus usuarios, vea [Configuración de la aplicación Portal de empresa de Microsoft Intune](../apps/company-portal-app.md).  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Requerimiento de administración de Jamf a grupos de usuarios de macOS<!-- 4061739  --> 
Puede dirigirse a grupos específicos de usuarios cuyos [dispositivos macOS serán administrados por Jamf](../protect/conditional-access-integrate-jamf.md). Esto le permite aplicar la integración de cumplimiento de Jamf a un subconjunto de dispositivos macOS mientras que otros dispositivos se administran mediante Intune. Si ya usa la integración de Jamf, la integración se destinará a todos los usuarios de manera predeterminada.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Nueva configuración de Exchange ActiveSync al crear un perfil de configuración de dispositivo de correo electrónico en dispositivos iOS<!-- 4892824   --> 
En dispositivos iOS/iPadOS, puede configurar la conectividad del correo electrónico en un perfil de configuración de dispositivos (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **iOS/iPadOS** como plataforma > **Correo electrónico** para tipo de perfil). 

Hay nuevas opciones de configuración de Exchange ActiveSync disponibles, entre las que se incluyen:
- **Datos de Exchange para sincronizar**: elija los servicios de Exchange que se sincronizarán (o cuya sincronización se bloqueará) con el calendario, los contactos, los recordatorios, las notas y el correo electrónico.
- **Permitir a los usuarios cambiar la configuración de sincronización**: permita (o impida) a los usuarios cambiar la configuración de sincronización para estos servicios en sus dispositivos.  

Para obtener más información sobre esta configuración, vaya a [Incorporación de la configuración de correo electrónico para dispositivos iOS en Microsoft Intune](../configuration/email-settings-ios.md). 

Se aplica a:

- iOS 13.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Evitación de que los usuarios agreguen cuentas personales de Google a dispositivos Android Enterprise dedicados y totalmente administrados<!-- 5353228   -->
En los dispositivos Android Enterprise dedicados y totalmente administrados, hay una nueva opción que impide que los usuarios creen cuentas de Google personales (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **Android Enterprise** para plataforma > **Solo el propietario del dispositivo > Restricciones de dispositivos** para tipo de perfil > **configuración de Usuarios y cuentas** > **Cuentas personales de Google**).

Para ver los valores que puede configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md).

Se aplica a:

- Dispositivos totalmente administrados de Android Enterprise
- Dispositivos Android Enterprise dedicados

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>Eliminación del parámetro de registro del servidor para los comandos de Siri en el perfil de restricciones de dispositivos de iOS/iPadOS <!-- 5468501   -->
En dispositivos iOS y iPadOS, el parámetro **Registro del servidor para los comandos de Siri** se ha quitado de la consola de administración de Microsoft Endpoint Manager (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > **iOS/iPadOS** para plataforma &gt; **Restricciones de dispositivos** para tipo de perfil &gt; **Aplicaciones integradas**). 

Esta configuración no tiene ningún efecto en los dispositivos. Para quitar el parámetro de los perfiles existentes, abra el perfil, realice cualquier cambio y, a continuación, guarde el perfil. El perfil se actualiza y la configuración se elimina de los dispositivos.

Para ver todos los valores que puede configurar, vea [Configuración de dispositivos iOS y iPadOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md).

Se aplica a:

- iOS/iPadOS

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Actualizaciones de características de Windows 10 (versión preliminar pública)<!-- 2384877 -->
Ahora puede implementar [actualizaciones de características de Windows 10](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) en dispositivos Windows 10. Las actualizaciones de características de Windows 10 son una nueva directiva de actualización de software que establece la versión de Windows 10 que desea que se instale y permanezca en los dispositivos. Puede usar este nuevo tipo de directiva junto con los anillos de actualización de Windows 10 existentes.

Los dispositivos que reciben la directiva de actualizaciones de características de Windows 10 instalarán la versión especificada de Windows y, a continuación, permanecerán con esa versión hasta que se edite o se quite la directiva. Los dispositivos que ejecutan una versión posterior de Windows permanecen en su versión actual. Los dispositivos que se encuentran en una versión específica de Windows pueden seguir instalando actualizaciones de calidad y seguridad para esa versión desde los anillos de actualización de Windows 10.

Este nuevo tipo de directiva comienza a implementarse en los inquilinos esta semana. Si esta directiva todavía no está disponible para el inquilino, lo estará pronto.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>Adición y cambio de información clave en archivos PLIST para aplicaciones macOS<!-- 4736278 -->
En los dispositivos macOS, ahora puede crear un perfil de configuración de dispositivos que cargue un archivo de lista de propiedades (. plist) asociado a una aplicación o el dispositivo (**Dispositivos** > **Perfiles de configuración** > **Crear perfil** > **macOS** para la plataforma > **Archivo de preferencias** para el tipo de perfil).

Solo algunas aplicaciones admiten preferencias administradas, y es posible que estas aplicaciones no le permitan administrar toda la configuración. Asegúrese de cargar un archivo de lista de propiedades que configure los valores del canal del dispositivo, no la configuración del canal del usuario.

Para obtener más información sobre esta característica, consulte [Adición de un archivo de lista de propiedades a dispositivos macOS mediante Microsoft Intune](../configuration/preference-file-settings-macos.md).

Se aplica a:

- dispositivos macOS con 10.7 y versiones más recientes

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Edición del valor de nombre de dispositivo para dispositivos Autopilot<!-- 2640074 -->
Puede editar el valor del nombre de dispositivo para los dispositivos Autopilot unidos a Azure AD.  Para obtener más información, consulte [Edición de atributos de dispositivo Autopilot](../../autopilot/enrollment-autopilot.md#edit-autopilot-device-attributes).

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Edición del valor de etiqueta de grupo para dispositivos Autopilot<!-- 4816775   -->
Puede editar el valor Etiqueta de grupo para dispositivos Autopilot. Para obtener más información, consulte [Edición de atributos de dispositivo Autopilot](../../autopilot/enrollment-autopilot.md#edit-autopilot-device-attributes).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="updated-support-experience---5012398---"></a>Experiencia de soporte técnico actualizada<!-- 5012398 -->

A partir de hoy, se está implantando en los inquilinos una experiencia actualizada y simplificada en la consola para [obtener ayuda y soporte técnico para Intune](get-support.md). Si esta experiencia todavía no está disponible para usted, lo estará pronto.

Se ha mejorado la búsqueda en la consola, los comentarios de incidencias comunes y el flujo de trabajo que se usa para ponerse en contacto con el servicio de soporte técnico. Al abrir una incidencia de soporte técnico, verá estimaciones en tiempo real de cuándo pueda esperar una devolución de llamada o una respuesta por correo electrónico; los clientes de soporte técnico Premier y Unified pueden especificar fácilmente la gravedad de su incidencia con el fin de obtener soporte técnico más rápido.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>Mejora de la experiencia de informes de Intune (versión preliminar pública) <!-- 3791418 -->
Intune ahora proporciona una experiencia de informes mejorada, con nuevos tipos de informes, una mejor organización de informes, vistas más centradas y una funcionalidad de informes más eficiente, así como datos más coherentes y precisos. Los nuevos tipos de informe se centran en lo siguientes aspectos:

- **Operativo**: proporciona registros nuevos con un enfoque de estado negativo. 
- **Organizativo**: proporciona un resumen más amplio del estado general.
- **Histórico**: proporciona patrones y tendencias a lo largo de un período de tiempo.
- **Especialista**: le permite usar datos sin procesar para crear sus propios informes personalizados.

El primer conjunto de informes nuevos se centra en el cumplimiento de los dispositivos. Para obtener más información, vea [Blog:marco de creación de informes de Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) e [Informes de Intune](reports.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Duplicación de roles personalizados o integrados <!-- 1081938   -->
Ahora puede copiar tanto roles integrados como roles personalizados. Para obtener más información, vea [Copia de un rol](../fundamentals/create-custom-role.md#copy-a-role).

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Nuevos permisos para el rol de administrador escolar <!-- 5621805  -->  
Se han agregado dos nuevos permisos, **Asignar perfil** y **Sincronizar dispositivo**, al rol de administrador escolar > **Permisos** > **Programas de inscripción**. El permiso de sincronizar perfil permite a los administradores de grupos sincronizar dispositivos Windows Autopilot. El permiso de asignar perfil les permite eliminar perfiles de inscripción de Apple iniciados por el usuario. También les concede permiso para administrar las asignaciones de dispositivos Autopilot y las asignaciones del perfil de implementación de Autopilot. Para obtener una lista de todos los permisos de administrador de grupo y administrador escolar, consulte [Asignación de un grupo de administración](/intune-education/group-admin-delegate).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Seguridad

#### <a name="bitlocker-key-rotation---2564951----"></a>Rotación de clave de BitLocker<!-- 2564951  -->
Puede usar una acción de dispositivo de Intune para [rotar de forma remota las claves de recuperación de BitLocker](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) para dispositivos administrados que ejecutan la versión 1909 o posterior de Windows. Para que se puedan rotar las claves de recuperación, los dispositivos deben configurarse para admitir la rotación de claves de recuperación.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>Actualizaciones en la inscripción de dispositivos dedicada para admitir la implementación de certificados de dispositivos SCEP <!-- 5198878  -->
Intune ahora admite la implementación de certificados de dispositivos SCEP en dispositivos Android Enterprise dedicados para permitir el acceso basado en certificados a los perfiles de Wi-Fi. La aplicación Microsoft Intune debe estar presente en el dispositivo para que funcione la implementación. Como resultado, hemos actualizado la experiencia de inscripción para dispositivos Android Enterprise dedicados. Las nuevas inscripciones siguen empezando de la misma manera (con QR, NFC, sin interacción o con identificador de dispositivo) pero ahora tienen un paso que requiere que los usuarios instalen la aplicación Intune. Los dispositivos existentes comenzarán a instalar la aplicación automáticamente de manera gradual.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>Registros de auditoría de Intune para colaboración de negocio a negocio<!--5670211 -->
La colaboración de negocio a negocio (B2B) le permite compartir de forma segura las aplicaciones y los servicios de la empresa con usuarios invitados de cualquier otra organización, manteniendo al mismo tiempo el control sobre sus propios datos corporativos. Intune ahora admite registros de auditoría para usuarios invitados de B2B. Por ejemplo, cuando los usuarios invitados realizan cambios, Intune podrá capturar estos datos a través de registros de auditoría. Para obtener más información, consulte [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](/azure/active-directory/b2b/what-is-b2b)

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Las líneas de base de seguridad se admiten en Microsoft Azure Government<!-- 4062552 -->

Las instancias de Intune que se hospedan en *Microsoft Azure Government* ahora pueden usar [líneas base de seguridad](../protect/security-baselines.md) para ayudarle a proteger sus usuarios y dispositivos.


<!-- ########################## -->
## <a name="october-2019"></a>Octubre de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Diseño de la lista de comprobación mejorado en la aplicación Portal de empresa para Android<!-- 5550857 -->  
La lista de comprobación de configuración de la aplicación Portal de empresa para Android se ha actualizado con un diseño ligero y nuevos iconos. Los cambios se alinean con las actualizaciones recientes realizadas en la aplicación Portal de empresa para iOS. Para una comparación en paralelo de los cambios, consulte [Novedades de la interfaz de usuario de aplicaciones](whats-new-app-ui.md). Para ver los pasos de inscripción actualizados, consulte [Inscripción con el perfil de trabajo Android](../user-help/enroll-device-android-work-profile.md) e [Inscripción de su dispositivo Android](../user-help/enroll-device-android-company-portal.md).  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Aplicaciones Win32 en dispositivos de modo Windows 10 S<!-- 3747604 --> 
Puede instalar y ejecutar aplicaciones Win32 en dispositivos administrados en modo Windows 10 S. Para ello, puede crear una o varias directivas complementarias para el modo S mediante las herramientas de PowerShell de Control de aplicaciones de Windows Defender (WDAC). Firme las directivas complementarias con el portal de firma de Device Guard y, después, cargue y distribuya las directivas mediante Intune. En Intune, encontrará esta funcionalidad seleccionando **Aplicaciones cliente** > **Directivas complementarias de Windows 10 S**. Para más información, consulte [Habilitación de aplicaciones Win32 en modo S](../apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>Establecimiento de la disponibilidad de las aplicaciones Win32 basada en una fecha y hora<!-- 3510685 -->
Como administrador, puede configurar la hora de inicio y la hora de la fecha límite para una aplicación Win32 necesaria. A la hora de inicio, la extensión de administración de Intune iniciará la descarga del contenido de la aplicación y lo almacenará en caché. La aplicación se instalará a la hora de la fecha límite. Para las aplicaciones disponibles, la hora de inicio determinará cuando la aplicación está visible en Portal de empresa. Para más información, consulte [Administración de aplicaciones Win32 de Intune](../apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Reinicio necesario del dispositivo basado en el período de gracia después de la instalación de la aplicación Win32<!-- 3136567 -->
Puede requerir que un dispositivo se reinicie después de que una aplicación Win32 se instale correctamente. Para más información, vea [Administración de aplicaciones Win32](../apps/apps-win32-app-management.md).

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Modo oscuro para el Portal de empresa de iOS<!-- 4911422 -->
El modo oscuro está disponible para el Portal de empresa de iOS. Los usuarios pueden descargar aplicaciones de empresa, administrar sus dispositivos y obtener soporte técnico de TI en la combinación de colores de su elección en función de la configuración del dispositivo. El Portal de empresa de iOS hará coincidir automáticamente la configuración del dispositivo del usuario final con el modo oscuro o claro. Para más información, consulte [Introducción al modo oscuro en el Portal de empresa de Microsoft Intune para iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). Para más información sobre el Portal de empresa de iOS, consulte [Configuración de la aplicación Portal de empresa de Microsoft Intune](../apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Versión mínima de la aplicación aplicada por el Portal de empresa de Android<!-- 2378776 -->
Con la opción **Min Company Portal version** (Versión mínima del Portal de empresa) de una directiva de protección de aplicaciones, puede especificar una versión definida mínima determinada del Portal de empresa que se aplique a un dispositivos de usuario final. Esta configuración de inicio condicional permite **bloquear el acceso**, **borrar datos** o **advertir** como posibles acciones cuando no se cumple el valor. Los posibles formatos de este valor siguen el patrón *[Principal].[Secundaria]* , *[Principal].[Secundaria].[Compilación]* o *[Principal].[Secundaria].[Compilación].[Revisión]* .

La opción **Min Company Portal version** (Versión mínima del Portal de empresa), si está configurada, afectará a cualquier usuario final que obtenga la versión 5.0.4560.0 del Portal de empresa y todas sus versiones futuras. Esta configuración no afectará a los usuarios que usen una versión del Portal de empresa anterior a la versión con la que se publique esta característica. Los usuarios finales que usen actualizaciones automáticas de aplicaciones en su dispositivo probablemente no verán ningún cuadro de diálogo de esta característica, dado que es posible que estén en la versión más reciente del Portal de empresa. Esta opción es solo para Android con la protección de aplicaciones para dispositivos inscritos y no inscritos. Para más información, consulte [Configuración de directivas de protección de aplicaciones de Android: inicio condicional](../apps/app-protection-policy-settings-android.md#conditional-launch).

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Incorporación de aplicaciones de Mobile Threat Defense a dispositivos no inscritos<!-- 3005337 -->
Puede crear una directiva de protección de aplicaciones de Intune que puede bloquear o borrar de forma selectiva los datos corporativos de los usuarios en función del estado de un dispositivo. El estado del dispositivo se determina mediante la solución Mobile Threat Defense (MTD) seleccionada. Esta funcionalidad existe en la actualidad con los dispositivos inscritos en Intune como una configuración de cumplimiento de dispositivos. Con esta nueva característica, ampliamos la detección de amenazas de un proveedor de Mobile Threat Defense para que funcione en dispositivos no inscritos. En Android, esta característica requiere la versión más reciente de Portal de empresa. En iOS, esta característica se podrá usar cuando las aplicaciones integren el SDK de Intune más reciente (v 12.0.15 +). Se actualizará el tema Novedades cuando la primera aplicación adopte el SDK de Intune más reciente. El resto de aplicaciones irán estando disponibles de manera gradual. Para más información, consulte [Creación de una directiva de protección de aplicaciones de Mobile Threat Defense con Intune](../protect/mtd-app-protection-policy.md).

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Notificación de aplicaciones de Google Play disponibles para perfiles de trabajo de Android<!-- 3041956   -->
En las instalaciones de aplicaciones disponibles en dispositivos dedicados, totalmente administrados y de perfil de trabajo de Android Enterprise, puede ver el estado de instalación de la aplicación, así como la versión instalada de aplicaciones administradas de Google Play. Para obtener más información, vea [Supervisión de las directivas de protección de aplicaciones](../apps/app-protection-policies-monitor.md), [Administrar dispositivos de perfil de trabajo Android con Intune](../enrollment/android-enterprise-overview.md) y [Tipo de aplicación de Google Play administrado](../apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge versión 77 y posteriores para Windows 10 y macOS (versión preliminar pública)<!-- 3872025, 4678761  -->
Microsoft Edge versión 77 y posteriores ya está disponible para implementarlo en equipos que ejecutan Windows 10 y macOS.

La versión preliminar pública ofrece los canales **Dev** y **Beta** para Windows 10 y un canal **Beta** para macOS. La implementación solo está en inglés (EN), pero los usuarios finales pueden cambiar el idioma para mostrar en el explorador desde **Configuración** > **Idiomas**. Microsoft Edge es una aplicación Win32 que se instala en el contexto del sistema y en arquitecturas similares (aplicación x86 en sistemas operativos x86 y aplicación x64 en sistemas operativos x64). Además, las actualizaciones automáticas del explorador están **Activadas** de forma predeterminada, y Microsoft Edge no se puede desinstalar. Para más información, vea [Adición de Microsoft Edge para Windows 10 a Microsoft Intune](../apps/apps-windows-edge.md) y la [documentación de Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Actualización de la interfaz de usuario de protección de aplicaciones y de la interfaz de usuario de aprovisionamiento de aplicaciones de iOS<!-- 4102027, 4102029   -->
La interfaz de usuario para crear y editar directivas de protección de aplicaciones y perfiles de aprovisionamiento de aplicaciones de iOS en Intune se ha actualizado. Los cambios de la UI son:
- Una experiencia más sencilla, dado el uso de un formato de tipo asistente condensado dentro de una hoja.
- Una actualización del flujo de creación para incluir asignaciones.
- Una página de resumen de todos los elementos establecidos al ver las propiedades, antes de crear una nueva directiva o al editar una propiedad. Además, al editar las propiedades, el resumen solo mostrará una lista de elementos de la categoría de propiedades que se están editando.

Para más información, vea [Creación y asignación de directivas de protección de aplicaciones](../apps/app-protection-policies.md) y [Uso de perfiles de aprovisionamiento de aplicaciones para iOS](../apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Escenarios guiados de Intune<!-- 4850318, 4831296, 3610611  -->
Ahora, Intune proporciona escenarios guiados que ayudan a realizar una tarea concreta o un conjunto de tareas en Intune. Un escenario guiado es una serie personalizada de pasos (flujo de trabajo) en torno a un caso de uso completo. Los escenarios más habituales se definen en función del rol que un administrador, un usuario o un dispositivo desempeñan en la organización. Estos flujos de trabajo suelen requerir una colección de perfiles, opciones, aplicaciones y controles de seguridad cuidadosamente organizados para proporcionar la mejor experiencia de usuario y seguridad. Estos son los nuevos escenarios guiados:
- [Implementación de Microsoft Edge para dispositivos móviles](guided-scenarios-edge.md)
- [Aplicaciones móviles seguras de Microsoft Office](guided-scenarios-office-mobile.md)
- [Escritorio moderno administrado en la nube](guided-scenarios-cloud-managed-pc.md)

Para más información, vea [Introducción a los escenarios guiados de Intune](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Variable de configuración de aplicaciones adicional disponible<!-- 4969237   -->
Al crear una directiva de configuración de aplicaciones, puede incluir la variable de configuración `AAD_Device_ID` como parte de los valores de configuración. En Intune, seleccione **Aplicaciones cliente** > **Directivas de configuración de aplicaciones** > **Agregar**. Especifique los detalles de la directiva de configuración y seleccione **Opciones de configuración** para ver la hoja **Opciones de configuración**. Para más información, vea la sección [Uso del diseñador de configuración en Adición de directivas de configuración de aplicaciones para dispositivos Android Enterprise administrados](../apps/app-configuration-policies-use-android.md#use-the-configuration-designer).

#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Creación de grupos de objetos de administración denominados conjuntos de directivas<!-- 3762880  -->
Los conjuntos de directivas permiten crear una agrupación de referencias a entidades de administración ya existentes que se deben identificar, establecer como destino y supervisar como una sola unidad conceptual. Los conjuntos de directivas no reemplazan los conceptos ni los objetos existentes. Puede seguir asignando objetos individuales en Intune y hacer referencia a objetos individuales como parte de un conjunto de directivas. Por lo tanto, cualquier cambio que se realice en esos objetos individuales se verá reflejado en el conjunto de directivas.  En Intune, deberá seleccionar **Conjuntos de directivas** > **Crear** para crear un conjunto de directivas desde cero.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo
'
#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Nuevo perfil de interfaz de configuración de firmware de dispositivo para dispositivos con Windows 10 y versiones posteriores (versión preliminar pública)<!-- 2266073  -->
En Windows 10 y versiones posteriores, puede crear un perfil de configuración de dispositivo para controlar la configuración y las características (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** como plataforma). En esta actualización, existe un nuevo tipo de perfil de interfaz de configuración de firmware de dispositivo que permite a Intune administrar la configuración de UEFI (BIOS).

Para más información sobre esta característica, vea [Uso de perfiles de DFCI en dispositivos Windows en Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md).

Se aplica a:

- Windows 10 RS5 (1809) y versiones más recientes en firmware compatible

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Actualización de la interfaz de usuario para crear y editar anillos de actualización de Windows 10<!-- 4099089         -->
Hemos actualizado la experiencia de interfaz de usuario para [crear y editar anillos de actualización de Windows 10](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) para Intune. Los cambios en la interfaz de usuario son los siguientes:  
- Formato de tipo asistente condensado en una sola hoja de la consola, bastante alejado de la dispersión de la hoja anterior cuando se configuraban anillos de actualización.   
- El flujo de trabajo revisado incluye las asignaciones antes de completar la configuración inicial del anillo.
- Una página de resumen que se puede usar para revisar todas las configuraciones realizadas antes de guardar e implementar un anillo de actualización nuevo. Al editar un anillo de actualización, en el resumen solo muestra la lista de elementos establecidos en la categoría de las propiedades que se hayan editado.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Actualización de la interfaz de usuario para crear y editar una directiva de actualización de software de iOS<!-- 4099090       --> 
Hemos actualizado la experiencia de interfaz de usuario para [crear](../protect/software-updates-ios.md#configure-the-policy) y [editar](../protect/software-updates-ios.md#edit-a-policy) directivas de actualización de software de iOS para Intune.  Los cambios en la interfaz de usuario son los siguientes:  
- Formato de tipo asistente condensado en una sola hoja de la consola, bastante alejado de la dispersión de la hoja anterior cuando se configuraban directivas de actualización.   
- El flujo de trabajo revisado incluye las asignaciones antes de completar la configuración inicial de la directiva.
- Una página de resumen que se puede usar para revisar todas las configuraciones realizadas antes de guardar e implementar una directiva nueva. Al editar una directiva, en el resumen solo muestra la lista de elementos establecidos en la categoría de las propiedades que se hayan editado.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>La configuración Reinicio establecido se ha quitado de los anillos de Windows Update<!--  4464404      -->
Como ya anunciamos en su día, ahora los anillos de actualización de Windows 10 de Intune [admiten la configuración de fechas límite](../protect/windows-update-settings.md) y ya no admiten *Reinicio establecido*. Las opciones de *Reinicio establecido* ya no están disponibles cuando al configurar o administrar anillos de actualización en Intune.  

Este cambio viene de la mano de algunos [cambios recientes en el Servicio de actualización de Windows](/windows/whats-new/whats-new-windows-10-version-1903#servicing) y en los dispositivos que ejecutan Windows 10 1903 o versiones posteriores, las *fechas límite* reemplazan las configuraciones de *Reinicio establecido*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Imposibilidad de instalar aplicaciones desde orígenes desconocidos en dispositivos de perfil de trabajo de Android Enterprise<!-- 4760025   -->
En los dispositivos de perfil de trabajo de Android Enterprise, los usuarios no pueden instalar aplicaciones procedentes de orígenes desconocidos en ninguna circunstancia. En esta actualización hay una nueva configuración, **Impedir la instalación de aplicaciones de orígenes desconocidos en el perfil personal**. Esta opción impide de forma predeterminada que los usuarios carguen aplicaciones de orígenes desconocidos en el perfil personal del dispositivo.

Para ver los valores que se pueden configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md).

Se aplica a:

- Perfil de trabajo de Android Enterprise

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Creación de un proxy HTTP global en los dispositivos de propietario de dispositivos de Android Enterprise<!-- 4816339   -->
En los dispositivos de Android Enterprise, se puede configurar un proxy HTTP global para cumplir los estándares de exploración web de la organización (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** como plataforma > **Propietario del dispositivo > Restricciones de dispositivos** como tipo de perfil > **Conectividad**). Una vez configurado, todo el tráfico HTTP usará este proxy.

Para configurar esta característica y ver los valores que se pueden configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md).

Se aplica a:

- Propietario del dispositivo Android Enterprise

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>La opción Conectar automáticamente se ha quitado de los perfiles de Wi-Fi del administrador de dispositivos Android y Android Enterprise<!-- 5021055   -->
En los dispositivos de administrador de dispositivos Android y Android Enterprise, puede crear un perfil de Wi-Fi para configurar diferentes opciones (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Administrador de dispositivos Android** o **Android Enterprise** como plataforma > **Wi-Fi** como tipo de perfil). En esta actualización, la opción **Conectar automáticamente** se ha quitado, ya que [no es compatible con Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Si utiliza esta configuración en un perfil de Wi-Fi, posiblemente haya notado que **Conectar automáticamente** no funciona. No es necesario realizar ninguna acción, pero tenga en cuenta que esta configuración se ha quitado en la interfaz de usuario de Intune.

Para ver la configuración actual, vaya a [Configuración de Wi-Fi de Android](../configuration/wi-fi-settings-android.md) y [Configuración de Wi-Fi de Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Se aplica a:

- Administrador de dispositivos Android 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Nuevos valores de configuración de dispositivo para dispositivos iOS e iPadOS supervisados<!-- 5199328   -->
En los dispositivos iOS e iPad se puede crear un perfil para restringir las características y la configuración de esos dispositivos (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS/iPadOS** como plataforma > **Restricciones de dispositivos** como tipo de perfil). En esta actualización, hay nuevas opciones de configuración que puede controlar: 
- El acceso a la unidad de red en la aplicación de archivos  
- El acceso a la unidad USB en la aplicación de archivos 
- La posibilidad tener Wi-Fi siempre activado 

Para ver estas opciones, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md).

Se aplica a:

- iOS 13.0 y versiones más recientes
- IPadOS 13.0 y versiones más recientes

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Cambiar a mostrar solo la página Estado de inscripción en los dispositivos aprovisionados mediante la configuración rápida (OOBE)<!--3959566-->
Ahora puede elegir mostrar solo la página Estado de inscripción en los dispositivos aprovisionados mediante OOBE de Autopilot.

Para ver el nuevo control de alternancia, elija **Intune** > **Inscripción de dispositivos** > **Inscripción de Windows** > **página Estado de inscripción** > **Crear perfil** > **Configuración** > **Mostrar solo la página en los dispositivos aprovisionados por la configuración rápida (OOBE)** .

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Especificar qué versiones de sistema operativo del dispositivo Android se inscriben con el perfil de trabajo o la inscripción del administrador de dispositivos<!-- 4350697   -->
Con las restricciones del tipo de dispositivo de Intune, puede usar la versión del sistema operativo del dispositivo para especificar qué dispositivos de usuario usarán la inscripción de perfil de trabajo de Android Enterprise o la inscripción de administrador de dispositivos Android.  Para obtener más información, consulte [Establecer restricciones de inscripción](../enrollment/enrollment-restrictions-set.md).



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Intune admite iOS 11 y posterior<!-- 4665324  -->
La inscripción en Intune y el Portal de empresa ahora admiten las versiones de iOS 11 y posteriores. No se admiten versiones anteriores.

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Nuevas restricciones para cambiar el nombre de los dispositivos Windows<!-- 3478938  -->
Al cambiar el nombre de un dispositivo Windows, se deben seguir reglas nuevas:
- 15 caracteres o menos (debe ser menor o igual que 63 bytes, sin incluir el valor NULL final).
- No puede ser una cadena nula o vacía.
- Caracteres ASCII permitidos: letras (a-z, A-Z), números (0-9) y guiones.
- Caracteres Unicode permitidos: caracteres >=0x80, debe tener un formato UTF8 válido, debe ser asignable mediante IDN (es decir, el proceso RtlIdnToNameprepUnicode debe finalizar correctamente. Consulte el documento RFC 3492).
- El nombre no debe contener números exclusivamente.
- El nombre no debe contener espacios.
- Caracteres no permitidos: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

 Para más información, vea [Cambio de nombre de un dispositivo en Intune](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Nuevo informe de Android en la página de información general de dispositivos<!-- 4924364 -->
Un nuevo informe en la página de información general de dispositivos muestra la cantidad de dispositivos Android inscritos en cada solución de administración de dispositivos. Este gráfico muestra la cantidad de dispositivos inscritos de perfil de trabajo, totalmente administrados, dedicados y de administrador de dispositivos. Para ver el informe, elija **Intune** > **Dispositivos** > **Información general**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Seguridad de dispositivos

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Línea de base de Microsoft Edge (versión preliminar)<!--  3787164  -->
Hemos agregado una versión preliminar de la línea de base de seguridad para la [configuración de Microsoft Edge](../protect/security-baseline-settings-edge.md). 

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>Certificados PKCS para macOS<!-- 1333650       -->
Ahora puede [usar certificados PKCS con macOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). Puede seleccionar el certificado PKCS como un tipo de perfil para macOS e implementar certificados de usuario y de dispositivo que tengan [campos de firmante y de nombre alternativo del firmante personalizados](../protect/certficates-pfx-configure.md#subject-name-format).  

El certificado PKCS para macOS también admite una nueva opción, _Permitir el acceso de todas las aplicaciones_. Con ella, puede permitir el acceso de todas las aplicaciones asociadas a la clave privada del certificado.  Para más información sobre esta opción, vea la documentación de Apple en https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Credenciales derivadas para aprovisionar dispositivos móviles iOS con certificados<!--  1736036, 1736037, 1772050, 2777333         -->  
Intune admite el uso de [credenciales derivadas](../protect/derived-credentials.md) como método de autenticación y para el cifrado y la firma S/MIME de dispositivos iOS. Las credenciales derivadas son una implementación de la norma *800-157 del National Institute of Standards and Technology (NIST)* relativa a la implementación de certificados en dispositivos.  

Las credenciales derivadas se basan en el uso de una tarjeta de verificación de identidad personal (PIV) o una tarjeta de acceso común (CAC), como una tarjeta inteligente. Para obtener una credencial derivada para un dispositivo móvil, los usuarios comienzan en la aplicación Portal de empresa y siguen un flujo de trabajo de inscripción que es único para el proveedor que usen.  Un requisito común a todos los proveedores es usar una tarjeta inteligente en un equipo para autenticarse en el proveedor de las credenciales derivadas. Tras ello, dicho proveedor emite un certificado para el dispositivo que viene derivado de la tarjeta inteligente del usuario.  

Intune admite los siguientes proveedores de credenciales derivadas:
- DISA Purebred
- Entrust Datacard
- Intercede

Las credenciales derivadas se usan como método de autenticación de los perfiles de configuración de dispositivos de VPN, Wi-Fi y correo electrónico. También se pueden usar para la autenticación de aplicaciones y el cifrado y la firma S/MIME.  

Para más información sobre la norma, vea el documento sobre [credenciales PIV derivadas](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) en www.nccoe.nist.gov.

#### <a name="use-graph-api-to-specify-an-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Uso de Graph API para especificar un nombre principal de usuario local como variable en certificados SCEP<!--  5437939        -->  
Cuando use [Graph API de Intune](/graph/api/resources/intune-graph-overview?view=graph-rest-1.0), puede especificar onPremisesUserPrincipalName como variable del nombre alternativo del firmante (SAN) de los certificados SCEP.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->'
### <a name="microsoft-365-device-management"></a>Administración de dispositivos de Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Experiencia de administración mejorada en Administración de dispositivos de Microsoft 365<!-- 5551239 -->
Existe ahora una experiencia de administración actualizada y optimizada que está disponible con carácter general en el área de trabajo de especialistas de Administración de dispositivos de Microsoft 365 en [https://endpoint.microsoft.com](https://endpoint.microsoft.com), por ejemplo:

- **Navegación actualizada**: encontrará una navegación de primer nivel simplificada que agrupa las características de manera lógica.
- **Nuevos filtros de plataforma**: puede seleccionar una sola plataforma, que muestra solo las directivas y las aplicaciones de la plataforma seleccionada, en las páginas Dispositivos y Aplicaciones.
- **Nueva página principal**: vea rápidamente el estado del servicio, el estado de su inquilino, noticias, etc., en la nueva página principal.
Para más información sobre estas mejoras, vea la [entrada de blog de Enterprise Mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) en el sitio web de la comunidad tecnológica de Microsoft.

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Introducción al nodo Seguridad del punto de conexión en Administración de dispositivos de Microsoft 365<!-- 5630102 -->

El nodo **Seguridad del punto de conexión** está ahora disponible con carácter general en el área de trabajo de especialistas de Administración de dispositivos de Microsoft 365 en https://endpoint.microsoft.com, que agrupa las funcionalidades para proteger los puntos de conexión como:

- Líneas de base de seguridad:  grupo preconfigurado de valores de configuración que le ayudan a aplicar un grupo conocido de valores de configuración y valores predeterminados que recomienda Microsoft.
- Tareas de seguridad: aproveche las ventajas de la administración de amenazas y vulnerabilidades (TVM) de Microsoft Defender ATP y use Intune para corregir las debilidades del punto de conexión.
- ATP de Microsoft Defender: integración de Microsoft Defender Advanced Threat Protection (ATP) para ayudar a evitar infracciones de seguridad en dispositivos móviles.""

Esta configuración seguirá siendo accesible desde otros nodos aplicables, como los dispositivos, y el estado configurado actual será el mismo, sin importar dónde tenga acceso a estas funcionalidades y las habilite.

Para más información sobre estas mejoras, consulte la [entrada de blog sobre el éxito de clientes de Intune](https://aka.ms/Endpoint_security_node) en el sitio web de la comunidad tecnológica de Microsoft.

<!-- ########################## -->
## <a name="september-2019"></a>Septiembre de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Aplicaciones de LOB privadas de Google Play administrado<!-- 1464182  -->'
Ahora, Intune permite a los administradores de TI publicar aplicaciones de LOB de Android privadas en Google Play administrado a través de un iframe incrustado en la consola de Intune.  Anteriormente, los administradores de TI tenían que publicar aplicaciones de LOB directamente en la consola de publicación de Google Play, lo cual requería varios pasos y llevaba mucho tiempo. Esta nueva característica permite publicar fácilmente aplicaciones de LOB siguiendo solo unos pocos pasos, sin necesidad de salir de la consola de Intune.  Los administradores ya no tendrán que registrarse manualmente como desarrolladores en Google, y tampoco será necesario abonar la tasa de registro de Google de 25 $.  Cualquiera de los escenarios de administración de Android Enterprise en que se use Google Play administrado pueden beneficiarse de esta característica (dispositivos con perfil de trabajo, dedicados, totalmente administrados y no inscritos). En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. Luego, en la lista **Tipo de aplicación**, seleccione **Google Play administrado**. Para obtener más información sobre las aplicaciones de Google Play administrado, consulte [Incorporación de aplicaciones de Google Play administrado a dispositivos Android Enterprise con Intune](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Experiencia en el Portal de empresa de Windows<!-- 1473353, 3598357 -->
El Portal de empresa de Windows se está actualizando. Podrá usar varios filtros en la página Aplicaciones del Portal de empresa de Windows. La página Detalles del dispositivo también se está actualizando con una experiencia de usuario mejorada. Estamos en proceso de implementar estas actualizaciones para todos los clientes, que se espera que finalicen al final de la semana próxima.

#### <a name="macos-support-for-web-apps---3174427---"></a>Compatibilidad de macOS con aplicaciones web<!-- 3174427 -->
Las aplicaciones web, que le permiten agregar un acceso directo a una dirección URL en la web, se pueden instalar en el Dock mediante Portal de empresa para macOS. Los usuarios finales pueden acceder a la acción de **Instalar** desde la página de detalles de la aplicación para una aplicación web en Portal de empresa para macOS. Para más información sobre el tipo de aplicación de **vínculo web**, consulte [Incorporación de aplicaciones a Microsoft Intune](../apps/apps-add.md) y [Agregar aplicaciones web a Microsoft Intune](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps---3173501----"></a>Compatibilidad de macOS con las aplicaciones de VPP<!-- 3173501  -->
Las aplicaciones macOS, compradas con Apple Business Manager, se muestran en la consola cuando se sincronizan los tokens de VPP de Apple en Intune. Puede asignar, revocar y reasignar licencias basadas en dispositivos y usuarios para grupos mediante la consola de Intune. Microsoft Intune le ayuda a administrar las aplicaciones de VPP compradas para su uso en su empresa:

- Informes sobre la información de licencia desde la tienda de aplicaciones.
- Realizando un seguimiento de cuántas licencias ha usado.
- Le ayudamos a impedir la instalación de más copias de la aplicación que las que tiene.

Para más información, consulte [Administración de aplicaciones y libros comprados por volumen con Microsoft Intune](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Compatibilidad con iframe de Google Play administrado<!-- 2871756  -->
Intune ahora proporciona compatibilidad para agregar y administrar vínculos web directamente en la consola de Intune a través del iframe de Google Play administrado.  Esto permite a los administradores de TI enviar una dirección URL y un gráfico de iconos y, a continuación, implementar esos vínculos en dispositivos como aplicaciones Android normales. Cualquiera de los escenarios de administración de Android Enterprise en que se use Google Play administrado pueden beneficiarse de esta característica (dispositivos con perfil de trabajo, dedicados, totalmente administrados y no inscritos). En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. Luego, en la lista **Tipo de aplicación**, seleccione **Google Play administrado**. Para obtener más información sobre las aplicaciones de Google Play administrado, consulte [Incorporación de aplicaciones de Google Play administrado a dispositivos Android Enterprise con Intune](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>Instalación silenciosa de aplicaciones de LOB de Android en dispositivos Zebra<!-- 4252734  -->
Al instalar aplicaciones de línea de negocio (LOB) de Android en [dispositivos Zebra](../configuration/android-zebra-mx-overview.md), en lugar de que se le solicite la descarga e instalación de la aplicación de LOB, podrá instalar la aplicación de forma silenciosa. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. En el panel **Seleccionar un tipo de aplicación**, seleccione **Aplicación de línea de negocio**. Para obtener más información, consulte [Incorporación de una aplicación de línea de negocio de Android a Microsoft Intune](../apps/lob-apps-android.md).

Actualmente, una vez descargada la aplicación de LOB, aparecerá una notificación informando de la **descarga correcta** en el dispositivo del usuario. La notificación solo se puede descartar pulsando **Borrar todo** en el sombreado de la notificación. Este problema se corregirá en una próxima versión y la instalación será totalmente silenciosa sin ningún indicador visual.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Operaciones de lectura y escritura de Graph API para aplicaciones de Intune<!-- 5031704  -->
Las aplicaciones pueden llamar a Graph API de Intune con operaciones de lectura y escritura mediante la identidad de la aplicación y sin credenciales de usuario. Para obtener más información sobre cómo obtener acceso a Microsoft Graph API para Intune, consulte [Trabajar con Intune en Microsoft Graph](/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Cifrado y uso compartido de datos protegidos para el SDK de aplicaciones de Intune para iOS<!-- 3586942  -->
El SDK de aplicaciones de Intune para iOS usará claves de cifrado de 256 bits cuando el cifrado esté habilitado mediante las directivas de protección de aplicaciones. Todas las aplicaciones deberán tener una versión de SDK 8.1.1 para permitir el uso compartido de datos protegidos.

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Actualizaciones a la aplicación de Microsoft Intune<!-- 4997846 -->
La aplicación de Microsoft Intune para Android se ha actualizado con las siguientes mejoras:
- Se ha actualizado y mejorado el diseño para incluir la navegación inferior para las acciones más importantes.
- Se ha agregado una página adicional que muestra el perfil del usuario.
- Se ha agregado la muestra de notificaciones interactivas en la aplicación para el usuario, como la necesidad de actualizar la configuración del dispositivo.
- Se ha agregado la muestra de notificaciones push personalizadas, alineando la aplicación con la compatibilidad agregada recientemente en la aplicación Portal de empresa para iOS y Android. Para más información, consulte [Envío de notificaciones personalizadas en Intune](../remote-actions/custom-notifications.md).
""
#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Para dispositivos iOS, personalice la pantalla de privacidad del proceso de inscripción del Portal de empresa.<!-- 4394993 -->
Con Markdown, puede personalizar la pantalla de privacidad del Portal de empresa que los usuarios finales ven durante la inscripción de iOS. En concreto, podrá personalizar la lista de elementos que la organización no puede ver o realizar en el dispositivo. Para más información, consulte [Configuración de la aplicación Portal de empresa de Intune](../apps/company-portal-app.md#configuration).



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Compatibilidad con perfiles VPN de IKEv2 para iOS<!-- 1943438   -->
En esta actualización, puede crear perfiles VPN para el cliente VPN nativo de iOS mediante el protocolo IKEv2. IKEv2 es un nuevo tipo de conexión en **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para plataforma > **VPN** para tipo de perfil > **Tipo de conexión**.

Estos perfiles de VPN configuran el cliente de VPN nativo, por lo que no se instalan ni insertan aplicaciones cliente de VPN en los dispositivos administrados. Esta característica exige que los dispositivos estén inscritos en Intune (inscripción de MDM).

Para ver la configuración VPN actual que puede establecer, vaya a [Configuración de VPN en dispositivos iOS](../configuration/vpn-settings-ios.md).

Se aplica a:

- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Las características del dispositivo, las restricciones de dispositivos y los perfiles de extensión de la configuración de iOS y macOS se muestran mediante el tipo de inscripción.<!-- 4886161   -->

En Intune, puede crear perfiles para dispositivos iOS y macOS (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **iOS** o **macOS** como plataforma > **Características del dispositivo**, **Restricciones de dispositivos** o **Extensiones** para tipo de perfil). 

En esta actualización, la configuración disponible en el portal de Intune se clasifica por el tipo de inscripción al que se aplica:

- iOS
  - Inscripción de usuarios""
  - Inscripción de dispositivos
  - Inscripción de dispositivo automatizada (supervisado)
  - Todos los tipos de inscripción

- macOS
  - Aprobada por el usuario
  - Inscripción de dispositivos
  - Inscripción de dispositivo automatizada
  - Todos los tipos de inscripción

Se aplica a:

- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Nueva configuración del control de voz para dispositivos iOS supervisados que se ejecutan en pantalla completa<!-- 4892835   -->
En Intune, puede crear directivas para ejecutar dispositivos iOS supervisados como una pantalla completa, o un dispositivo dedicado (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil > **Pantalla completa**).

En esta actualización, hay nuevas opciones de configuración que puede controlar:
- **Control de voz**: Habilita el control de voz en el dispositivo mientras se encuentra en pantalla completa.
- **Modificación del control de voz**: Permite a los usuarios cambiar el ajuste del control de voz del dispositivo mientras se encuentra en pantalla completa.

Para ver la configuración actual, vaya a los [parámetros de pantalla completa de iOS](../configuration/device-restrictions-ios.md#kiosk).

Se aplica a:

- iOS 13.0 y versiones posteriores

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Uso del inicio de sesión único para aplicaciones y sitios web en los dispositivos iOS y macOS<!-- 4893175   -->
En esta actualización, hay algunos nuevos ajustes para el inicio de sesión único para dispositivos iOS y macOS (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **iOS** o **macOS** como plataforma > **Características del dispositivo** para tipo de perfil).

Use estas opciones para configurar una experiencia de inicio de sesión único, especialmente para aplicaciones y sitios web que usan la autenticación Kerberos. Puede elegir entre una extensión de aplicación de inicio de sesión único de credencial genérica y la extensión integrada de Kerberos de Apple.

Para ver las características de dispositivo actuales que puede configurar, vaya a las [características de dispositivo de iOS](../configuration/ios-device-features-settings.md) y [Características de dispositivo de macOS](../configuration/macos-device-features-settings.md).

Se aplica a:

- iOS 13." y versiones más recientes
- macOS 10.15 y versiones más recientes

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Asociación de dominios a aplicaciones en dispositivos macOS 10.15 y versiones posteriores<!-- 4898079   -->
En los dispositivos macOS, puede configurar diferentes características e incorporar estas características a los dispositivos mediante una directiva (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > **macOS** para plataforma > **Características de dispositivo** para tipo de perfil). En esta actualización, puede asociar dominios a sus aplicaciones. Esta característica ayuda a compartir credenciales con sitios web relacionados con la aplicación, y se puede usar con la extensión de inicio de sesión único de Apple, vínculos universales y relleno automático de contraseñas. 

Para ver los parámetros actuales que puede configurar, vaya a [Configuración de características de dispositivos macOS en Intune](../configuration/macos-device-features-settings.md).

Se aplica a:

- macOS 10.15 y versiones más recientes

#### <a name="use-itunes-and-aps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Uso de "iTunes" y "apps" en la dirección URL de iTunes App Store al mostrar u ocultar aplicaciones en dispositivos iOS supervisados<!-- 4928474   --> 
En Intune, puede crear directivas para mostrar u ocultar aplicaciones en los dispositivos iOS supervisados (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil > **Mostrar u ocultar aplicaciones**). 

Puede especificar la dirección URL de iTunes App Store, como `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. En esta actualización, se pueden usar `apps` y `itunes` en la dirección URL, como:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Para obtener más información acerca de esta configuración, consulte [Mostrar u ocultar aplicaciones](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Se aplica a:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Los valores de tipo de contraseña de la directiva de cumplimiento de Windows 10 son más claros y coinciden con CSP.<!-- 5138985 -->
En los dispositivos Windows 10, puede crear una directiva de cumplimiento que requiera características de contraseña específicas (**Cumplimiento de dispositivos** > **Directivas** > **Crear directiva** > **Windows 10 y versiones posteriores** para plataforma > **Seguridad del sistema**). En esta actualización:
- Los valores de **Tipo de contraseña** son más claros y se han actualizado para coincidir con [DeviceLock/AlphanumericDevicePasswordRequired CSP](/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- El valor de **Expiración de contraseña (días)** se ha actualizado para permitir valores entre 1 y 730 días. 

Para obtener más información sobre la configuración del cumplimiento de Windows 10, consulte [Configuración de Windows 10 y versiones posteriores para marcar dispositivos como compatibles o no compatibles con Intune](../protect/compliance-policy-create-windows.md). 

Se aplica a:
- Windows 10 y versiones posteriores

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Actualización de la interfaz de usuario para configurar el acceso local de Microsoft Exchange<!-- 4092920 -->  
Hemos actualizado la consola en la que [configura el acceso local a Microsoft Exchange](../protect/conditional-access-exchange-create.md). Todas las configuraciones para el acceso local de Exchange están ahora disponibles en el mismo panel de la consola donde *habilita el control de acceso local de Exchange*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Permiso o restricción para la adición de widgets de aplicaciones a la pantalla principal en dispositivos de perfil de trabajo de Android Enterprise<!-- 1109650  --> 
En dispositivos Android Enterprise, puede configurar características en el perfil de trabajo (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para plataforma > **Solo perfil de trabajo > Restricciones de dispositivos** para tipo de perfil). En esta actualización, puede permitir que los usuarios agreguen widgets expuestos por las aplicaciones del perfil de trabajo a la pantalla principal del dispositivo.

Para ver los valores que puede configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md).

Se aplica a:
- Perfil de trabajo de Android Enterprise

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Los nuevos inquilinos desaparecerán de forma predeterminada de la administración del administrador de dispositivos de Android.<!-- 4869790   -->
Las funcionalidades del administrador de dispositivos de Android se han sustituido por Android Enterprise. Por lo tanto, se recomienda usar Android Enterprise para nuevas inscripciones. En una actualización futura, los nuevos inquilinos deberán completar los siguientes requisitos previos en la inscripción de Android para usar la administración del administrador de dispositivos: Vaya a **Intune** > **Inscripción de dispositivos** > **Inscripción de Android** > **Personal and corporate-owned devices with device administration privileges**(Dispositivos personales y corporativos con privilegios de administración de dispositivos) > **Use el administrador de dispositivos para administrar los dispositivos**.

Los inquilinos existentes no experimentarán cambio alguno en sus entornos.

Para obtener más información sobre el administrador de dispositivos Android en Intune, consulte [Inscripción del administrador de dispositivos Android](/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045----"></a>Lista de dispositivos DEP asociados a un perfil<!-- 5012045  -->
Ahora puede ver una lista paginada de los dispositivos del Programa de inscripción de dispositivos (DEP) automatizados de Apple que están asociados a un perfil. Puede buscar en la lista desde cualquier página. Para ver la lista, vaya a **Intune** > **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción** > elija un token > **Perfiles** > elija un perfil > **Dispositivos asignados** (bajo **Supervisar**).

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Inscripción de usuario de iOS en versión preliminar<!-- 4817900 -->
La versión iOS 13.1 de Apple incluye Inscripción de usuario, una nueva forma de administración ligera para dispositivos iOS. Se puede usar en lugar de Inscripción de dispositivos o de Inscripción de dispositivo automatizada (anteriormente Programa de inscripción de dispositivos) para dispositivos de propiedad personal. La versión preliminar de Intune es compatible con este conjunto de características, ya que permite:

- Realizar la inscripción de usuarios de destino en grupos de usuarios.
- Ofrecer a los usuarios finales la posibilidad de seleccionar entre la inscripción de usuarios más ligera o la inscripción de dispositivos más segura cuando inscriban sus dispositivos.

A partir del 24/9/2019 con la versión 13.1 de iOS, estaremos en el proceso de implementar estas actualizaciones para todos los clientes y se espera que finalicen al final de la semana próxima.

Se aplica a:

- iOS 13.1 y versiones posteriores

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Más compatibilidad con dispositivos Android totalmente administrados<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Hemos agregado la siguiente compatibilidad con dispositivos Android totalmente administrados:

- Los certificados SCEP para dispositivos Android totalmente administrados están disponibles para la autenticación de certificados en dispositivos administrados como propietario del dispositivo. Los certificados SCEP ya se admiten en los dispositivos con perfil de trabajo.  Con los certificados SCEP para el propietario del dispositivo, podrá: <!-- 5227935 -->
    - crear un perfil de SCEP en la sección correspondiente de Android Enterprise
    - vincular certificados SCEP con el perfil de Wi-Fi del propietario del dispositivo para la autenticación
    - vincular certificados SCEP con los perfiles VPM del propietario del dispositivo para la autenticación
    - vincular certificados SCEP con los perfiles de correo electrónico del propietario del dispositivo para la autenticación (a través de AppConfig)
- Las aplicaciones del sistema son compatibles con dispositivos de Android Enterprise. En Intune, agregue una aplicación del sistema Android Enterprise seleccionando **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. En la lista **Tipo de aplicación**, seleccione **Aplicación del sistema Android Enterprise**. Para más información, vea [Agregar aplicaciones del sistema Android Enterprise a Microsoft Intune](../apps/apps-ae-system.md). <!-- 4062195 -->
- En **Cumplimiento de dispositivos** > **Android Enterprise** > **Propietario del dispositivo**, puede crear una directiva de cumplimiento que cumpla con el nivel de atestación de Google SafetyNet.   <!-- 4631425 -->
- En dispositivos Android Enterprise totalmente administrados, se admiten los proveedores de Mobile Threat Defense. En **Cumplimiento de dispositivos** > **Android Enterprise** > **Propietario del dispositivo**, puede elegir un nivel de amenaza aceptable. <!-- 4631440 --> En [Configuración de Android Enterprise para marcar dispositivos como compatibles o no compatibles con Intune](../protect/compliance-policy-create-android-for-work.md) se muestra la configuración actual.
- En los dispositivos Android Enterprise totalmente administrados, la aplicación Microsoft Launcher ahora se puede configurar a través de directivas de configuración de aplicaciones para permitir una experiencia de usuario final estandarizada en el dispositivo totalmente administrado. La aplicación Microsoft Launcher se puede usar para personalizar el dispositivo Android. Usando la aplicación con una cuenta Microsoft o una cuenta profesional o educativa, puede acceder a su calendario, documentos y actividades recientes en la fuente personalizada. <!-- 5334044 -->

Con esta actualización, nos complace anunciar que la compatibilidad de Intune con Android Enterprise totalmente administrado ya está disponible con carácter general.

Se aplica a:

- Dispositivos totalmente administrados de Android Enterprise

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Envío de notificaciones personalizadas a un solo dispositivo<!-- 4928910 -->
Ahora puede seleccionar un solo dispositivo y, a continuación, usar una acción de dispositivo remoto para [enviar una notificación personalizada solo a ese dispositivo](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Las acciones de borrado y restablecimiento de código de acceso no están disponibles para los dispositivos iOS inscritos mediante la inscripción de usuarios.<!-- 4950491 -->
La inscripción de usuarios es un nuevo tipo de inscripción de dispositivos de Apple. Al inscribir dispositivos mediante la inscripción de usuarios, las acciones remotas de borrado y restablecimiento de código de acceso no estarán disponibles para dichos dispositivos.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Compatibilidad de Intune con dispositivos iOS 13 y macOS Catalina<!-- 4665317 -->
Intune admite ahora la administración de dispositivos iOS 13 y macOS Catalina.
Para más información, vea la [entrada de blog sobre la compatibilidad de Microsoft Intune con iOS 13 y iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Compatibilidad de Intune con dispositivos iPadOS e iOS 13.1<!--5439574-->
Intune admite ahora la administración de dispositivos iPadOS e iOS 13.1. Para más información, vea [esta entrada de blog](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Seguridad de dispositivos

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>Compatibilidad de BitLocker con la rotación de contraseñas de recuperación controlada por el cliente<!--  3444125 -->
Use la configuración de Endpoint Protection de Intune para configurar la [rotación de contraseñas de recuperación controlada por el cliente](../protect/endpoint-protection-windows-10.md#windows-encryption) para BitLocker en dispositivos que ejecutan la versión 1909 de Windows o una posterior.

Esta configuración inicia una actualización de la contraseña de recuperación controlada por el cliente después de la recuperación de la unidad del sistema operativo (mediante bootmgr o WinRE) y un desbloqueo de la contraseña de recuperación en una unidad de datos fija. Esta opción actualiza la contraseña de recuperación específica que se usó, y otras contraseñas no usadas en el volumen permanecen sin cambios. Para obtener más información, consulte la documentación de CSP de BitLocker para [ConfigureRecoveryPasswordRotation](/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Protección contra alteraciones para el antivirus de Windows Defender<!-- 4705448        -->
Use Intune para administrar la *Protección contra alteraciones* para el antivirus de Windows Defender. Encontrará el [ajuste para la Protección contra alteraciones](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) en el grupo del centro de seguridad de Microsoft Defender al usar perfiles de configuración de dispositivos para Windows 10 Endpoint Protection. Puede establecer la protección contra alteraciones en **Habilitado** para activar sus restricciones; en **Deshabilitado** para desactivarlas; o en **No configurado** para mantener la configuración actual de los dispositivos.  

Para obtener más información acerca de la Protección contra alteraciones, vea [Evitar cambios de la configuración de seguridad con Protección contra alteraciones](/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) en la documentación de Windows.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>La configuración avanzada del Firewall de Windows Defender ya está disponible con carácter general.<!--  5317392       -->  
Las [reglas de firewall personalizadas de Windows Defender para Endpoint Protection](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), que se configuran como parte de un perfil de configuración de dispositivos, ya están disponibles con carácter general en tanto que versión preliminar pública.  Puede usar estas reglas para especificar un comportamiento entrante y saliente en las aplicaciones, las direcciones de red y los puertos. Estas reglas se publicaron en julio como una versión preliminar pública. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Actualización de la interfaz de usuario de Intune: panel Estado del inquilino<!-- 5273210  -->
La interfaz de usuario para el panel Estado del inquilino se actualizó para alinearla con los estilos de interfaz de usuario de Azure. Para más información, consulte [Estado del inquilino](tenant-status.md).

### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863----"></a>Las etiquetas de ámbito ahora son compatibles con las directivas de términos de uso.<!-- 2358863  -->
Ahora puede asignar [etiquetas de ámbito](scope-tags.md) a las directivas de términos de uso. Para ello, vaya a **Intune** > **Inscripción de dispositivos** > **Términos y condiciones** > elija un elemento de la lista > **Propiedades** > **Etiquetas de ámbito** > elija una etiqueta de ámbito.

<!-- ########################## -->
## <a name="august-2019"></a>Agosto de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Control del comportamiento de desinstalación de aplicaciones iOS en anulación de la inscripción de dispositivos<!-- 3504144   -->
Los administradores pueden administrar si una aplicación se quita de un dispositivo o se conserva en este cuando se anula la inscripción de dicho dispositivo en el nivel de grupo de usuarios o dispositivos. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Categorización de aplicaciones de Microsoft Store para Empresas<!-- 3926922 -->
Puede categorizar las aplicaciones de la Tienda Microsoft para Empresas. Para ello, elija aplicaciones  > **cliente** > de **Intune** **aplicaciones** > seleccione una aplicación de Microsoft Store para empresas  > **categoría**de **información**de la aplicación. En el menú desplegable, asigne una categoría.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Notificaciones personalizadas para usuarios de aplicaciones de Microsoft Intune<!-- 4843354  -->
La aplicación de Microsoft Intune para Android ahora admite la visualización de notificaciones de envío personalizadas y se alinea con la compatibilidad agregada recientemente en las aplicaciones de Portal de empresa para iOS y Android. Para más información, consulte [Envío de notificaciones personalizadas en Intune](../remote-actions/custom-notifications.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Configuración de Microsoft Edge mediante plantillas administrativas para Windows 10 y versiones más recientes<!-- 5228061 -->
En los dispositivos Windows 10 y más recientes, puede crear plantillas administrativas para configurar las opciones de directiva de grupo en Intune. En esta actualización, puede configurar las opciones que se aplican a la versión 77 y posteriores de Microsoft Edge.

Para más información sobre las plantillas administrativas, vea [Usar plantillas de Windows 10 para configurar opciones de directiva de grupo en Intune](../configuration/administrative-templates-windows.md).

Se aplica a:

- Windows 10 y versiones más recientes (Windows RS4+)

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Nuevas características para dispositivos dedicados de Android Enterprise en el modo de varias aplicaciones<!-- 3755304 3041943 3041946   -->

En Intune, puede controlar las características y las configuraciones en una experiencia de estilo de quiosco en dispositivos dedicados (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Solo el propietario del dispositivo, Restricciones de dispositivos** para el tipo de perfil).

En esta actualización, se agregan las siguientes características:

- **Dispositivos dedicados** > **Varias aplicaciones:** el **botón Inicio virtual** se puede mostrar al avanzar en el dispositivo o flotar en la pantalla para que los usuarios puedan moverla.
- **Dispositivos dedicados** > **Varias aplicaciones:** **Acceso a la linterna** permite a los usuarios usar la linterna. 
- **Dispositivos dedicados** > **Varias aplicaciones:** **Control del volumen de elementos multimedia** permite a los usuarios controlar el volumen multimedia del dispositivo con un control deslizante. 
- **Dispositivos dedicados** > **Varias aplicaciones:**  **habilite un protector de pantalla**, cargue una imagen personalizada y controle cuándo se muestra el protector.

Para ver la configuración actual, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características mediante Intune](../configuration/device-restrictions-android-for-work.md#device-experience).

Se aplica a:

- Dispositivos Android Enterprise dedicados

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Nueva aplicación y perfiles de configuración para dispositivos Android Enterprise totalmente administrados<!-- 3574215 3574238 3574235 3574232   -->
Mediante el uso de perfiles, puede configurar las opciones que aplican la configuración de VPN, correo electrónico y Wi-Fi al propietario de dispositivos (totalmente administrados) Android Enterprise. En esta actualización, puede:

- Use las [directivas de configuración de aplicaciones](../apps/app-configuration-policies-use-android.md) para implementar la configuración de correo electrónico de Outlook, Gmail y Nine Work.
- Use los perfiles de configuración de dispositivos para implementar la [configuración de certificados raíz de confianza](../protect/certificates-configure.md).
- Use los perfiles de configuración de dispositivos para implementar la configuración de [VPN](../configuration/vpn-settings-android-enterprise.md) y [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

> [!IMPORTANT]
> Con esta característica, los usuarios se autentican con su nombre de usuario y contraseña para los perfiles de VPN, Wi-Fi y correo electrónico. Actualmente, la autenticación basada en certificados no está disponible.

Se aplica a:  
- Propietario del dispositivo Android Enterprise (totalmente administrado)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>Control de las aplicaciones, los archivos, los documentos y las carpetas que se abren cuando los usuarios inician sesión en dispositivos macOS<!--3914202   -->
Puede habilitar y configurar características de dispositivos macOS (**Configuración del dispositivos** > **Perfiles** > **Crear perfil** > **macOS** para la plataforma >**Características del dispositivo** para el tipo de perfil). 

En esta actualización, hay una nueva configuración de elementos de inicio de sesión para controlar qué aplicaciones, archivos, documentos y carpetas se abren cuando un usuario inicia sesión en el dispositivo inscrito. 

Para ver la configuración actual, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/macos-device-features-settings.md).

Se aplica a:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Las fechas límite reemplazan la configuración del reinicio establecido de los anillos de Windows Update<!-- 4464404        -->
Para estar en consonancia con [los cambios recientes en el servicio de Windows](/windows/whats-new/whats-new-windows-10-version-1903#servicing), los anillos de actualización de Windows 10 de Intune ahora [admiten la configuración de fechas límite](../protect/windows-update-settings.md). Las *fechas límite* determinan cuándo un dispositivo instala las actualizaciones de características y seguridad.  En los dispositivos que ejecutan Windows 10 1903 o una versión posterior, las *fechas límite* sustituyen a las configuraciones del *reinicio establecido*.  En el futuro, las *fechas límite* reemplazarán también al *reinicio establecido* de las versiones anteriores de Windows 10.  

Si no se configuran las *fechas límite*, los dispositivos seguirán usando la configuración de *Reinicio establecido*, pero Intune dejará de admitir la configuración de Reinicio establecido en una actualización futura.  

Planee el uso de *fechas límite* para todos los dispositivos Windows 10. Una vez que haya establecido la configuración de las *fechas límite*, puede cambiar las configuraciones de Intune para que el *reinicio establecido* sea Sin configurar. Si se establece en Sin configurar, Intune deja de administrar esa configuración en los dispositivos, pero no quitará las últimas opciones de la configuración del dispositivo. Por lo tanto, las últimas configuraciones que se establecieron para el *reinicio establecido* permanecen activas y en uso en los dispositivos hasta que dichas configuraciones se modifican mediante un método distinto de Intune. Más adelante, cuando la versión de los dispositivos de Windows cambia o cuando la compatibilidad de Intune con las *fechas límite* se expande a la versión de Windows de los dispositivos, el dispositivo comenzará a usar la nueva configuración, que ya está en su lugar.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Compatibilidad con varias instancias de Microsoft Intune Certificate Connector<!--   4704642      -->
Intune ahora admite la instalación y el uso de varias instancias de [Microsoft Intune Certificate Connectors para operaciones PKCS](../protect/certficates-pfx-configure.md). Este cambio admite el equilibrio de carga y la alta disponibilidad del conector. Cada instancia de conector puede procesar solicitudes de certificado desde Intune.  Si un conector no está disponible, otros conectores continúan procesando las solicitudes.

Para usar varios conectores, no es necesario actualizar a la versión más reciente del software del conector.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Nuevas configuraciones y cambios en la configuración existente para restringir características en dispositivos iOS y macOS<!-- 4867699 4867709   -->
Puede crear perfiles para restringir configuraciones en dispositivos que ejecutan iOS y macOS (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** o **macOS** para el tipo de plataforma > **Restricciones de dispositivos**). En esta actualización se incluyen las características siguientes:

- En**macOS** > **Restricciones de dispositivos** > **Nube y almacenamiento** use la nueva configuración **Handoff** para impedir que los usuarios empiecen a trabajar en un dispositivo macOS y sigan trabajando en otro dispositivo macOS o iOS.

  Para ver la configuración actual, vaya a [Configuración de dispositivos macOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-macos.md).

- En **iOS** > **Restricciones de dispositivos**, hay algunos cambios:

  - **Aplicaciones integradas** > **Buscar mi iPhone (solo supervisado)** : nueva configuración que bloquea esta característica en la característica Buscar mi aplicación. 
  - **Aplicaciones integradas** > **Find My Friends (solo supervisado)** : nueva configuración que bloquea esta característica en la característica Buscar mi aplicación. 
  - **Inalámbrica** > **Modificación del estado de Wi-Fi (solo supervisado)** : nueva configuración que impide que los usuarios activen o desactiven la conexión Wi-Fi en el dispositivo.
  - **Teclado y diccionario** > **QuickPath (solo supervisado)** : nueva configuración que bloquea la característica QuickPath.
  - **Nube y almacenamiento**: **Continuación de la actividad** pasa a llamarse **Handoff**.

  Para ver la configuración actual, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md).

Se aplica a:  
- macOS 10.15 y versiones más recientes
- iOS 13 y versiones más recientes

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Algunas restricciones de dispositivos iOS no supervisadas se supervisarán solo con la versión iOS 13.0<!-- 4867809   -->
En esta actualización, algunas configuraciones se aplican a los dispositivos solo supervisados con la versión iOS 13.0. Si esta configuración se definen y asignan a dispositivos no supervisados antes de la versión de iOS 13.0, dicha configuración se seguirá aplicando a esos dispositivos no supervisados. También se aplican después de que los dispositivos se actualicen a iOS 13.0. Estas restricciones se quitan de los dispositivos no supervisados de los que se realiza una copia de seguridad y se restauran.

Estas opciones incluyen:

- Tienda de aplicaciones, presentación de documentos, juegos
  - Tienda de aplicaciones
  - Música, podcasts o contenido de noticias explícitos de iTunes
  - Incorporación de amigos a Game Center
  - Juego multijugador
- Aplicaciones integradas
  - Cámara
    - FaceTime
  - Safari
    - Autorrellenar
- Nube y almacenamiento
  - Copia de seguridad en iCloud
  - Bloquear la sincronización de documentos de iCloud
  - Bloquear la sincronización de Keychain en iCloud

Para ver la configuración actual, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md).

Se aplica a:  
- iOS 13.0 y versiones más recientes

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Estado de dispositivo mejorado para el cifrado de FileVault de macOS<!-- 4944983         -->
Hemos actualizado varios [mensajes de estado de dispositivo](../protect/encryption-monitor.md#device-encryption-status) para el cifrado de FileVault en dispositivos macOS.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Algunas configuraciones de examen del Antivirus de Windows Defender en el informe muestran un estado de error<!-- 5119229 -->
En Intune, puede crear directivas para usar el Antivirus de Windows Defender para examinar los dispositivos Windows 10 (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para la plataforma > **Restricciones del dispositivo** para el tipo de perfil > **Antivirus de Windows Defender**). Los informes **Hora a la que se realizará un examen rápido diario** y **Tipo de examen del sistema para realizar** muestran un estado de error, cuando es realmente un estado correcto. 

En esta actualización se ha corregido este comportamiento. Por lo tanto las configuraciones **Hora a la que se realizará un examen rápido diario** y **Tipo de examen del sistema para realizar** muestran un estado correcto cuando los exámenes se completan correctamente y muestran un estado de error cuando la configuración no se puede aplicar.

Para más información sobre la configuración de Windows Defender Antivirus consulte [Configuración de dispositivos con Windows 10 y versiones posteriores para permitir o restringir características mediante Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Zebra Technologies es un OEM admitido para OEMConfig en dispositivos Android Enterprise<!-- 4843713 -->
En Intune, puede crear perfiles de configuración de dispositivo y aplicar la configuración a los dispositivos Android Enterprise mediante OEMConfig (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **OEMConfig** para el tipo de perfil).

En esta actualización, Zebra Technologies es un fabricante de equipos originales (OEM) admitido para OEMConfig. Para obtener más información sobre OEMConfig, consulte [Uso y administración de dispositivos Android Enterprise con OEMConfig](../configuration/android-oem-configuration-overview.md).

Se aplica a:  
- Android Enterprise


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="default-scope-tags---3702875----"></a>Etiquetas de ámbito predeterminadas<!-- 3702875  -->
Ahora hay disponible una nueva etiqueta de ámbito predeterminada integrada. Todos los objetos de Intune no etiquetados que admiten etiquetas de ámbito se asignan automáticamente a la etiqueta de ámbito predeterminada. La etiqueta de ámbito **predeterminada** se agrega a todas las asignaciones de roles existentes para mantener la paridad con la experiencia de administración hoy en día. Si no desea que un administrador vea los objetos de Intune con la etiqueta de ámbito predeterminada, quítela de la asignación de roles. Esta característica es similar a la característica de ámbitos de seguridad de Configuration Manager. Para más información, consulte [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito para TI distribuida](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Soporte técnico del administrador de dispositivos de inscripción de Android<!-- 4869749   -->
La opción de inscripción del administrador de dispositivos Android se ha agregado a la página Inscripción de Android (**Intune** > **Inscripción de dispositivos** > **Inscripción de Android**). El administrador de dispositivos Android seguirá estando habilitado de forma predeterminada para todos los inquilinos.  Para más información, consulte [Inscripción del administrador de dispositivos Android](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Omisión de más pantallas en el Asistente de configuración <!--4877451  -->
Puede establecer perfiles de Programa de inscripción de dispositivos para omitir las siguientes pantallas del Asistente de configuración:
- Para iOS
    - Apariencia
    - Express Language (Idioma rápido)
    - Idioma preferido
    - Device to Device Migration (Migración entre dispositivos)
- Para macOS
    - Tiempo de pantalla
    - Configuración de Touch ID

Para más información sobre la personalización del Asistente de configuración, consulte [Creación de un perfil de inscripción de Apple](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) y [Creación de un perfil de inscripción de Apple para macOS](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Incorporación de una columna de usuario al proceso de carga de CSV del dispositivo AutoPilot<!-- 3823054 -->
Ahora puede agregar una columna de usuario a la carga CSV para Dispositivos Autopilot. Esto le permite asignar usuarios en masa en el momento de importar el archivo CSV. Para más información, consulte [Inscripción de dispositivos Windows en Intune con Windows Autopilot](../../autopilot/enrollment-autopilot.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>Configuración del límite de tiempo de limpieza automática de dispositivos en treinta días<!--4231059  -->
Puede establecer el límite de tiempo de limpieza automática de dispositivos en un plazo de 30 días (en lugar del límite anterior de noventa días) después del último inicio de sesión. Para ello, vaya a **Intune** > **configuración** > de**dispositivos** > **limpiar reglas**.

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Número de compilación incluido en la página Hardware del dispositivo Android<!-- 4461910   -->
Una nueva entrada en la página Hardware de cada dispositivo Android incluye el número de compilación del sistema operativo del dispositivo. Para más información, consulte [Ver detalles del dispositivo en Intune](../remote-actions/device-inventory.md).

<!-- ########################## -->
## <a name="july-2019"></a>Julio de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Notificaciones personalizadas para usuarios y grupos<!-- 16766574          -->
Envíe notificaciones de inserción personalizadas desde la aplicación del Portal de empresa a los usuarios en dispositivos iOS y Android que administra con Intune. Estas notificaciones de inserción móviles son altamente personalizables con texto libre y se pueden usar con cualquier fin. Puede dirigirlas a diferentes grupos de usuarios de su organización. Para obtener más información, consulte [Notificaciones personalizadas](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app---3041950----"></a>Aplicación de controlador de directiva de dispositivo de Google<!-- 3041950  -->
La aplicación de Pantalla principal administrada ahora proporciona acceso a la aplicación de directiva de dispositivo Android de Google. La aplicación de Pantalla principal administrada es un iniciador personalizado que se usa para dispositivos inscritos en Intune, como dispositivos dedicados de Android Enterprise (AE) que usan el modo de pantalla completa de varias aplicaciones. Puede acceder a la aplicación de directiva de dispositivo Android o guiar a los usuarios a esta aplicación, con fines de soporte técnico y depuración. Esta capacidad de inicio está disponible en el momento en que el dispositivo se inscribe y se bloquea en la Pantalla principal administrada. No se necesitan instalaciones adicionales para usar esta funcionalidad.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Configuración de protección de Outlook para dispositivos iOS y Android<!-- 3212619 -->
Ahora puede configurar los valores de configuración de protección generales de datos y aplicaciones para Outlook para iOS y Android mediante controles de administración de Intune simples sin inscripción de dispositivos. Los valores de configuración generales de aplicaciones proporcionan paridad con la configuración que pueden habilitar los administradores al administrar Outlook para iOS y Android en dispositivos inscritos. Para obtener más información sobre la configuración de Outlook, consulte [Implementación de Outlook para iOS y opciones de configuración de aplicación de Android](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).


#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Iconos Managed Home Screen y Configuración administrada<!-- 4918107 -->
El icono de la aplicación Managed Home Screen y el icono **Configuración administrada** se han actualizado. La aplicación Managed Home Screen solo la usan dispositivos inscritos en Intune, como dispositivos dedicados de Android Enterprise (AE) y que se ejecutan en modo de pantalla completa con varias aplicaciones. Para obtener más información sobre la aplicación de Pantalla principal administrada, consulte [Configuración de la aplicación Managed Home Screen de Microsoft para Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Directiva de dispositivos Android en dispositivos dedicados de Android Enterprise<!-- 4918136 -->
Puede obtener acceso a la aplicación Directiva de dispositivos Android en la pantalla de depuración de la aplicación Managed Home Screen. La aplicación Managed Home Screen solo la usan dispositivos inscritos en Intune, como dispositivos dedicados de Android Enterprise (AE) y que se ejecutan en modo de pantalla completa con varias aplicaciones. Para obtener más información, consulte [Configuración de la aplicación Managed Home Screen de Microsoft para Android Enterprise](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates---3902931---"></a>Actualizaciones del Portal de empresa de iOS<!-- 3902931 -->
El nombre de la empresa reemplazará el texto "i.manage.microsoft.com" actual en los mensajes de administración de aplicaciones iOS. Por ejemplo, los usuarios verán el nombre de la empresa en lugar de "i.manage.microsoft.com" cuando intenten instalar una aplicación iOS desde el portal de empresa o cuando permitan la administración de la aplicación. Esto se implantará para todos los clientes en los próximos días.

#### <a name="azure-ad-and-app-on-android-enterprise-devices---3574267---"></a>Azure AD y APP en dispositivos Android Enterprise<!-- 3574267 -->
Ahora, al incorporar dispositivos Android Enterprise totalmente administrados, los usuarios se registrarán en Azure Active Directory (Azure AD) durante la configuración inicial de su nuevo dispositivo o el restablecimiento de fábrica del dispositivo. Anteriormente, en el caso de un dispositivo totalmente administrado, una vez completada la configuración, el usuario tenía que iniciar manualmente la aplicación de Microsoft Intune para iniciar el registro de Azure AD. Ahora, cuando el usuario tiene acceso a la página principal del dispositivo tras la configuración inicial, el dispositivo se inscribe y registra.

Además de las actualizaciones de Azure AD, las directivas de protección de aplicaciones (APP) de Intune se admiten ahora en dispositivos Android Enterprise totalmente administrados. Esta funcionalidad estará disponible a medida que la implementemos. Para obtener más información, consulte [Incorporación de aplicaciones de Google Play administrado a dispositivos Android Enterprise con Intune](../apps/apps-add-android-for-work.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Uso de "reglas de aplicabilidad" al crear perfiles de configuración de dispositivo Windows 10 <!-- 2549910 eeready    -->

Puede crear perfiles de configuración de dispositivo Windows 10 (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **Windows 10** para la plataforma > **Reglas de aplicabilidad**). En esta actualización, puede crear una **regla de aplicabilidad** para que el perfil solo se aplique a una edición o una versión en concreto. Por ejemplo, cree un perfil que permita algunas opciones de configuración de BitLocker. Una vez que agregue el perfil, use una regla de aplicabilidad para que este solo se aplique a los dispositivos que ejecuten Windows 10 Enterprise.

Para agregar una regla de aplicabilidad, consulte [Reglas de aplicabilidad](../configuration/device-profile-create.md#applicability-rules).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Uso de tokens para agregar información específica del dispositivo en perfiles personalizados para dispositivos iOS y macOS<!-- 3330008  -->
Puede usar perfiles personalizados en dispositivos iOS y macOS para configurar opciones y características no integradas en Intune (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** o **macOS** para la plataforma > **Personalizado** para el tipo de perfil). En esta actualización, puede agregar tokens a sus archivos `.mobileconfig` para agregar información específica del dispositivo. Por ejemplo, puede agregar `Serial Number: {{serialnumber}}` a su archivo de configuración para mostrar el número de serie del dispositivo.

Para crear un perfil personalizado, consulte [Configuración personalizada de iOS](../configuration/custom-settings-ios.md) o [Configuración personalizada de macOS](../configuration/custom-settings-macos.md).

Se aplica a:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Nuevo diseñador de configuraciones al crear un perfil OEMConfig para Android Enterprise<!-- 3712769   -->
En Intune, puede crear un perfil de configuración de dispositivo que use una aplicación OEMConfig (Configuración del dispositivo > Perfiles > Crear perfil > Android Enterprise para la plataforma > OEMConfig para el tipo de perfil). Al hacerlo, se abre un editor JSON con una plantilla y valores que debe cambiar. 

Esta actualización incluye un diseñador de configuraciones con una experiencia de usuario mejorada que muestra detalles insertados en la aplicación entre los que se incluyen títulos, descripciones, etc. El editor JSON sigue estando disponible y muestra cualquier cambio que realiza en el diseñador de aplicaciones.

Para ver la configuración actual, vaya a [Uso y administración de dispositivos Android Enterprise con OEMConfig](../configuration/android-oem-configuration-overview.md).

Se aplica a: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Interfaz de usuario actualizada para configurar Windows Hello<!-- 4089576            -->
Hemos actualizado la consola donde [configura Intune para usar Windows Hello para empresas](../protect/windows-hello.md). Ya están disponibles todas las opciones de configuración en el mismo panel de la consola donde habilita compatibilidad con Windows Hello.

#### <a name="intune-powershell-sdk---4924113---"></a>SDK de PowerShell de Intune<!-- 4924113 --> 
El SDK de PowerShell de Intune, que proporciona compatibilidad con la API de Intune a través de Microsoft Graph, se ha actualizado a la versión 6.1907.1.0. Ahora, el SDK admite lo siguiente:
- Funciona con Azure Automation.
- Admite operaciones de lectura de autenticación de solo aplicación. 
- Admite nombres abreviados descriptivos como alias.
- Se ajusta a las convenciones de nomenclatura de PowerShell. De forma específica, se ha cambiado el nombre del parámetro `PSCredential` (en el cmdlet `Connect-MSGraph`) por `Credential`.
- Admite la especificación manual del valor del encabezado `Content-Type` al usar el cmdlet `Invoke-MSGraphRequest`.

Para obtener más información, consulte [SDK de PowerShell para Graph API de Microsoft Intune](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>Administración de FileVault para macOS<!--  3858502 + 4557986 + 1210104  -->
Puede usar Intune para [administrar el cifrado de claves de FileVault para dispositivos macOS](../protect/encrypt-devices.md). Para cifrar los dispositivos, debe usar un perfil de configuración de dispositivos de Endpoint Protection.

Nuestra compatibilidad con FileVault incluye el cifrado de dispositivos descifrados, la custodia de la clave de recuperación personal de un dispositivo, la rotación automática o manual de claves de cifrado personales y la recuperación de clave para sus dispositivos corporativos. Los usuarios finales también pueden utilizar el sitio web del Portal de empresa para obtener la clave de recuperación personal para sus dispositivos cifrados.

También hemos expandido el informe de cifrado para incluir [información sobre FileVault](../protect/encryption-monitor.md) con información para BitLocker, de modo que puede ver todos los detalles del cifrado del dispositivo en un solo lugar.

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nueva configuración de Office, Windows y OneDrive en las plantillas administrativas de Windows 10 <!-- 3510695 -->

Puede crear plantillas administrativas en Intune que imiten la administración de directivas de grupo locales (**Administración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y posterior** para la plataforma > **Plantilla administrativa** para el tipo de perfil).

En esta actualización se incluyen más opciones de configuración de Office, Windows y OneDrive que pueden agregar a sus plantillas. Con esta nueva configuración, ahora puede configurar más de 2500 opciones totalmente basadas en la nube.

Para obtener más información sobre esta característica, consulte [Usar plantillas de Windows 10 para configurar opciones de directiva de grupo en Intune](../configuration/administrative-templates-windows.md).

Se aplica a: Windows 10 y versiones posteriores

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Actualizaciones de las restricciones de inscripción<!-- 2871968 -->
Las restricciones de inscripción para nuevos inquilinos se han actualizado para que se permitan los perfiles de trabajo de Android Enterprise de forma predeterminada. Los inquilinos existentes no experimentarán cambio alguno. Para usar los perfiles de trabajo de Android Enterprise, aún deberá [conectar su cuenta de Intune a su cuenta de Google Play administrada](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>Actualizaciones de interfaz de usuario de las restricciones de inscripción y la inscripción de Apple<!--4089575, 4089579  -->
Los dos procesos siguientes usan una interfaz de usuario de estilo de asistente:
- Inscripción de dispositivos de Apple. Para obtener más información, consulte [Inscripción automática de dispositivos iOS con el Programa de inscripción de dispositivos de Apple](../enrollment/device-enrollment-program-enroll-ios.md).
- Creación de restricciones de inscripción. Para obtener más información, consulte [Establecer restricciones de inscripción](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509-----"></a>Control de la configuración previa de identificadores de dispositivos corporativos para dispositivos Android Q<!-- 4711509   -->
En Android Q (v10), Google no permitirá a los agentes MDM de dispositivos Android (administrador de dispositivos) administrados heredados recopilar información del identificador de dispositivo.  Intune tiene una característica que permite a los administradores de TI [configurar de forma previa una lista de números de serie del dispositivo](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) para etiquetar automáticamente estos dispositivos como propiedad corporativa. Esta característica no funcionará para los dispositivos Android Q que administre el administrador de dispositivos.  Independientemente de si se carga el número de serie o IMEI del dispositivo, siempre se considerará personal durante la inscripción de Intune.  Puede cambiar manualmente la propiedad a corporativa tras la inscripción.  Esto solo afecta a las nuevas inscripciones, no a los dispositivos inscritos existentes.  Los dispositivos Android administrados con perfiles de trabajo no se ven afectados por este cambio y continuarán funcionando como lo hacen en la actualidad.  Además, los dispositivos Android Q inscritos como administrador de dispositivos ya no podrán informar sobre el número de serie o IMEI en la consola de Intune como propiedades del dispositivo.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Los iconos han cambiado para las inscripciones de Android Enterprise (perfil de trabajo, dispositivos dedicados y dispositivos completamente administrados)<!-- 4977730 -->
Los iconos de los perfiles de inscripción de Android Enterprise han cambiado. Para ver los nuevos iconos, vaya a **Intune** > **Inscripción** > **Inscripción de Android** > busque en **Perfiles de inscripción**.

#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Cambio en la recopilación de datos de diagnóstico de Windows<!-- 4113859 -->
El valor predeterminado de la recopilación de datos de diagnóstico ha cambiado para los dispositivos con la versión 1903 de Windows 10 y posteriores. A partir de Windows 10 1903, la recopilación de datos de diagnóstico se habilita de forma predeterminada. Los datos de diagnóstico de Windows son datos técnicos vitales de dispositivos Windows sobre el dispositivo y el rendimiento de Windows y el software relacionado. Para obtener más información, consulte [Configurar los datos de diagnóstico de Windows en la organización](/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Los dispositivos Autopilot también participan en la telemetría "completa", a menos que se establezca lo contrario en el perfil de Autopilot con [System/AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>El restablecimiento de Windows Autopilot quita el usuario primario del dispositivo<!-- 4156123 -->
Al usarse el restablecimiento de Autopilot en un dispositivo, se quitará el usuario primario del dispositivo. El próximo usuario que inicie sesión tras el restablecimiento se establecerá como usuario primario. Esta característica se implantará para todos los clientes en los próximos días.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="improve-device-location---3855417----"></a>Mejora de la ubicación del dispositivo<!-- 3855417  -->
Puede acercar las coordenadas exactas de un dispositivo mediante la acción **Buscar dispositivo**. Para obtener más información sobre cómo buscar dispositivos iOS perdidos, consulte [Búsqueda de dispositivos iOS perdidos](../remote-actions/device-locate.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Seguridad de dispositivos

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Configuración avanzada del Firewall de Windows Defender (versión preliminar pública)<!--  1311949     -->  
Use Intune para administrar las [reglas de firewall personalizadas como parte de un perfil de configuración de dispositivo](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) para Endpoint Protection en Windows 10. Las reglas pueden especificar un comportamiento entrante y saliente en las aplicaciones, las direcciones de red y los puertos. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Interfaz de usuario actualizada para administrar líneas de base de seguridad<!-- 4091125     -->
Hemos actualizado la [experiencia de creación y edición](../protect/security-baselines.md#create-the-profile) en la consola de Intune para nuestras líneas de base de seguridad. Los cambios son:

Un formato de estilo de asistente que se ha comprimido en una sola hoja. en una hoja. Este nuevo diseño elimina la expansión de la hoja que requiere que los profesionales de TI exploren en profundidad varios paneles independientes.  
Ahora puede crear asignaciones como parte de la experiencia de creación y edición, en lugar de tener que volver posteriormente para asignar líneas de base. Hemos agregado un resumen de la configuración que puede ver antes de crear una nueva línea de base y al editar una existente. Al editar, en el resumen solo se muestra la lista de elementos establecidos en la primera categoría de propiedades editadas.

<!-- ########################## -->
## <a name="june-2019"></a>Junio de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Configuración del explorador que se puede vincular a datos organizativos<!-- 3145939 -->
Ahora, las directivas de protección de aplicaciones (APP) de Intune en dispositivos iOS y Android permiten transferir vínculos web Org a un explorador determinado más allá de Intune Managed Browser o Microsoft Edge.  Consulte [¿Qué son las directivas de protección de aplicaciones?](../apps/app-protection-policy.md) para obtener más información sobre APP.

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>En la página Todas las aplicaciones se identifican las aplicaciones de Microsoft Store para Empresas en línea o sin conexión<!--4089647 -->
En la página **Todas las aplicaciones** ahora se incluye el etiquetado para identificar las aplicaciones de Microsoft Store para Empresas (MSFB) como aplicaciones en línea o sin conexión. Ahora, en cada aplicación MSFB se incluye un sufijo para **En línea** o **Sin conexión**. En la página de detalles de la aplicación también se incluye información sobre **Tipo de licencia** y **Supports device context installation** (Admite la instalación de contexto de dispositivo) (solo aplicaciones con licencia sin conexión).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Aplicación del Portal de empresa en los dispositivos compartidos de Windows<!--4393553 -->
Ahora, los usuarios pueden tener acceso a la aplicación del Portal de empresa en los dispositivos compartidos de Windows. Los usuarios finales verán una etiqueta **Compartida** en el icono de dispositivo. Esto se aplica a la versión 10.3.45609.0 y posteriores de la aplicación del Portal de empresa de Windows.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Ver todas las aplicaciones instaladas desde la página web del Portal de empresa<!-- 4224326 -->
La nueva página **Aplicaciones instaladas** del sitio web del Portal de empresa muestra todas las aplicaciones administradas (requeridas y disponibles) que están instaladas en los dispositivos de un usuario. Además del tipo de asignación, los usuarios pueden ver el editor de la aplicación, la fecha de publicación y el estado de instalación actual. Si todavía no hay ninguna aplicación requerida o disponible para los usuarios, estos verán un mensaje en el que se explica que no hay ninguna aplicación de la empresa instalada. Para ver la página nueva en la Web, vaya al [sitio web del Portal de empresa](https://portal.manage.microsoft.com) y haga clic en **Aplicaciones instaladas**.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>La vista nueva permite que los usuarios de las aplicaciones vean todas las aplicaciones administradas instaladas en el dispositivo<!-- 2352913 -->  
La aplicación Portal de empresa para Windows ahora muestra todas las aplicaciones administradas (tanto las requeridas como las disponibles) que están instaladas en el dispositivo de un usuario. Los usuarios también pueden ver las instalaciones de aplicaciones intentadas y pendientes, además de sus estados actuales. Si todavía no hay ninguna aplicación requerida o disponible para los usuarios, estos verán un mensaje en el que se explica que no hay ninguna aplicación de la empresa instalada. Para ver la vista nueva, vaya al panel de navegación del Portal de empresa y seleccione **Aplicaciones** > **Aplicaciones instaladas**.

#### <a name="new-features-in-microsoft-intune-app"></a>Características nuevas de la aplicación Microsoft Intune
Hemos agregado características nuevas a la aplicación Microsoft Intune (versión preliminar) para Android. Los usuarios de dispositivos Android totalmente administrados ahora pueden:  

* Ver y administrar los dispositivos inscritos mediante la aplicación Portal de empresa de Intune o Microsoft Intune.
* Ponerse en contacto con su organización para obtener soporte técnico.
* Enviar comentarios a Microsoft.
* Consultar los términos y condiciones, si la organización los estableció.

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Aplicaciones de ejemplo nuevas que muestran la integración del SDK de Intune disponible en GitHub<!-- 2653471 -->
La cuenta de GitHub msintuneappsdk agregó aplicaciones de ejemplo nuevas para iOS (Swift), Android, Xamarin.iOS, Xamarin Forms y Xamarin.Android. Estas aplicaciones están pensadas para complementar la documentación existente y ofrecen demostraciones sobre cómo integrar el SDK de la aplicación Intune en sus propias aplicaciones móviles. Si es desarrollador de aplicaciones y necesita más orientación sobre el SDK de Intune, consulte estos ejemplos vinculados:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App): una aplicación de mensajería instantánea nativa de iOS (Swift) que usa la Biblioteca de autenticación de Azure Active Directory (ADAL) para la autenticación intermediada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App): una aplicación de listas de tareas pendientes nativa de Android que usa ADAL para la autenticación intermediada.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps): una aplicación de listas de tareas pendientes de Xamarin.Android que usa ADAL para la autenticación intermediada. Este repositorio también tiene la aplicación Xamarin.Forms.
- [Aplicación de ejemplo de Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios): una aplicación de ejemplo esencial de Xamarin.iOS.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Configuración de las extensiones de kernel en dispositivos macOS<!-- 2043024 -->
En dispositivos macOS, puede crear un perfil de configuración de dispositivos (**Configuración de dispositivo** > **Perfiles** > **Crear perfil** > elija **macOS** como plataforma). Esta actualización incluye un nuevo grupo de opciones de configuración que permite configurar y usar las extensiones de kernel en los dispositivos. Puede agregar extensiones específicas o permitir todas las extensiones de un asociado o desarrollador específico.

Para obtener más información sobre esta característica, consulte los artículos sobre [información general de las extensiones de kernel](../configuration/kernel-extensions-overview-macos.md) y la [configuración de las extensiones de kernel](../configuration/kernel-extensions-settings-macos.md).

Se aplica a: macOS 10.13.2 y versiones posteriores

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>La opción Permitir solo aplicaciones de la Tienda para dispositivos Windows 10 incluye más opciones de configuración<!-- 2697002 -->
Al crear un perfil de restricciones de dispositivos para dispositivos Windows, se puede usar la opción **Permitir solo aplicaciones de la Tienda** de modo que los usuarios solo instalen aplicaciones de la Tienda Windows (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para plataforma > **Restricciones de dispositivos** para tipo de perfil). En esta actualización, este valor se amplía para admitir más opciones.

Para ver la nueva configuración, vaya al artículo sobre la [configuración de dispositivos con Windows 10 y versiones posteriores para permitir o restringir características](../configuration/device-restrictions-windows-10.md#app-store).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Implementación de varios perfiles de dispositivo de extensiones de movilidad de Zebra en un dispositivo, el mismo grupo de usuarios o el mismo grupo de dispositivos<!-- 4089955 -->
En Intune, puede usar extensiones de movilidad (MX) de Zebra en un perfil de configuración de dispositivo para personalizar la configuración de dispositivos Zebra que no se integran en Intune. Actualmente, puede implementar un perfil en un único dispositivo. En esta actualización, puede implementar varios perfiles en:
- Mismo grupo de usuarios
- Mismo grupo de dispositivos
- Dispositivo único

En [Usar y administrar dispositivos Zebra con extensiones de movilidad de Zebra en Microsoft Intune](../configuration/android-zebra-mx-overview.md) se muestra cómo usar MX en Intune.

Se aplica a: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Algunas opciones de configuración de pantalla completa en dispositivos iOS se establecen mediante "Bloquear", en sustitución de "Permitir"<!-- 4404075  -->
Al crear un perfil de restricciones de dispositivos en dispositivos iOS (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil > **Pantalla completa**), se establecen el **Bloqueo automático**, el **Cambio de timbre**, la **Rotación de pantalla**, el **Botón de suspensión de pantalla** y los **Botones de volumen**.

En esta actualización, los valores son **Bloquear** (bloquea la característica) o **Sin configurar** (permite la característica). Para ver la configuración, vaya a [Configuración de dispositivos iOS para permitir o restringir características ](../configuration/device-restrictions-ios.md#kiosk).

Se aplica a iOS.

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Uso de Face ID para la autenticación de contraseña en dispositivos iOS<!-- 4490704 -->
Al crear un perfil de restricciones de dispositivos para dispositivos iOS, puede usar una huella digital para una contraseña. En esta actualización, la configuración de contraseña de huella digital también permite el reconocimiento facial (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil > **Contraseña**). Como resultado, han cambiado las opciones de configuración siguientes:

- **Desbloqueo con huella digital** es ahora **Desbloqueo de Touch ID y Face ID**.
- **Modificación de huella digital (solo con supervisión)** es ahora **Modificación de Touch ID y Face ID (solo con supervisión)** .

Face ID está disponible en iOS 11.0 y versiones posteriores. Para ver la configuración, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md#password).

Se aplica a iOS.

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>La restricción de características de juegos y aplicaciones de la tienda en dispositivos iOS depende ahora de la región de clasificación<!-- 4593948 -->
En dispositivos iOS, puede permitir o restringir características relacionadas con los juegos, la tienda de aplicaciones y la visualización de documentos (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil > **App Store, presentación de documentos, juegos**). También puede elegir la región de clasificación, por ejemplo, Estados Unidos.

En esta actualización, la característica **Aplicaciones** pasa a ser un elemento secundario de **Región de clasificación** y a depender de **Región de clasificación**. Para ver la configuración, vaya a [Configuración de dispositivos iOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Se aplica a iOS.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Compatibilidad de Windows Autopilot con Unión a Azure AD híbrido<!-- 4809146-->
Ahora, Windows Autopilot para los dispositivos existentes admite Unión a Azure AD híbrido (además de la compatibilidad con Unión a Azure AD existente). Se aplica a dispositivos con la versión 1809 de Windows 10 y posteriores. Para obtener más información, consulte [Windows Autopilot para dispositivos existentes](/windows/deployment/windows-autopilot/existing-devices).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Consulta del nivel de revisión de seguridad para dispositivos Android<!-- 4461911 -->
Ahora puede consultar el nivel de revisión de seguridad para dispositivos Android. Para ello, seleccione **Intune** > **Dispositivos** > **Todos los dispositivos** > seleccione un dispositivo > **Hardware**.
El nivel de revisión se muestra en la sección **Sistema operativo**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Asignación de etiquetas de ámbito a todos los dispositivos administrados de un grupo de seguridad<!-- 3173810 -->
Ahora puede asignar etiquetas de ámbito a un grupo de seguridad y todos los dispositivos del grupo de seguridad también se asociarán a esas etiquetas de ámbito. La etiqueta de ámbito también se asigna a todos los dispositivos de estos grupos. Las etiquetas de ámbito establecidas con esta característica sobrescriben a las establecidas con el flujo de etiquetas de ámbito de dispositivo actual. Para obtener más información, consulte el artículo sobre el [uso de RBAC y las etiquetas de ámbito para TI distribuida](scope-tags.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Seguridad de dispositivos

#### <a name="use-keyword-search-with-security-baselines------"></a>Uso de la búsqueda de palabras clave con Líneas de base de seguridad<!--  -->
Al crear o editar [perfiles de línea de base de seguridad](../protect/security-baselines.md#create-the-profile), puede especificar las palabras clave en la nueva barra de *búsqueda* para filtrar los grupos disponibles de opciones de configuración a aquellos que incluyen sus criterios de búsqueda.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>La característica Líneas de base de seguridad ya está disponible con carácter general<!-- 3785395 -->
La característica **Líneas de base de seguridad** está fuera de la versión preliminar y ya está disponible con carácter general (GA).  Esto significa que la característica está lista para usarse en producción. Sin embargo, las plantillas de línea de base individuales pueden permanecer en versión preliminar y se evalúan y publican con carácter general según su propia programación.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>La plantilla Línea de base de seguridad MDM ya está disponible con carácter general<!-- 3794072, 4217151,  3534649 -->
La plantilla Línea de base de seguridad MDM se ha sacado de la versión preliminar y ya está disponible con carácter general (GA). La plantilla con disponibilidad general se identifica como **Línea de base de seguridad MDM de mayo de 2019**.  Se trata de una nueva plantilla y no de una actualización de la versión preliminar.  Como nueva plantilla, deberá revisar la [configuración que contiene](../protect/security-baseline-settings-mdm.md) y, después, crear nuevos perfiles para implementar la plantilla en su dispositivo. Otras plantillas de línea de base de seguridad pueden permanecer en versión preliminar. Para ver una lista de líneas de base disponibles, consulte [Líneas de base de seguridad disponibles](../protect/security-baselines.md#available-security-baselines).  

Además de ser una nueva plantilla, *Línea de base de seguridad MDM de mayo de 2019* incluye las dos opciones de configuración que hemos anunciado recientemente en nuestro artículo En desarrollo:  
- Above Lock (Por encima de la pantalla de bloqueo): la voz activa las aplicaciones de una pantalla bloqueada  
- DeviceGuard: use la seguridad basada en la virtualización (VBS) la próxima vez que reinicie los dispositivos.  

*Línea de base de seguridad MDM de mayo de 2019* también incluye la incorporación de varias opciones de configuración nuevas, la eliminación de otras y una revisión del valor predeterminado de una configuración. Para ver una lista detallada de los cambios realizados de la versión preliminar a la disponibilidad general, consulte los **cambios en la nueva plantilla**.

#### <a name="security-baseline-versioning---3194322---"></a>Control de versiones de líneas de base de seguridad<!-- 3194322 -->
Líneas de base de seguridad para el control de versiones del soporte técnico de Intune. Con este soporte técnico, a medida que se publican nuevas versiones de cada línea de base de seguridad, puede actualizar sus perfiles de línea de base de seguridad para usar la versión de línea de base más reciente sin tener que volver a crear e implementar una nueva línea de base desde cero. Además, en la consola de Intune puede ver información sobre cada una de las líneas de base, como, por ejemplo, el número de perfiles individuales que tiene y que usan la línea de base, cuántas de las diferentes versiones de línea de base usan sus perfiles y de qué fecha data la versión más reciente de una línea de base de seguridad específica.  Para obtener más información, consulte **Líneas de base de seguridad**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>Se ha movido la opción Utilice las claves de seguridad para el inicio de sesión<!-- 4501151 -->
La opción de configuración del dispositivo para la protección de identidad llamada **Utilice las claves de seguridad para el inicio de sesión** ya no se encuentra como configuración secundaria de *Configurar Windows Hello para empresas*. Ahora se trata de una opción de nivel superior que está siempre disponible, incluso si no habilita el uso de Windows Hello para empresas. Para obtener más información, consulte [Protección de identidad](../protect/identity-protection-windows-settings.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Nuevos permisos para administradores de grupos asignados<!-- 4504437   -->
Ahora, el rol de administrador de la escuela integrado de Intune tiene permisos de creación, lectura, actualización y eliminación (CRUD) para Aplicaciones administradas. Esta actualización significa que si se le asigna como administrador de grupos en Intune for Education, ahora puede crear, ver, actualizar y eliminar el certificado push MDM de iOS, los tokens de servidor de MDM de iOS y los tokens de VPP de iOS, junto con [todos los permisos existentes que tenga](/intune-education/group-admin-delegate#group-admin-permissions). Para tomar alguna de estas medidas, vaya a **Configuración de inquilinos** > **Administración de dispositivos iOS**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Las aplicaciones pueden usar Graph API para llamar a operaciones de lectura sin credenciales de usuario<!-- 4655885 -->
Las aplicaciones pueden llamar a operaciones de lectura de Graph API de Intune con la identidad de la aplicación y sin credenciales de usuario. Para obtener más información sobre cómo obtener acceso a Microsoft Graph API para Intune, consulte [Trabajar con Intune en Microsoft Graph](/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Aplicación de etiquetas de ámbito a las aplicaciones de Microsoft Store para Empresas<!-- 4392555 -->
Ahora puede aplicar etiquetas de ámbito a las aplicaciones de Microsoft Store para Empresas. Para obtener más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en roles y de las etiquetas de ámbito para la TI distribuida](scope-tags.md).

<!-- ########################## -->
## <a name="may-2019"></a>Mayo de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Informes de aplicaciones potencialmente peligrosas en dispositivos Android<!-- 4223162 -->
Intune ahora proporciona más datos sobre informes de aplicaciones potencialmente peligrosas en dispositivos Android. 

#### <a name="windows-company-portal-app---3316993---"></a>Aplicación Portal de empresa de Windows<!-- 3316993 -->
La aplicación Portal de empresa de Windows ahora tiene una nueva página denominada **Dispositivos**. La página **Dispositivos** ahora mostrará a los usuarios finales los dispositivos inscritos. Los usuarios verán este cambio en Portal de empresa cuando usen la versión 10.3.4291.0 o una posterior. Para obtener información sobre cómo configurar Portal de empresa, vea [Configuración de la aplicación Portal de empresa de Microsoft Intune](../apps/company-portal-app.md).

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Método de autenticación de actualizaciones de directivas de Intune e instalación de aplicaciones de Portal de empresa<!-- 1927359  -->
En los dispositivos ya inscritos mediante el Asistente de configuración a través de uno de los métodos de inscripción de dispositivos corporativos de Apple, Intune ya no será compatible con Portal de empresa cuando los usuarios finales de la tienda de aplicaciones lo instalen manualmente. Este cambio solo es pertinente cuando se realiza la autenticación con el Asistente de configuración de Apple durante la inscripción. Este cambio solo afecta a los dispositivos iOS inscritos a través de:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Programa de inscripción de dispositivos (DEP) de Apple

Si los usuarios instalan la aplicación Portal de empresa desde la tienda de aplicaciones y luego intentan inscribir estos dispositivos a través de ella, recibirán un error. Se espera que estos dispositivos solo usen la aplicación Portal de empresa cuando Intune lo inserta, automáticamente, durante la inscripción. Se actualizarán los perfiles de inscripción de Intune en Azure Portal para que pueda especificar cómo los dispositivos se autentican y si reciben la aplicación Portal de empresa. Si quiere que los usuarios de dispositivos DEP tengan la aplicación Portal de empresa, deberá especificar sus preferencias en un perfil de inscripción. 

Además, se va a quitar la pantalla **Identificar el dispositivo** de la aplicación Portal de empresa de iOS. Por lo tanto, los administradores que quieren habilitar el acceso condicional o implementar aplicaciones de la empresa deben actualizar el perfil de inscripción de DEP. Este requisito solo se aplica si la inscripción de DEP se autentica con el Asistente para la configuración. En ese caso, debe insertar la aplicación Portal de empresa en el dispositivo. Para ello, elija **Intune** > **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción** > elija un token > **Perfiles** > elija un perfil > **Propiedades** > establezca **Instalar Portal de empresa** en **Sí**.

Para instalar la aplicación Portal de empresa en dispositivos DEP ya inscritos, deberá ir a Intune > Aplicaciones cliente e insertarla como una aplicación administrada con directivas de configuración de aplicación. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Configurar cómo los usuarios finales actualizan una aplicación de línea de negocio (LOB) con una directiva de protección de aplicaciones<!-- 3568384 -->
Ahora puede configurar dónde los usuarios finales pueden obtener una versión actualizada de una aplicación de línea de negocio (LOB). Los usuarios finales verán esta característica en el cuadro de diálogo de inicio condicional **Versión mínima de la aplicación**, que le pedirá a los usuarios finales que actualicen a una versión mínima de la aplicación de LOB. Debe proporcionar estos detalles de actualización como parte de la directiva de protección de aplicaciones (APP) de LOB. Esta característica está disponible en iOS y en Android. En iOS, esta característica requiere que la aplicación esté integrada (o encapsulada con la herramienta de encapsulado) con el SDK de Intune para iOS v. 10.0.7 o superior. En Android, esta característica requeriría la versión más reciente de la aplicación Portal de empresa. Para configurar cómo un usuario final actualiza una aplicación de LOB, la aplicación necesita que se le envíe una directiva de configuración de aplicación administrada con la clave `com.microsoft.intune.myappstore`. El valor enviado definirá desde qué tienda descargará la aplicación el usuario final. Si la aplicación se implementa a través de Portal de empresa, el valor debe ser `CompanyPortal`. En el caso de cualquier otra tienda, debe escribir una dirección URL completa.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Scripts de PowerShell de extensión de administración de Intune<!-- 3734186  -->
Puede configurar los scripts de PowerShell para que se ejecuten con los privilegios de administración del usuario en el dispositivo. Para más información, consulte [Uso de scripts de PowerShell para dispositivos Windows 10 en Intune](../apps/intune-management-extension.md) y [Administración de aplicaciones Win32](../apps/app-management.md).

#### <a name="android-enterprise-app-management---4459905---"></a>Administración de aplicaciones de Android Enterprise<!-- 4459905 -->
Para facilitar a los administradores de TI la configuración y el uso de la administración de Android Enterprise, Intune agregará automáticamente cuatro aplicaciones comunes relacionadas con Android Enterprise a la consola de administración de Intune. Las cuatro aplicaciones de Android Enterprise son las siguientes:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : se usa para escenarios totalmente administrados de Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : ayuda a iniciar sesión en las cuentas si se usa la verificación de dos fases.
- **[Portal de empresa de Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : se usa para las directivas de protección de aplicación y escenarios de perfil de trabajo de Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): se usa para los escenarios de pantalla completa o dedicados de Android Enterprise.

Anteriormente, los administradores de TI tenían que buscar y aprobar manualmente estas aplicaciones en la [Tienda de Google Play administrada](https://play.google.com/store/apps) como parte de la configuración. Este cambio elimina los pasos que antes eran manuales para facilitar y agilizar el uso de la administración de Android Enterprise por parte de los clientes.

Los administradores verán que estas cuatro aplicaciones se agregan automáticamente a la lista de aplicaciones de Intune en el momento en que conecten por primera vez a su inquilino de Intune con Google Play administrado. Para más información, consulte [Conexión de una cuenta de Intune a una cuenta de Google Play administrado](../enrollment/connect-intune-android-enterprise.md). Para los inquilinos que ya han conectado a su inquilino o que ya utilizan Android Enterprise, no hay nada que los administradores tengan que hacer. Estas cuatro aplicaciones aparecerán automáticamente dentro de los siete días siguientes a la finalización de la implementación del servicio en mayo de 2019.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Conector de certificados PFX actualizado para Microsoft Intune<!-- 1533038 -->
Hemos publicado una actualización del [Conector de certificado PFX para Microsoft Intune](../protect/certificate-connectors.md#whats-new-for-connectors) que resuelve un problema por el que los certificados PFX existentes se siguen reprocesando, lo que provoca que el conector deje de procesar nuevas solicitudes.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Tareas de seguridad de Intune para ATP de Defender (en versión preliminar pública)<!-- 3208597 -->
En la versión preliminar pública, puede usar Intune para administrar las [tareas de seguridad para Protección contra amenazas avanzada (ATP) de Microsoft Defender](../protect/atp-manage-vulnerabilities.md). Esta integración con ATP agrega un enfoque basado en riesgos para detectar vulnerabilidades y errores de configuración de puntos de conexión, establecer su prioridad y corregirlos, a la vez que reduce el tiempo entre la detección y la mitigación.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Buscar un conjunto de chips TPM en una directiva de cumplimiento de dispositivos Windows 10<!-- 3617671   -->
Muchos dispositivos Windows 10 y posteriores tienen conjuntos de chips del Módulo de plataforma segura (TPM). Esta actualización incluye una nueva configuración de cumplimiento que comprueba la versión del chip TPM en el dispositivo.

[La configuración de directivas de cumplimiento de Windows 10 y versiones posteriores](../protect/compliance-policy-create-windows.md#device-security) describe esta configuración.

Se aplica a: Windows 10 y versiones posteriores

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Impedir que los usuarios finales modifiquen su punto de acceso personal y deshabilitar el registro del servidor Siri en dispositivos iOS<!-- 4097904   -->  
Crear un perfil de restricciones de dispositivo en el dispositivo iOS (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para la plataforma y **Restricciones de dispositivo** para el tipo de perfil). Esta actualización incluye nuevas opciones que puede configurar:

- **Aplicaciones integradas**: registro del servidor para los comandos de Siri
- **Inalámbrica**: modificación por el usuario del punto de acceso personal (solo con supervisión)

Para ver esta configuración, vaya a la [configuración de aplicaciones integradas para iOS](../configuration/device-restrictions-ios.md#built-in-apps) y [configuración inalámbrica para iOS](../configuration/device-restrictions-ios.md#wireless).

Se aplica a iOS 12.2 y versiones más recientes.

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Nueva configuración de restricción de dispositivos de aplicaciones en el aula para dispositivos macOS<!-- 4097905   --> 
Puede crear un perfil de configuración de dispositivos para dispositivos MacOS (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **macOS** como plataforma >**Restricciones del dispositivo** para tipo de perfil). Esta actualización incluye una nueva configuración de aplicaciones en el aula, la opción para bloquear capturas de pantalla y la opción para deshabilitar la Fototeca de iCloud.

Para ver la configuración actual, vaya a [Configuración de dispositivos macOS para permitir o restringir características mediante Intune](../configuration/device-restrictions-macos.md).

Se aplica a: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Se cambia el nombre de la configuración Contraseña para acceder a la tienda de aplicaciones de iOS<!-- 4557891  -->
El nombre de la configuración **Contraseña para acceder a la tienda de aplicaciones** se cambia a **Require iTunes Store password for all purchases** (Requerir contraseña de iTunes Store para todas las compras) (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **iOS** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil > **Tienda de aplicaciones, presentación de documentos y juegos**).

Para ver la configuración disponible, vaya a [Tienda de aplicaciones, presentación de documentos, juegos de iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Se aplica a iOS.

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Línea de base de Protección contra amenazas avanzada de Microsoft Defender (versión preliminar)<!--  3754134 -->
Agregamos una versión preliminar de línea de base de seguridad para la configuración [Protección contra amenazas avanzada de Microsoft Defender](../protect/security-baseline-settings-defender-atp.md). Esta línea de base está disponible cuando el entorno cumple con los requisitos previos para usar [Protección contra amenazas avanzada de Windows Defender](../protect/advanced-threat-protection.md#prerequisites).

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Configuración de biometría y firma de Outlook para dispositivos iOS y Android<!-- 4050557 -->
Ahora puede especificar si la firma predeterminada está habilitada en Outlook en dispositivos iOS y Android. Además, puede elegir permitir que los usuarios cambien la configuración de biometría en Outlook en iOS.

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Compatibilidad del control de acceso de red (NAC) con F5 Access para dispositivos iOS<!-- 4500808 -->
F5 ha publicado una actualización para BIG-IP 13 que permite la funcionalidad NAC para F5 Access para iOS en Intune. Para usar esta característica,:

- Actualice BIG-IP a 13.1.1.5. No se admite BIG-IP 14.
- Integre BIG-IP con Intune para NAC. Los pasos se describen en [Overview: Configuring APM for device posture checks with endpoint management systems](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html) (Información general: Configuración de APM para comprobaciones de posición del dispositivo con sistemas de administración de puntos de conexión).
- Active la opción **Habilitar el control de acceso a la red (NAC)** del perfil de VPN en Intune.

Para ver las opciones disponibles, vaya a [Configuración de VPN en dispositivos iOS](../configuration/vpn-settings-ios.md).

Se aplica a iOS.

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Conector de certificados PFX actualizado para Microsoft Intune<!-- doc-vso 1521237  -->  
Se ha publicado una actualización para el [Conector de certificados PFX para Microsoft Intune](../protect/certificate-connectors.md#whats-new-for-connectors) que reduce el intervalo de sondeo de 5 minutos a 30 segundos.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Nombre del atributo OrderID del dispositivo de Autopilot cambiado a Etiqueta de grupo <!-- 4659453 -->

Para hacer que sea más intuitivo, el nombre del atributo **OrderID** en los dispositivos de Autopilot se ha cambiado a **Etiqueta de grupo**. Al usar archivos CSV para cargar información de dispositivos de Autopilot, debe usar Etiqueta de grupo como encabezado de columna, en lugar de OrderID.  

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>La página Estado de inscripción (ESP) de Windows ya está disponible con carácter general<!-- 3605348 -->
La página Estado de inscripción dejó de estar en versión preliminar. Para más información, consulte [Configurar una página de estado de inscripción](../enrollment/windows-enrollment-status.md).

#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Actualización de la interfaz de usuario de Intune: creación de un perfil de inscripción de Autopilot<!-- 4593669 -->
La interfaz de usuario para crear un perfil de inscripción de Autopilot se actualizó para alinearla con los estilos de interfaz de usuario de Azure. Para obtener más información, consulte cómo [crear un perfil de inscripción de Autopilot](../../autopilot/enrollment-autopilot.md#create-an-autopilot-deployment-profile). Más adelante, se actualizarán más escenarios de Intune a este nuevo estilo de interfaz de usuario.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Habilitar Restablecimiento de Autopilot para todos los dispositivos Windows<!-- 4225665 -->
Restablecimiento de Autopilot ahora funciona para todos los dispositivos Windows, incluso para los que no están configurados para usar la página Estado de inscripción. Si no se configuró una página de estado de inscripción para el dispositivo durante la inscripción de dispositivo inicial, el dispositivo irá directamente al escritorio después de iniciar sesión. Puede tardar hasta ocho horas en sincronizar y aparecer como compatible en Intune. Para más información, consulte el artículo sobre cómo [restablecer dispositivos con Restablecimiento de Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>No se requiere un formato IMEI exacto al buscar en todos los dispositivos<!--30407680 -->
No será necesario que incluya espacios en los números IMEI cuando busca en **Todos los dispositivos**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Reflejo de la eliminación de un dispositivo del portal de Apple en el portal de Intune<!--2489996 -->
Si se elimina un dispositivo de los portales del Programa de inscripción de dispositivos de Apple o de Apple Business Manager, el dispositivo se eliminará automáticamente de Intune durante la siguiente sincronización.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>La página de estado de inscripción ahora realiza un seguimiento de las aplicaciones de Win32<!-- 2714451 -->
Esto solo se aplica a dispositivos que ejecutan Windows 10 versión 1903 y posteriores. Para más información, consulte [Configurar una página de estado de inscripción](../enrollment/windows-enrollment-status.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Restablecimiento y borrado de dispositivos de forma masiva mediante Graph API<!-- 3295288 -->
Ahora podrá restablecer y borrar hasta 100 dispositivos de forma masiva mediante Graph API.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>El informe de cifrado dejó de estar en versión preliminar pública<!-- 4587546      -->
El [informe sobre BitLocker y el cifrado de dispositivo](../protect/encryption-monitor.md) está disponible con carácter general y ya no forma parte de la versión preliminar pública.


<!-- ########################## -->
## <a name="april-2019"></a>Abril de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones
#### <a name="user-experience-update-for-the-company-portal-app-for-ios---2536024---"></a>Actualización de la experiencia de usuario para la aplicación Portal de empresa para iOS<!-- 2536024 -->
Se ha rediseñado la página principal de la aplicación Portal de empresa para dispositivos iOS. Con este cambio, la página principal seguirá mejor los patrones de la interfaz de usuario de iOS y ofrecerá una función de detección mejorada para aplicaciones y libros electrónicos.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users--3448635---"></a>Cambios en la inscripción del Portal de empresa para los usuarios de dispositivos iOS 12<!--3448635 -->
Se han actualizado los pasos y las pantallas de inscripción del Portal de empresa para iOS con el fin de ajustarlos a los cambios en la inscripción de MDM que se introdujeron en Apple iOS 12.2. En el nuevo flujo de trabajo, se pide a los usuarios que hagan esto:  

* Permitir que Safari abra el sitio web del Portal de empresa y descargue el perfil de administración antes de volver a la aplicación Portal de empresa.  
* Abrir la aplicación Ajustes para instalar el perfil de administración en el dispositivo.
* Volver a la aplicación Portal de empresa para completar la inscripción.  

Para conocer los pasos y las pantallas de inscripción actualizados, vea [Enroll iOS device in Intune](../user-help/enroll-your-device-in-intune-ios.md) (Inscripción de dispositivos iOS en Intune).

#### <a name="openssl-encryption-for-android-app-protection-policies---3747362---"></a>Cifrado de OpenSSL para las directivas de protección de aplicaciones Android<!-- 3747362 -->
Las directivas de protección de aplicaciones (APP) de Intune en dispositivos Android ahora usan una biblioteca de cifrado de OpenSSL que es compatible con FIPS 140-2. Para más información, vea la sección sobre [cifrado](../apps/app-protection-policy-settings-android.md#encryption) de [Configuración de directivas de protección de aplicaciones Android en Microsoft Intune](../apps/app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies---2617348----"></a>Habilitar dependencias de la aplicación Win32<!-- 2617348  -->
Como administrador, puede exigir que otras aplicaciones se instalen como dependencias antes de instalar la aplicación Win32. En concreto, el dispositivo debe instalar las aplicaciones dependientes antes de que se instale la aplicación Win32. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar** para mostrar la hoja **Agregar aplicación**. Seleccione **Aplicación de Windows (Win32)** como **Tipo de aplicación**. Después de agregar la aplicación, puede seleccionar **Dependencias** para agregar las aplicaciones dependientes que se deben instalar antes de poder instalar la aplicación Win32. Para más información, vea [Intune independiente: administración de aplicaciones Win32](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps---3537391-----"></a>Información de instalación de la versión para aplicaciones de Microsoft Store para Empresas<!-- 3537391   -->
Los informes de instalación de aplicaciones incluyen información de la versión de la aplicación para aplicaciones de Microsoft Store para Empresas. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones**. Elija una **Aplicación de Microsoft Store para Empresas** y luego seleccione **Estado de instalación del dispositivo** en la sección **Supervisión**.

#### <a name="additions-to-win32-apps-requirement-rules---3676883-----"></a>Adiciones a las reglas de requisitos de las aplicaciones Win32<!-- 3676883   -->
Puede crear reglas de requisitos basadas en los scripts de PowerShell, los valores del Registro y la información del sistema de archivos. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. Después, seleccione **Aplicación de Windows (Win32)** como **Tipo de aplicación** en la hoja **Agregar aplicación**.  Seleccione **Requisitos** > **Agregar** para configurar más reglas de requisitos. Después, seleccione **Tipo de archivo**, **Registro** o **Script** como **Tipo de requisito**. Para más información, vea [Administración de aplicaciones Win32](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices---3695227----"></a>Configurar las aplicaciones Win32 para instalarlas en dispositivos unidos a Azure AD inscritos en Intune<!-- 3695227  -->
Puede asignar las aplicaciones Win32 para instalarlas en dispositivos unidos a Azure AD inscritos en Intune. Para más información sobre las aplicaciones Win32 en Intune, vea [Administración de aplicaciones Win32](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user--3794259----"></a>Usuario primario mostrado en Resumen del dispositivo<!--3794259  -->
La página Resumen del dispositivo mostrará el usuario primario, también denominado el usuario de afinidad de dispositivo de usuario (UDA). Para ver el usuario primario de un dispositivo, seleccione **Intune** > **Dispositivos** > **Todos los dispositivos** y elija un dispositivo. El usuario primario se muestra cerca de la parte superior de la página **Resumen**.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices---4105925----"></a>Otros informes de aplicaciones de Google Play administrado para dispositivos de perfil de trabajo de Android Enterprise<!-- 4105925  -->
Para aplicaciones de Google Play administrado implementadas en dispositivos de perfil de trabajo de Android Enterprise, puede ver el número de versión específica de la aplicación instalada en un dispositivo. Esto se aplica solo a las aplicaciones necesarias.  

#### <a name="ios-third-party-keyboards---4111843-----"></a>Teclados de terceros de iOS<!-- 4111843   -->
La compatibilidad de la directiva de protección de aplicaciones (APP) de Intune con la configuración **Teclados de terceros** para iOS ya no se admite debido a un cambio de la plataforma iOS. No podrá configurar esta opción en la consola de administración de Intune y no se aplicará en el cliente en el SDK de aplicaciones de Intune.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="updated-certificate-connectors---icm-113304612---"></a>Conectores de certificado actualizados<!-- ICM 113304612 -->
Se han publicado actualizaciones para [Intune Certificate Connector y el conector de certificados PFX para Microsoft Intune](../protect/certificate-connectors.md#whats-new-for-connectors). Las nuevas versiones corrigen varios problemas conocidos.

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices---1210083----"></a>Establecer configuración de inicio de sesión y opciones de reinicio de control en dispositivos macOS<!-- 1210083  -->
En dispositivos macOS, puede crear un perfil de configuración de dispositivos (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > elija **macOS** como plataforma > **Características del dispositivo** para tipo de perfil). Esta actualización incluye una nueva configuración de la ventana de inicio de sesión, como mostrar un encabezado personalizado, elegir cómo inician sesión los usuarios, mostrar u ocultar la configuración de energía y mucho más.

Para ver esta configuración, vaya a [macOS device feature settings](../configuration/macos-device-features-settings.md) (Configuración de características de dispositivos macOS).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode--3041940----"></a>Configurar Wi-Fi en Android Enterprise para dispositivos dedicados de propietario del dispositivo que se ejecutan en pantalla completa con varias aplicaciones<!--3041940  -->
Puede habilitar la configuración de propietario del dispositivo en Android Enterprise cuando se ejecuta como un dispositivo dedicado en pantalla completa con varias aplicaciones. En esta actualización, puede permitir que los usuarios configuren y se conecten a Wi-Fi (**Intune** > **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Solo el propietario del dispositivo, Restricciones de dispositivo** para el tipo de perfil >  **Dispositivos dedicados** > **Pantalla completa**: **Varias aplicaciones** > **Configuración de Wi-Fi**).

Para ver todos los valores que puede configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características](../configuration/device-restrictions-android-for-work.md).

Se aplica a: Dispositivos dedicados de Android Enterprise que se ejecutan en pantalla completa con varias aplicaciones

#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041941----"></a>Configurar Bluetooth y emparejamiento en Android Enterprise para dispositivos dedicados de propietario del dispositivo que se ejecutan en pantalla completa con varias aplicaciones<!-- 3041941  -->
Puede habilitar la configuración de propietario del dispositivo en Android Enterprise cuando se ejecuta como un dispositivo dedicado en pantalla completa con varias aplicaciones. En esta actualización, puede permitir que los usuarios finales habiliten Bluetooth y emparejen sus dispositivos mediante Bluetooth (**Intune** > **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Solo el propietario del dispositivo, Restricciones de dispositivo** para el tipo de perfil >  **Dispositivos dedicados** > **Pantalla completa**: **Varias aplicaciones** > **Configuración de Bluetooth**).

Para ver todos los valores que puede configurar, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características](../configuration/device-restrictions-android-for-work.md).

Se aplica a: Dispositivos dedicados de Android Enterprise que se ejecutan en pantalla completa con varias aplicaciones

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune---3305883----"></a>Crear y usar perfiles de configuración de dispositivos OEMConfig en Intune<!-- 3305883  -->
En esta actualización, Intune admite la configuración de dispositivos Android Enterprise con OEMConfig. En concreto, puede crear un perfil de configuración de dispositivo y aplicar la configuración a los dispositivos Android Enterprise mediante OEMConfig (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma).

Actualmente, la compatibilidad con fabricantes de equipos originales depende del fabricante. Si quiere una aplicación OEMConfig que no está disponible en la lista de aplicaciones OEMConfig, póngase en contacto con `IntuneOEMConfig@microsoft.com`.

Para más información sobre esta característica, vaya a [Use and manage Android Enterprise devices with OEMConfig in Microsoft Intune](../configuration/android-oem-configuration-overview.md) (Uso y administración de dispositivos Android Enterprise con OEMConfig en Microsoft Intune).

Se aplica a: Android Enterprise

#### <a name="windows-update-notifications---3316758-3316782----"></a>Notificaciones de Windows Update<!-- 3316758, 3316782  -->
Se han agregado dos valores de *Configuración de la experiencia de usuario* a las configuraciones de anillo de Windows Update que puede administrar desde la consola de Intune. Ahora puede:
- Bloquear o permitir que los usuarios [busquen actualizaciones de Windows](../protect/windows-update-settings.md).
- Administrar el [nivel de notificación de Windows Update](../protect/windows-update-settings.md) que los usuarios pueden ver.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner---3574254----"></a>Nueva configuración de restricción de dispositivos para Propietario del dispositivo en Android Enterprise<!-- 3574254  -->
En dispositivos Android Enterprise, puede crear un perfil de restricción de dispositivos para permitir o restringir características, establecer reglas de contraseña y mucho más (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > elija **Android Enterprise** para plataforma > **Solo el propietario del dispositivo > Restricciones de dispositivos** para el tipo de perfil). 

Esta actualización incluye nuevas opciones de contraseña, permite el acceso completo a las aplicaciones en Google Play Store para dispositivos totalmente administrados y mucho más. Para ver la lista actual de configuraciones, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características](../configuration/device-restrictions-android-for-work.md). 

Se aplica a: Dispositivos totalmente administrados de Android Enterprise

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671---"></a>Buscar un conjunto de chips TPM en una directiva de cumplimiento de dispositivos Windows 10<!-- 3617671 -->

El lanzamiento de esta característica se ha retrasado y está previsto que sea más adelante.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices---3775833-----"></a>Cambios de la interfaz de usuario actualizada para el explorador Microsoft Edge en dispositivos con Windows 10 y versiones posteriores<!-- 3775833   -->
Cuando se crea un perfil de configuración de dispositivo, puede permitir o restringir las características de Microsoft Edge en dispositivos con Windows 10 y versiones posteriores (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil > **Explorador Microsoft Edge**). En esta actualización, la configuración de Microsoft Edge es más descriptiva y fácil de entender.

Para ver estas características, vaya a [Configuración de restricción de dispositivos del explorador Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-----3903241-3903244-3903246-----"></a>Compatibilidad ampliada para dispositivos totalmente administrados de Android Enterprise (versión preliminar)<!--   3903241, 3903244, 3903246   -->
Aún en versión preliminar pública, hemos ampliado la compatibilidad de dispositivos totalmente administrados de Android Enterprise. Se anunció por primera vez en enero de 2019 para incluir lo siguiente:

- En dispositivos totalmente administrados y dedicados, puede crear [directivas de cumplimiento](../protect/compliance-policy-create-android-for-work.md) para incluir las reglas de contraseña y requisitos del sistema operativo (**Cumplimiento del dispositivo** > **Directivas** > **Crear directiva** > **Android Enterprise** para plataforma > **Propietario del dispositivo** para tipo de perfil).

  En dispositivos dedicados, el dispositivo puede aparecer como **No compatible**. El acceso condicional no está disponible en dispositivos dedicados. Asegúrese de completar las tareas o acciones para obtener dispositivos dedicados compatibles con las directivas asignadas.

- [Acceso condicional](../protect/conditional-access.md): las directivas de acceso condicional que se aplican a Android también se aplican a dispositivos totalmente administrados de Android Enterprise. Los usuarios ahora pueden registrar su dispositivo totalmente administrado en Azure Active Directory mediante la **aplicación Microsoft Intune**. Después, pueden ver y resolver los problemas de cumplimiento para acceder a recursos de la organización.

- Nueva aplicación de usuario final (aplicación Microsoft Intune): hay una nueva aplicación de usuario final para dispositivos Android totalmente administrados denominada **Microsoft Intune**. Esta nueva aplicación, ligera y moderna, ofrece funciones similares a las de la aplicación Portal de empresa, pero para dispositivos totalmente administrados. Para más información, vea la [aplicación Microsoft Intune en Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Para configurar dispositivos Android totalmente administrados, vaya a **Dispositivo administrado** > **Inscripción de Android** > **Corporate-owned, fully managed user devices** (Dispositivos de usuario totalmente administrados de propiedad corporativa). La compatibilidad con dispositivos Android totalmente administrados sigue en versión preliminar y algunas características de Intune podrían no ser totalmente funcionales.  

Para más información sobre esta versión preliminar, lea nuestro blog [Microsoft Intune - Versión preliminar 2 para dispositivos totalmente administrados de Android Enterprise](https://aka.ms/preview2_AE_fullymanaged).

#### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Usar el Administrador de cumplimiento para crear evaluaciones para Microsoft Intune<!-- 4404750 -->

El [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) (abre otro sitio de Microsoft) es una herramienta de evaluación de riesgos según el flujo de trabajo que se encuentra en el Portal de confianza de servicios de Microsoft. Permite asignar y comprobar las actividades de cumplimiento normativo de la organización relacionadas con los servicios de Microsoft, y realizar un seguimiento de dichas actividades. Puede crear su propia evaluación de cumplimiento con Microsoft 365, Azure, Dynamics, Servicios profesionales e Intune. Intune tiene dos evaluaciones disponibles: FFIEC y RGPD.

Con el Administrador de cumplimiento es más fácil centrarse en las actividades, ya que divide los controles en controles administrados por Microsoft y controles administrados por la organización. Permite completar las evaluaciones y, después, exportarlas e imprimirlas.

El cumplimiento normativo del [Consejo federal de examen de instituciones financieras (FFIEC, del inglés Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (abre otro sitio de Microsoft) es un conjunto de estándares para la banca electrónica emitido por el FFIEC. Es la evaluación para instituciones financieras más solicitada que se usa en Intune. Interpreta cómo Intune le permite cumplir las directrices de ciberseguridad del FFIEC relacionadas con cargas de trabajo en la nube pública. La evaluación del FFIEC de Intune es la segunda evaluación del FFIEC en el Administrador de cumplimiento.

En este ejemplo puede ver el desglose de los controles del FFIEC. Microsoft abarca 64 controles. El usuario se encarga de los 12 controles restantes.

![Vea un ejemplo de la evaluación de Intune para el FFIEC, incluidas las acciones de cliente y las acciones de Microsoft.](./media/whats-new/intune-ffiec-assessment-status.png)

El [Reglamento general de protección de datos (RGPD)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (abre otro sitio de Microsoft) es una ley de la Unión Europea (UE) que permite proteger los derechos de los usuarios y sus datos. El RGPD es la evaluación más solicitada para cumplir con las normas de privacidad. 

En este ejemplo puede ver el desglose de los controles del RGPD. Microsoft abarca 49 controles. El usuario se encarga de los 66 controles restantes.

![Vea un ejemplo de la evaluación de Intune para el RGPD, incluidas las acciones de cliente y las acciones de Microsoft.](./media/whats-new/intune-assessment-status.png)


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant---2276470----"></a>Configuración del perfil para omitir algunas pantallas durante el Asistente para configuración<!-- 2276470  -->
Cuando se crea un perfil de inscripción de macOS, se puede configurar para que omita cualquiera de las siguientes pantallas cuando un usuario realiza los pasos del Asistente para configuración:
- Aspecto
- Tono de visualización
- iCloudStorage: si crea un nuevo perfil o edita uno, las pantallas de omisión seleccionadas deben sincronizarse con el servidor MDM de Apple.  Los usuarios pueden emitir una sincronización manual de los dispositivos para que no haya ningún retraso en la recogida de los cambios de perfil.
Para más información, consulte el artículo [Inscripción automática de dispositivos macOS con el Programa de inscripción de dispositivos o Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Asignar nombres en masa a dispositivos al inscribir dispositivos iOS corporativos<!--3566569  -->
Al usar uno de los métodos de inscripción corporativa de Apple (DEP/ABN/ASM), puede establecer un formato de nombre de dispositivo para que asigne un nombre automáticamente a los dispositivos iOS entrantes. Puede especificar un formato que incluya el tipo de dispositivo y el número de serie en la plantilla. Para hacerlo, elija **Intune** > **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción** > **Seleccione un token** >**Crear perfil** > **Formato de nomenclatura de dispositivo**. Puede editar los perfiles existentes, pero el nombre se aplicará solamente a los dispositivos que acaba de sincronizar.

#### <a name="updated-default-timeout-message-on-enrollment-status-page---3959331---"></a>Actualizado el mensaje de tiempo de espera predeterminado en la página de estado de inscripción<!-- 3959331 -->
Hemos actualizado el mensaje de tiempo de espera predeterminado que se muestra a los usuarios cuando la página de estado de inscripción (ESP) supera el valor de tiempo de espera especificado en el perfil de ESP. El nuevo mensaje predeterminado es lo que los usuarios ven y les permite comprender las siguientes acciones que deben realizar con su implementación de ESP.  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="retire-noncompliant-devices---1827291-----"></a>Retirar dispositivos no compatibles<!-- 1827291   -->
Esta característica se ha retrasado y se incluirá en una versión futura.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta---4403765---"></a>Cambios de Intune Data Warehouse V1.0 reflejados hasta la versión beta<!-- 4403765 -->
Cuando V1.0 apareció por primera vez en agosto de 2018, difería en algunos aspectos importantes de la versión beta de API. En marzo de 2019 esos cambios se reflejan en la versión beta de la API. Si tiene informes importantes que usan la versión beta de API, se recomienda encarecidamente cambiar dichos informes a V1.0 para evitar cambios bruscos. Para más información, vea [Registro de cambios en la API Almacenamiento de datos de Intune](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Supervisar el estado de las líneas bases de seguridad (versión preliminar) <!-- 3082047 --> 
Hemos agregado una [vista por categorías](../protect/security-baselines-monitor.md) para la supervisión de las líneas bases de seguridad. (Las líneas base de seguridad siguen en versión preliminar). La vista por categorías muestra cada categoría desde la línea base junto con el porcentaje de dispositivos que pertenecen a cada grupo de estado para esa categoría. Ahora puede ver cuántos dispositivos no coinciden con las categorías individuales, están mal configurados o no son aplicables.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="scope-tags-for-apple-vpp-tokens--2371886----"></a>Etiquetas de ámbito para los tokens del Programa de compras por volumen (VPP) de Apple<!--2371886  -->
Ahora puede agregar etiquetas de ámbito a los tokens de VPP de Apple. Solo los usuarios que tienen asignada la misma etiqueta de ámbito tendrán acceso al token de VPP de Apple con esa etiqueta. Las aplicaciones y libros electrónicos de VPP comprados con ese token heredan sus etiquetas de ámbito. Para más información sobre las etiquetas de ámbito, vea [Use RBAC and scope tags](scope-tags.md) (Usar RBAC y etiquetas de ámbito).

<!-- ########################## -->
## <a name="march-2019"></a>Marzo de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones
#### <a name="deploy-microsoft-visio-and-microsoft-project---3725386----"></a>Implementar Microsoft Visio y Microsoft Project<!-- 3725386  -->
Ahora puede implementar Microsoft Visio Pro para Microsoft 365 y el cliente de escritorio de Microsoft Project Online como aplicaciones independientes para dispositivos Windows 10 con Microsoft Intune, si dispone de licencias para estas aplicaciones. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar** para mostrar la hoja **Agregar aplicación**. En la hoja **Agregar aplicación**, seleccione **Windows 10** como **Tipo de aplicación**. Después, elija **Configurar conjunto de aplicaciones** para seleccionar las aplicaciones que instalará. Para obtener más información sobre las aplicaciones de Microsoft 365 para dispositivos Windows 10, vea [Asignación de aplicaciones de Microsoft 365 a dispositivos Windows 10 con Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change---3593653----"></a>Cambio de nombre de producto de Microsoft Visio Pro para Office 365<!-- 3593653  -->
**Microsoft Visio Pro para Office 365** ahora se conocerá como **Microsoft Visio Online Plan 2**.  Para más información sobre Microsoft Visio, vea [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Para más información sobre cómo las aplicaciones de Office 365 para dispositivos Windows 10, vea [Asignación de aplicaciones de Office 365 a dispositivos Windows 10 con Microsoft Intune](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting---3291302----"></a>Configuración de límite de caracteres de la directiva de protección de aplicaciones (APP) de Intune<!-- 3291302  -->
Los administradores de Intune pueden especificar una excepción en la configuración de la directiva **Restringir cortar, copiar y pegar con otras aplicaciones** de la APP de Intune.  También pueden especificar el número de caracteres que se pueden cortar o copiar de una aplicación administrada. Esto permitirá compartir el número especificado de caracteres en cualquier aplicación, independientemente de la opción "Restringir cortar, copiar y pegar con otras aplicaciones". Tenga en cuenta que para la aplicación Portal de empresa de Intune para Android se necesita la versión 5.0.4364.0 o posterior. Para más información, vea [Configuración de directivas de protección de aplicaciones de iOS](../apps/app-protection-policy-settings-ios.md#data-protection), [Configuración de directivas de protección de aplicaciones Android en Microsoft Intune](../apps/app-protection-policy-settings-android.md#data-protection) y [Revisión de los registros de protección de aplicaciones cliente](../apps/app-protection-policy-settings-log.md).

#### <a name="office-deployment-tool-odt-xml-for-microsoft-365-apps-for-enterprise-deployment---3192477-----"></a>XML de la Herramienta de implementación de Office (ODT) para Aplicaciones de Microsoft 365 para el desarrollo empresarial<!-- 3192477   -->
Será capaz de proporcionar el XML de la Herramienta de implementación de Office (ODT) al crear una instancia de Aplicaciones de Microsoft 365 para el desarrollo empresarial en la consola de administración de Intune. Esto permite mayor capacidad de personalización si las opciones actuales de la interfaz de usuario de Intune no satisfacen sus necesidades. Para obtener más información, vea [Asignación de aplicaciones de Microsoft 365 a dispositivos Windows 10 con Microsoft Intune](../apps/apps-add-office365.md) y [Opciones de configuración de la Herramienta de implementación de Office](/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background---1429026----"></a>Los iconos de aplicación se mostrarán con un fondo generado automáticamente<!-- 1429026  -->
En la aplicación Portal de empresa, ahora los iconos de aplicación se muestran con un fondo generado automáticamente según el color dominante del icono (si se puede detectar). Si procede, este fondo reemplaza el borde gris que antes se veía en los iconos de aplicación. Los usuarios verán este cambio en las versiones posteriores de Portal de empresa posteriores a 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment---2751523-----"></a>Instalar aplicaciones disponibles mediante la aplicación Portal de empresa después de la inscripción masiva de dispositivos Windows<!-- 2751523   -->
Los dispositivos Windows inscritos en Intune mediante [Inscripción masiva de Windows](../enrollment/windows-bulk-enroll.md) (paquetes de aprovisionamiento) podrán usar la aplicación Portal de empresa para instalar aplicaciones disponibles. Para más información sobre cómo configurar la aplicación Portal de empresa, vea [Adición manual de la aplicación Portal de empresa para Windows 10 con Microsoft Intune](../apps/store-apps-company-portal-app.md) y [Configuración de la aplicación Portal de empresa de Microsoft Intune](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite---3828932----"></a>Posibilidad de seleccionar la aplicación Microsoft Teams como parte del conjunto de aplicaciones de Office<!-- 3828932  -->
La aplicación Microsoft Teams se puede incluir o excluir como parte de la instalación del conjunto de Aplicaciones de Microsoft 365 para la implementación empresarial. Esta característica funciona para las Aplicaciones de Microsoft 365 para la implementación empresarial con el número de compilación 16.0.11328.20116+. El usuario debe cerrar sesión y después iniciar sesión en el dispositivo para que se complete la instalación. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. Seleccione uno de los tipos de aplicación del **Conjunto de aplicaciones Office 365** y elija **Configurar conjunto de aplicaciones**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices---2351390---"></a>Iniciar automáticamente una aplicación cuando se ejecutan varias aplicaciones en modo de pantalla completa en dispositivos con Windows 10 y versiones posteriores<!-- 2351390 -->

En dispositivos con Windows 10 y versiones posteriores, puede ejecutar un dispositivo en modo de pantalla completa y ejecutar muchas aplicaciones. En esta actualización, hay un valor **Ejecución automática** configuración (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para plataforma > **Pantalla completa** para el tipo de perfil > **Pantalla completa con varias aplicaciones**). Con este valor se puede iniciar automáticamente una aplicación cuando el usuario inicia sesión en el dispositivo.

Para ver una lista y una descripción de todos los valores de pantalla completa, vea [Windows 10 and later device settings to run as a kiosk in Intune](../configuration/kiosk-settings-windows.md) (Configuración de dispositivos con Windows 10 y versiones posteriores para ejecutarlos en pantalla completa en Intune).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="operational-logs-also-show-details-on-non-compliant-devices---4063755----"></a>Registros operativos también muestran detalles en dispositivos no compatibles<!-- 4063755  -->
Al enrutar registros de Intune a características de supervisión de Azure, también puede enrutar los registros operativos. En esta actualización, los registros operativos también proporcionan información sobre los dispositivos no compatibles.

Para más información sobre esta característica, vea [Envío de datos de registro al almacenamiento, a Event Hubs o a Log Analytics en Intune (versión preliminar)](review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads---3804627---"></a>Enrutar registros a Azure Monitor en más cargas de trabajo de Intune<!-- 3804627 -->
En Intune, puede enrutar los registros operativos y de auditoría a centros de eventos, almacenamiento y análisis de registros en Azure Monitor (**Intune** > **Supervisión** > **Configuración de diagnósticos**). En esta actualización, puede enrutar estos registros en más cargas de trabajo de Intune, incluido el cumplimiento, las configuraciones, las aplicaciones cliente y mucho más.

Para más información sobre el enrutamiento de registros a Azure Monitor, vea [Envío de datos de registro al almacenamiento, a Event Hubs o a Log Analytics en Intune (versión preliminar)](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune---3305880-----"></a>Crear y usar extensiones de movilidad en dispositivos Android Zebra en Intune<!-- 3305880   -->
En esta actualización, Intune admite la configuración de dispositivos Android Zebra. En concreto, puede crear un perfil de configuración de dispositivo y aplicar la configuración a dispositivos Android Zebra mediante perfiles de movilidad extensiones (MX) generados por StageNow (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android** para plataforma > **Perfil de MX (solo Zebra)** para tipo de perfil).

Para más información sobre esta característica, vea [Use and manage Zebra devices with mobility extensions in Intune](../configuration/android-zebra-mx-overview.md) (Uso y administración de dispositivos Zebra con extensiones de movilidad en Intune).

Se aplica a: Android

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos
#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Informe de cifrado para dispositivos Windows 10 (en versión preliminar pública)<!-- 2351538 -->
Use la nueva opción [Informe de cifrado (vista previa)](../protect/encryption-monitor.md) para ver los detalles sobre el estado de cifrado de los dispositivos Windows 10. Entre los detalles disponibles se incluye una versión de TPM de los dispositivos, el estado y la preparación para cifrado, informes de errores y mucho más.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview---2351547-----"></a>Acceder a claves de recuperación de BitLocker desde el portal de Intune (en versión preliminar pública)<!-- 2351547   -->
Ahora puede usar Intune para [ver detalles](../protect/encryption-monitor.md) sobre el identificador de clave de BitLocker y las claves de recuperación de BitLocker, desde Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>Compatibilidad de Microsoft Edge con escenarios de Intune en dispositivos iOS y Android<!-- 3411007 -->
Microsoft Edge será compatible con los mismos escenarios de administración que Intune Managed Browser con la adición de mejoras en la experiencia del usuario final. Entre las características para empresas de Microsoft Edge que se habilitan mediante las directivas de Intune se incluyen la identidad dual, la integración de la directiva de protección de aplicaciones, la integración del proxy de aplicación de Azure, favoritos administrados y accesos directos a la página principal. Para más información, vea [Compatibilidad con Microsoft Edge](../apps/manage-microsoft-edge.md).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices--3105122----"></a>Exchange Online y Conector de Intune retiran su compatibilidad para dispositivos EAS solamente<!--3105122  -->
La consola de Intune ya no admite la visualización y la administración de dispositivos de EAS solamente conectados a Exchange Online con el Conector de Intune. Dispone de estas otras opciones:
- Inscribir dispositivos en Administración de dispositivos móviles (MDM)
- Usar las directivas de Intune App Protection para administrar los dispositivos
- Usar controles de Exchange como se describe en [Clients and mobile in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) (Clientes y dispositivos móviles en Exchange Online)

#### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name--4254930---"></a>Buscar la página Todos los dispositivos para un dispositivo concreto mediante el uso de [nombre]<!--4254930 -->
Ahora puede buscar un nombre de dispositivo exacto. Vaya a **Intune** > **Dispositivos** > **Todos los dispositivos** > en el cuadro de búsqueda, escriba el nombre de dispositivo entre {} para buscar una coincidencia exacta. Por ejemplo, **{Device12345}** .

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="support-for-additional-connectors-on-the-tenant-status-page---3617202----"></a>Compatibilidad con conectores adicionales en la página Estado del inquilino<!-- 3617202  -->
La [página Estado del inquilino](tenant-status.md) ahora muestra información de estado de los conectores adicionales, incluidos *Protección contra amenazas avanzada de Windows Defender* (ATP) y otros conectores de Mobile Threat Defense.

#### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune---4260871---"></a>Compatibilidad con la aplicación de cumplimiento de Power BI en la hoja Almacenamiento de datos en Microsoft Intune<!-- 4260871 -->
Antes, el vínculo **Descargar archivo de Power BI** en la hoja **Almacenamiento de datos de Intune** descargaba un informe de Almacenamiento de datos de Intune (archivo .pbix). Este informe se ha reemplazado por la aplicación de cumplimiento de Power BI. Para la aplicación de cumplimiento de Power BI no se necesitará ninguna configuración o carga especial. Se abrirá directamente en el portal en línea de Power BI y mostrará datos específicamente para el inquilino de Intune según sus credenciales. En Intune, seleccione el vínculo **Configurar el almacenamiento de datos de Intune**  en el lado derecho de la hoja de Intune. Después, haga clic en **Obtener aplicación de Power BI**. Para más información, vea [Connect to the Data Warehouse with Power BI](../developer/reports-proc-get-a-link-powerbi.md) (Conectarse al almacenamiento de datos con Power BI).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles---3637917----"></a>Concesión del acceso de solo lectura a Intune a algunos roles de Azure Active Directory<!-- 3637917  -->
Se ha concedido acceso de solo lectura de Intune a estos roles de Azure AD. Los permisos concedidos con roles de Azure AD sustituyen a los permisos concedidos con control de acceso basado en roles (RBAC) de Intune.

Acceso de solo lectura a los datos de auditoría de Intune:

- Administrador de cumplimiento
- Administrador de datos de cumplimiento

Acceso de solo lectura a todos los datos de Intune:

- Administrador de seguridad
- Operador de seguridad
- Lector de seguridad

Para más información, vea [Control de acceso basado en roles](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles--2934430-----"></a>Etiquetas de ámbito para perfiles de aprovisionamiento de aplicaciones iOS<!--2934430   -->
Puede agregar una etiqueta de ámbito a un perfil de aprovisionamiento de aplicaciones iOS para que solo los usuarios con roles que también tengan asignada esa etiqueta de ámbito puedan acceder al perfil de aprovisionamiento de aplicaciones iOS. Para más información, vea [Use RBAC and scope tags](scope-tags.md) (Usar RBAC y etiquetas de ámbito).

#### <a name="scope-tags-for-app-configuration-policies--2371891-----"></a>Etiquetas de ámbito para directivas de configuración de aplicaciones<!--2371891   -->
Puede agregar una etiqueta de ámbito a una directiva de configuración de aplicaciones para que solo los usuarios con roles que también tengan asignada esa etiqueta de ámbito puedan acceder a la directiva de configuración de aplicaciones. La directiva de configuración de aplicaciones solo puede asociarse a aplicaciones que tengan asignada la misma etiqueta de ámbito. Para más información, vea [Use RBAC and scope tags](scope-tags.md) (Usar RBAC y etiquetas de ámbito).

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>Compatibilidad de Microsoft Edge con escenarios de Intune en dispositivos iOS y Android<!-- 3411007 -->
Microsoft Edge será compatible con los mismos escenarios de administración que Intune Managed Browser con la adición de mejoras en la experiencia del usuario final. Entre las características para empresas de Microsoft Edge que se habilitan mediante las directivas de Intune se incluyen la identidad dual, la integración de la directiva de protección de aplicaciones, la integración del proxy de aplicación de Azure, favoritos administrados y accesos directos a la página principal. Para más información, vea [Compatibilidad con Microsoft Edge](../apps/manage-microsoft-edge.md).




<!-- ########################## -->
## <a name="february-2019"></a>Febrero de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones
#### <a name="intune-macos-company-portal-dark-mode---3300524----"></a>Modo oscuro del Portal de empresa de macOS para Intune<!-- 3300524  -->
El Portal de empresa de macOS para Intune ahora admite el Modo oscuro para macOS. Cuando habilita el Modo oscuro en un dispositivo macOS 10.14 o una versión posterior, el Portal de empresa ajustará su apariencia para que los colores reflejen ese modo.

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices---2577355-----"></a>Intune aprovechará las API de Google Play Protect en dispositivos Android<!-- 2577355   -->
Algunos administradores de TI se enfrentan a un panorama BYOD donde los usuarios finales pueden acabar por obtener privilegios de usuario root o realizar jailbreaking en sus teléfonos móviles. Este comportamiento, aunque en ocasiones no sea malintencionado, tiene como resultado la omisión de muchas directivas de Intune que se establecen con el fin de proteger los datos de la organización en los dispositivos de los usuarios finales. Por tanto, Intune proporciona la detección de jailbreak y de obtención de permisos de usuario root para los dispositivos inscritos y no inscritos. Con esta versión, ahora Intune aprovechará las API de Google Play Protect para agregarlas a nuestras comprobaciones de detección de modificaciones existentes para los dispositivos no inscritos. Aunque Google no comparte la totalidad de las comprobaciones de detección de modificaciones que se producen, esperamos que estas API detecten los usuarios que han modificado sus dispositivos por cualquier motivo, desde la personalización del dispositivo a la obtención de las actualizaciones más recientes del sistema operativo en dispositivos más antiguos. Después, se puede bloquear el acceso de estos usuarios a los datos corporativos, o bien se pueden eliminar sus cuentas de empresa desde sus aplicaciones habilitadas para la directiva. Para obtener valor adicional, ahora los administradores de TI tendrán varias actualizaciones de informes en la hoja Protección de aplicaciones de Intune: en el informe "Usuarios marcados" se mostrarán los usuarios que se han detectado mediante el examen de la API SafetyNet de Google Play Protect, y en el informe "Aplicaciones potencialmente peligrosas" se mostrarán las aplicaciones que se hayan detectado mediante el examen de la API Verify Apps de Google. Esta característica está disponible en Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade---2617342-----"></a>Información de aplicaciones Win32 disponible en la hoja Solución de problemas<!-- 2617342   -->
Ya puede recopilar archivos de registro de errores de la instalación de una aplicación Win32 desde la hoja **Solución de problemas** de la aplicación Intune. Para más información sobre la solución de problemas de instalación de aplicaciones, vea [Troubleshoot app installation issue](./../apps/troubleshoot-app-install.md) (Solución de problemas de instalación de aplicaciones) y [Solucionar los problemas de aplicaciones Win32](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps---3761235-----"></a>Detalles del estado de la aplicación para aplicaciones iOS<!-- 3761235   -->
Hay nuevos mensajes de error de instalación de aplicaciones relacionados con lo siguiente:
- Error de las aplicaciones VPP cuando se instalan en un iPad compartido
- Error cuando la tienda de aplicaciones está deshabilitada
- No se puede encontrar la licencia VPP de la aplicación
- No se pueden instalar las aplicaciones del sistema con el proveedor de MDM
- No se pueden instalar aplicaciones cuando el dispositivo está en modo de pantalla completa o modo perdido
- No se puede instalar la aplicación cuando el usuario no ha iniciado sesión en la App Store

En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > "Nombre de la aplicación" > **Estado de instalación del dispositivo**. Los mensajes de error nuevos estarán disponibles en el estado **Detalles del estado**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nuevas pantalla de categorías de aplicaciones en la aplicación Portal de empresa para Windows 10<!-- 3834780  -->
Se ha agregado una nueva pantalla denominada **Categorías de aplicaciones** para mejorar la experiencia de exploración y selección en la aplicación Portal de empresa para Windows 10. Los usuarios ahora verán sus aplicaciones ordenadas en categorías como **Destacadas**, **Educación** y **Productividad**. Este cambio aparece en las versiones 10.3.3451.0 y posteriores de Portal de empresa. Para ver la nueva pantalla, vea [Actualizaciones de la interfaz de usuario para las aplicaciones de usuario final de Intune](whats-new-app-ui.md). Para más información sobre las aplicaciones del Portal de empresa, vea [Instalar y compartir aplicaciones en el dispositivo](../user-help/install-apps-cpapp-windows.md).  

#### <a name="power-bi-compliance-app---1455231-doc-work-item---"></a>Aplicación de cumplimiento de Power BI<!-- 1455231 doc-work-item -->
Acceda al almacenamiento de datos de Intune en Power BI Online mediante la aplicación [Cumplimiento de Intune (Almacenamiento de datos)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Con esta aplicación de Power BI, ahora puede acceder y compartir informes creados previamente sin necesidad de configuración y sin salir de su explorador web. Para más información, vea el [registro de cambios en la aplicación del cumplimiento de Power BI](../developer/reports-changelog.md#power-bi-compliance-app).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices---1862675-----"></a>Los scripts de PowerShell se pueden ejecutar en un host de 64 bits en dispositivos de 64 bits<!-- 1862675   -->
Al agregar un script de PowerShell a un perfil de configuración de dispositivo, el script siempre se ejecuta en 32 bits, incluso en sistemas operativos de 64 bits. Con esta actualización, un administrador puede ejecutar el script en un host de PowerShell de 64 bits en dispositivos de 64 bits (**Configuración del dispositivo** > **Scripts de PowerShell** >  **Agregar** > **Configurar** > **Ejecutar script en el host de PowerShell de 64 bits**).

Para obtener más detalles sobre el uso de PowerShell, vea [Scripts de PowerShell en Intune](../apps/intune-management-extension.md).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="macos-users-are-prompted-to-update-their-password---1873216---"></a>Se pide a los usuarios de macOS que actualicen su contraseña<!-- 1873216 -->
Intune está exigiendo el valor **ChangeAtNextAuth** en los dispositivos macOS. Esta opción afecta a los usuarios finales y los dispositivos que tienen directivas de contraseña de cumplimiento o perfiles de contraseña de restricción de dispositivo. Se pide a los usuarios finales que actualicen su contraseña una vez. Este mensaje se produce cada vez que un usuario realiza por primera vez una tarea que necesita autenticación, como iniciar sesión en el dispositivo. También se pide a los usuarios que actualicen su contraseña cuando hagan algo que necesite privilegios administrativos, como por ejemplo, pedir acceso a cadenas de llaves.

Cuando el administrador cambia la directiva de contraseña nueva o existente, se pide a los usuarios finales que vuelvan a actualizar su contraseña.

Se aplica a:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device---2340521------"></a>Asignar certificados SCEP en un dispositivo macOS sin usuarios<!-- 2340521    -->
Puede asignar los certificados del Protocolo de inscripción de certificados simple (SCEP) mediante los atributos del dispositivo para dispositivos macOS, incluidos los dispositivos sin afinidad de usuario y asociar el perfil de certificado con perfiles de Wi-Fi o VPN. Esto amplía la compatibilidad que ya tenemos para [asignar certificados del SCEP a dispositivos con y sin afinidad de usuario](../protect/certificates-profile-scep.md) que tienen instalado Windows, iOS y Android.  Esta actualización agrega la opción de seleccionar un tipo de certificado de *Dispositivo* al configurar un perfil de certificado SCEP para macOS.

Se aplica a:
- macOS

#### <a name="intune-conditional-access-ui-update---2432313-----"></a>Actualización de la interfaz de usuario del acceso condicional de Intune<!-- 2432313   -->
Hemos realizado mejoras en la interfaz de usuario para el acceso condicional en la consola de Intune. Entre ellos, se incluye:
- Hemos reemplazado la hoja *Acceso condicional* de Intune con la hoja de Azure Active Directory. Esto garantiza que tendrá acceso a toda la gama de opciones y configuraciones para el [acceso condicional](../protect/conditional-access.md) (que sigue siendo una tecnología de Azure AD) desde la consola de Intune. 
- Hemos cambiado el nombre de la hoja *Acceso local* a *Acceso de Exchange* y hemos cambiado de sitio el programa de instalación del *Conector de servicio de Exchange* a esta hoja con el nuevo nombre.  Este cambio consolida donde se puede [configurar y supervisar los detalles relacionados con Exchange en línea y local](../protect/exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode---2935135-----"></a>Las aplicaciones de explorador del Quiosco y Microsoft Edge se pueden ejecutar en dispositivos Windows 10 en modo de pantalla completa<!-- 2935135   -->
Puede usar dispositivos Windows 10 en modo de pantalla completa para ejecutar una o varias aplicaciones. En esta actualización se incluyen varios cambios en el uso de las aplicaciones de explorador en modo de pantalla completa, incluidos los siguientes:

- Se agrega el explorador Microsoft Edge o Kiosk Browser para que se ejecuten como aplicaciones en el dispositivo de pantalla completa (**Configuración del dispositivo** > **Perfiles** > **Nuevo perfil** > **Windows 10 y versiones posteriores** para plataforma > **Pantalla completa** para el tipo de perfil).
- Hay disponibles nuevas características y configuraciones para permitir o restringir (**Configuración del dispositivo** > **Perfiles** > **Nuevo perfil** > **Windows 10 y versiones posteriores** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil), incluidos:

- Explorador Microsoft Edge:
  - Usar el modo de pantalla completa de Microsoft Edge
  - Actualizar el explorador después del tiempo de inactividad

- Favoritos y búsqueda:
  - Permitir cambios en el motor de búsqueda

Para obtener una lista de estos valores, vea:

- [Configuración de dispositivos con Windows 10 y versiones posteriores para ejecutarse como una pantalla completa](../configuration/kiosk-settings-windows.md)
- [Restricciones de dispositivos del explorador Microsoft Edge](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Favoritos y restricciones de búsqueda de dispositivos](../configuration/device-restrictions-windows-10.md#favorites-and-search)

Se aplica a: Windows 10 y versiones posteriores

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices---3448774-----"></a>Nueva configuración de restricción de dispositivos para dispositivos iOS y macOS<!-- 3448774   -->
Puede restringir algunas opciones y características de los dispositivos que ejecutan iOS y macOS (**Configuración del dispositivo** > **Perfiles** > **Nuevo perfil** > **iOS** o **macOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil). En esta actualización se agregan más características y valores de configuración que puede controlar, incluida la configuración del tiempo de pantalla, el cambio de la configuración eSIM, planes de telefonía móvil y mucho más en dispositivos iOS. También la opción de retrasar la visibilidad para el usuario de las actualizaciones de software y el bloqueo de almacenamiento en caché de contenido en dispositivos macOS.

Para ver las características y la configuración que se pueden restringir, vea:

- [Configuración de restricciones de dispositivos iOS](../configuration/device-restrictions-ios.md)
- [Configuración de restricciones de dispositivos macOS](../configuration/device-restrictions-macos.md)

Se aplica a:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices---3598402-----"></a>Los dispositivos de "Pantalla completa" ahora se denominan "Dispositivos dedicados" en dispositivos Android Enterprise<!-- 3598402   -->
Para alinear con la terminología de Android, **Pantalla completa** cambia a **Dispositivos dedicados** para dispositivos Android Enterprise (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > ** Android Enterprise para la plataforma > **Solo el propietario del dispositivo** > **Restricciones de dispositivos** > **Dispositivos dedicados**).

Para ver los valores disponibles, vaya a [Android Enterprise device settings to allow or restrict features using Intune](../configuration/device-restrictions-android-for-work.md#device-experience) (Configuración de dispositivos Android Enterprise para permitir o restringir características con Intune).

Se aplica a:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui---3640850-3803313-----"></a>Las opciones de Safari y Retrasar la visibilidad de las actualizaciones de software iOS se cambian a la interfaz de usuario de Intune<!-- 3640850, 3803313   -->
Para los dispositivos iOS, puede establecer la configuración de Safari y configurar actualizaciones de software. En esta actualización, estas opciones se van a cambiar a otra partes de la interfaz de usuario de Intune:

- La configuración de Safari cambia de **Safari** (**Configuración del dispositivo** > **Perfiles** > **Nuevo perfil** > **iOS** para la plataforma > **Restricciones de dispositivos** para el tipo de perfil) a **[Aplicaciones integradas](../configuration/device-restrictions-ios.md#built-in-apps)** .
- La opción **Delaying user software update visibility for supervised iOS devices** (Retrasar la visibilidad de las actualizaciones de software para los dispositivos iOS supervisados) (**Actualizaciones de software** > **Directivas de actualización para iOS**) se va a cambiar a **Restricciones de dispositivos** >  **[General](../configuration/device-restrictions-ios.md#general)** .  Para más información sobre el impacto en las directivas existentes, vea [Configuración de directivas de actualización de iOS en Intune](../protect/software-updates-ios.md#configure-the-policy).

Para obtener una lista de estos valores, vea:

- [Restricciones de dispositivos iOS](../configuration/device-restrictions-ios.md) 
- [Actualizaciones del software iOS](../protect/software-updates-ios.md)

Esta característica se aplica a:

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices---3699164-----"></a>En los dispositivos iOS se ha cambiado el nombre de Habilitar restricciones en la configuración del dispositivo por Tiempo de uso<!-- 3699164   -->
Puede configurar **Habilitar restricciones en la configuración del dispositivo**  en dispositivos iOS supervisados (**Configuración del dispositivo** > **Perfiles** > **Nuevo perfil** > **iOS** para plataforma > **Restricciones de dispositivos** para tipo de perfil > **General**). En esta actualización, se ha cambiado el nombre de esta opción por **Tiempo de uso (solo con supervisión)** .

El comportamiento es el mismo. De manera específica:

- iOS 11.4.1 y versiones anteriores: **Bloquear** impide que los usuarios finales establezcan sus propias restricciones en la configuración del dispositivo. 
- iOS 12.0 y versiones posteriores: **Bloquear** impide que los usuarios finales establezcan su propio **Tiempo de uso** en la configuración del dispositivo, incluidas las restricciones de contenido y privacidad. En los dispositivos actualizados a iOS 12.0 ya no aparecerá la pestaña Restricciones en la configuración del dispositivo. Estas opciones se encuentran en **Tiempo de uso**. 

Para obtener una lista de los valores, vea [Restricciones de dispositivos iOS](../configuration/device-restrictions-ios.md#general).

Se aplica a:
- iOS


#### <a name="intune-powershell-module---951068----"></a>Módulo de PowerShell de Intune<!-- 951068  -->
El módulo de PowerShell de Intune, que proporciona compatibilidad con la API de Intune a través de Microsoft Graph, ya está disponible en la [Galería de Microsoft PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Detalles sobre cómo usar este módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Ejemplos de escenarios de uso de este módulo](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization--3183757----"></a>Compatibilidad mejorada para la optimización de entrega<!--3183757  -->
Hemos ampliado la compatibilidad de Intune para configurar la optimización de entrega. Ahora puede configurar una lista expandida de [Configuración de optimización de entrega](../configuration/delivery-optimization-settings.md) y aplicarla a los dispositivos directamente desde la consola de Intune.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración de dispositivos

#### <a name="rename-an-enrolled-windows-device---1911112----"></a>Cambio del nombre de un dispositivo Windows inscrito<!-- 1911112  -->
Ahora puede cambiar el nombre de un dispositivo Windows 10 inscrito (RS4 o posterior). Para ello, seleccione **Intune** > **Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **Cambiar el nombre del dispositivo**. Esta característica no es compatible actualmente con el cambio de nombre de dispositivos Windows híbridos con Azure AD.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope---3173823----"></a>Asignación automática de etiquetas de ámbito a los recursos creados por un administrador con ese ámbito<!-- 3173823  -->
Cuando un administrador crea un recurso, las etiquetas de ámbito asignadas al administrador se asignarán de forma automática a esos recursos nuevos.

### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade---3560202----"></a>El informe Errores de inscripción se mueve a la hoja Inscripción de dispositivos<!-- 3560202  -->
El informe **Errores de inscripción** se ha movido a la sección **Supervisar** de la hoja **Inscripción de dispositivos**. Se han agregado dos columnas nuevas (Método de inscripción y Versión del sistema operativo).

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments--3815076-eemiss---"></a>Se ha cambiado el nombre del informe Abandono del Portal de empresa a Inscripciones de usuario incompletas<!--3815076 eemiss -->
Se ha cambiado el nombre del informe **Abandono del Portal de empresa** a **Inscripciones de usuario incompletas**.






<!-- ########################## -->
## <a name="january-2019"></a>Enero de 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Administración de aplicaciones

#### <a name="intune-app-pin---2298397---"></a>PIN de aplicación de Intune<!-- 2298397 -->
Como administrador de TI, podrá configurar el número de días que un usuario final puede esperar hasta que se tenga que cambiar el PIN de aplicación de Intune. La nueva configuración es *Restablecimiento del PIN después de un número de días* y está disponible en Azure Portal; para acceder a esta configuración, seleccione **Intune** > **Aplicaciones cliente** > **Directivas de protección de aplicaciones** > **Crear directiva** > **Configuración** > **Requisitos de acceso**. Esta característica está disponible para dispositivos [iOS](../apps/app-protection-policy-settings-ios.md) y [Android](../apps/app-protection-policy-settings-android.md), y admite un valor entero positivo.

#### <a name="intune-device-reporting-fields---2748738---"></a>Campos de informes de dispositivo de Intune<!-- 2748738 -->
Intune proporciona campos adicionales con información sobre el dispositivo, como el identificador de registro de aplicación, el fabricante de Android, el modelo, la versión de la revisión de seguridad y el modelo de iOS. En Intune, estos campos estarán disponibles en **Aplicaciones cliente** > **Estado de protección de aplicaciones** y **Informe de protección de aplicaciones: iOS, Android**. Además, estos parámetros lo ayudarán a configurar la lista de **admitidos** correspondiente al fabricante de dispositivo (Android), la lista de **admitidos** del modelo de dispositivo (iOS y Android) y la configuración de versión de la revisión de seguridad mínima de Android.

#### <a name="toast-notifications-for-win32-apps---3136566-----"></a>Notificaciones del sistema para aplicaciones Win32<!-- 3136566   -->
Puede suprimir notificaciones del sistema para el usuario final por asignación de aplicaciones. En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > seleccione la aplicación > **Asignaciones** > **Incluir grupos**.

#### <a name="intune-app-protection-policies-ui-update---3251427----"></a>Actualización de la interfaz de usuario de las directivas de protección de aplicaciones de Intune<!-- 3251427  -->
Hemos cambiado las etiquetas para las opciones y los botones de la protección de aplicaciones de Intune para que sean más fáciles de entender. Algunos de los cambios son:  
- Los controles han cambiado de **sí** / **no** a principalmente **bloquear** / **permitir** y **deshabilitar** / **habilitar**. Las etiquetas también se actualizaron.  
- Se cambió el formato de las opciones, de tal forma que la opción y su etiqueta aparezcan una al lado de la otra en el control, para así facilitar la navegación.

La configuración predeterminada y el número de opciones se conservan, pero este cambio permite al usuario entender, navegar y utilizar la configuración con más facilidad para aplicar las directivas de protección de aplicaciones seleccionadas. Para información, consulte la [configuración para iOS](../apps/app-protection-policy-settings-ios.md) y la [configuración para Android](../apps/app-protection-policy-settings-android.md).

#### <a name="additional-settings-for-outlook---3301182----"></a>Configuración adicional para Outlook<!-- 3301182  -->
Ahora puede cambiar estos otros valores de configuración de Outlook para iOS y Android mediante Intune:

- Permitir que solo se usen cuentas profesionales o educativas en iOS y Android.
- Implementar la autenticación moderna para Microsoft 365 y la autenticación moderna híbrida para cuentas locales.
- Usar `SAMAccountName` para el campo de nombre de usuario en el perfil de correo electrónico al tener seleccionada la autenticación básica.
- Permitir que se guarden contactos.
- Configurar información sobre el correo electrónico de destinatarios externos.
- Configurar la **Bandeja de entrada Prioritarios**.
- Requerir autenticación biométrica para acceder a Outlook para iOS.
- Bloquear las imágenes externas.

> [!NOTE]
> Si usa directivas de Intune App Protection para administrar el acceso de las identidades corporativas, le recomendamos que no habilite el **requisito de autenticación biométrica**. Para más información, vea **Requerir credenciales corporativas en acceso**, en los artículos relativos a la [configuración de acceso de iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) y la [configuración de acceso de Android](../apps/app-protection-policy-settings-android.md#access-requirements), respectivamente.

Para más información, vea [Opciones de configuración de Microsoft Outlook](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps---1352553---"></a>Eliminación de aplicaciones de Android Enterprise<!-- 1352553 -->
Puede eliminar aplicaciones de Google Play administrado desde Microsoft Intune. Para eliminar una aplicación de Google Play administrado, abra Microsoft Intune en Azure Portal y seleccione **Aplicaciones cliente** > **Aplicaciones**. En la lista de aplicaciones, seleccione los puntos suspensivos (...) a la derecha de la aplicación de Google Play administrado y luego seleccione **Eliminar** en la lista que aparece. Cuando se elimina una aplicación de Google Play administrada de la lista de aplicaciones, automáticamente se desactiva la aprobación de la aplicación administrada de Google Play.

#### <a name="managed-google-play-app-type---1352580---"></a>Tipo de aplicaicón de Google Play administrado<!-- 1352580 -->
El tipo de aplicación **administrada de Google Play** le permitirá agregar específicamente [aplicaciones de Google Play administradas](https://play.google.com/work/search?q=microsoft&c=apps) a Intune. Como administrador de Intune, ahora podrá examinar, buscar, aprobar, sincronizar y asignar aplicaciones de Google Play administrado aprobadas dentro de Intune.  Ya no necesita ir a la consola de Google Play administrado por separado ni tiene que volver a autenticarse.  En Intune, seleccione **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. En la lista **Tipo de aplicación**, seleccione **Google Play administrada** como tipo de aplicación.

#### <a name="default-android-pin-keyboard---3802457---"></a>Teclado de PIN de Android predeterminado<!-- 3802457 -->
Los usuarios finales que hayan establecido un PIN de directiva de Intune App Protection (APP) en sus dispositivos Android con el tipo de PIN “Numérico” ahora verán el teclado de Android predeterminado en lugar de la interfaz de usuario de teclado de Android que se había diseñado anteriormente. Este cambio se ha llevado a cabo para que sea coherente al usar los teclados predeterminados en Android e iOS, para ambos tipos de PIN “Numérico” o “Código de acceso”. Para obtener más información sobre la configuración de acceso de los usuarios finales en Android, como el PIN de APP, consulte [Requisitos de acceso de Android](../apps/app-protection-policy-settings-android.md#access-requirements).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Las plantillas administrativas están en versión preliminar pública y se movieron a su propio perfil de configuración <!-- 3322847 -->

Las plantillas administrativas de Intune (**Configuración del dispositivo** > **Plantillas administrativas**) están actualmente en versión preliminar pública. Con esta actualización:

- Las plantillas administrativas contienen unos 300 valores de configuración que se pueden administrar en Intune. Anteriormente, estas configuraciones solo existían en el editor de directivas de grupo.
- Las plantillas administrativas están disponibles en versión preliminar pública.
- Las plantillas administrativas están disponibles en versión preliminar pública y se han migrado desde **Configuración del dispositivo** > **Plantillas administrativas** a **Configuración del dispositivo** > **Perfiles** > **Crear perfil**. Luego, en **Plataforma**, seleccione **Windows 10 y versiones posteriores**, en **Tipo de perfil**, y haga clic en **Plantillas administrativas**.
- Se han habilitado los informes.

Para obtener más información sobre esta característica, vaya a [Plantillas de Windows 10 para configurar opciones de directiva de grupo](../configuration/administrative-templates-windows.md).

Se aplica a: Windows 10 y versiones posteriores

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user---1333642---"></a>Uso de S/MIME para cifrar y firmar varios dispositivos para un usuario<!-- 1333642 -->
Esta actualización incluye cifrado de correo electrónico S/MIME mediante un nuevo perfil de certificado importado (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > seleccione la plataforma > tipo de perfil **Certificado PKCS importado**). En Intune, puede importar los certificados en formato PFX. Después, Intune puede entregar esos mismos certificados a varios dispositivos inscritos por un solo usuario. Esto también incluye lo siguiente:
- El perfil de correo electrónico de iOS nativo permite habilitar el cifrado S/MIME mediante certificados importados en formato PFX.
- La aplicación de correo nativo de los dispositivos Windows Phone 10 usa automáticamente el certificado S/MIME.
- Los certificados privados se pueden entregar en varias plataformas. Aun así, no todas las aplicaciones de correo electrónico son compatibles con S/MIME.
- En otras plataformas, podría tener que configurar manualmente la aplicación de correo electrónico para habilitar S/MIME.  
- Las aplicaciones de correo electrónico que admiten el cifrado S/MIME pueden controlar la recuperación de certificados para el cifrado de correo electrónico S/MIME de una manera que no es compatible con un servicio MDM, por ejemplo, si los lee desde el almacén de certificados del publicador.
Para obtener más información sobre esta característica, vea [Información general sobre S/MIME para firmar y cifrar correos electrónicos](../protect/certificates-s-mime-encryption-sign.md).
Compatible con: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices---1333665-2999078---"></a>Nuevas opciones para conectarse automáticamente y conservar las reglas al usar la configuración DNS en dispositivos Windows 10 y posteriores<!-- 1333665, 2999078 -->
En dispositivos Windows 10 y versiones posteriores, podrá crear un perfil de configuración de VPN que incluya una lista de servidores DNS para resolver dominios, como contoso.com. En esta actualización se incluirá una nueva configuración para la resolución de nombres (**Configuración del dispositivo** > **Perfiles** > **Crear perfil**; seleccione **Windows 10 y versiones posteriores** como la plataforma, **VPN** como el tipo de perfil, y **Configuración DNS** >**Agregar**): 
- **Conectar automáticamente**: si esta opción está **Habilitada**, el dispositivo se conecta automáticamente a la VPN cuando se comunica con un dominio especificado, como contoso.com.
- **Persistente**: de manera predeterminada, todas las reglas de la tabla de directivas de resolución de nombres (NRPT) están activas siempre que el dispositivo esté conectado mediante este perfil de VPN. Si esta opción está **habilitada** en una regla de NRPT, la regla sigue activa en el dispositivo incluso si la VPN se desconecta. La regla se mantiene hasta que se el perfil de VPN se quita o hasta que la regla se quita manualmente, lo cual puede hacerse mediante PowerShell.
En [Configuración de VPN de Windows 10](../configuration/vpn-settings-windows-10.md), se describe la configuración.

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices---1500165---"></a>Uso de la detección de redes de confianza para perfiles de VPN en dispositivos Windows 10<!-- 1500165 -->
Al usar la detección de redes de confianza, podrá impedir que los perfiles VPN creen automáticamente una conexión VPN cuando el usuario ya esté en una red de confianza. Con esta actualización, podrá agregar sufijos DNS para habilitar la detección de redes de confianza en dispositivos que ejecuten Windows 10 y versiones posteriores (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para la plataforma > **VPN** para el tipo de perfil).
[Configuración de VPN de Windows 10](../configuration/vpn-settings-windows-10.md) muestra la configuración de VPN actual.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users---1907917-1063203---"></a>Administración de dispositivos con Windows Holographic for Business empleados por varios usuarios<!-- 1907917, 1063203 -->
Actualmente, puede configurar parámetros de equipos compartidos en Windows 10 y dispositivos Windows Holographic for Business mediante una configuración personalizada de OMA-URI. En esta actualización se agregará un nuevo perfil para configurar las opciones de dispositivos compartidos (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** > **Dispositivo multiusuario compartido**).
Para obtener más información sobre esta característica, vaya a [Configuración de Intune para administrar dispositivos compartidos](../configuration/shared-user-device-settings.md).
Se aplica a: Windows 10 y versiones posteriores, Windows Holographic for Business

#### <a name="new-windows-10-update-settings--2626030--2512994----"></a>Nueva configuración de actualizaciones de Windows 10<!--2626030  2512994  -->
Para sus [Círculos de actualizaciones de Windows 10](../protect/windows-update-for-business-configure.md), puede configurar lo siguiente:
- **Comportamiento de actualizaciones automáticas**: use una nueva opción (*Restablecer valores predeterminados*) para restaurar la configuración de actualizaciones automáticas original en equipos con Windows 10 que ejecuten la *actualización de octubre de 2018*.
- **Impedir al usuario pausar las actualizaciones de Windows**: establezca una nueva configuración de actualizaciones de software que impida o permita que los usuarios pausen la instalación de actualizaciones en el menú *Configuración* de sus equipos.

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption---2662949---"></a>Los perfiles de correo electrónico de iOS pueden usar cifrado y firma de S/MIME<!-- 2662949 -->
Podrá crear un perfil de correo electrónico que incluya otra configuración. En esta actualización, se incluye la configuración de S/MIME que se puede usar para firmar y cifrar las comunicaciones por correo electrónico de dispositivos iOS (**Configuración del dispositivo** > **Perfiles** > **Crear perfil**; elija **iOS** para la plataforma y **Correo electrónico** para el tipo de perfil).
La configuración actual se muestra en [Opciones de configuración de correo electrónico de iOS](../configuration/email-settings-ios.md).

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Algunos valores de configuración de BitLocker admiten Windows 10 Pro Edition<!-- 2727036 -->
Podrá crear un perfil de configuración que establezca los ajustes de Endpoint Protection en dispositivos con Windows 10, incluido BitLocker. En esta actualización se agrega la compatibilidad con Windows 10 Professional Edition en algunas opciones de configuración de BitLocker.
Para ver estos ajustes de protección, vaya a [Configuración de Endpoint Protection para Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Cambio del nombre de Configuración de dispositivo compartido a Mensaje de la pantalla de bloqueo para dispositivos iOS en Azure Portal<!-- 2809362 -->
Al crear un perfil de configuración de dispositivos iOS, puede agregar la opción **Configuración de dispositivo compartido** para mostrar texto específico en la pantalla de bloqueo. En esta actualización se incluyen los cambios siguientes: 
- El nombre de la opción **Configuración de un dispositivo compartido** en Azure Portal se cambia a "Mensaje de la pantalla de bloqueo (solo con supervisión)" (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > Elegir **iOS** para la plataforma > Elegir **Características del dispositivo** para el tipo de perfil > **Mensaje de la pantalla de bloqueo**).
- Al agregar mensajes de la pantalla de bloqueo, puede insertar un número de serie, un nombre de dispositivo u otro valor específico del dispositivo como una variable en **Información de etiqueta del activo** y **Nota al pie en la pantalla de bloqueo**. Por ejemplo, puede escribir `Device name: {{devicename}}` o `Serial number is {{serialnumber}}` entre llaves. [Tokens de iOS](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) muestra los tokens disponibles que se pueden usar.
En [Configuración para mostrar mensaje en la pantalla de bloqueo](../configuration/ios-device-features-settings.md#lock-screen-message), se muestra la configuración actual.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices---2827760--"></a>Adición en dispositivos iOS de nuevo App Store, visualización de documentos y configuración de restricción de dispositivos de juego<!-- 2827760-->
En **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para la plataforma y **Restricciones de dispositivo** para el tipo de perfil, en **App Store, visualización de documentos y juegos**, se han agregado las siguientes opciones de configuración: Permitir a las aplicaciones administradas escribir contactos en cuentas de contactos no administradas y Permitir a las aplicaciones no administradas leer en cuentas de contactos administradas. Para ver estas opciones de configuración, vaya a [Restricciones de dispositivos iOS](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices---3201839-3201843---"></a>Nueva configuración de notificaciones, sugerencias y bloqueo del teclado para dispositivos de propietarios de dispositivos Android Enterprise<!-- 3201839 3201843 -->
Esta actualización incluye varias características de los dispositivos Android Enterprise cuando se ejecutan como propietario del dispositivo. Para usar estas características, vaya a **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > en **Plataforma**, elija **Android Enterprise** > en **Tipo de perfil**, elija **Solo el propietario del dispositivo** > **Restricciones de dispositivos**.

Nuevas características:

- Deshabilitar la visualización de las notificaciones del sistema, incluidas las llamadas entrantes, las alertas del sistema, los errores del sistema, etc.
- Sugerir omitir los tutoriales de inicio y las sugerencias para las aplicaciones que se abren por primera vez.
- Deshabilitar la configuración avanzada del bloqueo del teclado, como la cámara, las notificaciones, el desbloqueo con huella digital, etc.

Para ver la configuración actual, vaya a [Configuración de restricciones de dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections---3202194---"></a>Los dispositivos de propietarios de dispositivos Android Enterprise pueden usar conexiones VPN siempre activas<!-- 3202194 -->
En esta actualización, puede usar conexiones VPN siempre activas en dispositivos propietarios del dispositivo Android Enterprise. Las conexiones VPN siempre activas permanecen conectadas o se vuelven a conectar inmediatamente cuando el usuario desbloquea el dispositivo, cuando se reinicia el dispositivo o cuando cambia la red inalámbrica. También puede poner la conexión en modo “bloqueo”, que bloquea todo el tráfico de red hasta que la conexión VPN esté activa.
Puede habilitar la VPN siempre activa en **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Restricciones de dispositivos** solo para el propietario del dispositivo > **Conectividad**. Para ver la configuración actual, vaya a [Configuración de restricciones de dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices---3285177---"></a>Nueva configuración para terminar procesos en el Administrador de tareas de dispositivos Windows 10<!-- 3285177 --> 
Esta actualización incluye una configuración nueva para terminar los procesos con el Administrador de tareas en dispositivos Windows 10. Con un perfil de configuración de dispositivo (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > en **Plataforma**, elija **Windows 10** > en **Tipo de perfil**, elija **Restricciones de dispositivos** > **Configuración general**), elige si permitir o impedir esta configuración.
Para ver la configuración actual, vaya a [Configuración de restricciones de dispositivos Windows 10](../configuration/device-restrictions-windows-10.md).
Se aplica a: Windows 10 y versiones posteriores

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview---2055484-----"></a>Uso de la configuración recomendada por Microsoft con líneas de base de seguridad (versión preliminar pública)<!-- 2055484   -->

Intune se integra con otros servicios centrados en la seguridad, incluidos ATP de Windows Defender y Office 365 ATP. Los clientes solicitan una estrategia común y un conjunto coherente de flujos de trabajo de seguridad integrales entre los servicios de Microsoft 365. Nuestro objetivo es alinear las estrategias para crear soluciones que actúen de puente entre las operaciones de seguridad y las tareas de administración comunes. En Intune, este objetivo se pretende lograr mediante la publicación de un conjunto de "Líneas de base de seguridad" recomendadas de Microsoft (**Intune** > **Líneas de base de seguridad**).  Un administrador puede crear directivas de seguridad directamente a partir de estas líneas de base y, después, implementarlas en sus usuarios. También puede personalizar los procedimientos recomendados para satisfacer las necesidades de su organización. Intune garantiza que los dispositivos cumplan estas líneas de base y notifica a los administradores los usuarios o dispositivos que no están en cumplimiento.

Esta característica está en versión preliminar pública, por lo que los perfiles creados ahora no se moverán a las plantillas de líneas base de seguridad que están disponibles con carácter general (GA). No debería planear usar estas plantillas de versión preliminar en el entorno de producción.

Para más información sobre las líneas de base de seguridad, vea [Create a Windows 10 security baseline in Intune](../protect/security-baselines-monitor.md) (Crear una línea de base de seguridad de Windows 10 en Intune).

Esta característica se aplica a: Windows 10 y versiones posteriores

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Quienes no son administradores pueden habilitar BitLocker en dispositivos Windows 10 unidos a Azure AD<!-- 2147379   -->
Cuando se habilita la configuración de BitLocker en dispositivos Windows 10 (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para la plataforma > **Endpoint Protection** para el tipo de perfil > **Cifrado de Windows**), se agrega la configuración de BitLocker.

Esta actualización incluye una configuración de BitLocker nueva para permitir que los usuarios estándar (no administradores) habiliten el cifrado.

Para ver esta configuración, vaya a [Configuración de Windows 10 (y versiones posteriores) para proteger dispositivos mediante Intune](../protect/endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance---2192052--eepublished----"></a>Comprobación de cumplimiento de Configuration Manager<!-- 2192052  eepublished  -->
Esta actualización incluye una nueva configuración de conformidad de Configuration Manager (**Conformidad de dispositivos** > **Directivas** > **Crear directiva** > **Windows 10 y versiones posteriores** > **Cumplimiento de Configuration Manager**). Configuration Manager envía señales a la conformidad de Intune. Mediante esta configuración, puede exigir que todas las señales de Configuration Manager devuelvan “conforme”.

Por ejemplo, exige que todas las actualizaciones de software se instalen en los dispositivos. En Configuration Manager, este requisito tiene el estado "Instalado". Si algún programa del dispositivo se encuentra en un estado desconocido, dicho dispositivo no será conforme en Intune.

[Cumplimiento de Configuration Manager](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) describe esta configuración.

Se aplica a: Windows 10 y versiones posteriores

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile---2809324-----"></a>Personalización del papel tapiz en dispositivos iOS supervisados mediante un perfil de configuración de dispositivo<!-- 2809324   -->
Cuando cree un perfil de configuración de dispositivos para dispositivos iOS, podrá personalizar algunas características (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** para la plataforma > **Características del dispositivo** para el tipo de perfil). Esta actualización incluye nuevas configuraciones **Fondo de pantalla** que permiten a un administrador usar una imagen .png, .jpg o .jpeg en la pantalla de inicio o en la pantalla de bloqueo. Esta configuración de fondo de pantalla solo se aplica a los dispositivos supervisados. 

Para una lista de esta configuración, consulte [iOS device feature settings](../configuration/ios-device-features-settings.md) (Configuración de características de dispositivos iOS).

#### <a name="windows-10-kiosk-is-generally-available---3594661----"></a>Pantalla completa de Windows 10 disponible con carácter general<!-- 3594661  -->
En esta actualización, la característica Pantalla completa en dispositivos con Windows 10 y versiones posteriores está disponible con carácter general (GA). Para ver todas las configuraciones que puede agregar y definir, consulte [Configuración de dispositivos con Windows 10 y versiones posteriores para ejecutarse como una pantalla completa dedicada con Intune](../configuration/kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise---3598396-----"></a>Se eliminó la opción para compartir contacto a través de Bluetooth en Restricciones del dispositivo > Propietario del dispositivo para Android Enterprise<!-- 3598396   -->
Cuando se crea un perfil de restricciones de dispositivos para dispositivos de Android Enterprise, hay una configuración para **Compartir contacto a través de Bluetooth**. En esta actualización, se elimina la configuración **Compartir contacto a través de Bluetooth** (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android Enterprise** para la plataforma > **Restricciones de dispositivos > Propietario del dispositivo** para el tipo de perfil > **General**).

La configuración **Compartir contacto a través de Bluetooth** no es compatible con la administración de Propietario del dispositivo Android Enterprise. Por lo que cuando se quite esta configuración, no afectará a ningún dispositivo ni inquilino, incluso si esta opción está habilitada y configurada en su entorno.

Para ver la lista actual de configuraciones, vaya a [Configuración de dispositivos Android Enterprise para permitir o restringir características](../configuration/device-restrictions-android-for-work.md).

Se aplica a: Propietario del dispositivo Android Enterprise


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="more-detailed-enrollment-restriction-failure-messaging---3111564---"></a>Mensajes de error de restricción de inscripción más detallados<!-- 3111564 -->
Los mensajes de error más detallados estarán disponibles cuando no se cumplan las restricciones de inscripción. Para ver estos mensajes, vaya a **Intune** > **Solucionar problemas** > y revise la tabla Errores de inscripción. Para obtener más información, vea la [lista de errores de inscripción](help-desk-operators.md#enrollment-failure-reference).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Administración del dispositivo
#### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices---1574342----"></a>Versión preliminar de la compatibilidad con dispositivos Android totalmente administrados de propiedad corporativa<!-- 1574342  -->
Intune ya admite dispositivos Android totalmente administrados; un escenario de "propietario de dispositivo" de propiedad corporativa en el que el departamento de TI administra de manera rigurosa los dispositivos y estos se asocian a usuarios individuales. Esto permite que los administradores administren todo el dispositivo, apliquen una amplia variedad de controles de directivas no disponibles para los perfiles de trabajo y restrinjan las instalaciones de aplicaciones por parte de los usuarios solo a Google Play administrado. Para obtener más información, vea [Set up Intune enrollment of Android fully managed devices](../enrollment/android-fully-managed-enroll.md) (Configuración de la inscripción en Intune de dispositivos Android totalmente administrados) y [Enroll your dedicated devices or fully managed devices](../enrollment/android-dedicated-devices-fully-managed-enroll.md) (Inscripción de dispositivos dedicados o dispositivos totalmente administrados).  Tenga en cuenta que esta característica está en versión preliminar. Algunas funcionalidades de Intune, como certificados, cumplimiento y acceso condicional, no están disponibles actualmente con dispositivos Android totalmente administrados.

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices---1434452---"></a>Compatibilidad con el borrado selectivo para dispositivos con trabajos en curso sin inscripción<!-- 1434452 -->
Windows Information Protection Without Enrollment (WIP-WE) permite a los clientes proteger sus datos corporativos en dispositivos con Windows 10 sin necesidad de realizar una inscripción de MDM completa. Una vez que los documentos están protegidos con una directiva de WIP-WE, un administrador de Intune puede borrar de forma selectiva los datos protegidos. Mediante la selección del usuario y dispositivo, y el envío de una solicitud de borrado, todos los datos protegidos mediante la directiva de WIP-WE quedarán inservibles. En Intune en Azure Portal, seleccione **Aplicación móvil** > **Borrado selectivo de aplicaciones**.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="tenant-status-dashboard---1124854---"></a>Panel Estado del inquilino<!-- 1124854 -->
En la nueva [página Estado del inquilino](tenant-status.md) se proporciona una ubicación única donde puede ver el estado del inquilino y los detalles relacionados.  El panel se divide en cuatro áreas:
- **Detalles del inquilino**: se muestra información como el nombre del inquilino y la ubicación, la entidad de MDM, el número total de dispositivos inscritos en el inquilino y el número de licencias. En esta sección también se indica la versión de mantenimiento actual del inquilino.
- **Estado del conector**: muestra información sobre conectores disponibles que ha configurado y, además, se puede mostrar una lista de los que aún no ha habilitado.  
   Basándose en el estado actual de cada conector, se marcan como Correcto, Advertencia o Incorrecto. Seleccione un conector para explorarlo en profundidad y ver sus detalles, o bien para configurar información adicional sobre este.
- **Estado del servicio Intune**: muestra detalles sobre incidentes activos o interrupciones del inquilino. La información de esta sección se obtiene directamente del Centro de mensajes de Office.
- **Noticias de Intune**: muestra mensajes activos para el inquilino. En estos mensajes, se incluyen notificaciones cuando el inquilino recibe las características de Intune más recientes.  La información de esta sección se obtiene directamente del Centro de mensajes de Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10---1488939--"></a>Nueva experiencia de ayuda y soporte técnico en el Portal de empresa para Windows 10<!-- 1488939-->
La nueva página de ayuda y soporte técnico del Portal de empresa ayuda a los usuarios a solucionar problemas y solicitar ayuda para problemas de acceso y de aplicaciones. Desde la nueva página, puede enviar por correo electrónico detalles de registros de diagnóstico y errores, así como obtener los detalles del departamento de soporte técnico de su organización. También encontrará una sección de preguntas más frecuentes con vínculos a la documentación de Intune relevante.

#### <a name="new-help-and-support-experience-for-intune---3307080---"></a>Nueva experiencia de ayuda y soporte técnico para Intune<!-- #3307080 -->
Implementaremos la nueva experiencia de ayuda y soporte técnico a todos los inquilinos en los próximos días. Esta experiencia está disponible para Intune y puede accederse al usar las hojas de Intune en [Azure Portal](https://portal.azure.com/).
La nueva experiencia le permite describir el problema con sus propias palabras y recibir información sobre solución de problemas y contenido de corrección basado en la Web. Estas soluciones se ofrecen mediante un algoritmo de aprendizaje automático con reglas, basado en las consultas de los usuarios.
Además de instrucciones específicas del problema, también puede usar el nuevo flujo de trabajo de creación de casos para abrir una incidencia de soporte técnico por teléfono o correo electrónico. Esta nueva experiencia reemplaza a la experiencia de ayuda y soporte técnico anterior de un conjunto estático de opciones seleccionadas previamente que se basan en el área de la consola en la que se encuentra cuando abre la sección Ayuda y soporte técnico.
Para obtener más información, vea [Cómo obtener asistencia para Microsoft Intune](get-support.md).

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services---3762211----"></a>Nuevos registros operativos y posibilidad de enviar registros a los servicios de Azure Monitor<!-- 3762211  -->
Intune tiene el registro de auditoría integrado que realiza el seguimiento de eventos cuando se realizan cambios. Esta actualización incluye nuevas características de registro, como las siguientes: 
- Registros operativos (versión preliminar) que se muestran detalles sobre los usuarios y dispositivos que se inscribieron, incluidos los intentos correctos y erróneos.
- Los registros de auditoría y los registros operativos también se pueden enviar a Azure Monitor, incluidas las cuentas de almacenamiento, Event Hubs y Log Analytics. Estos servicios permiten almacenar, usar análisis como Splunk y QRadar y obtener visualizaciones de los datos de registro.

En [Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) (Envío de datos de registro al almacenamiento, Event Hubs o Log Analytics en Intune) se proporciona más información sobre esta característica.

#### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device---2687509----"></a>Omisión de más pantallas del Asistente de configuración de un dispositivo DEP iOS<!-- 2687509  -->
Además de las pantallas que actualmente se pueden omitir, podrá establecer dispositivos DEP de iOS para omitir las pantallas siguientes en el Asistente para la configuración cuando un usuario inscribe el dispositivo: Tono de pantalla, Privacidad, Migración de Android, botón Inicio, iMessage y FaceTime, Incorporación, Migración de Watch, Apariencia, Tiempo de uso, Actualización de software, Configuración de SIM.
Para elegir qué pantallas omitir, vaya a **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción** > elija un token > **Perfiles** > elija un perfil > **Propiedades** > **Personalización del Asistente de configuración** > elija **Ocultar** en todas las pantallas que quiera omitir > **Aceptar**.
Si crea un nuevo perfil o edita uno, las pantallas de omisión seleccionadas deben sincronizarse con el servidor MDM de Apple. Los usuarios pueden emitir una sincronización manual de los dispositivos para que no haya ningún retraso en la recogida de los cambios de perfil.

#### <a name="android-enterprise-app-we-app-deployment---1171203---"></a>Implementación de aplicaciones APP-WE de Android Enterprise<!-- 1171203 -->
En el caso de los dispositivos Android en un escenario de implementación de directiva de protección de aplicaciones sin inscripción (APP-WE) no inscrito, ahora puede usar Google Play administrado para implementar aplicaciones de la tienda y aplicaciones de LOB en los usuarios. En concreto, puede brindar a los usuarios finales un catálogo de aplicaciones y experiencia de instalación que ya no requiere que los usuarios finales flexibilicen la posición de seguridad de sus dispositivos al permitir instalaciones de orígenes desconocidos. Además, este escenario de implementación proporcionará una mejor experiencia del usuario final.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="scope-tags-for-apps---1081941---"></a>Etiquetas de ámbito para las aplicaciones<!-- 1081941 -->
Puede crear etiquetas de ámbito para limitar el acceso a roles y aplicaciones. Puede agregar una etiqueta de ámbito a una aplicación para que solo los usuarios con roles que también tengan asignada esa etiqueta de ámbito puedan acceder a la aplicación. Actualmente, no es posible asignar etiquetas de ámbito a las aplicaciones que se agregan a Intune desde Google Play administrado o a aquellas que se compran mediante el Programa de Compras por Volumen de Apple (VPP), si bien será posible en el futuro. Para obtener más información, vea [Uso de etiquetas de ámbito para filtrar directivas](scope-tags.md).




<!-- ########################## -->
## <a name="december-2018"></a>Diciembre de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="updates-for-application-transport-security---748318---"></a>Actualizaciones para Seguridad de transporte de aplicaciones<!-- 748318 -->

Microsoft Intune admite la versión 1.2+ del protocolo Seguridad de la capa de transporte (TLS) para proporcionar el mejor cifrado en su clase, a fin de garantizar que Intune sea más seguro de forma predeterminada, y alinearlo con otros servicios de Microsoft, como Microsoft 365. Con el fin de satisfacer este requisito, en los portales de empresa de iOS y macOS se exigirán los requisitos de Seguridad de transporte de aplicaciones (ATS) actualizados de Apple que también requieren TLS 1.2+. ATS se utiliza para exigir una seguridad más estricta en todas las comunicaciones de aplicación a través de HTTPS. Este cambio afecta a los clientes de Intune que usan las aplicaciones Portal de empresa para iOS y macOS. Para más información, vea el [blog de soporte técnico de Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys---1832174---"></a>El SDK de aplicaciones de Intune admitirá claves de cifrado de 256 bits<!-- 1832174 -->
El SDK de aplicaciones de Intune para Android ahora usa claves de cifrado de 256 bits cuando el cifrado esté habilitado mediante las directivas de protección de aplicaciones. El SDK seguirá siendo compatible con las claves de 128 bits para mantener la compatibilidad con el contenido y las aplicaciones que usen las versiones anteriores del SDK.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices---3503442---"></a>Versión de actualización automática 4.5.0 de Microsoft necesaria para dispositivos macOS<!-- 3503442 -->
Para seguir recibiendo actualizaciones del Portal de empresa y otras aplicaciones de Office, los dispositivos macOS administrados por Intune se deben actualizar a la actualización automática 4.5.0 de Microsoft. Es posible que los usuarios ya tengan esta versión para sus aplicaciones de Office.

### <a name="device-management"></a>Administración de dispositivos

#### <a name="intune-requires-macos-1012-or-later---2827778---"></a>Intune requiere macOS 10.12 o versiones posteriores<!-- 2827778 -->
Intune ahora requiere macOS versión 10.12 o posterior. Los dispositivos con versiones anteriores de macOS no pueden usar el Portal de empresa para inscribirse en Intune. Para recibir asistencia de soporte técnico y nuevas características, los usuarios deben actualizar su dispositivo a macOS 10.12 o posterior y actualizar el Portal de empresa a la versión más reciente.

<!-- ########################## -->
## <a name="november-2018"></a>Noviembre de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices---1281677---"></a>Desinstalación de aplicaciones en dispositivos iOS supervisados corporativos<!-- 1281677 -->
Puede quitar cualquier aplicación en dispositivos iOS corporativos supervisados. Puede quitar cualquier aplicación estableciendo como destino grupos de usuarios o dispositivos con un tipo de asignación **Desinstalar**. Para dispositivos iOS personales o no supervisados, podrá quitar solo las aplicaciones que se instalaron mediante Intune.

#### <a name="downloading-intune-win32-app-content---2617320---"></a>Descarga de contenido de aplicaciones Win32 de Intune<!-- 2617320 -->
Los clientes Windows 10 RS3 y versiones posterior descargarán contenido de aplicaciones Win32 de Intune mediante un componente de Optimización de distribución del cliente Windows 10. La Optimización de distribución proporciona la funcionalidad punto a punto está activada de manera predeterminada. Actualmente, la Optimización de distribución se puede configurar según la directiva de grupo. Para más información, consulte el artículo sobre la [Optimización de distribución para Windows 10](/windows/deployment/update/waas-delivery-optimization).

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Menú de contenido de aplicaciones y dispositivos del usuario final<!-- 2771453 -->
Los usuarios finales ahora pueden usar el menú contextual del dispositivo y las aplicaciones para desencadenar acciones comunes, como cambiar el nombre de un dispositivo o comprobar el cumplimiento.

#### <a name="set-custom-background-in-managed-home-screen-app----3041945---"></a>Establecer un fondo personalizado en la aplicación Managed Home Screen <!-- 3041945 -->
Se está agregando una configuración que permitirá personalizar la apariencia del fondo de la aplicación Managed Home Screen en dispositivos Android Enterprise en pantalla completa con varias aplicaciones.  Para configurar el **fondo de dirección URL personalizado**, vaya a Intune en Azure Portal > Configuración del dispositivo. Seleccione un perfil de configuración del dispositivo actual o cree uno para editar su configuración de quiosco.
Para ver la configuración de pantalla completa, consulte las [restricciones de los dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply---3104570---"></a>Guardar y aplicar asignaciones de la directiva de protección de la aplicación<!-- 3104570 -->
Ahora puede controlar mejor las [asignaciones de la directiva de protección de la aplicación](../apps/app-protection-policies.md). Cuando selecciona *Asignaciones* para establecer o editar las asignaciones de una directiva, debe **guardar** la configuración antes de que se aplique el cambio. Use **Descartar** para borrar todos los cambios que haga sin guardar ningún cambio en las listas de inclusión o exclusión.  Como se requiere guardar o descartar, solo los usuarios deseados tienen asignada una directiva de protección de la aplicación.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later---3174639---"></a>Nueva configuración del explorador Microsoft Edge en Windows 10 y versiones posteriores<!-- 3174639 -->
Esta actualización incluye una nueva configuración para ayudar a controlar y administrar el explorador Microsoft Edge en los dispositivos. Para ver una lista de estas configuraciones, consulte[Restricciones de dispositivos para Windows 10 (y versiones posteriores)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies---3330037---"></a>Las nuevas aplicaciones son compatibles con las directivas de protección de aplicaciones<!-- 3330037 -->
Ahora puede administrar las aplicaciones siguientes con las [directivas de protección de aplicaciones de Intune](../apps/app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Use las directivas de protección de aplicaciones para proteger los datos corporativos y controlar la transferencia de datos de estas aplicaciones, como otras aplicaciones administradas por las directivas de Intune. Nota: Si Flow todavía no aparece en la consola, lo agregará al crear o editar directivas de protección de aplicaciones. Para hacerlo, use la opción **+ Más aplicaciones** y especifique el *id. de la aplicación* para Flow en el campo de entrada. Para Android use *com.microsoft.flow* y para iOS, *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles--2155106---"></a>Compatibilidad con OAuth de iOS 12 en perfiles de correo electrónico de iOS<!--2155106 -->
Los perfiles de correo electrónico iOS de Intune son compatibles con Open Authorization (OAuth) para iOS 12. Para ver esta característica, cree un perfil (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **iOS** como plataforma > **Correo electrónico** como tipo de perfil) o actualice un perfil de correo electrónico iOS existente. Si habilita OAuth en un perfil que ya se ha implementado en los usuarios, se les pedirá que se vuelvan a autenticar y que vuelvan a descargar su correo electrónico.

En [Perfiles de correo electrónico iOS](../configuration/email-settings-ios.md) hay más información sobre cómo usar OAuth en un perfil de correo electrónico.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios---3259404---"></a>Compatibilidad del control de acceso de red (NAC) con Citrix SSO para iOS<!-- 3259404 -->
Citrix lanzó una actualización para Citrix Gateway para permitir el control de acceso de red (NAC) para Citrix SSO para iOS en Intune. Puede optar por incluir un identificador de dispositivo en un perfil de VPN en Intune y luego insertar este perfil en los dispositivos iOS. Deberá instalar la actualización más reciente de Citrix Gateway para usar esta funcionalidad.

[Configuración de VPN en dispositivos iOS](../configuration/vpn-settings-ios.md#base-vpn-settings) proporciona más información sobre el uso de NAC, incluidos algunos requisitos adicionales. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown---1892471---"></a>Se muestran los números de versión y los números de compilación de iOS y macOS<!-- 1892471 -->
En **Conformidad de dispositivos** > **Conformidad de dispositivos** se muestran las versiones de los sistemas operativos iOS y macOS, que se pueden usar en las directivas de cumplimiento. Esta actualización incluye el número de compilación, que se puede configurar para ambas plataformas.
Cuando se publican las actualizaciones de seguridad, Apple normalmente deja el número de versión como está, pero actualiza el número de compilación. Si usa el número de compilación en una directiva de cumplimiento, puede comprobar fácilmente si hay instalada una actualización de vulnerabilidad.
Para usar esta característica, consulte las directivas de cumplimiento de [iOS](../protect/compliance-policy-create-ios.md#device-health) y [macOS](../protect/compliance-policy-create-mac-os.md#device-properties).

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later---2753807---"></a>Los círculos de actualizaciones se reemplazan por la configuración Optimización de distribución para Windows 10 y versiones posteriores<!-- 2753807 -->
Optimización de distribución es un perfil de configuración nuevo para Windows 10 y versiones posteriores. Esta característica proporciona una experiencia más simplificada para brindar actualizaciones de software a los dispositivos de la organización. Esta actualización también ayuda a entregar la configuración en círculos de actualizaciones nuevos y existentes con un perfil de configuración.
Para configurar un perfil de configuración de optimización de distribución, consulte la [configuración de Optimización de distribución de Windows 10 (y versiones posteriores)](../configuration/delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices---2827760---"></a>Nueva configuración de restricción de dispositivos agregada a dispositivos iOS y macOS<!-- 2827760 -->
Esta actualización incluye nuevas configuraciones para los dispositivos iOS y Mac OS que se lanzan con iOS 12:

**Configuración de iOS**: 
- General: bloquear la eliminación de aplicaciones (solo supervisado)
- General: bloquear el modo restringido USB (solo supervisado)
- General: exigir fecha y hora automáticas (solo supervisado)
- Contraseña: bloquear el relleno automático de contraseñas (solo supervisado)
- Contraseña: bloquear las solicitudes de proximidad de contraseñas (solo supervisadas)
- Contraseña: bloquear el uso compartido de contraseñas (solo supervisado)

**Configuración de macOS**: 
- Contraseña: bloquear el relleno automático de contraseñas
- Contraseña: bloquear las solicitudes de proximidad de contraseñas
- Contraseña: bloquear el uso compartido de contraseñas

Para más información sobre estas configuraciones, consulte la configuración de restricciones de dispositivos [iOS](../configuration/device-restrictions-ios.md) y [macOS](../configuration/device-restrictions-macos.md).

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview---1048100--"></a>Compatibilidad con Autopilot para dispositivos híbridos unidos a Azure Active Directory (versión preliminar)<!-- 1048100-->
Ahora puede configurar dispositivos híbridos unidos a Azure Active Directory mediante AutoPilot. Los dispositivos deben estar unidos a la red de la organización para usar la característica de AutoPilot híbrida. Para más información, vea [Implementar dispositivos unidos a Azure AD híbrido mediante Intune y Windows Autopilot (versión preliminar)](../../autopilot/windows-autopilot-hybrid.md).
Esta característica se implementará en toda la base de usuarios durante los próximos días. Por tanto, es posible que no pueda seguir estos pasos hasta que se implemente en su cuenta.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Seleccionar las aplicaciones de las que se realiza un seguimiento en la página de estado de la inscripción<!-- 2531007 -->
Puede elegir de qué aplicaciones se realiza un seguimiento en la página de estado de la inscripción. El usuario no puede usar el dispositivo hasta que se instalen estas aplicaciones. Para más información, consulte [Configurar una página de estado de inscripción](../enrollment/windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number--2595788---"></a>Búsqueda del dispositivo Autopilot por número de serie<!--2595788 -->
Ahora puede buscar dispositivos Autopilot por número de serie. Para hacerlo, elija **Inscripción de dispositivos** > **Inscripción de Windows** > **Dispositivos** > escriba un número de serie en el cuadro **Buscar por número de serie** > presione ENTRAR.

#### <a name="track-installation-of-office-proplus--2620217---"></a>Seguimiento de la instalación de Office Pro Plus<!--2620217 -->
Los usuarios pueden realizar un seguimiento del progreso de instalación de [Office ProPlus](../apps/apps-add-office365.md) en la [página de estado de la inscripción](../enrollment/windows-enrollment-status.md). Para más información, consulte [Configurar una página de estado de inscripción](../enrollment/windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low---2237572---"></a>Alertas sobre tokens de VPP que expiran próximamente o licencias del Portal de empresa a punto de agotarse<!-- 2237572 -->
Si usa el Programa de Compras por Volumen (VPP) para tener en servicio el Portal de empresa durante la inscripción de DEP, Intune le avisará cuando el token de VPP esté a punto de expirar y las licencias del Portal de empresa se estén agotando.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts--3006133---"></a>Compatibilidad del Programa de inscripción de dispositivos macOS para cuentas de Apple School Manager<!--3006133 -->
Intune permite usar el Programa de inscripción de dispositivos en dispositivos macOS para las cuentas de Apple School Manager.  Para más información, consulte el artículo sobre la [inscripción automática de dispositivos macOS con el Programa de inscripción de dispositivos de Apple o Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="new-intune-device-subscription-sku--3312071--"></a>Nueva SKU de suscripción a dispositivos de Intune<!--3312071-->
Para ayudar a reducir el costo de administración de dispositivos en las empresas, ahora tiene a su disposición una nueva SKU de suscripción basada en dispositivos. Las licencias de esta SKU de dispositivos de Intune se conceden mensualmente por dispositivo. El precio varía según el programa de licencias. Está disponible directamente mediante el centro de administración de Microsoft 365 y el [Contrato Enterprise](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), el [contrato de productos y servicios de Microsoft](https://www.microsoft.com/licensing/mpsa/default) (MPSA), los [contratos abiertos de Microsoft ](https://partner.microsoft.com/licensing/licensing-agreements) y los [proveedores de soluciones en la nube](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Administración de dispositivos

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes---3041935---"></a>Detener temporalmente el modo de pantalla completa en dispositivos Android para realizar cambios<!-- 3041935 -->
Al usar dispositivos Android en modo quiosco con varias aplicaciones, puede que un administrador de TI deba realizar cambios en el dispositivo. Esta actualización incluye una configuración nueva de pantalla completa con varias aplicaciones que permite que un administrador de TI pause de manera temporal la pantalla completa con un PIN y obtener acceso a todo el dispositivo.
Para ver la configuración de pantalla completa, consulte las [restricciones de los dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices----3042021---"></a>Habilitar el botón de inicio virtual en dispositivos Android Enterprise en pantalla completa <!-- 3042021 -->
Una nueva configuración permitirá a los usuarios pulsar un botón de tecla programable en su dispositivo para cambiar entre la aplicación Managed Home Screen y otras aplicaciones asignadas en su dispositivo de quiosco con varias aplicaciones asignadas. Esta configuración es especialmente útil en escenarios donde una aplicación de quiosco del usuario no responde correctamente al botón "Atrás". Podrá configurar esta opción para dispositivos Android corporativos de un solo uso. Para habilitar o deshabilitar el **botón de inicio virtual**, vaya a Intune en Azure Portal > Configuración del dispositivo. Seleccione un perfil de configuración del dispositivo actual o cree uno para editar su configuración de quiosco.
Para ver la configuración de pantalla completa, consulte las [restricciones de los dispositivos Android Enterprise](../configuration/device-restrictions-android-for-work.md).




<!-- ########################## -->
## <a name="october-2018"></a>Octubre de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="access-to-key-profile-properties-using-the-company-portal-app---772203---"></a>Acceso a las propiedades de perfil principales mediante la aplicación del Portal de empresa<!-- 772203 -->
Los usuarios finales pueden acceder ahora a las propiedades y acciones de cuenta principales, como el restablecimiento de contraseña, desde la aplicación del Portal de empresa. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios---1248481---"></a>Configuración de la directiva de protección de aplicaciones para el bloqueo de teclados de terceros en iOS<!-- 1248481 -->
En dispositivos iOS, los administradores de Intune pueden bloquear el uso de teclados de terceros al acceder a datos de la organización en aplicaciones protegidas mediante directivas. Cuando la directiva de protección de aplicaciones (APP) está configurada para bloquear teclados de terceros, el usuario del dispositivo recibe un mensaje la primera vez que interactúa con los datos corporativos al usar un teclado de terceros. Todas las demás opciones, que no afecten al teclado nativo, se bloquean y los usuarios de los dispositivos no podrán verlas. Los usuarios de los dispositivos verán el mensaje del cuadro de diálogo una vez. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices---1248496---"></a>Acceso a la cuenta de usuario de aplicaciones de Intune en dispositivos iOS y Android administrados<!-- 1248496 -->
Como administrador de Microsoft Intune, puede controlar qué cuentas de usuario se agregan a las aplicaciones de Microsoft Office en dispositivos administrados. Puede limitar el acceso solo a las cuentas de usuario de la organización permitidas y bloquear las cuentas personales en los dispositivos inscritos. 

#### <a name="outlook-ios-and-android-app-configuration-policy--1828527---"></a>Directiva de configuración de aplicaciones iOS y Android para Outlook<!--1828527 -->
Ahora, puede crear una directiva de configuración de aplicaciones de Outlook iOS y Android para usuarios locales que aprovechan la autenticación básica con el protocolo ActiveSync. Se agregarán opciones de configuración adicionales a medida que se habiliten en Outlook para iOS y Android.

#### <a name="microsoft-365-apps-for-enterprise-language-packs---1833450---"></a>Paquetes de idioma de las Aplicaciones de Microsoft 365 para empresas<!-- 1833450 -->
Como administrador de Intune, podrá implementar idiomas adicionales para las Aplicaciones de Microsoft 365 para aplicaciones empresariales administradas mediante Intune. La lista de idiomas disponibles incluye el **Tipo** de paquete de idioma (núcleo, parcial y corrección). En Azure Portal, seleccione **Microsoft Intune** > **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. En la lista **Tipo de aplicación** de la hoja **Agregar aplicación**, seleccione **Windows 10** en **Conjunto de aplicaciones de Office 365**. Seleccione **Idiomas** en la hoja **Configuración del conjunto de aplicaciones**.

#### <a name="windows-line-of-business-lob-apps-file-extensions---1884873---"></a>Extensiones de los archivos de aplicaciones de línea de negocio (LOB) de Windows<!-- 1884873 -->
Ahora, las extensiones de archivo de las aplicaciones de LOB de Windows incluirán las extensiones *.msi*, *.appx*, *.appxbundle*, *.msix* y *.msixbundle*. Puede agregar una aplicación en Microsoft Intune seleccionando **Aplicaciones cliente** > **Aplicaciones** > **Agregar**. Se mostrará el panel **Agregar aplicación**, que permite seleccionar el **tipo de aplicación**. En el caso de las aplicaciones de LOB de Windows, seleccione la aplicación de **línea de negocio** como el tipo de aplicación, elija el **archivo de paquete de aplicación** y, después, especifique un archivo de instalación con la extensión adecuada.

#### <a name="windows-10-app-deployment-using-intune---2309001---"></a>Implementación de aplicaciones Windows 10 con Intune<!-- 2309001 -->
Aprovechando la compatibilidad actual con aplicaciones de línea de negocio (LOB) y Microsoft Store para aplicaciones empresariales, los administradores pueden usar Intune para implementar la mayoría de las aplicaciones existentes de su organización a los usuarios finales en dispositivos Windows 10. Los administradores pueden agregar, instalar y desinstalar aplicaciones para los usuarios de Windows 10 en una variedad de formatos, como archivos MSI, Setup.exe o MSP. Intune evaluará las reglas de requisitos antes de realizar la descarga y la instalación, y notificará a los usuarios finales del estado o los requisitos de reinicio a través del Centro de actividades de Windows 10. Esta función desbloqueará de manera eficaz las organizaciones interesadas en el desplazamiento de esta carga de trabajo a Intune y la nube. Esta característica está actualmente en versión preliminar pública y esperamos poder agregarle nuevas funciones importantes en los próximos meses. 

#### <a name="app-protection-policy-app-settings-for-web-data---2662995---"></a>Configuración de directiva de protección de la aplicación (APP) de datos web<!-- 2662995 -->
La configuración de directiva APP de contenido web en dispositivos iOS y Android se actualizará para controlar mejor los vínculos web http y https, así como la transferencia de datos a través de vínculos universales de iOS y vínculos de aplicación de Android. 

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Menú de contenido de aplicaciones y dispositivos del usuario final<!-- 2771453 -->
Los usuarios finales ahora pueden usar el menú contextual de aplicaciones y dispositivos para desencadenar acciones comunes, como cambiar el nombre de un dispositivo o comprobar su cumplimiento. 

#### <a name="windows-company-portal-keyboard-shortcuts---2771518---"></a>Métodos abreviados de teclado del Portal de empresa de Windows<!-- 2771518 -->
Ahora, los usuarios finales podrán desencadenar acciones de aplicación y dispositivo en el Portal de empresa de Windows mediante métodos abreviados de teclado (aceleradores).

#### <a name="require-non-biometric-pin-after-a-specified-timeout---1506985---"></a>Solicitar PIN que no sea biométrico después de un tiempo de expiración especificado<!-- 1506985 -->
Al exigir un número de identificación personal no biométrico después de transcurrir un tiempo de expiración especificado por el administrador, Intune proporcionará una mayor seguridad para las aplicaciones compatibles con Administración de aplicaciones de móviles (MAM), ya que restringe el uso de identificación biométrica para el acceso a datos corporativos. La configuración afectará a los usuarios que dependen de Touch ID (iOS), Face ID (iOS), Android Biometric u otros métodos de autenticación biométrica futuros para tener acceso a aplicaciones compatibles con APP/MAM. Con esta configuración, los administradores de Intune tendrán un control más exhaustivo del acceso de los usuarios. De este modo, se evitan situaciones en las que un dispositivo con varias huellas digitales u otros métodos de acceso biométrico pueda revelar datos corporativos a un usuario incorrecto. En Azure Portal, abra **Microsoft Intune**. Seleccione **Aplicaciones cliente** > **Directivas de protección de aplicaciones** > **Agregar una directiva** > **Configuración**. En la **Acceso** encontrará ajustes específicos. Para obtener información sobre la configuración del acceso, vea la [configuración para iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) y la [configuración para Android](../apps/app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices---2244713---"></a>Configuración de transferencia de datos de APP de Intune en dispositivos iOS inscritos en MDM<!-- 2244713 -->
Podrá controlar por separado la configuración de la transferencia de datos de la aplicación de Intune en dispositivos iOS inscritos en MDM y la especificación de la identidad del usuario inscrito, que se conoce también como nombre principal de usuario (UPN). Los administradores que no usen el IntuneMAMUPN no observarán un cambio de comportamiento. Cuando esta función esté disponible, los administradores que usan el IntuneMAMUPN para controlar el comportamiento de la transferencia de datos en los dispositivos inscritos deben revisar la nueva configuración y actualizar la configuración de APP según sea necesario.

#### <a name="windows-10-win32-apps---2617325---"></a>Aplicaciones Win32 de Windows 10<!-- 2617325 -->
Puede configurar las aplicaciones Win32 para instalarlas en el contexto de usuario para usuarios individuales, en comparación con la instalación de la aplicación para todos los usuarios del dispositivo.

#### <a name="windows-win32-apps-and-powershell-scripts---2617330---"></a>Aplicaciones Win32 de Windows y scripts de PowerShell<!-- 2617330 -->
Los usuarios finales ya no tienen que iniciar sesión en el dispositivo para instalar las aplicaciones Win32 o ejecutar scripts de PowerShell. 

#### <a name="troubleshooting-client-app-installation---1363711---"></a>Solución de problemas de instalación de la aplicación cliente<!-- 1363711 -->
Puede solucionar los problemas para que las aplicaciones cliente se instalen correctamente si consulta la columna etiquetada como **Instalación de la aplicación** en la hoja **Solución de problemas**. Para ver la hoja **Solución de problemas**, en el portal de Intune, seleccione **Solución de problemas** en **Ayuda y soporte técnico**.

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Creación de sufijos DNS en los perfiles de configuración de VPN en dispositivos que ejecutan Windows 10<!-- 1333668 -->
Cuando se crea un perfil de configuración del dispositivo VPN (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para plataforma > **VPN** para tipo de perfil), se escriben algunos valores de DNS. Con esta actualización, también puede especificar varios **sufijos DNS** en Intune. Al usar los sufijos DNS, puede buscar un recurso de red mediante su nombre corto, en lugar del nombre de dominio completo (FQDN). Esta actualización también le permite cambiar el orden de los sufijos DNS en Intune.
[Configuración de VPN de Windows 10](../configuration/vpn-settings-windows-10.md#dns-settings) muestra la configuración de DNS actual.
Se aplica a: Dispositivos Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles---1333705---"></a>Compatibilidad con VPN siempre activa para perfiles de trabajo empresarial de Android<!-- 1333705 -->
En esta actualización, puede usar conexiones VPN siempre activas en dispositivos empresariales Android con perfiles de trabajo administrados. Las conexiones VPN siempre activas permanecen conectadas o se vuelven a conectar inmediatamente cuando el usuario desbloquea el dispositivo, cuando se reinicia el dispositivo o cuando cambia la red inalámbrica. También puede poner la conexión en modo “bloqueo”, que bloquea todo el tráfico de red hasta que la conexión VPN esté activa.
Puede habilitar la VPN siempre activa en **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Android empresarial** para plataforma > **Restricciones de dispositivo** > **Conectividad**.

#### <a name="issue-scep-certificates-to-user-less-devices---1744554---"></a>Emitir certificados SCEP para los dispositivos sin usuario<!-- 1744554 -->
Actualmente, los certificados se emiten a los usuarios. Con esta actualización, se pueden emitir certificados SCEP para los dispositivos, incluidos los dispositivos sin usuario, como los quioscos multimedia (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para plataforma > **Certificado SCEP** para perfil). Otras actualizaciones incluyen:
- La propiedad **Asunto** en un perfil SCEP pasará a ser un cuadro de texto personalizado y puede incluir nuevas variables. 
- La propiedad **Nombre alternativo del firmante (SAN)** en un perfil SCEP ahora es un formato de tabla y puede incluir nuevas variables. En la tabla un administrador puede agregar un atributo y rellenar el valor en un cuadro de texto personalizado. La SAN será compatible con los siguientes atributos: 
  - DNS
  - Dirección de correo electrónico
  - UPN

  Estas nuevas variables se pueden agregar con texto estático en un cuadro de texto de valor personalizado. Por ejemplo, el atributo DNS puede agregarse como `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Las llaves, los puntos y coma y los símbolos de barra vertical “ { } ; | ” no funcionará en el texto estático de la SAN. Las llaves solo deben rodear una de las nuevas variables de certificado de dispositivo que debe aceptar `Subject` o `Subject alternative name`. 

Nuevas variables de certificado de dispositivo:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
> - `{{FullyQualifiedDomainName}}` solo funciona para Windows y dispositivos unidos a dominios. 
> - Al especificar las propiedades del dispositivo como el IMEI, el número de serie y el nombre de dominio completo en el asunto o SAN para un certificado de dispositivo, tenga en cuenta que una persona con acceso al dispositivo podría suplantar estas propiedades. 

[Crear un perfil de certificado SCEP](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) enumera las variables actuales al crear un perfil de configuración de SCEP. 

Se aplica a: Windows 10 y posterior e iOS, compatible con Wi-Fi

#### <a name="remotely-lock-uncompliant-devices---2064495---"></a>Bloquear dispositivos no compatibles de forma remota<!-- 2064495 -->
Cuando un dispositivo no cumple los requisitos, puede crear una acción en la directiva de cumplimiento que bloquee el dispositivo de forma remota. En Intune > **Cumplimiento del dispositivo**, cree una nueva directiva o seleccione una directiva existente > **Propiedades**. Seleccione **Acciones en caso de incumplimiento** > **Agregar** y elija bloquear de forma remota el dispositivo.
Compatible con: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 y versiones posteriores 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal---2748224---"></a>Mejoras de perfil de quiosco multimedia de Windows 10 y versiones posteriores en Azure Portal<!-- 2748224 -->
Esta actualización incluye las siguientes mejoras para el perfil de configuración de dispositivo de quiosco multimedia de Windows 10 (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** para plataforma > **Versión preliminar de quiosco** para tipo de perfil): 
- Actualmente, puede crear varios perfiles de quiosco multimedia en el mismo dispositivo. Con esta actualización, Intune admitirá un solo perfil de quiosco multimedia por dispositivo. Si necesita varios perfiles de quiosco multimedia en un único dispositivo, puede usar un URI personalizado.
- En un perfil de **Quiosco con varias aplicaciones**, puede seleccionar el tamaño del icono de la aplicación y el orden del **Diseño del menú inicio** en la cuadrícula de la aplicación. Si prefiere una mayor personalización, puede cargar un archivo XML.
- La configuración del explorador de quiosco multimedia pasará a estar en la configuración de **Quiosco**. Actualmente, la configuración **Explorador web del quiosco** tiene su propia categoría en Azure Portal.
Se aplica a: Windows 10 y versiones posteriores

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device----2637704----"></a>Solicitud de PIN al cambiar las huellas digitales o Face ID en un dispositivo iOS <!-- 2637704  -->
Ahora se solicitará a los usuarios un PIN después de realizar cambios biométricos en su dispositivo iOS. Esto incluye los cambios en Face ID o huellas digitales registrados. El tiempo de la solicitud depende de la configuración del tiempo de expiración de *Volver a comprobar los requisitos de acceso después de (minutos)* .  Cuando no se establece ningún PIN, se solicita al usuario que establezca uno. 
 
Esta característica solo está disponible para iOS y requiere la participación de aplicaciones que integran Intune APP SDK para iOS, versión 9.0.1 o posterior. La integración del SDK es necesaria para poder aplicar el comportamiento en las aplicaciones de destino. Esta integración ocurre de manera gradual y depende de los equipos de la aplicación específica. Algunas aplicaciones participantes incluyen WXP, Outlook, Managed Browser y Yammer.

#### <a name="network-access-control-support-on-ios-vpn-clients---1333693---"></a>Compatibilidad del control de acceso a la red en clientes VPN de iOS<!-- 1333693 -->
Con esta actualización, hay una nueva configuración para habilitar el control de acceso de red (NAC) al crear un perfil de configuración de VPN de Cisco AnyConnect, F5 Access y Citrix SSO para iOS. Esta configuración permite que el identificador de NAC del dispositivo se incluya en el perfil de VPN. Actualmente, no existe ningún cliente de VPN ni solución de asociados de NAC que admita este nuevo identificador de NAC, pero le mantendremos informado en nuestra [entrada de blog de soporte técnico](https://aka.ms/iOS12_and_vpn) cuando estén disponibles.

Para usar NAC, deberá:
1. Optar por permitir que Intune incluya los identificadores de dispositivo en perfiles de VPN
2. Actualizar el software/firmware del proveedor de NAC con instrucciones directas de dicho proveedor

Para obtener información sobre esta configuración en un perfil de VPN para iOS, vea [Configuración de VPN en Microsoft Intune para dispositivos que ejecutan iOS](../configuration/vpn-settings-ios.md). Para obtener más información sobre el control de acceso de red, vea [Integración del control de acceso de red (NAC) con Intune](../protect/network-access-control-integrate.md). 

Se aplica a iOS.

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile---1818139---"></a>Eliminación de un perfil de correo electrónico de un dispositivo, incluso cuando solo hay un perfil<!-- 1818139 -->
Antes no se podía quitar un perfil de correo electrónico de un dispositivo *si* era el único perfil de correo electrónico. Con esta actualización, se ha cambiado este comportamiento y ahora se puede quitar un perfil de correo electrónico aunque sea el único perfil de este tipo del dispositivo. Vea [Configuración del correo electrónico en Microsoft Intune](../configuration/email-settings-configure.md) para obtener más información.

#### <a name="powershell-scripts-and-azure-ad---2309469---"></a>Scripts de PowerShell y Azure AD<!-- 2309469 -->
Los scripts de PowerShell en Intune pueden estar dirigidos a grupos de seguridad de dispositivos de Azure AD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nueva configuración predeterminada "Tipo de contraseña requerida" para Android, Android Enterprise<!-- 2649963 -->
Al crear una directiva de cumplimiento (**Intune** > **Conformidad de dispositivos** > **Directivas** > **Crear directiva** > **Android** o **Android Enterprise** para Plataforma > Seguridad del sistema), el valor predeterminado de **Tipo de contraseña requerida** cambiará:

Desde: Valor predeterminado del dispositivo Hasta: Al menos numérica

Se aplica a: Android, Android Enterprise

Para ver esta configuración, vaya a [Android](../protect/compliance-policy-create-android.md) y [Android Enterprise](../protect/compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile---2662938---"></a>Usar una clave precompartida en un perfil de Wi-Fi de Windows 10<!-- 2662938 -->
Con esta actualización, puede usar una clave precompartida (PSK) con el protocolo de seguridad WPA o WPA2-Personal para autenticar un perfil de configuración de Wi-Fi para Windows 10. También puede especificar la configuración de costo para una red de uso medido para la actualización del 10 de octubre de 2018 en dispositivos Windows 10.

Actualmente, debe importar un perfil de Wi-Fi o crear un perfil personalizado para usar una clave precompartida. [Configuración de Wi-Fi para Windows 10](../configuration/wi-fi-settings-windows.md) muestra la configuración actual. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices---3218390---"></a>Eliminación de certificados PKCS y SCEP de los dispositivos<!-- 3218390 -->
En algunos casos, los certificados PKCS y SCEP se conservaban en los dispositivos incluso si se quitaba una directiva de un grupo, se eliminaba una configuración o una implementación de cumplimiento, o bien un administrador actualizaba un perfil SCEP o PKCS existente. Esta actualización cambia el comportamiento. Hay algunos casos en los que los certificados PKCS y SCEP se quitan de los dispositivos y otros casos en los que dichos certificados se conservan. Vea [Eliminación de certificados SCEP y PKCS en Microsoft Intune](../protect/remove-certificates.md) para conocer estos casos.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance---2504381---"></a>Usar un equipo selector para cumplimiento en dispositivos macOS<!-- 2504381 -->
Esta actualización incluye el equipo selector de macOS para evaluar el cumplimiento de los dispositivos. Para configurar la directiva del equipo selector, vea [Incorporación de una directiva de cumplimiento de dispositivos macOS con Intune](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot---1558983---"></a>Aplicar perfil de Autopilot para dispositivos Windows 10 inscritos que aún no están registrados para Autopilot<!-- 1558983 -->
Puede aplicar perfiles de Autopilot para dispositivos Windows 10 inscritos que aún no se han registrado para Autopilot. En el perfil de Autopilot, elija la opción **Convertir todos los dispositivos de destino a Autopilot** para registrar automáticamente los dispositivos que no se han registrado para Autopilot con los servicios de implementación de Autopilot. Permita un plazo de 48 horas para que se procese el registro. Cuando se anule la inscripción del dispositivo y este se restablezca, Autopilot lo aprovisionará.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups---2526564---"></a>Crear y asignar varios perfiles de la página Estado de inscripción a grupos de Azure AD<!-- 2526564 -->
Ya puede [crear y asignar](../enrollment/windows-enrollment-status.md) varios perfiles de la página Estado de inscripción a grupos de Azure AD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune--2748613--"></a>Migración desde el Programa de inscripción de dispositivos a Apple Business Manager en Intune<!--2748613-->
Apple Business Manager (ABM) funciona en Intune, así que puede actualizar su cuenta desde el Programa de inscripción de dispositivos (DEP) a ABM. El proceso en Intune es el mismo. Para actualizar la cuenta de Apple de DEP a ABN, vaya a [https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page--2748656--"></a>Pestañas de estado de alerta e inscripción en la página de información general de inscripción de dispositivos<!--2748656-->
Ahora, las alertas y los errores de inscripción aparecen en pestañas distintas en la página de información general de inscripción de dispositivos.

#### <a name="enrollment-abandonment-report---1382924---"></a>Informe de abandono de la inscripción<!-- 1382924 -->
Un nuevo informe en el que se proporciona información detallada sobre las inscripciones abandonadas está disponible en **Inscripción de dispositivos** > **Supervisión**. Para obtener más información, vea [Company portal abandonment report](../enrollment/enrollment-report-company-portal-abandon.md) (Informe de abandono del portal de empresa).

#### <a name="new-azure-active-directory-terms-of-use-feature---2870393---"></a>Nuevos característica de términos de uso de Azure Active Directory<!-- 2870393 -->
Azure Active Directory tiene una característica de términos de uso que puede usar en lugar de los términos y condiciones existentes de Intune. La característica de términos de uso de Azure AD proporciona más flexibilidad sobre qué términos se van a mostrar y cuándo, mejor compatibilidad de localización, mayor control sobre cómo se representan los términos y creación de informes mejorada. La característica de términos de uso de Azure AD requiere Azure Active Directory Premium P1, que también forma parte del conjunto de aplicaciones Enterprise Mobility + Security E3. Para más información, vea el artículo [Administrar los términos y condiciones de acceso de los usuarios de su empresa](../enrollment/terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support--3188762--"></a>Compatibilidad con el modo de propietario del dispositivo Android<!--3188762-->
Para Samsung Knox Mobile Enrollment, Intune ahora admite la inscripción de dispositivos en el modo de administración de propietario del dispositivo Android. Los usuarios en redes Wi-Fi o de telefonía móvil se pueden inscribir con unas pocas pulsaciones al encender sus dispositivos por primera vez. Para más información, vea [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](../enrollment/android-samsung-knox-mobile-enroll.md) (Inscripción automática de dispositivos Android mediante Samsung Knox Mobile Enrollment).

### <a name="device-management"></a>Administración de dispositivos
#### <a name="new-settings-for-software-updates-----1907869---"></a>Nuevas configuraciones para actualizaciones de software  <!-- 1907869 -->  
- Ahora puede configurar algunas notificaciones para avisar a los usuarios finales sobre los reinicios necesarios para finalizar la instalación de las actualizaciones de software más recientes.   
- Ahora puede configurar un mensaje de advertencia de reinicio para los reinicios que se producen fuera de las horas de trabajo. Estos mensajes admiten escenarios BYOD.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id---2075110---"></a>Agrupación de dispositivos inscritos en Windows Autopilot por identificador de correlación<!-- 2075110 -->
Intune ahora admite la agrupación de dispositivos Windows mediante un identificador de correlación cuando se inscriban mediante [AutoPilot para dispositivos existentes](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) con Configuration Manager. El identificador de correlación es un parámetro del archivo de configuración de AutoPilot. Intune establecerá de forma automática el [atributo enrollmentProfileName de dispositivo de Azure AD](/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) para que sea igual a "OfflineAutopilotprofile-<correlator ID>". Esto permite la creación de grupos dinámicos de Azure AD arbitrarios en función del identificador de correlación a través del atributo enrollmentprofileName para las inscripciones de AutoPilot sin conexión. Para obtener más información, consulte [Windows Autopilot para dispositivos existentes](../../autopilot/enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies---2984657---"></a>Directivas de protección de aplicaciones de Intune<!-- 2984657 -->
Las directivas de protección de aplicaciones de Intune permiten configurar varias opciones de protección de datos para aplicaciones protegidas de Intune, como Microsoft Outlook y Microsoft Word. Se ha cambiado la apariencia de estas opciones para [iOS](../apps/app-protection-policy-settings-ios.md) y [Android](../apps/app-protection-policy-settings-android.md) a fin de facilitar su detección de forma individual. Hay tres categorías de configuraciones de directiva:
- **Reubicación de datos** : este grupo incluye los controles de prevención de pérdida de datos (DLP), como restricciones para cortar, copiar, pegar y guardar como. Esta configuración determina cómo los usuarios interactúan con los datos en las aplicaciones.
- **Requisitos de acceso**: este grupo contiene las opciones de PIN por aplicación que determinan cómo el usuario final tiene acceso a las aplicaciones en un contexto de trabajo.  
- **Inicio condicional** : este grupo contiene configuraciones como la configuración mínima del sistema operativo, la detección de dispositivos liberados o modificados y períodos de gracia sin conexión.  
  
No cambia la funcionalidad de la configuración, pero será más fácil encontrarla cuando se trabaja en el flujo de creación de la directiva.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices---2451462----"></a>Restricción de aplicaciones y bloqueo del acceso a los recursos de la compañía dispositivos Android<!-- 2451462  -->  
En **Conformidad de dispositivos** > **Directivas** > **Crear directiva** > **Android** > **Seguridad del sistema**, hay un nuevo valor en la sección *Seguridad del dispositivo* que se llama **Aplicaciones restringidas**. El valor **Aplicaciones restringidas** usa una directiva de cumplimiento para bloquear el acceso a recursos de la compañía si ciertas aplicaciones están instaladas en el dispositivo. El dispositivo se considera no compatible hasta que las aplicaciones restringidas se quitan del dispositivo.
Se aplica a: 
- Android

### <a name="intune-apps"></a>Aplicaciones de Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps---1727158---"></a>Intune admitirá un tamaño de paquete máximo de 8 GB para las aplicaciones de línea de negocio<!-- 1727158 -->
Intune aumentó el tamaño de paquete máximo a 8 GB para las aplicaciones de línea de negocio (LOB). Para más información, vea [Agregar aplicaciones a Microsoft Intune](../apps/apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app---1916266---"></a>Adición de una imagen de marca personalizada para la aplicación Portal de empresa<!-- 1916266 -->
Como administrador de Microsoft Intune, puede cargar una imagen de marca personalizada que se mostrará como imagen de fondo en la página de perfil del usuario en la aplicación Portal de empresa de iOS. Para obtener más información sobre cómo configurar la aplicación Portal de empresa, vea [How to configure the Microsoft Intune Company Portal app](../apps/company-portal-app.md) (Cómo configurar la aplicación Portal de empresa de Microsoft Intune).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines---2971030---"></a>Intune mantendrá el idioma de Office localizado al actualizar Office en los equipos de los usuarios finales<!-- 2971030 -->
Cuando Intune instala Office en los equipos de los usuarios finales, estos recibirán automáticamente los mismos paquetes de idioma que tenían con las instalaciones de Office .MSI anteriores. Para obtener más información, vea [Asignación de aplicaciones de Microsoft 365 a dispositivos Windows 10 con Microsoft Intune](../apps/apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal---3076965---"></a>Nueva experiencia de soporte técnico de Intune en el portal de administración de dispositivos de Microsoft 365<!-- 3076965 -->
Se va a lanzar una nueva experiencia de ayuda y soporte técnico para Intune en el [portal de administración de dispositivos de Microsoft 365]( https://endpoint.microsoft.com). La nueva experiencia le permite describir el problema con sus propias palabras y recibir información sobre solución de problemas y contenido de corrección basado en la Web. Estas soluciones se ofrecen mediante un algoritmo de aprendizaje automático con reglas, basado en las consultas de los usuarios.  

Además de instrucciones específicas del problema, también puede utilizar el nuevo flujo de trabajo de creación de casos para abrir una incidencia de soporte técnico por teléfono o correo electrónico.  

Los clientes que forman parte del lanzamiento, esta nueva experiencia reemplaza la actual experiencia de ayuda y soporte técnico de un conjunto estático de opciones previamente seleccionadas que se basan en el área de la consola en la que se encuentra cuando abre la sección Ayuda y soporte técnico.  

*Esta nueva experiencia de ayuda y soporte técnico se va a lanzar para algunos pero no todos los inquilinos y está disponible en el portal de administración de dispositivos. Los participantes de esta nueva experiencia se seleccionan aleatoriamente entre los inquilinos de Intune disponibles. Se agregarán nuevos inquilinos a medida que se expanda el lanzamiento.*  

Para obtener más información, vea [Nueva experiencia de Ayuda y soporte técnico](get-support.md#help-and-support-experience) en Cómo obtener asistencia para Microsoft Intune.  

#### <a name="powershell-module-for-intune--preview-available---951068---"></a>Módulo de PowerShell para Intune: versión preliminar disponible<!-- 951068 -->
Ya hay disponible en [GitHub](https://aka.ms/intunepowershell) una versión preliminar de un nuevo módulo de PowerShell, que proporciona compatibilidad con la API de Intune a través de Microsoft Graph. Para obtener más información sobre cómo usar este módulo, consulte el archivo Léame en esa ubicación.

<!-- ########################## -->
## <a name="september-2018"></a>Septiembre de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="remove-duplication-of-app-protection-status-tiles---3083391---"></a>Eliminación de la duplicación de los iconos de estado de protección de la aplicación<!-- 3083391 -->
Los iconos **Estado del usuario para iOS** y **Estado del usuario para Android** estaban presentes en las páginas **Aplicaciones cliente: Información general** y **Aplicaciones cliente: Estado de protección de la aplicación**. Se han quitado los iconos de estado de la página **Aplicaciones cliente: Información general** para evitar la duplicación. 

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="support-for-more-third-party-certification-authorities-ca---3093107---"></a>Compatibilidad con más entidades de certificación de terceros (CA)<!-- 3093107 -->
Si usa el protocolo de inscripción de certificados Simple (SCEP), ya puede emitir nuevos certificados y renovarlos en dispositivos móviles con Windows, iOS, Android y macOS.

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="intune-moves-to-support-ios-10-and-later---2454656---"></a>Intune cambia para admitir iOS 10 y versiones posteriores<!-- 2454656 -->  
Ahora la inscripción de Intune, el Portal de empresa y el explorador administrado incluyen dispositivos iOS que tengan solo la versión iOS 10 y posteriores. Para comprobar si hay dispositivos o usuarios que se vean afectados en la organización, vaya a Intune en Azure Portal > **Dispositivos** > **Todos los dispositivos**. Filtre por sistema operativo y, después, haga clic en **Columnas** para mostrar los detalles de la versión de sistema operativo. Pida a los usuarios que actualicen sus dispositivos a una versión del sistema operativo que sea compatible.  

Si posee o quiere inscribir alguno de los siguientes dispositivos, debe estar al tanto de que solo admiten iOS 9 y versiones anteriores.  Para seguir accediendo al Portal de empresa de Intune, debe actualizar estos dispositivos a dispositivos compatibles con iOS 10 o versiones posteriores:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3ª generación) 
* iPad Mini (1ª generación)  

### <a name="device-management"></a>Administración de dispositivos

#### <a name="microsoft-365-device-management-administration-center---3078424---"></a>Centro de Administración de dispositivos de Microsoft 365<!-- 3078424 -->
Una de las promesas de Microsoft 365 es la simplificación de la administración. Con los años, hemos ido integrando servicios de Microsoft 365 back-end para entregar escenarios de extremo a extremo, como el acceso condicional de Intune y Azure AD. El nuevo [Centro de administración de Microsoft 365](https://endpoint.microsoft.com) consolida, simplifica e integra la experiencia de administración. El área de trabajo especialista en administración de dispositivos proporciona fácil acceso a todas las tareas y la información relacionadas con la administración de dispositivos y aplicaciones que necesita su organización. Esperamos que esto se convierta en el área de trabajo principal en la nube para los equipos informáticos de usuario final de empresa.


<!-- ########################## -->
## <a name="august-2018"></a>Agosto de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types---1520957---"></a>Compatibilidad de túnel de paquete para perfiles de VPN por aplicación de iOS para los tipos de conexión Pulse Secure y personalizados<!-- 1520957 -->
Al usar perfiles de VPN por aplicación de iOS, puede elegir entre usar tunelización de capa de aplicación (app-proxy) o tunelización de nivel de paquete (packet-tunnel). Estas opciones están disponibles con los tipos de conexión siguientes:
- VPN personalizada
- Pulse Secure. Si no está seguro de qué valor usar, consulte la documentación de su proveedor de VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device---1949583---"></a>Retraso cuando las actualizaciones de software de iOS se muestran en el dispositivo<!-- 1949583 -->
En Intune > **Actualizaciones de software** > **Directivas de actualización para iOS**, puede configurar los días y las horas en los que no desea que los dispositivos instalen ninguna actualización. En una actualización futura, podrá retrasar entre 1 y 90 días el momento en el que una actualización de software se muestra de forma visible en el dispositivo. 
[Configurar directivas de actualización de iOS en Microsoft Intune](../protect/software-updates-ios.md) enumera la configuración actual.

#### <a name="microsoft-365-apps-for-enterprise-version---2213968---"></a>Versión de las Aplicaciones de Microsoft 365 para empresas<!-- 2213968 -->
Al asignar las Aplicaciones de Microsoft 365 para aplicaciones empresariales a dispositivos Windows 10 mediante Intune, podrá seleccionar la versión de Office. En Azure Portal, seleccione **Microsoft Intune** > **Aplicaciones** > **Agregar aplicación**. Después, seleccione **Conjunto de aplicaciones Office 365 ProPlus (Windows 10)** en la lista desplegable **Tipo**. Seleccione **Configuración del conjunto de aplicaciones** para mostrar la hoja asociada. Establezca **Canal de actualización** en un valor, como **Mensualmente**. Si lo desea, quite otra versión de Office (msi) de los dispositivos del usuario final seleccionando **Sí**. Seleccione **Específico** para instalar una versión específica de Office del canal seleccionado en los dispositivos del usuario final. En este momento, en **Versión específica**, puede seleccionar la versión de Office que desee usar. Las versiones disponibles cambiarán con el tiempo. Por lo tanto, al crear una nueva implementación, las versiones disponibles pueden ser más recientes y no tener determinadas versiones anteriores disponibles. Las implementaciones actuales seguirán implementando la versión anterior, pero la lista de versiones se actualizará continuamente por canal. Para más información, vea [Información general de los canales de actualización para Aplicaciones de Microsoft 365](/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn---2282852---"></a>Compatibilidad con la configuración de DNS de registro para VPN de Windows 10<!-- 2282852 -->
Con esta actualización, puede configurar perfiles de VPN de Windows 10 para registrar dinámicamente las direcciones IP asignadas a la interfaz VPN con el DNS interno, sin necesidad de usar perfiles personalizados.
Para obtener información sobre la configuración de perfil de VPN actual disponible, vea [Configuración de VPN de Windows 10](../configuration/vpn-settings-windows-10.md).

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name--2652728--"></a>El instalador de Portal de empresa para macOS ahora incluye el número de versión en el nombre de archivo del instalador<!--2652728-->

#### <a name="ios-automatic-app-updates---2729759---"></a>Actualizaciones de aplicaciones automáticas de iOS<!-- 2729759 -->
Las actualizaciones de aplicaciones automáticas funcionan para las aplicaciones con licencia de dispositivo y usuario para la versión 11.0 de iOS y versiones posteriores.

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="windows-hello-will-target-users-and-devices---1106609---"></a>Windows Hello estará dirigido a usuarios y dispositivos<!-- 1106609 -->
Cuando crea una directiva [Windows Hello para empresas](../protect/windows-hello.md), se aplica a todos los usuarios dentro de la organización (inquilinos). Con esta actualización, la directiva también se puede aplicar a determinados usuarios o específicos mediante una directiva de configuración de dispositivo (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Identity Protection** > **Windows Hello para empresas**).
En Intune en Azure Portal, la configuración de Windows Hello ahora existe tanto en **Inscripción del dispositivo** como en **Configuración del dispositivo**. **Inscripción del dispositivo** tiene como destino toda la organización (inquilinos) y es compatible con Windows AutoPilot (OOBE). **Configuración del dispositivo** tiene como destino los dispositivos y usuarios mediante una directiva que se aplica durante la inserción en el repositorio.
Esta característica se aplica a:  
- Windows 10 y versiones posteriores
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios---1769858---"></a>Zscaler es una conexión disponible para los perfiles VPN en iOS<!-- 1769858 -->
Cuando crea un perfil de configuración de dispositivo de VPN para iOS (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > plataforma **iOS** > tipo de perfil **VPN**), hay varios tipos de conexión, incluidos Cisco, Citrix, etc. Esta actualización agrega Zscaler como un tipo de conexión. 
[Configuración de VPN para dispositivos que ejecutan iOS](../configuration/vpn-settings-ios.md) enumera los tipos de conexión disponibles.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10---1879077---"></a>Modo FIPS para perfiles de Wi-Fi de empresa para Windows 10<!-- 1879077 -->
Ahora puede habilitar el modo Estándar federal de procesamiento de información (FIPS) para los perfiles de Wi-Fi de empresa para Windows 10 en Intune en Azure Portal. Asegúrese de que el modo FIPS está habilitado en la infraestructura de Wi-Fi si lo habilita en los perfiles de Wi-Fi.
En [Configuración de Wi-Fi para dispositivos Windows 10 y versiones posteriores en Intune](../configuration/wi-fi-settings-windows.md) se muestra cómo crear un perfil de Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview---1958649---"></a>Control del modo S en Windows 10 y dispositivos posteriores: versión preliminar pública<!-- 1958649 -->
Con esta actualización de características, puede crear un perfil de configuración de dispositivo que haga cambiar el modo S de un dispositivo Windows 10 o evitar que los usuarios cambien el modo S del dispositivo. Esta característica está en Intune > **Configuración del dispositivo** > **Perfiles** >  **Windows 10 y versiones posteriores** > **Edition upgrade and mode switch (Actualización de edición y conmutación de modo)** .
En [Presentamos Windows 10 en modo S](https://www.microsoft.com/windows/s-mode) se proporciona más información sobre el modo S.
Se aplica a: la compilación más reciente de [Windows Insider](/windows-insider/at-work-pro/) (todavía en versión preliminar).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile---2144658---"></a>Paquete de configuración de ATP de Windows Defender agregado automáticamente al perfil de configuración<!-- 2144658 -->
Cuando se usa la [Protección contra amenazas avanzada y la incorporación](../protect/advanced-threat-protection-configure.md#onboard-devices) de dispositivos en Intune, antes era necesario descargar un paquete de configuración y agregarlo al perfil de configuración. Con esta actualización, Intune obtiene de forma automática el paquete del Centro de seguridad avanzada de Windows Defender y lo agrega al perfil.
Se aplica a Windows 10 y versiones posteriores.

#### <a name="require-users-to-connect-during-device-setup--2311457--"></a>Requerir que los usuarios se conecten durante la instalación del dispositivo<!--2311457-->
Ahora puede establecer los perfiles de dispositivo para requerir que el dispositivo se conecte a una red antes de continuar más allá de la página Red durante la instalación de Windows 10. Aunque esta característica está en versión preliminar, se requiere una compilación 1809 de Windows Insider o una versión posterior para usar esta configuración.
Se aplica a: la compilación más reciente de [Windows Insider](/windows-insider/at-work-pro/) (todavía en versión preliminar).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices---2451462---"></a>Restricción de aplicaciones y bloqueo del acceso a los recursos de la empresa en dispositivos iOS y Android Enterprise<!-- 2451462 -->
En **Conformidad de dispositivos** > **Directivas** > **Crear directiva** > **iOS** > **Seguridad del sistema**, hay una nueva opción **Aplicaciones restringidas**. Esta nueva opción usa una directiva de cumplimiento para bloquear el acceso a recursos de la compañía si ciertas aplicaciones están instaladas en el dispositivo. El dispositivo se considera no compatible hasta que las aplicaciones restringidas se quitan del dispositivo.
Se aplica a iOS.

#### <a name="modern-vpn-support-updates-for-ios---2459928-1819876-and-2650856---"></a>Actualizaciones de compatibilidad con VPN moderna para iOS<!-- 2459928, 1819876, and 2650856 -->
Esta actualización agrega compatibilidad con los siguientes clientes VPN de iOS:
- F5 Access (versión 3.0.1 y versiones posteriores)
- SSO de Citrix
- GlobalProtect de Palo Alto Networks versión 5.0 y versiones posteriores. También en esta actualización:
- El nombre del tipo de conexión de **F5 Access** existente se cambia a **F5 Access Legacy** para iOS.
- El nombre del tipo de conexión de **GlobalProtect de Palo Alto Networks** existente se cambia a **GlobalProtect de Palo Alto Networks (legacy)** para iOS.
Los perfiles existentes con estos tipos de conexión siguen funcionando con su correspondiente cliente heredado de VPN. Si usa Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN o GlobalProtect de Legacy Palo Alto Networks versión 4.1 y versiones anteriores con iOS, debe cambiar a las nuevas aplicaciones. Hágalo tan pronto como sea posible para garantizar que el acceso VPN esté disponible para dispositivos iOS a medida que se actualicen a iOS 12.
Para obtener más información sobre iOS 12 y los perfiles de VPN, vea el [blog del equipo de soporte técnico de Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal---2469637---"></a>Exportación de las directivas de cumplimiento del Portal de Azure clásico para volver a crearlas en Intune en Azure Portal<!-- 2469637 -->
Las directivas de cumplimiento creadas en el Portal de Azure clásico dejarán de utilizarse. Puede revisar y eliminar todas las directivas de cumplimiento existentes, pero no podrá actualizarlas. Si tiene que migrar las directivas de cumplimiento a Intune en Azure Portal, puede exportarlas como un archivo separado por comas (archivo *.csv*). Después, use los detalles del archivo para volver a crear estas directivas en Intune en Azure Portal.

> [!IMPORTANT]
> Cuando se retire el Portal de Azure clásico, ya no podrá acceder ni ver las directivas de cumplimiento. Por tanto, asegúrese de exportar las directivas y volverlas a crear en Azure Portal antes de la retirada del Portal de Azure clásico.

#### <a name="better-mobile---new-mobile-threat-defense-partner---22662717---"></a>Better Mobile: nuevo socio de Mobile Threat Defense<!-- 22662717 -->
Puede controlar el acceso desde dispositivos móviles a los recursos corporativos mediante el acceso condicional basado en la evaluación de riesgos efectuada por Better Mobile, una solución de Mobile Threat Defense integrada en Microsoft Intune.

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in--1067692---"></a>Bloqueo del Portal de empresa en el modo de aplicación única hasta el inicio de sesión del usuario<!--1067692 --> 
Ahora tiene la opción de ejecutar Portal de empresa en el modo de aplicación única si autentica un usuario a través de Portal de empresa en lugar del Asistente para configuración durante la inscripción de DEP. Esta opción bloquea el dispositivo inmediatamente después de completar el Asistente para configuración, de manera que un usuario debe iniciar sesión para acceder al dispositivo. Este proceso garantiza que el dispositivo completa la incorporación y no está huérfano en un estado sin ningún usuario asociado.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device--1346521---"></a>Asignación de un usuario y un nombre descriptivo a un dispositivo AutoPilot<!--1346521 -->
Ahora puede [asignar un usuario a un único dispositivo Autopilot ](../../autopilot/enrollment-autopilot.md). Los administradores también podrán proporcionar nombres descriptivos para saludar a los usuarios al configurar sus dispositivos con AutoPilot.
Se aplica a: la compilación más reciente de [Windows Insider](/windows-insider/at-work-pro/) (todavía en versión preliminar).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment---1608345---"></a>Uso de licencias de dispositivo de VPP para el aprovisionamiento previo de Portal de empresa durante la inscripción de DEP<!-- 1608345 -->
Ahora puede usar licencias de dispositivo del Programa de compras por volumen (VPP) para aprovisionar previamente Portal de empresa durante las inscripciones en el Programa de inscripción de dispositivos (DEP). Para ello, al [crear o editar un perfil de inscripción](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), especifique el token de VPP que quiera usar para instalar Portal de empresa. Asegúrese de que el token no expire y que dispone de suficientes licencias para la aplicación de Portal de empresa. En los casos en los que el token expire o se agoten las licencias, Intune instalará el Portal de empresa del App Store (se solicitará un identificador de Apple).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning---2237634---"></a>Confirmación requerida para eliminar el token de VPP que se usa para preaprovisionar el Portal de empresa<!-- 2237634 -->
Ahora se solicita confirmación para eliminar un token del Programa de Compras por Volumen (VPP) si se usa para preaprovisionar el Portal de empresa durante la inscripción de DEP.

#### <a name="block-windows-personal-device-enrollments---1849498---"></a>Bloqueo de inscripciones de dispositivos personales Windows<!-- 1849498 -->
Puede [bloquear la inscripción de dispositivos personales Windows](../enrollment/enrollment-restrictions-set.md) con la [administración de dispositivos móviles](../enrollment/windows-enroll.md) en Intune. Los dispositivos inscritos con el [agente de PC de Intune](manage-windows-pcs-with-microsoft-intune.md) no se puede bloquear con esta característica. Esta característica se desplegará gradualmente durante las próximas semanas, por lo que quizá no la vea de inmediato en la interfaz de usuario.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile--1849855--"></a>Especificación de patrones de nombre de equipo en un perfil de AutoPilot<!--1849855-->
Puede [especificar una plantilla de nombre de equipo](../../autopilot/enrollment-autopilot.md#create-an-autopilot-deployment-profile) para generar y establecer el [nombre de equipo](/windows/client-management/mdm/accounts-csp) durante la inscripción de AutoPilot. Se aplica a: la compilación más reciente de [Windows Insider](/windows-insider/at-work-pro/) (todavía en versión preliminar).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page--1901669---"></a>Para los perfiles de Windows AutoPilot, se ocultan las opciones de cambio de cuenta en las páginas de inicio de sesión y de error de dominio de la empresa<!--1901669 -->
Hay [nuevas opciones de perfil de Windows AutoPilot](../../autopilot/enrollment-autopilot.md#create-an-autopilot-deployment-profile) para que los administradores oculten las opciones de cambio de cuenta en las páginas de inicio de sesión de la empresa y de error de dominio. La ocultación de estas opciones requiere que se configure la personalización de marca de empresa en Azure Active Directory. Se aplica a: la compilación más reciente de [Windows Insider](/windows-insider/at-work-pro/) (todavía en versión preliminar).

### <a name="macos-support-for-apple-device-enrollment-program---747651---"></a>Compatibilidad de macOS para el Programa de inscripción de dispositivos de Apple<!-- 747651 -->
Intune ahora admite la inscripción de dispositivos macOS el Programa de inscripción de dispositivos de Apple (DEP). Para obtener más información, vea [Inscripción automática de dispositivos macOS con el Programa de inscripción de dispositivos de Apple](../enrollment/device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Administración de dispositivos

#### <a name="delete-jamf-devices---2653306--"></a>Eliminación de dispositivos Jamf<!-- 2653306-->
Puede eliminar los dispositivos administrados por JAMF desde **Dispositivos** > seleccione el dispositivo de Jamf > **Eliminar**.

#### <a name="change-terminology-to-retire-and-wipe---2175759---"></a>Cambio de terminología para "retirar" y "borrar"<!-- 2175759 -->
Para mantener la coherencia con Graph API, en la documentación y la interfaz de usuario de Intune se han cambiado los términos siguientes:
- **Eliminar datos de la compañía** se cambiará por "retirar".
- **Restablecimiento de fábrica** cambiará a **borrar**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate---297909500--"></a>Cuadro de diálogo de confirmación si el administrador intenta eliminar el certificado push MDM<!-- 297909500-->
Si alguien intenta eliminar un certificado push MDM de Apple, en un cuadro de diálogo de confirmación se muestra el número de dispositivos iOS y macOS relacionados. Si se elimina el certificado, será necesario volver a inscribir estos dispositivos.

#### <a name="additional-security-settings-for-windows-installer---2282430---"></a>Configuración de seguridad adicional de Windows Installer<!-- 2282430 -->
Puede dejar que los usuarios controlen las instalaciones de aplicaciones. Si lo permite, las instalaciones que antes se detendrían debido a una infracción de seguridad podrán seguir funcionando. Puede indicar a Windows Installer que use permisos elevados cuando instale un programa en un sistema. Además, los elementos protegidos por WIP (Windows Information Protection) se pueden indexar y los metadatos relativos a estos elementos se pueden almacenar en una ubicación sin cifrar. Cuando la directiva está deshabilitada, los elementos protegidos por WIP no se indexan y no se muestran en los resultados de Cortana o del explorador de archivos. La funcionalidad de estas opciones está deshabilitada de forma predeterminada. 

#### <a name="new-user-experience-update-for-the-company-portal-website--2000968---"></a>Nueva actualización de la experiencia de usuario para el sitio web del Portal de empresa<!--2000968 -->
Tras escuchar los comentarios de los clientes, hemos agregado características nuevas al sitio web de Portal de empresa. Experimentará una mejora considerable en las funciones y la facilidad de uso actual de los dispositivos. Se ha aplicado un nuevo diseño moderno y dinámico a las áreas del sitio, como los detalles del dispositivo, los comentarios, el soporte técnico y la descripción general del dispositivo. También verá:

- Flujos de trabajo optimizados en todas las plataformas de dispositivo
- Flujos mejorados para la inscripción e identificación de dispositivos
- Mensajes de error más útiles
- Lenguaje más descriptivo y menos terminología técnica
- Capacidad de compartir vínculos directos a aplicaciones
- Rendimiento mejorado de los catálogos de aplicaciones de gran tamaño
- Aumento de accesibilidad para todos los usuarios  

Se ha actualizado la [documentación del sitio web de Portal de empresa de Intune](../user-help/using-the-intune-company-portal-website.md) para reflejar estos cambios. Para ver un ejemplo de las mejoras de la aplicación, vea [Actualizaciones de la interfaz de usuario para las aplicaciones de usuario final de Intune](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Detección de jailbreak mejorada en informes de cumplimiento<!-- 2198738 -->
Ahora la configuración de detección de jailbreak mejorada aparece en todos los informes de cumplimiento en la consola de administración.

### <a name="role-based-access-control"></a>Control de acceso basado en roles.

#### <a name="scope-tags-for-policies--1081974---"></a>Etiquetas de ámbito para las directivas<!--1081974 -->
Puede crear [etiquetas de ámbito](scope-tags.md) para limitar el acceso a los recursos de Intune. Agregue una etiqueta de ámbito a una asignación de roles y luego agregue dicha etiqueta a un perfil de configuración. El rol solo tendrá acceso a los recursos con perfiles de configuración que tengan etiquetas de ámbito coincidentes (o no tengan ninguna etiqueta de ámbito).





<!-- ########################## -->
## <a name="july-2018"></a>Julio de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="line-of-business-lob-app-support-for-macos---1895847---"></a>Compatibilidad con aplicaciones de línea de negocio (LOB) para macOS<!-- 1895847 -->
Microsoft Intune permite implementar aplicaciones de LOB macOS como **Required** (Obligatoria) o como **Available with enrollment** (Disponible con inscripción). Los usuarios finales pueden obtener las aplicaciones implementadas como **Available** (Disponible) a través del Portal de empresa para macOS o del [sitio web del Portal de empresa](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode---2051098---"></a>Compatibilidad con aplicaciones integradas de iOS para pantalla completa<!-- 2051098 -->
Además de las aplicaciones de la Tienda y las aplicaciones administradas, ahora puede seleccionar una aplicación integrada (como Safari) que se ejecuta en pantalla completa en un dispositivo iOS.

#### <a name="edit-your-microsoft-365-apps-for-enterprise-app-deployments---2150145---"></a>Edición de las Aplicaciones de Microsoft 365 para implementaciones de aplicaciones empresariales<!-- 2150145 -->
Como administrador de Microsoft Intune, tiene más capacidad para editar las Aplicaciones de Microsoft 365 para implementaciones de aplicaciones empresariales. Además, ya no tiene que eliminar las implementaciones para cambiar las propiedades del conjunto. En Azure Portal, seleccione **Microsoft Intune** > **Aplicaciones cliente** > **Aplicaciones**. En la lista de aplicaciones, seleccione su conjunto de Aplicaciones de Microsoft 365 para empresas.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available---2744271--"></a>El SDK de aplicaciones de Intune para Android ya está disponible<!-- 2744271-->
Hay disponible una versión actualizada del SDK para aplicaciones de Intune para Android compatible con la versión de Android P. Si es desarrollador de aplicaciones y usa el SDK de Intune para Android, debe instalar la versión actualizada del SDK para aplicaciones de Intune a fin de garantizar que la funcionalidad de Intune dentro de las aplicaciones Android seguirá funcionando según lo esperado en dispositivos de Android P. Esta versión del SDK de aplicaciones de Intune ofrece un complemento integrado que realiza las actualizaciones del SDK. No es necesario que reescriba ningún código existente que ya esté integrado. Para detalles, consulte el artículo sobre el [SDK de Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Si usa el anterior estilo de distintivo para Intune, se recomienda usar el icono de maletín. Para detalles de personalización de la marca, consulte [este repositorio de GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Más oportunidades para la sincronización en la aplicación de Portal de empresa para Windows  
La aplicación Portal de empresa para Windows ahora permite iniciar una sincronización directamente desde la barra de tareas de Windows y el menú Inicio. Esta característica es especialmente útil si la única tarea es sincronizar los dispositivos y obtener acceso a los recursos corporativos. Para acceder a la nueva característica, haga clic con el botón derecho en el icono de Portal de empresa que está anclado a la barra de tareas o el menú Inicio. En las opciones de menú (también denominada lista de accesos directos), seleccione **Sincronizar este dispositivo**. El Portal de empresa se abrirá en la página **Configuración** e iniciará la sincronización. Para comprobar la nueva funcionalidad, vea [Novedades de la interfaz de usuario](whats-new-app-ui.md).

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nuevas experiencias de navegación en la aplicación Portal de empresa para Windows  
Ahora al examinar o buscar aplicaciones en la aplicación Portal de empresa para Windows, puede alternar entre la vista **Iconos** existente y la vista **Detalles** recién agregada. En la nueva vista se muestran detalles de la aplicación, como el nombre, el editor, la fecha de publicación y el estado de la instalación.  

La vista **Instaladas** de la página **Aplicaciones** le permite ver detalles sobre las instalaciones de aplicaciones completadas y en curso. Para ver el aspecto de la vista nueva, vea [Novedades de la interfaz de usuario](whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Mejora de la experiencia en la aplicación Portal de empresa para administradores de inscripciones de dispositivos  
Cuando un administrador de inscripciones de dispositivos (DEM) inicia sesión en la aplicación Portal de empresa para Windows, ahora la aplicación solo mostrará el dispositivo en ejecución actual de DEM. Esta mejora reducirá los tiempos de espera que se producían anteriormente cuando la aplicación intentaba mostrar todos los dispositivos inscritos en DEM.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models----1425689----"></a>Bloqueo del acceso a aplicaciones según proveedores y modelos de dispositivos no aprobados <!-- 1425689 ! -->
El administrador de TI de Intune puede aplicar una lista específica de fabricantes de dispositivos Android o modelos de iOS a través de las directivas de Intune App Protection. El administrador de TI puede brindar una lista de fabricantes separados por punto y coma para las directivas Android y los modelos de dispositivo para las directivas iOS. Las directivas de Intune App Protection solo son para Android e iOS. Se pueden realizar dos acciones independientes en esta lista especificada:
- Bloquear el acceso a la aplicación en dispositivos no especificados.
- O bien, borrar de manera selectiva los datos corporativos en dispositivos no especificados. 

El usuario no podrá acceder a la aplicación de destino si no se cumplen los requisitos que establece la directiva. En función de la configuración, se podrá bloquear al usuario o borrar de manera selectiva sus datos corporativos dentro de la aplicación. En dispositivos iOS, esta característica requiere el uso de ciertas aplicaciones (como WXP, Outlook, Managed Browser o Yammer) para integrar Intune APP SDK para que esta característica se aplique en las aplicaciones de destino. Esta integración ocurre de manera gradual y depende de los equipos de la aplicación específica. En Android, esta característica requiere la versión más reciente de Portal de empresa. 

En dispositivos de usuario final, el cliente de Intune actúa en función de una coincidencia simple de las cadenas especificadas en la hoja de Intune para directivas de protección de aplicaciones. Esto depende por completo del valor que informa el dispositivo. Por lo tanto, se recomienda que el administrador de TI se asegure de que el comportamiento previsto sea preciso. Para ello, pruebe esta configuración en función de una variedad de fabricantes de dispositivos y de modelos dirigidos a un grupo de usuarios pequeño. En Microsoft Intune, seleccione **Aplicaciones cliente** > **Directivas de protección de aplicaciones** para ver y agregar directivas de protección de aplicaciones. Para obtener más información sobre las directivas de protección de aplicaciones, vea [¿Qué son las directivas de protección de aplicaciones?](../apps/app-protection-policy.md) y [Borrar los datos de forma selectiva mediante acciones de acceso de la directiva de protección de aplicaciones en Intune](../apps/app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build---1734766---"></a>Acceso a la compilación de versión preliminar del Portal de empresa de macOS<!-- 1734766 -->
Con Microsoft AutoUpdate, puede registrarse para recibir antes las compilaciones si se une al programa Insider. El registro le permite usar Portal de empresa actualizado antes de que esté disponible para los usuarios finales. Para obtener más información, vea el [blog de Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices---1497640---"></a>Creación de directivas de cumplimiento de dispositivos mediante la configuración de firewall en dispositivos macOS<!-- 1497640 -->
Cuando se crea una directiva de cumplimiento de macOS (**Conformidad de dispositivos** > **Directivas** > **Crear directiva** > **Plataforma: macOS** > **Seguridad del sistema**), hay nuevas opciones de **Firewall** disponibles: 

- **Firewall**: configure cómo se administran las conexiones entrantes en el entorno.
- **Conexiones entrantes**: **bloquee** todas las conexiones entrantes excepto las necesarias para los servicios básicos de Internet, como DHCP, Bonjour e IPSec. Esta opción también bloquea todos los servicios de uso compartido.
- **Modo sigiloso**: **habilite** el modo sigiloso para evitar que el dispositivo responda a solicitudes de sondeo. El dispositivo sigue respondiendo a las solicitudes entrantes de las aplicaciones autorizadas.

Se aplica a: macOS 10.12 y versiones posteriores

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later---1879077---"></a>Nuevo perfil de configuración de dispositivos Wi-Fi para Windows 10 y versiones posteriores<!-- 1879077 -->
Actualmente, puede importar y exportar perfiles de Wi-Fi mediante archivos XML. Con esta actualización, puede crear un perfil de configuración de dispositivo Wi-Fi directamente en Intune, igual que en otras plataformas.

Para crear el perfil, abra **Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** > **Wi-Fi**. 

Se aplica a Windows 10 y versiones posteriores.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed---2149998---"></a>La característica Quiosco (obsoleto) aparece atenuada y no se puede cambiar<!-- 2149998 -->
La característica Quiosco (versión preliminar) (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Windows 10 y versiones posteriores** > **Restricciones de dispositivos**) está obsoleta y se sustituye por la [configuración de Quiosco para Windows 10 y versiones posteriores](../configuration/kiosk-settings.md). Con esta actualización, la característica **Quiosco (obsoleto)** está atenuada y la interfaz de usuario no se puede modificar ni actualizar. 

Para habilitar el modo quiosco, vea [Configuración de quiosco para Windows 10 (y versiones posteriores)](../configuration/kiosk-settings.md).

Se aplica a Windows 10 y versiones posteriores, Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities---2184013---"></a>API para usar entidades de certificación de terceros<!-- 2184013 -->
En esta actualización, hay una API de Java que permite que las entidades de certificación de terceros se integren con Intune y SCEP. Después, los usuarios pueden agregar el certificado SCEP a un perfil y aplicarlo a los dispositivos mediante MDM.

Actualmente, Intune admite [solicitudes SCEP mediante Servicios de certificados de Active Directory](../protect/certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser---2455253---"></a>Alternar para mostrar u ocultar el botón Finalizar sesión en un explorador de Quiosco<!-- 2455253 -->
Ahora puede configurar si los exploradores de Quiosco muestran o no el botón Finalizar sesión. Puede ver el control en **Configuración del dispositivo** > **Quiosco (versión preliminar)**  > **Kiosk Web Browser**. Si está activado, cuando un usuario hace clic en el botón, la aplicación solicita confirmación para finalizar la sesión. Cuando se confirma, el explorador borra todos los datos de exploración y vuelve a la dirección URL predeterminada.

#### <a name="create-an-esim-cellular-configuration-profile---2564077---"></a>Creación de un perfil de configuración de red de telefonía móvil eSIM<!-- 2564077 -->
En **Configuración del dispositivo**, puede crear un perfil de red de telefonía móvil eSIM. Puede importar un archivo que contenga códigos de activación de red de telefonía móvil proporcionados por el operador de telefonía móvil. Después, puede implementar estos perfiles en sus dispositivos Windows 10 habilitados para eSIM LTE, como Surface Pro LTE y otros dispositivos compatibles con eSIM.

Compruebe si sus [dispositivos admiten perfiles de eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Se aplica a Windows 10 y versiones posteriores.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings---1058963-eenotready---"></a>Selección de las categorías de dispositivos mediante la configuración de acceso profesional o educativo<!-- 1058963 eenotready --> 
Si ha habilitado la [asignación de grupos de dispositivos](../enrollment/device-group-mapping.md), ahora se pedirá a los usuarios de Windows 10 que seleccionen una categoría de dispositivo después de la inscripción a través del botón **Conectar** en **Configuración** > **Cuentas** > **Obtener acceso a trabajo o escuela**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles---1500307---"></a>Uso de sAMAccountName como nombre de usuario de cuenta para perfiles de correo electrónico<!-- 1500307 -->
Puede usar el nombre local **sAMAccountName** como nombre de usuario de cuenta de los perfiles de correo electrónico para Android, iOS y Windows 10. También puede obtener el dominio de los atributos `domain` o `ntdomain` en Azure Active Directory (Azure AD). O si lo prefiere, podrá especificar un dominio estático personalizado.

Para usar esta característica, debe sincronizar el atributo `sAMAccountName` desde el entorno de Active Directory local con Azure AD.

Se aplica a [Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 y versiones posteriores](../configuration/email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict---1556983---"></a>Visualización de perfiles de configuración de dispositivos en conflicto<!-- 1556983 -->
En **Configuración del dispositivo**, se muestra una lista de los perfiles existentes. Con esta actualización, se agrega una nueva columna que proporciona información detallada sobre los perfiles que tienen un conflicto. Puede seleccionar una fila en conflicto para ver la configuración y el perfil que tiene el conflicto. 

Obtenga más información sobre cómo [administrar perfiles de configuración](../configuration/device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance---2308882---"></a>Nuevo estado para dispositivos en la conformidad de dispositivos<!-- 2308882 -->
En **Conformidad de dispositivos** > **Directivas** > seleccione una directiva > **Información general**, se han agregado los estados nuevos siguientes:
- Correcto
- error
- Conflicto
- pending
- No aplicable: una imagen que también muestra el número de dispositivos de una plataforma diferente. Por ejemplo, si está buscando un perfil de iOS, el nuevo icono muestra el número de dispositivos que no son de iOS que también están asignados a este perfil. Vea [Directivas de cumplimiento de dispositivos](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions---2325484---"></a>Conformidad de dispositivos compatible con soluciones antivirus de terceros<!-- 2325484 -->
Cuando se crea una directiva de cumplimiento del dispositivo (**Cumplimiento del dispositivo** > **Directivas** > **Crear directiva** > **Plataforma: Windows 10 y versiones posteriores** > **Configuración** > **Seguridad del sistema**), hay nuevas opciones de **[Seguridad del dispositivo](../protect/compliance-policy-create-windows.md)** : 
- **Antivirus**: cuando se establece en **Requerir**, puede comprobar el cumplimiento mediante soluciones antivirus registradas con Windows Security Center, como Symantec y Windows Defender. 
- **Antispyware**: cuando se establece en **Requerir**, puede comprobar el cumplimiento mediante soluciones antispyware registradas con Windows Security Center, como Symantec y Windows Defender. 

Se aplica a: Windows 10 y versiones posteriores 

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate---2404851---"></a>Marcado automático de dispositivos Android inscritos mediante Samsung Knox Mobile Enrollment como "corporativos".<!-- 2404851 -->
De forma predeterminada, los dispositivos Android inscritos mediante Samsung Knox Mobile Enrollment ahora se marcan como **corporativos** en **Propiedad del dispositivo**. No es necesario identificar manualmente los dispositivos corporativos mediante IMEI o números de serie antes de realizar la inscripción mediante Knox Mobile Enrollment.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens---1853904---"></a>Dispositivos sin columna de perfiles en la lista de tokens del programa de inscripción<!-- 1853904 -->
En la lista de tokens del programa de inscripción hay una nueva columna que muestra el número de dispositivos sin un perfil asignado. Esto ayuda a los administradores a asignar perfiles a estos dispositivos antes de entregarlos a los usuarios. Para ver la nueva columna, vaya a **Inscripción de dispositivos** > **Inscripción de Apple** > **Tokens del programa de inscripción**.

### <a name="device-management"></a>Administración de dispositivos

#### <a name="bulk-delete-devices-on-devices-blade---1793693---"></a>Eliminación en masa de dispositivos en la hoja de dispositivos<!-- 1793693 -->
Ahora puede eliminar varios dispositivos a la vez en la hoja de dispositivos. Elija **Dispositivos** > **Todos los dispositivos** > seleccione los dispositivos que quiere eliminar > **Eliminar**. En el caso de los dispositivos que no se puedan eliminar, se mostrará una alerta.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work--842873---"></a>Cambio de nombre en Google para Android for Work y Play for Work<!--842873 -->
Intune ha actualizado el término "Android for Work" para reflejar los cambios de personalización de marca de Google. Ya no se usan los términos "Android for Work" ni "Play for Work". Se usa otra terminología en función del contexto:
- "Android Enterprise" hace referencia a la pila de administración general de Android moderna.
- "Perfil de trabajo" o "Propietario de perfil" hacen referencia a dispositivos BYOD administrados con perfiles de trabajo.
- "Google Play administrada" hace referencia a la tienda de aplicaciones de Google.

#### <a name="rules-for-removing-devices---1609459---"></a>Reglas para quitar dispositivos<!-- 1609459 -->
Hay disponibles nuevas reglas que permiten quitar automáticamente dispositivos que no se hayan protegido durante un número de días que establezca. Para ver la nueva regla, vaya al panel **Intune**, seleccione **Dispositivos** y, luego, **Reglas de limpieza de dispositivos**.

#### <a name="corporate-owned-single-use-support-for-android-devices---1630973---"></a>Compatibilidad con dispositivos Android de un solo uso y propiedad corporativa<!-- 1630973 -->

Ahora, Intune admite dispositivos Android de estilo quiosco, que estén bloqueados y con una elevada administración. De este modo, los administradores pueden bloquear aún más el uso de un dispositivo para restringir su uso a una sola aplicación o un pequeño conjunto de aplicaciones, impidiendo así que los usuarios habiliten otras aplicaciones o realicen otras acciones en el dispositivo. Para configurar el quiosco de Android, vaya a Intune > **Inscripción de dispositivos** > **Inscripción de Android** > **Inscripciones de dispositivos de tareas y quiosco**. Para obtener más información, vea [Set up enrollment of Android enterprise kiosk devices](../enrollment/android-kiosk-enroll.md) (Configurar la inscripción de dispositivos de quiosco de Android Enterprise).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded---2203794--"></a>Revisión por fila de los identificadores de dispositivos corporativos duplicados cargados<!-- 2203794-->
Ahora, al cargar identificadores corporativos, Intune facilita una lista de cualquier dispositivo duplicado y ofrece la posibilidad de reemplazar o conservar la información existente. El informe se mostrará si hay duplicados después de elegir **Inscripción de dispositivos** > **Identificadores de dispositivos corporativos** > **Agregar identificadores**. 

#### <a name="manually-add-corporate-device-identifiers---2203803---"></a>Adición manual de identificadores de dispositivos corporativos<!-- 2203803 -->
Ahora puede agregar manualmente identificadores de dispositivos corporativos. Elija **Inscripción de dispositivos** > **Identificadores de dispositivos corporativos** > **Agregar**. 


<!-- ########################## -->
## <a name="june-2018"></a>Junio de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies---1817882---"></a>Compatibilidad móvil de Microsoft Edge para directivas de protección de aplicaciones de Intune<!-- 1817882 -->
El navegador Microsoft Edge para dispositivos móviles ahora admite las directivas de protección de aplicaciones definidas en Intune.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode---1560077----"></a>Recuperación del identificador de modelo de usuario de la aplicación (AUMID) asociado para aplicaciones de Microsoft Store para Empresas en pantalla completa<!-- 1560077 ! -->
Intune ya puede recuperar los identificadores de modelo de usuario de la aplicación (AUMID) para aplicaciones de Microsoft Store para Empresas (WSfB) con el fin de mejorar la configuración del perfil de pantalla completa.

Para más información sobre las aplicaciones de Microsoft Store para Empresas, consulte el artículo sobre la [administración de aplicaciones de Microsoft Store para Empresas](../apps/windows-store-for-business.md).

#### <a name="new-company-portal-branding-page---1916370---"></a>Nueva página de personalización de marca del Portal de empresa<!-- 1916370 -->
La página de personalización de marca del Portal de empresa tiene un nuevo diseño, mensajes e información sobre herramientas.


### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="pradeo---new-mobile-threat-defense-partner---1169249---"></a>Pradeo: nuevo colaborador de Mobile Threat Defense<!-- 1169249 -->
Puede controlar el acceso desde dispositivos móviles a recursos corporativos en función de la evaluación de riesgos efectuada por Pradeo, una solución de Mobile Threat Defense integrada con Microsoft Intune.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector---1333688---"></a>Uso del modo FIPS con el conector de certificado NDES<!-- 1333688 -->
Al instalar el conector de certificado NDES en un equipo con el modo Estándar federal de procesamiento de información (FIPS) habilitado, la emisión y revocación de certificados no funciona según lo previsto. Con esta actualización, con el conector de certificado NDES se incluye la compatibilidad con FIPS. 

Esta actualización también incluye:

- El conector de certificado NDES requiere .NET 4.5 Framework, que se incluye automáticamente con Windows Server 2016 y Windows Server 2012 R2. Anteriormente, .NET 3.5 Framework era la versión mínima requerida.
- Con el conector de certificado NDES se incluye la compatibilidad con TLS 1.2. Por tanto, si el servidor con el conector de certificado NDES instalado es compatible con TLS 1.2, entonces se usará TLS 1.2. Si el servidor no admite TLS 1.2, entonces se usará TLS 1.1. Actualmente, se usa TLS 1.1 para la autenticación entre los dispositivos y el servidor.

Para obtener más información, vea [Configuración y uso de certificados SCEP](../protect/certificates-scep-configure.md) y [Configuración y uso de certificados PKCS](../protect/certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles---1333680----"></a>Compatibilidad con perfiles de VPN de Palo Alto Networks GlobalProtect<!-- 1333680 ! -->
Con esta actualización, puede elegir Palo Alto Networks GlobalProtect como un tipo de conexión VPN para perfiles de VPN en Intune (**Configuración del dispositivo** > **Perfiles** > **Crear perfil** > **Tipo de perfil** > **VPN**). En esta versión, se admiten las siguientes plataformas: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings---1403702---"></a>Adiciones a la configuración de opciones de seguridad del dispositivo local<!-- 1403702 -->
Ya puede configurar opciones adicionales de seguridad del dispositivo local para dispositivos con Windows 10. Las opciones adicionales están disponibles en las áreas Cliente de redes de Microsoft, Servidor de red Microsoft, Acceso y seguridad de red e Inicio de sesión interactivo. Encuentre estos valores en la categoría de Endpoint Protection cuando cree una directiva de configuración de dispositivo de Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices---1560072----"></a>Habilitación de la pantalla completa en dispositivos Windows 10<!-- 1560072 ! -->
En los dispositivos Windows 10, puede crear un perfil de configuración y habilitar la pantalla completa (**Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **Windows 10** > **Restricciones de dispositivos** > **Quiosco**). En esta actualización, la configuración **Quiosco (versión preliminar)** cambia de nombre a **Quiosco (obsoleto)** . Ya no se recomienda usar **Quiosco (obsoleto)** , pero seguirá funcionando hasta la actualización de julio. El nuevo tipo de perfil **Quiosco** reemplaza a **Quiosco (obsoleto)** (**Crear perfil** > **Windows 10** > **Quiosco (versión preliminar)** ), que contendrá los valores para configurar Quioscos en Windows 10 RS4 y versiones posteriores.

Se aplica a Windows 10 y versiones posteriores.

#### <a name="device-profile-graphical-user-chart-is-back---2160133---"></a>Vuelve el gráfico de usuario del perfil del dispositivo<!-- 2160133 -->
Si bien mejoraba el valor numérico que aparece en el gráfico del perfil del dispositivo (**Configuración de dispositivos** > **Perfiles** > seleccione un perfil existente > **Información general**), el gráfico de usuario se quitó de manera temporal.

Con esta actualización, dicho gráfico vuelve y aparece en Azure Portal.

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication---1165118---"></a>Compatibilidad con la inscripción de Windows Autopilot sin autenticación de usuario<!-- 1165118 -->
Intune admite la inscripción de Windows Autopilot sin autenticación de usuario. Se trata de una nueva opción en el perfil de implementación de Windows Autopilot "Modo de implementación Autopilot" establecido en "Self-Deploying" (Autoimplementable).  El dispositivo debe ejecutar Windows 10 Insider Preview, compilación 17672 o posterior, y poseer un chip de TPM 2.0 para completar correctamente este tipo de inscripción. Puesto que no se requiere ninguna autenticación de usuario, solo puede asignar esta opción a dispositivos sobre los que tenga control físico.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot---1821766---"></a>Nueva configuración de idioma y región al realizar la configuración rápida de Autopilot<!-- 1821766 -->
Hay disponible una nueva configuración para establecer el idioma y la región de los perfiles de Autopilot durante la configuración rápida. Para ver la nueva configuración, elija **Inscripción de dispositivos** > **Inscripción de Windows** > **Implementación perfiles** > **Crear perfil** > **Modo de implementación** = **Self-deploying (Autoimplementable)**  > **Valores predeterminados configurados**.

#### <a name="new-setting-for-configuring-device-keyboard---1821768---"></a>Nuevo valor para configurar el teclado del dispositivo<!-- 1821768 -->
Habrá disponible un valor nuevo para configurar el teclado de los perfiles de Autopilot durante la configuración rápida. Para ver la nueva configuración, elija **Inscripción de dispositivos** > **Inscripción de Windows** > **Implementación perfiles** > **Crear perfil** > **Modo de implementación** = **Self-deploying (Autoimplementable)**  > **Valores predeterminados configurados**.

#### <a name="autopilot-profiles-moving-to-group-targeting---1877935---"></a>Los perfiles AutoPilot se migran a un destinatario de grupo<!-- 1877935 -->
Se pueden asignar perfiles de implementación de AutoPilot a grupos de Azure AD que contengan dispositivos AutoPilot.

### <a name="device-management"></a>Administración de dispositivos

#### <a name="set-compliance-by-device-location---851881----"></a>Establecimiento del cumplimiento por ubicación del dispositivo<!-- 851881 ! -->
En algunas situaciones, es posible que desee restringir el acceso a los recursos corporativos a una ubicación específica, definida por una conexión de red. Ya puede crear una directiva de cumplimiento (**Cumplimiento de dispositivos** > **Ubicaciones**) en función de la dirección IP del dispositivo. Si el dispositivo sale del intervalo IP, no podrá acceder a los recursos corporativos.

Se aplica a: Solo para dispositivos Android 6.0 y versiones posteriores, con la aplicación Portal de empresa actualizada.

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Evitar aplicaciones y experiencias de consumidor en dispositivos Windows 10 Enterprise RS4 Autopilot<!-- 1621980 -->
Puede evitar la instalación de aplicaciones y experiencias de consumidor en los dispositivos Windows 10 Enterprise RS4 Autopilot. Para ver esta característica, vaya a **Intune** > **Configuración de dispositivos** > **Perfiles** > **Crear perfil** > **Plataforma** = **Windows 10 o versiones posteriores** > **Tipo de perfil** = **Restricciones de dispositivo** > **Configurar** > **Windows Spotlight** > **Características de consumidor**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates---1732948---"></a>Desinstalar las últimas actualizaciones de software de Windows 10<!-- 1732948 -->
En caso de que detecte un problema importante en las máquinas con Windows 10, puede optar por desinstalar (revertir) la última actualización de características o la última actualización de calidad. La desinstalación de una actualización de característica o de calidad solo está disponible para el canal de servicio en el que se encuentra el dispositivo. La desinstalación desencadenará una directiva para restaurar la actualización anterior en las máquinas con Windows 10. Para las actualizaciones de características concretamente, puede limitar el tiempo de 2 a 60 días durante el cual se puede aplicar una desinstalación de la versión más reciente. Para configurar las opciones de desinstalación de actualización de software, seleccione **Actualizaciones de software** en la hoja **Microsoft Intune** en el portal de Azure. Después, seleccione **Anillos de actualización de Windows 10** en la hoja **Actualizaciones de software**. Elija después la opción **Desinstalar** en la sección **Información general**.

#### <a name="search-all-devices-for-imei-and-serial-number---1793685---"></a>Búsqueda del IMEI y número de serie en todos los dispositivos<!-- 1793685 -->
Ya puede buscar IMEI y los números de serie en la hoja Todos los dispositivos (correo electrónico, UPN, nombre de dispositivo y nombre de la administración siguen estando disponibles). En Intune, elija **Dispositivos** > **Todos los dispositivos** y escriba la búsqueda en el cuadro de búsqueda.

#### <a name="management-name-field-will-be-editable---1875989---"></a>El campo de nombre de administración se podrá editar<!-- 1875989 -->
Ya puede editar el campo de nombre de administración en la hoja **Propiedades** de un dispositivo. Para editar este campo, elija **Dispositivos** > **Todos los dispositivos** > elija el dispositivo > **Propiedades**. Puede usar el campo de nombre de administración para identificar un dispositivo de manera única.

#### <a name="new-all-devices-filter-device-category---1878520---"></a>Nuevo filtro Todos los dispositivos: Categoría de dispositivo<!-- 1878520 -->
Ya puede filtrar la lista **Todos los dispositivos** por categoría de dispositivo. Para ello, elija **Dispositivos** > **Todos los dispositivos** > **Filtro** > **Categoría de dispositivo**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices---1985547---"></a>Uso de TeamViewer para compartir la pantalla de dispositivos iOS y macOS<!-- 1985547 -->
Los administradores podrán conectarse a [TeamViewer](../remote-actions/teamviewer-support.md) e iniciar una sesión de uso compartido de pantalla con dispositivos iOS y macOS. Los usuarios de iPhone, iPad y macOS pueden compartir sus pantallas en vivo con cualquier otro dispositivo móvil o de escritorio. 

#### <a name="multiple-exchange-connector-support---2070451---"></a>Compatibilidad con múltiples instancias de Exchange Connector<!-- 2070451 -->
Ya no estará limitado a una instancia de Microsoft Intune Exchange Connector por inquilino. Intune admite varias instancias de Exchange Connector para que pueda configurar el acceso condicional de Intune con varias organizaciones de Exchange local.

Con un conector de Exchange local de Intune, se puede controlar el acceso de los dispositivos a los buzones de Exchange locales en función de si un dispositivo está inscrito en Intune y cumple con las directivas de cumplimiento de dispositivos de Intune. Para configurar un conector, descargue el conector de Exchange local de Intune desde Azure Portal e instálelo en un servidor en la organización de Exchange. En el panel de Microsoft Intune, elija **Acceso local** y, después, en **Instalación**, elija **Conector de Exchange ActiveSync**. Descargue el conector de Exchange local e instálelo en un servidor en la organización de Exchange. Ahora que ya no está limitado a un conector de Exchange por inquilino, si tiene otras organizaciones de Exchange, puede seguir el mismo proceso para descargar e instalar un conector para cada organización de Exchange adicional.

#### <a name="new-device-hardware-detail-ccid---2156657---"></a>Nuevos detalles de hardware de dispositivo: CCID<!-- 2156657 -->
La información de dispositivo de interfaz de tarjeta de chip (CCID) ya se incluye para cada dispositivo. Para verla, elija **Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **Hardware**> compruebe en **Detalles de red**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups---2196803---"></a>Asignación de todos los usuarios y dispositivos como grupos de ámbito<!-- 2196803 -->
Podrá asignar todos los usuarios, todos los dispositivos y todos los usuarios y dispositivos en los grupos de ámbito. Para ello, elija **Roles de Intune** > **Todos los roles** > **Policy and profile manager (Administrador de directivas y perfiles)**  > **Asignaciones** > elija una asignación > **Ámbito (grupos)** .

#### <a name="udid-information-now-included-for-ios-and-macos-devices---2219806---"></a>La información de UDID ahora se incluye para dispositivos iOS y macOS<!-- 2219806 -->
Para ver el identificador único de dispositivo (UDID) para dispositivos iOS y macOS, vaya a **Dispositivos** > **Todos los dispositivos** > elija un dispositivo > **Hardware**. UDID solo está disponible para dispositivos corporativos, tal y como se configura en **Dispositivos** > **Todos los dispositivos** > dispositivo > **Propiedades** > **Propiedad del dispositivo**.

### <a name="intune-apps"></a>Aplicaciones de Intune

#### <a name="improved-troubleshooting-for-app-installation---928990---"></a>Solución de problemas mejorada para la instalación de aplicaciones<!-- 928990 -->
En algunas ocasiones, las instalaciones de aplicaciones en los dispositivos administrados por MDM de Microsoft Intune pueden presentar errores. Cuando esto ocurre, puede ser complicado entender el motivo del error o cómo solucionarlo. Incluimos una Versión preliminar pública de las características de solución de problemas de las aplicaciones. Verá un nodo nuevo bajo cada dispositivo individual denominado **Aplicaciones administradas**. En él aparecen las aplicaciones que se han entregado a través de MDM de Intune. Dentro del nodo, verá una lista de los estados de instalación de las aplicaciones. Si selecciona una aplicación individual, aparecerá la vista de solución de problemas de esa aplicación específica. En la vista de solución de problemas, verá el ciclo de vida completo de la aplicación, como cuándo se creó y modificó la aplicación, el momento en que se estableció su destino y cuándo se entregó a un dispositivo. Además, si la instalación de la aplicación no se realizó correctamente, verá el código de error y un mensaje útil sobre la causa del mismo. 

#### <a name="intune-app-protection-policies-and-microsoft-edge---1818968---"></a>Directivas de protección de aplicaciones de Intune y Microsoft Edge<!-- 1818968 -->
Ahora, el explorador Microsoft Edge para dispositivos móviles (iOS y Android) admite directivas de protección de aplicaciones de Microsoft Intune. Intune protegerá a los usuarios de dispositivos iOS y Android que inicien sesión con sus cuentas corporativas de Azure AD en la aplicación Microsoft Edge. En dispositivos iOS, la directiva **Require managed browser for web content** (Requerir explorador administrado para contenido web) permitirá a los usuarios abrir vínculos en Microsoft Edge cuando esté administrado.

<!-- ########################## -->
## <a name="may-2018"></a>Mayo de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="configuring-your-app-protection-policies---2144597-part-2---"></a>Configuración de las directivas de protección de aplicaciones<!-- 2144597 Part 2 -->

En Azure Portal, en lugar de dirigirse a la hoja del servicio Intune App Protection, solo tiene que ir a Intune. Ahora hay una única ubicación para las directivas de protección de aplicaciones en Intune. Tenga en cuenta que todas las directivas de protección de aplicaciones se encuentran en la hoja **Aplicación móvil** de Intune, en **Directivas de protección de aplicaciones**. Esta integración ayuda a simplificar la administración en la nube. Recuerde que todas las directivas de protección de aplicaciones ya están en Intune y que puede modificar cualquiera de las directivas configuradas anteriormente. Las directivas de protección de aplicaciones (APP) y acceso condicional (CA) de Intune se encuentran ahora en **Acceso condicional**, que se encuentra en la sección **Administrar** de la hoja **Microsoft Intune** o en la sección **Seguridad** de la hoja **Azure Active Directory**. Para más información sobre cómo modificar directivas de acceso condicional, consulte [Acceso condicional en Azure Active Directory](/azure/active-directory/active-directory-conditional-access-azure-portal). Para obtener más información, vea [¿Qué son las directivas de protección de aplicaciones?](../apps/app-protection-policy.md)

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles---1553555---"></a>Exigencia de instalación de perfiles de directivas, aplicaciones, certificados y red<!-- 1553555 -->
Los administradores pueden evitar que los usuarios finales accedan al escritorio de Windows 10 RS4 hasta que Intune instale los perfiles de red y certificado, las aplicaciones y las directivas durante el aprovisionamiento de dispositivos AutoPilot. Para obtener más información, consulte [Configurar una página de estado de inscripción](../enrollment/windows-enrollment-status.md).

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="samsung-knox-mobile-enrollment-support--1112863--"></a>Compatibilidad con Samsung Knox Mobile Enrollment<!--1112863-->
Al usar Intune con Samsung Knox Mobile Enrollment (KME), puede inscribir un gran número de dispositivos Android propiedad de la empresa. Los usuarios en redes Wi-Fi o de telefonía móvil se pueden inscribir con unas pocas pulsaciones al encender sus dispositivos por primera vez. Con la aplicación de implementación Knox, los dispositivos se pueden inscribir mediante Bluetooth o NFC. Para más información, vea [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](../enrollment/android-samsung-knox-mobile-enroll.md) (Inscripción automática de dispositivos Android mediante Samsung Knox Mobile Enrollment).

### <a name="monitor-and-troubleshoot"></a>Supervisión y solución de problemas 

#### <a name="requesting-help-in-the-company-portal-for-windows-10---1874137---"></a>Solicitud de ayuda en el Portal de empresa para Windows 10<!-- 1874137 -->
El Portal de empresa para Windows 10 ahora enviará registros de aplicaciones directamente a Microsoft cuando el usuario inicie el flujo de trabajo para obtener ayuda con un problema. Esto permitirá que sea más fácil solucionar los problemas que se envían a Microsoft.

<!-- ########################## -->
## <a name="april-2018"></a>Abril de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Compatibilidad de código de acceso con el PIN de MAM en Android<!-- 1438086 -->

Los administradores de Intune pueden establecer un requisito de inicio de aplicación para exigir un código de acceso en lugar de un PIN numérico de MAM. Si se configura, se le pide al usuario que establezca y use un código de acceso cuando se le solicite antes de obtener acceso a aplicaciones habilitadas para MAM. Un código de acceso se define como un PIN numérico con al menos un carácter especial o un carácter alfabético en mayúsculas/minúsculas. Intune admite un código de acceso de forma similar al PIN numérico existente... puede establecer una longitud mínima y permite la repetición de caracteres y secuencias en la consola de administración. Esta característica requiere la versión más reciente del Portal de empresa en Android. Esta característica ya está disponible para iOS.

#### <a name="line-of-business-lob-app-support-for-macos---1473977---"></a>Compatibilidad con aplicaciones de línea de negocio (LOB) para macOS<!-- 1473977 -->
Microsoft Intune proporciona la capacidad de instalar aplicaciones LOB de macOS desde Azure Portal. Se puede agregar una aplicación LOB de macOS a Intune una vez procesada por la herramienta disponible en GitHub. En Azure Portal, seleccione **Aplicaciones cliente** en la hoja **Intune**. En la hoja **Aplicaciones cliente**, elija **Aplicaciones** > **Agregar**. En la hoja **Agregar aplicación**, seleccione **Aplicación de línea de negocio**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment---1813073---"></a>Grupo integrado Todos los usuarios y Todos los dispositivos para la asignación de aplicaciones de perfil de trabajo de Android Enterprise<!-- 1813073 -->
Puede aprovechar los grupos integrados **Todos los usuarios** y **Todos los dispositivos** para la asignación de aplicaciones de perfil de trabajo de Android Enterprise. Para obtener más información, vea [Inclusión y exclusión de asignaciones de aplicaciones en Microsoft Intune](../apps/apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users---1947010---"></a>Intune volverá a instalar las aplicaciones requeridas desinstaladas por los usuarios<!-- 1947010 -->
Si un usuario final desinstala una aplicación requerida, Intune la reinstala de forma automática antes de que transcurran 24 horas en lugar de esperar al ciclo de reevaluación de siete días.

#### <a name="update-where-to-configure-your-app-protection-policies---2144597---"></a>Actualización de la ubicación donde se configuran las directivas de protección de aplicaciones<!-- 2144597 -->

En el servicio Microsoft Intune en Azure Portal, vamos a redirigirle temporalmente de la hoja del servicio **Intune App Protection** a la hoja **Aplicación móvil**. Tenga en cuenta que todas las directivas de protección de aplicaciones ya se encuentran en la hoja **Aplicación móvil** de Intune, en Configuración de aplicaciones. En lugar de ir a Intune App Protection, simplemente irá a Intune. En abril de 2018, se suspenderá el redireccionamiento y se quitará por completo la hoja del servicio **Intune App Protection**, para que haya una sola ubicación para las directivas de protección de aplicaciones en Intune. 

**¿Cómo me afecta esto a mí?**
Este cambio afectará tanto a los clientes de Intune independientes como a los clientes híbridos (Intune con Configuration Manager). Esta integración le ayudará a simplificar la administración en la nube.

**¿Qué he de hacer para prepararme para este cambio?**
Etiquete **Intune** como favorito en lugar de la hoja del servicio **Intune App Protection** y asegúrese de que conoce el flujo de trabajo de la directiva de protección de aplicaciones de la hoja de la aplicación **Móvil** en Intune. Se le redirigirá durante un breve período de tiempo y, luego, se quitará la hoja **Intune App Protection**. Recuerde que todas las directivas de protección de aplicaciones ya están en Intune y que puede modificar las directivas de acceso condicional. Para más información sobre cómo modificar directivas de acceso condicional, consulte [Acceso condicional en Azure Active Directory](/azure/active-directory/active-directory-conditional-access-azure-portal). Para obtener más información, vea [¿Qué son las directivas de protección de aplicaciones?](../apps/app-protection-policy.md) 

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group---1449153---"></a>Representación de todos los dispositivos de un grupo en el gráfico de perfiles de dispositivos y la lista de estado<!-- 1449153 -->
Al configurar un perfil de dispositivo (**Configuración del dispositivo** > **Perfiles**), elija el perfil del dispositivo, por ejemplo, iOS. Este perfil se asigna a un grupo que incluye los dispositivos iOS y los dispositivos que no son iOS. El recuento del gráfico muestra que el perfil se aplica a dispositivos iOS *y* no iOS (**Configuración del dispositivo** > **Perfiles** > seleccionar un perfil existente > **Información general**). Cuando se selecciona el gráfico en la pestaña **Información general**, el **Estado del dispositivo** enumera todos los dispositivos del grupo, en lugar de solo los dispositivos iOS. 

Con esta actualización, el gráfico (**Configuración del dispositivo** > **Perfiles** > seleccionar un perfil existente > **Información general**) solo muestra el recuento del perfil de dispositivo determinado. Por ejemplo, si el perfil de dispositivo de configuración se aplica a dispositivos iOS, el gráfico muestra solo el número de dispositivos iOS. Al seleccionar el gráfico y abrir **Estado del dispositivo**, solo se muestran los dispositivos iOS.

Mientras se realiza esta actualización, se quita temporalmente el gráfico de usuario. 

#### <a name="always-on-vpn-for-windows-10--1333666---"></a>VPN de Always On para Windows 10<!--1333666 -->

Actualmente, [Always On](/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) puede usarse en dispositivos Windows 10 mediante un perfil de red privada virtual (VPN) personalizado creado con OMA-URI.

Con esta actualización, los administradores pueden habilitar Always On para perfiles de VPN de Windows 10 directamente en Intune en Azure Portal. Los perfiles VPN de Always On se conectarán automáticamente cuando:

- Los usuarios inicien sesión en sus dispositivos
- La red del dispositivo cambie
- La pantalla del dispositivo se vuelva a activar después de haberse desactivado

#### <a name="new-printer-settings-for-education-profiles---1308900---"></a>Nueva configuración de impresora para perfiles de educación<!-- 1308900 -->

Para los perfiles de educación, hay nuevos valores de configuración disponibles en la categoría **Impresoras**: **Impresoras**, **Impresora predeterminada**, **Agregar nuevas impresoras**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile--1098984---"></a>Mostrar el identificador de llamada en el perfil personal: perfil de trabajo de Android Enterprise<!--1098984 -->
Al usar un perfil personal en un dispositivo, es posible que los usuarios finales no vean los detalles del identificador del autor de la llamada de un contacto de trabajo. 

Con esta actualización, hay una nueva opción en **Android Enterprise** > **Restricciones de dispositivos** > **Configuración del perfil de trabajo**:
- Mostrar el identificador de llamada de contacto profesional en el perfil personal

Cuando se habilita (sin configurar), se muestran los detalles del autor de la llamada del contacto en el perfil personal. Cuando se bloquea, no se muestra el número del autor de la llamada del contacto en el perfil personal. 

Se aplica a: Dispositivos de perfil de trabajo Android con la versión del sistema operativo Android 6.0 y versiones más recientes

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings--1102252-----from-1802-and-1804--"></a>Nueva configuración de Credential Guard de Windows Defender agregada a la configuración de Endpoint Protection<!--1102252 --><!--from 1802 and 1804-->

Con esta actualización, [Credential Guard de Windows Defender](/windows/access-protection/credential-guard/credential-guard) (**Configuración de dispositivos** > **Perfiles** > **Endpoint Protection**) incluye la siguiente configuración: 

- **Credential Guard de Windows Defender**: activa Credential Guard con seguridad basada en virtualización. Habilitar esta característica ayuda a proteger las credenciales en el siguiente reinicio cuando las opciones **///Platform Security Level with Secure Boot** (Nivel de seguridad de plataforma con arranque seguro) y **///Virtualization Based Security** (Seguridad basada en virtualización) are están ambas habilitadas. Las opciones son:
  - **Deshabilitado**: si Credential Guard se activó anteriormente con la opción **Habilitar sin bloqueo**", entonces Credential Guard se desactiva de forma remota.

  - **Habilitado con el bloqueo UEFI**: garantiza que Credential Guard no se puede deshabilitar mediante una clave de Registro o por medio de la directiva de grupo. Para deshabilitar Credential Guard después de usar esta opción, debe establecer la directiva de grupo en "Deshabilitado". A continuación, quite la funcionalidad de seguridad de cada equipo, con un usuario físicamente presente. Estos pasos borrar la configuración almacenada en UEFI. Mientras se conserve la configuración de UEFI, Credential Guard estará habilitado.

  - **Habilitar sin bloqueo**: permite deshabilitar Credential Guard de forma remota mediante la directiva de grupo. Los dispositivos que usen esta configuración deben ejecutar al menos Windows 10 (versión 1511).

Las siguientes tecnologías dependientes se habilitan automáticamente al configurar Credential Guard: 

- **Enable Virtualization-based Security (VBS)** (Habilitar la seguridad basada en la virtualización [VBS]): activa la seguridad basada en la virtualización (VBS) en el siguiente reinicio. La seguridad basada en la virtualización emplea el hipervisor de Windows para proporcionar compatibilidad con servicios de seguridad, y requiere arranque seguro.
- **Secure Boot with Direct Memory Access (DMA)** (Arranque seguro con acceso directo a memoria [DMA]): activa VBS con arranque seguro y acceso directo a memoria. La protección de DMA requiere compatibilidad con el hardware y solo se habilita en los dispositivos configurados correctamente. 

#### <a name="use-a-custom-subject-name-on-scep-certificate---2064190---"></a>Uso de un nombre de firmante personalizado en certificados SCEP<!-- 2064190 -->
Puede usar el nombre común **OnPremisesSamAccountName** de un sujeto personalizado en un perfil de certificado SCEP. Por ejemplo, puede usar `CN={OnPremisesSamAccountName})`.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles---1098977---"></a>Bloqueo de la cámara y capturas de pantalla en los perfiles de trabajo de Android Enterprise<!-- 1098977 -->
Hay dos nuevas propiedades disponibles para bloquear al configurar restricciones de dispositivo para dispositivos Android: 
- Cámara: bloquea el acceso a todas las cámaras en el dispositivo.
- Captura de pantalla: bloquea la captura de pantalla y además evita que el contenido se muestre en los dispositivos de pantalla que no tengan una salida de vídeo segura.

Se aplica a los perfiles de trabajo de Android Enterprise.

#### <a name="use-cisco-anyconnect-client-for-ios---1333708---"></a>Uso del cliente de Cisco AnyConnect para iOS<!-- 1333708 -->

Al crear un nuevo perfil de VPN para iOS, ahora hay dos opciones: **Cisco AnyConnect** y **Cisco Legacy AnyConnect**. Los perfiles de Cisco AnyConnect admiten las versiones 4.0.7x y más recientes. Los perfiles de VPN existentes de Cisco AnyConnect para iOS se etiquetan como **Cisco Legacy AnyConnect**, y siguen funcionando con Cisco AnyConnect 4.0.5x y versiones posteriores, como lo hacen en la actualidad.

> [!NOTE]
> Este cambio sólo se aplica a iOS. Sigue habiendo una única opción de Cisco AnyConnect para perfiles de trabajo de Android y Android Enterprise y las plataformas macOS.


### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132--1734567---"></a>Nuevos pasos de inscripción para los usuarios en dispositivos con macOS High Sierra 10.13.2+<!--1734567 -->
macOS high Sierra 10.13.2 presentó el concepto de inscripción de inscripción de MDM "aprobada por el usuario". Las inscripciones aprobadas permiten a Intune administrar algunas configuraciones dependientes de la seguridad. Para obtener más información, vea la documentación de soporte técnico de Apple aquí: https://support.apple.com/HT208019.

Los dispositivos inscritos mediante el Portal de empresa de macOS se consideran "No aprobados por el usuario", a menos que el usuario final abra las preferencias del sistema y los apruebe de forma manual. Así, el Portal de empresa de macOS ahora insta a los usuarios de macOS 10.13.2 y versiones posteriores a aprobar manualmente su inscripción al final del proceso de inscripción. La consola de administración de Intune indicará si un dispositivo inscrito está aprobado por el usuario.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune---2370684---"></a>Ahora los dispositivos macOS inscritos en Jamf se pueden registrar en Intune<!-- 2370684 -->
Las versiones 1.3 y 1.4 del portal de empresa de macOS no registraban correctamente los dispositivos Jamf en Intune. La versión 1.4.2 del portal de macOS corrige este problema.

#### <a name="updated-help-experience-in-company-portal-app-for-android---1631531---"></a>Experiencia de ayuda actualizada en la aplicación Portal de empresa para Android<!-- 1631531 -->
Se ha actualizado la experiencia de ayuda en la aplicación Portal de empresa para Android de acuerdo con los procedimientos recomendados para la plataforma Android. Ahora, cuando los usuarios detectan un problema en la aplicación, pueden pulsar en **Menú** > **Ayuda** y:
- Cargar registros de diagnóstico en Microsoft.
- Enviar un mensaje de correo electrónico que describe el problema y un Id. de incidente a un miembro del equipo de soporte técnico de la empresa.  

Para ver la experiencia de ayuda actualizada, vaya a [Send logs using email](../user-help/send-logs-to-your-it-admin-by-email-android.md) (Enviar registros por correo electrónico) y [Send errors to Microsoft](../user-help/send-logs-to-microsoft-android.md) (Enviar errores a Microsoft).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table---1471783---"></a>Nuevo gráfico de tendencias sobre errores de inscripción y tabla de motivos de error<!-- 1471783 -->
En la página de información general de inscripción, puede ver la tendencia de los errores de inscripción y los cinco motivos de error principales. Al hacer clic en el gráfico o la tabla, puede explorar los detalles para obtener consejos de resolución de problemas y sugerencias de corrección.


### <a name="device-management"></a>Administración de dispositivos

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated---1629303---"></a>Integración completa de Advanced Threat Protection (ATP) e Intune<!-- 1629303 -->

[Protección contra amenazas avanzada (ATP)](/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) muestra el nivel de riesgo de los dispositivos Windows 10. En el Centro de seguridad de Windows Defender (portal de ATP), puede crear una conexión a Microsoft Intune. Una vez creada, se usa una directiva de cumplimiento de Intune para determinar un nivel de amenaza aceptable. Si se supera el nivel de amenaza, una directiva de acceso condicional de Azure Active Directory (AD) puede bloquear el acceso a diferentes aplicaciones dentro de su organización.

Esta característica permite que ATP examine archivos, detecte amenazas y notifique cualquier riesgo en los dispositivos Windows 10.

Consulte [Habilitación de ATP con acceso condicional en Intune](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices---1637553---"></a>Compatibilidad con dispositivos sin usuario<!-- 1637553 -->
Intune ofrece la posibilidad de evaluar el cumplimiento en dispositivos sin usuario, como Microsoft Surface Hub. La directiva de cumplimiento puede tener como destino dispositivos concretos. Así, es posible determinar el cumplimiento (y no cumplimiento) de dispositivos sin un usuario asociado.

#### <a name="delete-autopilot-devices---1713650---"></a>Eliminación de dispositivos Autopilot<!-- 1713650 -->
Los administradores de Intune pueden [eliminar dispositivos Autopilot](../../autopilot/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience--1832333---"></a>Experiencia de eliminación de dispositivos mejorada<!--1832333 -->
Ya no se le pide que quite los datos de la empresa o que restablezca el dispositivo a los valores de fábrica para [eliminar un dispositivo de Intune](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal).

Para ver la nueva experiencia, inicie sesión en Intune y seleccione **Dispositivos** > **Todos los dispositivos** > el nombre del dispositivo > **Eliminar**.

Si todavía quiere confirmar el borrado o eliminación, puede usar la ruta de ciclo de vida de dispositivo estándar al usar **Eliminar datos de la compañía** y **Restablecimiento de fábrica** antes de **Eliminar**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode---1947769---"></a>Reproducción de sonidos en iOS en modo Perdido<!-- 1947769 -->
Cuando los dispositivos iOS supervisados están en el [modo perdido](../remote-actions/device-lost-mode.md) de administración de dispositivos móviles (MDM), puede [reproducir un sonido](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Dispositivos** > **Todos los dispositivos** > seleccionar un dispositivo iOS > **Información general** > **Más**). El sonido sigue reproduciéndose hasta que el dispositivo se quita del modo Perdido o un usuario deshabilita el sonido en el dispositivo. Se aplica a dispositivos iOS 9.3 y versiones más recientes.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device--1972804--"></a>Bloquear o permitir resultados web en búsquedas realizadas en un dispositivo de Intune<!--1972804-->

Ahora, los administradores pueden bloquear los resultados web en las búsquedas realizadas en un dispositivo.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure---2172331---"></a>Mensajes de error mejorados para errores de carga del certificado push MDM de Apple<!-- 2172331 -->

El mensaje de error explica que se debe usar el mismo identificador de Apple al renovar un certificado MDM existente.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines---2216679---"></a>Probar el Portal de empresa para macOS en máquinas virtuales<!-- 2216679 -->

Se han publicado instrucciones para ayudar a los administradores de TI a probar la aplicación Portal de empresa para macOS en máquinas virtuales en Parallels Desktop y VMware Fusion. Encuentre más información en [Inscribir máquinas virtuales macOS para realizar pruebas](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing).

### <a name="intune-apps"></a>Aplicaciones de Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios--1412866---"></a>Actualización de la experiencia de usuario para la aplicación Portal de empresa para iOS<!--1412866 -->
Hemos publicado una importante actualización de la experiencia de usuario para la aplicación Portal de empresa para iOS. La actualización incluye un completo cambio de diseño visual con una apariencia modernizada. Hemos mantenido la funcionalidad de la aplicación, pero hemos mejorado su facilidad de uso y accesibilidad.  

También verá:
- Compatibilidad con el iPhone X.
- Inicio de la aplicación y carga de las respuestas más rápidos, para ahorrar tiempo a los usuarios.
- Barras de progreso adicionales para proporcionar a los usuarios la información de estado más reciente.
- Mejoras en la forma en que los usuarios cargan los registros, de modo que, si hay algún problema, sea más fácil de informar al respecto.  

Para ver el aspecto actualizado vaya a [Actualizaciones de la interfaz de usuario para las aplicaciones de usuario final de Intune](whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca---1056954---"></a>Protección de los datos locales de Exchange mediante APP y CA de Intune<!-- 1056954 -->
Ahora puede usar directivas de protección de aplicaciones (APP) y acceso condicional (CA) de Intune para proteger el acceso a datos locales de Exchange con Outlook Mobile. Para agregar o modificar una directiva de protección de aplicaciones en Azure Portal, seleccione **Microsoft Intune** > **Aplicaciones cliente** > **Directivas de protección de aplicaciones**. Antes de usar esta característica, asegúrese de cumplir los [requisitos de Outlook para iOS y Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).


### <a name="user-interface"></a>Interfaz de usuario

#### <a name="improved-device-tiles-in-the-windows-10-company-portal--2213364---"></a>Iconos de dispositivo mejorados en el Portal de empresa de Windows 10<!--2213364 -->

Se han actualizado los iconos para que sean más accesibles para los usuarios con deficiencia visual y para que funcionen mejor con las herramientas de lectura de pantalla.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos---2216677---"></a>Enviar informes de diagnóstico en la aplicación Portal de empresa para macOS<!-- 2216677 -->
La aplicación Portal de empresa para dispositivos macOS se ha actualizado para mejorar la forma en que los usuarios notifican errores relacionados con Intune. Desde la aplicación Portal de empresa, los empleados pueden:

- Cargar informes de diagnóstico directamente para el equipo de desarrollo de Microsoft.
- Enviar por correo electrónico un identificador de incidente al equipo de soporte técnico de TI de la empresa.

Para más información, consulte [Envío de errores de macOS](../user-help/send-errors-macos.md).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10---1195010---"></a>Intune se adapta a Fluent Design System en la aplicación de Portal de empresa para Windows 10<!-- 1195010 -->
La aplicación Portal de empresa de Intune para Windows 10 se ha actualizado con la [vista de navegación de Fluent Design System](/windows/uwp/design/basics/navigation-basics). En la parte lateral de la aplicación, verá una lista estática vertical de todas las páginas de nivel superior. Haga clic en cualquier vínculo para ver y cambiar entre páginas rápidamente. Esta es la primera de varias actualizaciones que verá como parte de nuestros esfuerzos para crear una experiencia más adaptable, empática y familiar en Intune. Para ver el aspecto actualizado vaya a [Actualizaciones de la interfaz de usuario para las aplicaciones de usuario final de Intune](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="march-2018"></a>Marzo de 2018

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune---748789---"></a>Alertas para aplicaciones de línea de negocio (LOB) iOS a punto de expirar para Microsoft Intune<!-- 748789 -->

En Azure Portal, Intune le avisa de las aplicaciones de línea de negocio iOS que están a punto de expirar. Al cargar una nueva versión de la aplicación de línea de negocio iOS, Intune quita la notificación de expiración de la lista de aplicaciones. Esta notificación de expiración solo está activa para las aplicaciones de línea de negocio iOS recién cargadas. 30 días antes de que expire el perfil de aprovisionamiento de la aplicación LOB iOS, aparece una advertencia. Cuando expira, la alerta cambia a Expirada.

#### <a name="customize-your-company-portal-themes-with-hex-codes--1049561---"></a>Personalización de los temas del Portal de empresa con códigos hexadecimales<!--1049561 -->

Puede personalizar el color del tema de las aplicaciones del Portal de empresa mediante códigos hexadecimales. Cuando escribe el código hexadecimal, Intune determina el color del texto que proporciona el nivel más alto de contraste entre el color del texto y el color del fondo. Puede obtener una vista previa del color de texto y el logotipo de la empresa con el color en **Aplicaciones cliente** > **Portal de empresa**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise---1813081---"></a>Inclusión o exclusión de la asignación de aplicaciones con base en grupos para Android Enterprise<!-- 1813081 -->

Android Enterprise (anteriormente conocido como Android for Work) admite la inclusión y exclusión de grupos, pero no los grupos integrados creados previamente **Todos los usuarios** y **Todos los dispositivos**. Para obtener más información, vea [Inclusión y exclusión de asignaciones de aplicaciones en Microsoft Intune](../apps/apps-inc-exl-assignments.md).


### <a name="device-management"></a>Administración de dispositivos

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome---2258071---"></a>Exportación de todos los dispositivos a archivos CSV en IE, Microsoft Edge o Chrome<!-- 2258071 -->
En **Dispositivos** > **Todos los dispositivos**, puede **Exportar** los dispositivos a una lista con formato CSV. Los usuarios de Internet Explorer (IE) con >10.000 dispositivos pueden exportar correctamente sus dispositivos a varios archivos. Cada archivo tiene un máximo de 10.000 dispositivos.

Los usuarios de Microsoft Edge y Chrome con más de 30 000 dispositivos pueden exportar correctamente sus dispositivos a varios archivos. Cada archivo tiene un máximo de 30.000 dispositivos.

[Administrar dispositivos](../remote-actions/device-management.md) proporciona más detalles sobre lo que puede hacer con los dispositivos que administra.

#### <a name="new-security-enhancements-in-the-intune-service----1637539---"></a>Nuevas mejoras de seguridad en el servicio de Intune <!-- 1637539 -->   

Se ha incorporado un botón de alternancia en Intune en Azure que los clientes independientes de Intune pueden usar para tratar dispositivos sin ninguna directiva asignada como **Compatible** (característica de seguridad desactivada) o como **No compatible** (característica de seguridad activada). Esto garantiza el acceso a los recursos únicamente después de que se haya evaluado el cumplimiento del dispositivo.

Esta característica afecta al usuario de forma distinta según tenga ya directivas de cumplimiento asignadas o no.

- Si es una cuenta nueva o existente y no tiene ninguna directiva de cumplimiento asignada a los dispositivos, el botón de alternancia se establece automáticamente en **Compatible**. La característica está desactivada como opción predeterminada en la consola. Los usuarios finales no se ven afectados.
- Si es una cuenta existente y tiene algún dispositivo con una directiva de cumplimiento asignada, el botón de alternancia se establece automáticamente en **No compatible**. La característica está activada como opción predeterminada en cuanto se lanza la actualización de marzo.

Si usa directivas de cumplimiento con acceso condicional (CA) y tiene la característica activada, los dispositivos que no tengan asignada como mínimo una directiva de cumplimiento son bloqueados por CA. Los usuarios finales asociados a estos dispositivos y a los que se haya concedido acceso previamente al correo electrónico pierden el acceso a menos que se asigne como mínimo una directiva de cumplimiento a todos los dispositivos.   

Tenga en cuenta que aunque el estado predeterminado del botón de alternancia se muestra en la interfaz de usuario inmediatamente con las actualizaciones de marzo del servicio de Intune, este estado del botón de alternancia no se aplica de inmediato. Los cambios que realice en el botón de alternancia no afectan al cumplimiento del dispositivo hasta la distribución de paquetes piloto a la cuenta para que tenga un botón de alternancia que funcione. Se le informa mediante el centro de mensajes una vez que se terminan de distribuir paquetes piloto a la cuenta. Esto podría tardar unos días después de la actualización del servicio de Intune de marzo.

**Información adicional**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection---846515---"></a>Detección de jailbreak mejorada<!-- 846515 -->

La detección de jailbreak mejorada es una nueva opción de cumplimiento que mejora la forma en que Intune evalúa los dispositivos con Jailbreak. La opción hace que el dispositivo se comunique con Intune con más frecuencia, lo que usa los servicios de ubicación del dispositivo y afecta al uso de la batería.

#### <a name="reset-passwords-for-android-o-devices---1238299---"></a>Restablecimiento de contraseñas para dispositivos Android O<!-- 1238299 -->
Puede restablecer las contraseñas de los dispositivos Android 8.0 inscritos con perfiles de Work. Cuando se envía una solicitud de "Restablecer contraseña" a un dispositivo Android 8.0, se establece una nueva contraseña de desbloqueo de dispositivo o un desafío de perfil administrado al usuario actual. La contraseña o el desafío se envían y se aplican de inmediato.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups--1307012---"></a>Destinación de las directivas de cumplimiento a dispositivos en grupos de dispositivos<!--1307012 -->

Puede destinar directivas de cumplimiento a usuarios de grupos de usuarios. Con esta actualización, puede destinar directivas de cumplimiento a dispositivos de grupos de dispositivos. Los dispositivos de destino como parte de grupos de dispositivos no reciben ninguna acción de cumplimiento.

#### <a name="new-management-name-column---1333586---"></a>Nueva columna Nombre de administración<!-- 1333586 -->
 Hay una nueva columna denominada **Nombre de administración** disponible en la hoja de dispositivos. Se trata de un nombre generado automáticamente y que no se puede modificar asignado por cada dispositivo, en función de la fórmula siguiente:
- Nombre predeterminado para todos los dispositivos: <username><em><devicetype></em><enrollmenttimestamp>
- Para dispositivos agregados en masa: <IdentificadorPaquete/IdentificadorPerfil><em><DeviceType></em><EnrollmentTime>

Se trata de una columna opcional en la hoja de dispositivos. No está disponible de forma predeterminada y solo se puede acceder a ella mediante el selector de columnas. El nombre del dispositivo no se ve afectado por esta nueva columna.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes--1550837---"></a>Los dispositivos iOS solicitan un PIN cada 15 minutos<!--1550837 -->
Después de aplicar una directiva de configuración o cumplimiento a un dispositivo iOS, cada 15 minutos se pide al usuario que establezca un PIN, y se le sigue pidiendo hasta que lo hace.

#### <a name="schedule-your-automatic-updates--1805514---"></a>Programación de las actualizaciones automáticas<!--1805514 -->
Intune le permite controlar la instalación de las actualizaciones automáticas por medio de la opción [Anillo de actualización de Windows](../protect/windows-update-for-business-configure.md). Con esta actualización, puede programar actualizaciones recurrentes, incluidos la semana, el día y la hora.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate--2221763---"></a>Uso de un nombre completo como sujeto de un certificado SCEP<!--2221763 -->
Cuando se crea un perfil de certificado SCEP, hay que indicar el nombre del sujeto. Con esta actualización, puede usar el nombre completo como sujeto. En **Nombre del sujeto**, seleccione **Personalizado** y, después, escriba `CN={{OnPrem_Distinguished_Name}}`. Para usar la variable `{{OnPrem_Distinguished_Name}}`, no olvide sincronizar el atributo de usuario `onpremisesdistingishedname` por medio de [Azure Active Directory (AD) Connect](/azure/active-directory/connect/active-directory-aadconnect) con Azure AD.

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="enable-bluetooth-contact-sharing---android-for-work--1098983---"></a>Habilitación del uso compartido de contactos a través de Bluetooth: Android for Work<!--1098983 -->
Android impide de forma predeterminada que los contactos del perfil del trabajo se sincronicen con dispositivos Bluetooth. Como consecuencia, los contactos del perfil de trabajo no aparecen en la identificación de llamadas en los dispositivos Bluetooth.

Con esta actualización, hay una nueva opción en **Android for Work** > **Restricciones de dispositivos** > **Configuración del perfil de trabajo**:
- Uso compartido de contactos a través de Bluetooth

El administrador de Intune puede configurar esta opción para permitir el uso compartido de contactos. Esto resulta útil para emparejar un dispositivo con el dispositivo Bluetooth de un coche que muestra el identificador de llamada cuando se usa el manos libres. Si se habilita, se mostrarán los contactos del perfil de trabajo. Si no, no se mostrarán.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source---1690459---"></a>Configuración del equipo selector para controlar el origen de descarga de las aplicaciones macOS<!-- 1690459 -->

Puede configurar el equipo selector para proteger los dispositivos desde las aplicaciones mediante el control del origen de descarga de las aplicaciones. Puede configurar los orígenes de descarga siguientes: **Mac App Store**, **Mac App Store y desarrolladores identificados** o **Cualquier sitio**. Puede configurar si los usuarios pueden instalar una aplicación al presionar Control+clic para invalidar estos controles del equipo selector.

Esta configuración se puede encontrar en **Configuración del dispositivo** -> **Crear perfil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall---1690461---"></a>Configuración del firewall de aplicaciones Mac<!-- 1690461 -->

Puede configurar el firewall de aplicaciones Mac. Puede usarlo para controlar las conexiones en cada aplicación, en lugar de en cada puerto. Esto facilita la capacidad de aprovechar las ventajas de protección de firewall y ayuda a evitar que aplicaciones no deseadas tomen el control de los puertos de red abiertos para las aplicaciones legítimas.

Esta característica se puede encontrar en **Configuración del dispositivo** -> **Crear perfil** -> **macOS** -> **Endpoint Protection**.

Una vez que habilite la opción Firewall, puede configurar el firewall con dos estrategias:

- Bloqueo de todas las conexiones entrantes

   Puede bloquear todas las conexiones entrantes para los dispositivos de destino. Si decide hacerlo, las conexiones entrantes se bloquean para todas las aplicaciones.

- Permiso o bloqueo de aplicaciones específicas

   Puede permitir o bloquear la recepción de conexiones entrantes en aplicaciones específicas. También puede habilitar el modo sigiloso para impedir respuestas a las solicitudes de sondeo.

#### <a name="detailed-error-codes-and-messages---1376342---"></a>Códigos de error y mensajes detallados<!-- 1376342 -->

En la configuración del dispositivo, se pueden ver mensajes y códigos de error más detallados. Este informe detallado muestra la configuración, el estado de esta configuración y los detalles sobre cómo solucionar problemas.

##### <a name="more-information"></a>Más información

- Bloqueo de todas las conexiones entrantes

   Esto impide que todos los servicios de uso compartido (como Uso compartido de archivos y Pantalla compartida) reciban conexiones entrantes. Los servicios del sistema a los que se sigue permitiendo recibir conexiones entrantes son los siguientes:
  - configd: implementa DHCP y otros servicios de configuración de red
  - mDNSResponder: implementa Bonjour
  - racoon: implementa IPSec

    Para usar los servicios de uso compartido, asegúrese de que **Conexiones entrantes** esté establecido en **Sin configurar**, y no en **Bloquear**.

- Modo sigiloso

   Habilite esta opción para impedir que el equipo responda a las solicitudes de sondeo. El equipo seguirá respondiendo a las solicitudes entrantes de las aplicaciones autorizadas. Las solicitudes inesperadas, como ICMP (ping), se ignoran.

#### <a name="disable-checks-on-device-restart--1805490---"></a>Deshabilitación de las comprobaciones al reiniciar el dispositivo<!--1805490 -->
Intune le permite controlar la [administración de las actualizaciones de software](../protect/windows-update-for-business-configure.md). Con esta actualización, la propiedad <strong>Comprobaciones de reinicio</strong> está disponible y habilitada de forma predeterminada. Para omitir las comprobaciones típicas que tienen lugar cuando un dispositivo se reinicia (por ejemplo, usuarios activos, niveles de batería, etc.), seleccione <strong>Omitir</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings---1746293---"></a>Nuevos canales de Windows 10 Insider Preview disponibles para anillos de implementación<!-- 1746293 -->
Ahora tiene la opción de seleccionar los siguientes canales de servicio de Windows 10 Insider Preview al crear un anillo de implementación de Windows 10:
- Compilación de Windows Insider: Rápida
- Compilación de Windows Insider: Lenta
- Versión de lanzamiento de Windows Insider 

Para obtener más información sobre estos canales, vea [Manage Insider Preview Builds](https://insider.windows.com/en-us/for-business-getting-started/#explore) (Administrar compilaciones de Insider Preview).
Para obtener más información sobre cómo crear canales de implementación en Intune, vea [Manage software updates in Intune](../protect/windows-update-for-business-configure.md) (Administrar actualizaciones de software en Intune).

### <a name="new-windows-defender-exploit-guard-settings---1631893---"></a>Nueva configuración de Protección contra vulnerabilidades de seguridad de Windows Defender<!-- 1631893 -->

Seis nuevas opciones de <strong>reducción de la superficie expuesta a ataques</strong> y funcionalidades ampliadas de <strong>Acceso controlado a carpetas: protección de carpetas</strong> están ahora disponibles. Estas opciones se pueden encontrar en: Configuración del dispositivo\Perfiles\
Crear perfil\Endpoint protection\Protección contra vulnerabilidades de seguridad de Windows Defender.

#### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

|Nombre de la configuración  |Opciones de configuración  |Descripción  |
|---------|---------|---------|
|Protección de ransomware avanzada|Habilitado, Auditoría, No configurado|Usar protección ransomware intensa.|
|Marcar el robo de credenciales desde el subsistema de autoridad de seguridad local de Windows|Habilitado, Auditoría, No configurado|Marcar el robo de credenciales desde el subsistema de autoridad de seguridad local de Windows (lsass.exe).|
|Creación del proceso desde comandos PSExec y WMI|Bloquear, Auditoría, No configurado|Bloquear creaciones del proceso que se originan desde comandos PSExec y WMI.|
|Procesos que no son de confianza y sin firma que se ejecutan desde una unidad USB|Bloquear, Auditoría, No configurado|Bloquee la ejecución desde USB de procesos que no sean de confianza y estén sin firmar.|
|Archivos ejecutables que no cumplen unos criterios de uso habitual, edad o lista de confianza|Bloquear, Auditoría, No configurado|Bloquee la ejecución de archivos ejecutables a menos que cumplan una¡os criterios de prevalencia, antigüedad o lista de confianza.|

#### <a name="controlled-folder-access"></a>Acceso controlado a carpetas

|              Nombre de la configuración               |                                                              Opciones de configuración                                                              | Descripción |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Protección de carpetas (ya implementado) | No configurado, Habilitar, Solo auditoría (ya implementado)<br><br> <strong>Nuevo</strong><br>Impedir la modificación del disco, Auditar la modificación del disco |             |

Proteger los archivos y carpetas frente a cambios no autorizados de aplicaciones hostiles.<br><br>**Habilitar**: impida que las aplicaciones que no son de confianza modifiquen o eliminen archivos de carpetas protegidas y que escriban en los sectores de disco.<br><br>
**Solo impedir la modificación del disco**:<br>Impedir que las aplicaciones que no son de confianza escriban en los sectores de disco. Las aplicaciones que no son de confianza todavía podrán modificar o eliminar archivos en las carpetas protegidas.|

### <a name="intune-apps"></a>Aplicaciones de Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview---710595---"></a>Los sitios web de Azure Active Directory pueden requerir la aplicación Intune Managed Browser y compatibilidad con el inicio de sesión único para Managed Browser (versión preliminar pública)<!-- 710595 -->

Con Azure Active Directory (Azure AD), ya puede restringir el acceso a sitios web en dispositivos móviles para la aplicación Intune Managed Browser. En Managed Browser, los datos del sitio web permanecen seguros y separados de los datos personales del usuario final. Además, Managed Browser admitirá la función de inicio de sesión único para sitios protegidos por Azure AD. Al iniciar sesión en Managed Browser o al usar Managed Browser en un dispositivo con otra aplicación administrada por Intune, Managed Browser puede acceder a sitios corporativos protegidos por Azure AD sin que el usuario tenga que escribir sus credenciales. Esta función se aplica a sitios como Outlook Web Access (OWA) y SharePoint Online, además de otros sitios corporativos, como los recursos de la intranet a los que se accede mediante Azure App Proxy. Para más información, consulte [Controles de acceso en el acceso condicional de Azure Active Directory](/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates--976944---"></a>Actualizaciones visuales de la aplicación Portal de empresa para Android<!--976944 -->

Hemos actualizado la aplicación Portal de empresa para Android para seguir las directrices de [Material Design](https://material.io/) de Android. Puede ver las imágenes de los iconos nuevos en el artículo [Novedades de la interfaz de usuario de aplicaciones](whats-new-app-ui.md).

#### <a name="company-portal-enrollment-improved---1874230-eeready--"></a>Mejora de la inscripción de Portal de empresa<!-- 1874230 eeready-->
Los usuarios que inscriben un dispositivo mediante el Portal de empresa en Windows 10, compilación 1709 y versiones posteriores, ahora pueden realizar el primer paso de la inscripción sin salir de la aplicación.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists--1725868---"></a>HoloLens y Surface Hub ahora aparecen en las listas de dispositivos<!--1725868 -->
Se ha agregado compatibilidad para mostrar los dispositivos HoloLens y Surface Hub inscritos en Intune en la aplicación Portal de empresa para Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks---1488911---"></a>Categorías personalizadas para libros electrónicos comprados a través de un programa de compras por volumen (VPP)<!-- 1488911 -->
Puede crear categorías personalizadas de libros electrónicos y, después, asignar libros electrónicos de VPP a esas categorías personalizadas. Después, los usuarios finales podrán ver las categorías de libros electrónicos recién creadas y los libros asignados a las categorías. Para obtener más información, vea [Administración de aplicaciones y libros comprados por volumen con Microsoft Intune](../apps/vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option---2070166---"></a>Cambios de compatibilidad con la opción Enviar comentarios de la aplicación Portal de empresa para Windows<!-- 2070166 -->
A partir del 30 de abril de 2018 la opción **Enviar comentarios** de la aplicación Portal de empresa para Windows solo funcionará en dispositivos que ejecuten la Actualización de aniversario de Windows 10 (1607) y versiones posteriores. La opción Enviar comentarios ya no se admite cuando se usa la aplicación Portal de empresa para Windows con:  
- Windows 10, versión 1507  
- Windows 10, versión 1511  
- Windows Phone 8.1

Si su dispositivo ejecuta Windows 10 RS1 o una versión posterior, descargue de la tienda la versión más reciente de la aplicación Portal de empresa para Windows. Si ejecuta una versión no compatible, siga enviando los comentarios a través de los canales siguientes:
- La aplicación Concentrador de comentarios en Windows 10
- Un correo electrónico a WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings---1631890---"></a>Nueva configuración de Protección de aplicaciones de Windows Defender<!-- 1631890 -->

- **Habilitar la aceleración gráfica**: los administradores pueden habilitar un procesador de gráficos virtuales para Windows Defender Application Guard. Esta configuración permite que la CPU descargue el procesamiento de gráficos a la vGPU. Esto puede mejorar el rendimiento cuando se trabaja con sitios web con gran cantidad de datos gráficos o se ve un vídeo dentro del contenedor.

- **SaveFilestoHost**: los administradores pueden permitir que los archivos pasen de Microsoft Edge que se ejecuta en el contenedor al sistema de archivos host. Su activación permite que los usuarios descarguen archivos de Microsoft Edge en el contenedor al sistema de archivos de host.

#### <a name="mam-protection-policies-targeted-based-on-management-state---1665993---"></a>Destino de directivas de protección de MAM en función del estado de administración<!-- 1665993 -->
Puede destinar las directivas de MAM en función del estado de administración del dispositivo:
- **Dispositivos Android**: puede tener como destino dispositivos no administrados, dispositivos administrados con Intune y perfiles de Android Enterprise administrados con Intune (anteriormente Android for Work).
- **Dispositivos iOS**: puede tener como destino dispositivos no administrados (solo MAM) o dispositivos administrados con Intune.

    > [!NOTE]
    > - La compatibilidad de iOS con esta funcionalidad se ha ido lanzando a lo largo de abril de 2018.

Para obtener más información, vea [Target app protection policies based on device management state](../apps/app-protection-policies.md) (Destinar directivas de protección de aplicaciones en función del estado de administración del dispositivo).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows---1683758---"></a>Mejoras en el lenguaje de la aplicación Portal de empresa para Windows<!-- 1683758 -->
Se ha mejorado el lenguaje del Portal de empresa para Windows 10 para que sea más fácil de usar y más específico para la empresa. Para ver algunas imágenes de ejemplo de lo que se ha hecho, vea [Novedades en la UI de la aplicación](whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy---1440709---"></a>Nuevas adiciones a los documentos sobre privacidad del usuario<!-- 1440709 -->
Como parte del esfuerzo por proporcionar a los usuarios finales más control sobre sus datos y su privacidad, se han publicado actualizaciones de los documentos que explican cómo ver y quitar datos almacenados localmente por las aplicaciones del Portal de empresa. Puede encontrar estas actualizaciones en:

- **Android**: [Cómo quitar un dispositivo Android de Intune](../user-help/unenroll-your-device-from-intune-android.md)
- **Android, si el usuario ha rechazado los términos de uso**: [Quitar un dispositivo de la administración si ha rechazado los "términos de uso"](../user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Quitar un dispositivo iOS de Intune](../user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Quitar el dispositivo Windows de Intune](../user-help/unenroll-your-device-from-intune-windows.md)

<!-- ########################## -->
## <a name="february-2018"></a>Febrero de 2018

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685---"></a>Compatibilidad de Intune con varias cuentas del programa del Programa de inscripción de dispositivos (DEP) de Apple o de Apple School Manager<!-- 747685 -->

Intune ahora admite la inscripción de dispositivos de hasta 100 cuentas distintas del [Programa de inscripción de dispositivos de Apple](../enrollment/device-enrollment-program-enroll-ios.md) o de [Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md). Cada token cargado puede administrarse por separado para los perfiles y los dispositivos de inscripción. Es posible asignar un perfil de inscripción diferente para cada token de DEP/School Manager. Si se cargan varios tokens de School Manager, solo pueden compartirse de uno en uno con Microsoft School Data Sync.

Tras la migración, la versión beta de las API Graph y los scripts publicados para la administración de Apple DEP o ASM en Graph ya no funcionará. Las nuevas versiones beta de las API Graph están en desarrollo y se publicarán después de la migración.

#### <a name="see-enrollment-restrictions-per-user---1634444-eeready-wnready---"></a>Visualización de las restricciones de inscripción por usuario<!-- 1634444 eeready wnready -->
En la hoja **Solución de problemas**, ahora puede ver las [restricciones de inscripción](../enrollment/enrollment-restrictions-set.md) que están en vigor para cada usuario si selecciona **Restricciones de inscripción** en la lista **Asignaciones**.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment---747625-eeready---"></a>Nueva opción para la autenticación de usuario para la inscripción masiva de Apple<!-- 747625 eeready -->

> [!NOTE]
> Los nuevos inquilinos verán esta característica inmediatamente. En cambio, en el caso de los inquilinos existentes, se implementará en abril. Es posible que no tenga acceso a estas nuevas características hasta que la implementación se haya completado.

Intune ofrece ahora la opción de autenticar los dispositivos mediante la aplicación Portal de empresa para los siguientes métodos de inscripción:

- Programa de inscripción de dispositivos de Apple
- Apple School Manager
- Inscripción de Apple Configurator

Al usar la opción Portal de empresa, se puede aplicar la autenticación multifactor de Azure Active Directory sin bloquear estos métodos de inscripción.

Al usar la opción Portal de empresa, Intune omite la autenticación de usuario en el Asistente de configuración de iOS para la inscripción de afinidad del usuario. Esto significa que el dispositivo se inscribe inicialmente como un dispositivo sin usuario, por lo que no recibe las configuraciones ni las directivas de grupos de usuarios. Solo recibe las configuraciones y las directivas de grupos de dispositivos. Sin embargo, Intune instalará automáticamente la aplicación Portal de empresa en el dispositivo. El primer usuario que inicie la aplicación Portal de empresa e inicie sesión en ella se asociará con el dispositivo en Intune. En este momento, el usuario recibirá las configuraciones y las directivas de sus grupos de usuarios. No se puede cambiar la asociación del usuario sin volver a realizar la inscripción.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685-eeready---"></a>Compatibilidad de Intune con varias cuentas del programa del Programa de inscripción de dispositivos (DEP) de Apple o de Apple School Manager<!-- 747685 eeready -->

Intune ahora admite la inscripción de dispositivos de hasta 100 cuentas distintas del Programa de inscripción de dispositivos de Apple o de Apple School Manager. Cada token cargado puede administrarse por separado para los perfiles y los dispositivos de inscripción. Es posible asignar un perfil de inscripción diferente para cada token de DEP/School Manager. Si se cargan varios tokens de School Manager, solo pueden compartirse de uno en uno con Microsoft School Data Sync.

Tras la migración, la versión beta de las API Graph y los scripts publicados para la administración de Apple DEP o ASM en Graph ya no funcionará. Las nuevas versiones beta de las API Graph están en desarrollo y se publicarán después de la migración.

### <a name="remote-printing-over-a-secure-network---1709994----"></a>Impresión remota a través de una red segura<!-- 1709994  -->
Las soluciones de impresión móvil inalámbricas de PrinterOn permitirán a los usuarios imprimir remotamente desde cualquier lugar en cualquier momento a través de una red segura. PrinterOn se integrará con el SDK de aplicaciones de Intune para iOS y Android. Podrá destinar las directivas de protección de aplicaciones a esta aplicación a través de la hoja **Directivas de protección de aplicaciones** de Intune de la consola de administración. Los usuarios finales podrán descargar la aplicación "PrinterOn for Microsoft" a través de Play Store o iTunes para usarla dentro de su ecosistema de Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager---1352411---"></a>Compatibilidad del Portal de empresa de macOS para las inscripciones que usen el administrador de inscripciones de dispositivos<!-- 1352411 -->

Los usuarios ya pueden usar el administrador de inscripciones de dispositivos cuando se inscriban con Portal de empresa para macOS.

### <a name="device-management"></a>Administración de dispositivos

#### <a name="windows-defender-health-status-and-threat-status-reports--854704---"></a>Informes de estado de mantenimiento y de estado de amenazas de Windows Defender<!--854704 -->

Conocer el estado de mantenimiento de Windows Defender es clave para la administración de equipos de Windows.  Con esta actualización, Intune agrega nuevos informes y acciones para el estado y el mantenimiento del agente de Windows Defender. Con un informe de resumen de estado en la [carga de trabajo Cumplimiento de dispositivos](../protect/compliance-policy-monitor.md), puede ver los dispositivos que necesitan alguna de las acciones siguientes:
- actualización de la firma
- Reiniciar
- intervención manual
- examen completo
- otros estados del agente que requieren intervención

Un informe de obtención de detalles para cada categoría de estado muestra los equipos individuales que requieren atención o identificados como **limpios**.

#### <a name="new-privacy-settings-for-device-restrictions--1308926---"></a>Nueva configuración de privacidad para las restricciones de dispositivos<!--1308926 -->
Hay [dos nuevas opciones de privacidad](../configuration/device-restrictions-windows-10.md#privacy) disponibles para los dispositivos:
- **Publicar las actividades del usuario**: establezca esta opción en **Bloquear** para evitar experiencias compartidas y la detección de recursos usados recientemente en el selector de tareas.
- **Solo actividades locales**: establezca esta opción en **Bloquear** para evitar experiencias compartidas y la detección de recursos usados recientemente en el selector de tareas según la actividad local únicamente.

#### <a name="new-settings-for-the-microsoft-edge-browser--1469166---"></a>Nueva configuración para el explorador Microsoft Edge<!--1469166 -->
[Dos nuevas opciones](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) están ahora disponibles para los dispositivos con el explorador Microsoft Edge: **Path to favorites file** (Ruta de acceso al archivo de favoritos) y **Changes to Favorites** (Cambios en Favoritos).

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="protocol-exceptions-for-applications--1035509---"></a>Excepciones de protocolo para las aplicaciones<!--1035509 -->

Puede crear excepciones a la directiva de transferencia de datos de la administración de aplicaciones móviles (MAM) de Intune para abrir determinadas aplicaciones no administradas. Dichas aplicaciones deben ser de confianza para el departamento de TI. Aparte de las excepciones que cree, la transferencia de datos sigue estando limitada a las aplicaciones que se administran mediante Intune cuando la directiva de transferencia de datos se establece en **Managed apps only** (Solo aplicaciones administradas). Puede crear las restricciones mediante protocolos (iOS) o paquetes (Android).

Por ejemplo, puede agregar el paquete de WebEx como una excepción a la directiva de transferencia de datos de MAM. Esto permitirá que los vínculos de WebEx en un mensaje de correo electrónico de Outlook administrado se abran directamente en la aplicación de WebEx. Se seguirá restringiendo la transferencia de datos en otras aplicaciones no administradas. Para obtener más información, consulte [Data transfer policy exceptions for apps](../apps/app-protection-policies-exception.md) (Excepciones de la directiva de transferencia de datos para aplicaciones).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results---1469193---"></a>Datos cifrados de Windows Information Protection (WIP) en los resultados de la búsqueda de Windows<!-- 1469193 -->
Un parámetro de configuración de la directiva de Windows Information Protection (WIP) le permite controlar si los datos cifrados por WIP se incluyen en los resultados de la búsqueda de Windows. Para establecer esta opción de la directiva de protección de aplicaciones, seleccione **Permitir que el indizador de Windows Search busque elementos cifrados** en la **Configuración avanzada** de la directiva de Windows Information Protection. La directiva de protección de aplicaciones debe establecerse en la plataforma *Windows 10* y la directiva de aplicación **Estado de inscripción** debe establecerse en **Con inscripción**. Para obtener más información, consulte [Permitir que el indizador de Windows Search busque elementos cifrados](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app---1740840---"></a>Configuración de una aplicación MSI móvil de auto-actualización<!-- 1740840 -->
Puede configurar una aplicación móvil MSI con auto-actualización para que omita el proceso de comprobación de versión. Esta capacidad resulta útil para evitar que se produzca una condición de carrera. Por ejemplo, este tipo de condición de carrera podría producirse cuando la aplicación que el desarrollador de aplicaciones actualiza automáticamente también la estuviera actualizando Intune. Ambos podrían tratar de aplicar una versión de la aplicación en un cliente de Windows, lo que podría crear un conflicto. Para estas aplicaciones MSI que se actualizan automáticamente, puede configurar el valor **Omitir la versión de la aplicación** en la hoja **Información de la aplicación**. Cuando se cambia esta configuración a **Sí**, Microsoft Intune omite la versión de la aplicación instalada en el cliente de Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune---1864117---"></a>Conjuntos de licencias de aplicaciones relacionadas admitidas en Intune<!-- 1864117 -->
Intune en Azure Portal ya admite conjuntos de licencias de aplicaciones relacionadas como un elemento de aplicación único en la interfaz de usuario. Además, las aplicaciones con licencia sin conexión sincronizadas desde Microsoft Store para Empresas se consolidarán en una entrada de aplicación única y los detalles de implementación de los paquetes individuales se migrarán a la entrada única. Para ver los conjuntos de licencias de aplicaciones relacionadas en Azure Portal, seleccione **Licencias de aplicación** en la hoja **Aplicaciones cliente**.

### <a name="device-configuration"></a>Configuración del dispositivo
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption---1463582---"></a>Extensiones de archivo de Windows Information Protection (WIP) para el cifrado automático<!-- 1463582 -->
Un valor de la directiva de Windows Information Protection (WIP) le permite ahora especificar qué extensiones de archivo se cifran automáticamente al copiar desde un recurso compartido del bloque de mensajes del servidor (SMB) dentro de los límites corporativos, como se define en la directiva de WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Configurar las opciones de la cuenta del recurso para Surface Hubs

Ya puede configurar de forma remota las opciones de la cuenta del recurso para Surface Hubs.

Una instancia de Surface Hub usa la cuenta del recurso para autenticarse en Skype o Exchange y así poder unirse a una reunión.
Deberá crear una cuenta del recurso única para que Surface Hub pueda aparecer en la reunión como la sala de conferencias.
Por ejemplo, una cuenta del recurso como **Sala de conferencias B41/6233**.

> [!NOTE]
> - Si deja campos en blanco invalidará los atributos configurados previamente en el dispositivo.
>
> - Las propiedades de la cuenta del recurso pueden cambiar dinámicamente en Surface Hub. Por ejemplo, si el cambio de contraseñas está activado. Por lo tanto, es posible que los valores de la consola de Azure tarden algún tiempo en reflejar la realidad en el dispositivo.
>
>   Para entender lo que está configurado actualmente en Surface Hub, se puede incluir la información de la cuenta del recurso en el inventario de hardware (que ya tiene un intervalo de 7 días) o como propiedades de solo lectura. Para mejorar la precisión después de llevar a cabo la acción remota, puede obtener el estado de los parámetros inmediatamente después de ejecutar la acción para actualizar la cuenta o los parámetros en Surface Hub.

##### <a name="attack-surface-reduction"></a>Reducción de la superficie expuesta a ataques

|Nombre de la configuración  |Opciones de configuración  |Descripción  |
|---------|---------|---------|
|Ejecución de contenido ejecutable protegido por contraseña del correo electrónico|Bloquear, Auditoría, No configurado|Evitar que se ejecuten los archivos ejecutables protegidos por contraseña descargados a través del correo electrónico.|
|Protección de ransomware avanzada|Habilitado, Auditoría, No configurado|Usar protección ransomware intensa.|
|Marcar el robo de credenciales desde el subsistema de autoridad de seguridad local de Windows|Habilitado, Auditoría, No configurado|Marcar el robo de credenciales desde el subsistema de autoridad de seguridad local de Windows (lsass.exe).|
|Creación del proceso desde comandos PSExec y WMI|Bloquear, Auditoría, No configurado|Bloquear creaciones del proceso que se originan desde comandos PSExec y WMI.|
|Procesos que no son de confianza y sin firma que se ejecutan desde una unidad USB|Bloquear, Auditoría, No configurado|Bloquee la ejecución desde USB de procesos que no sean de confianza y estén sin firmar.|
|Archivos ejecutables que no cumplen unos criterios de uso habitual, edad o lista de confianza|Bloquear, Auditoría, No configurado|Bloquee la ejecución de archivos ejecutables a menos que cumplan una¡os criterios de prevalencia, antigüedad o lista de confianza.|

##### <a name="controlled-folder-access"></a>Acceso controlado a carpetas

|              Nombre de la configuración               |                                                              Opciones de configuración                                                              | Descripción |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Protección de carpetas (ya implementado) | No configurado, Habilitar, Solo auditoría (ya implementado)<br><br> <strong>Nuevo</strong><br>Impedir la modificación del disco, Auditar la modificación del disco |             |

Proteger los archivos y carpetas frente a cambios no autorizados de aplicaciones hostiles.<br><br>**Habilitar**: impida que las aplicaciones que no son de confianza modifiquen o eliminen archivos de carpetas protegidas y que escriban en los sectores de disco.<br><br>
**Solo impedir la modificación del disco**:<br>Impedir que las aplicaciones que no son de confianza escriban en los sectores de disco. Las aplicaciones que no son de confianza todavía podrán modificar o eliminar archivos en las carpetas protegidas.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies--1704133--"></a>Adiciones a la configuración de seguridad del sistema para las directivas de cumplimiento de Windows 10 y posteriores<!--1704133-->

Ya hay disponibles adiciones a la configuración de cumplimiento de Windows 10, incluida la necesidad del Firewall y el Antivirus de Windows Defender.

### <a name="intune-apps"></a>Aplicaciones de Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business--1222672--"></a>Compatibilidad con aplicaciones sin conexión de Microsoft Store para Empresas<!--1222672-->
Las aplicaciones sin conexión que ha adquirido en Microsoft Store para Empresas ahora se sincronizan con Azure Portal. Puede implementar estas aplicaciones en grupos de usuarios o dispositivos. Las aplicaciones sin conexión se instalan mediante Intune, no Microsoft Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile---1728700---"></a>Impedir que los usuarios finales agreguen o quiten cuentas manualmente en el perfil de trabajo<!-- 1728700 -->

Al implementar la aplicación Gmail en un perfil de Android for Work, puede impedir que los usuarios finales agreguen o quiten cuentas en el perfil de trabajo mediante la opción de configuración **Agregar y quitar cuentas** del perfil de restricciones del dispositivo Android for Work.

<!-- ########################## -->
## <a name="january-2018"></a>Enero de 2018

### <a name="device-enrollment"></a>Inscripción de dispositivos

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire---1639263---"></a>Alertas de tokens caducados y tokens que caducan pronto<!-- 1639263 -->
Ahora en la página de introducción se muestran las alertas de los tokens caducados y los tokens que caducan pronto. Al hacer clic en una alerta para un único token, se le dirigirá a la página de detalles del token.  Si hace clic en la alerta con varios tokens, se le dirigirá a una lista de todos los tokens con su estado. Los administradores deben renovar sus tokens antes de la fecha de caducidad.

### <a name="device-management"></a>Administración de dispositivos

#### <a name="remote-erase-command-support-for-macos-devices---1438084---"></a>Compatibilidad con el comando "Borrar" de forma remota en dispositivos macOS<!-- 1438084 -->

Los administradores pueden emitir un comando Borrar de forma remota en dispositivos macOS.

> [!IMPORTANT]
> El comando de borrado no se puede deshacer y debe utilizarse con precaución.

El comando de borrado quita todos los datos, incluido el sistema operativo, de un dispositivo. También quita el dispositivo de la administración de Intune. No se genera ninguna advertencia al usuario y el borrado se produce inmediatamente al emitir el comando.

Debe configurar un PIN de recuperación de 6 dígitos. Este código PIN se puede usar para desbloquear el dispositivo borrado, momento en que comenzará la reinstalación del sistema operativo. Una vez iniciado el borrado, el PIN aparece en una barra de estado en la hoja de información general del dispositivo en Intune. El PIN permanecerá mientras el borrado esté en curso. Una vez completada la eliminación, el dispositivo desaparecerá por completo de la administración de Intune. Asegúrese de registrar el PIN de recuperación para que la persona que esté restaurando el dispositivo lo pueda usar.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token---820870---"></a>Revocación de las licencias de un token del programa de compras por volumen de iOS<!-- 820870 -->
Puede revocar la licencia de todas las aplicaciones del programa de compras por volumen (VPP) de iOS para un token de VPP determinado.

### <a name="app-management"></a>Administración de aplicaciones

#### <a name="revoking-ios-volume-purchase-program-apps----820863---"></a>Revocación de las aplicaciones del programa de compras por volumen de iOS <!-- 820863 -->
En el caso de un dispositivo determinado con una o más aplicaciones del programa de compras por volumen (VPP) de iOS, puede revocar la licencia de aplicación basada en dispositivo asociada para el dispositivo. Revocar una licencia de aplicación no desinstalará la aplicación VPP desde el dispositivo. Para desinstalar una aplicación VPP, debe cambiar la acción de asignación a **Desinstalar**. Para más información, consulte [Administrar aplicaciones de iOS compradas a través de un programa de compras por volumen con Microsoft Intune](../apps/vpp-apps-ios.md).

#### <a name="assign-microsoft-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type---1332318---"></a>Asignación de aplicaciones móviles de Microsoft 365 a dispositivos iOS y Android mediante el tipo de aplicación integrada<!-- 1332318 -->
El tipo de aplicación **integrada** facilita la creación y la asignación de aplicaciones de Microsoft 365 a los dispositivos iOS y Android administrados. Entre estas aplicaciones están las de Microsoft 365, como Word, Excel, PowerPoint y OneDrive. Puede asignar aplicaciones específicas al tipo de aplicación y, luego, editar la configuración de la información de la aplicación.

#### <a name="including-and-excluding-app-assignment-based-on-groups---1406920---"></a>Inclusión o exclusión de la asignación de aplicaciones con base en grupos<!-- 1406920 -->

Durante la asignación de aplicaciones y después de seleccionar un tipo de asignación, puede seleccionar los grupos para incluir, así como los grupos para excluir.

### <a name="device-configuration"></a>Configuración del dispositivo

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments----1480316---"></a>Puede asignar una directiva de configuración de aplicación a grupos mediante asignaciones de inclusión o exclusión <!-- 1480316 -->

Puede asignar una directiva de configuración de aplicación a un grupo de usuarios y dispositivos mediante una combinación de asignaciones de inclusión y exclusión. Las asignaciones se pueden elegir como una selección personalizada de grupos o como un grupo virtual. Un grupo virtual puede incluir **Todos los usuarios**, **Todos los dispositivos** o **Todos los usuarios + todos los dispositivos**.

#### <a name="support-for-windows-10-edition-upgrade-policy-----903672archived-1119689---"></a>Compatibilidad con una directiva de actualización de la edición de Windows 10  <!-- 903672(archived), 1119689 -->  
Puede crear una directiva de actualización de la edición de Windows 10 que actualice los dispositivos con Windows 10 a Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education y Windows 10 Professional Education N. Para obtener más información sobre las actualizaciones de la edición de Windows 10, vea [Configuración de actualizaciones de la edición de Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal----1737088-1634311---"></a>Directivas de acceso condicional de Intune solo disponibles en Azure Portal <!-- 1737088 1634311 -->

A partir de esta versión, debe configurar y administrar las directivas de acceso condicional en [Azure Portal](https://portal.azure.com) desde **Azure Active Directory** > **Acceso condicional**. Para su comodidad, también puede acceder a esta hoja de Intune en Azure Portal en **Intune** > **Acceso condicional**.

#### <a name="updates-to-compliance-emails--1637547---"></a>Actualizaciones de los correos electrónicos sobre compatibilidad<!--1637547 -->

Cuando se envía un correo electrónico para informar de un dispositivo no compatible, se incluyen detalles sobre dicho dispositivo.

### <a name="intune-apps"></a>Aplicaciones de Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices--1583480--"></a>Nueva funcionalidad para la acción "Resolver" en dispositivos Android<!--1583480-->

La aplicación Portal de empresa para Android expande la acción "Resolver" para la opción **Actualizar configuración del dispositivo** para resolver [problemas con el cifrado del dispositivo](../user-help/encrypt-your-device-android.md).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10--676506--"></a>Bloqueo remoto disponible en la aplicación de Portal de empresa para Windows 10<!--676506-->
Los usuarios finales ya pueden bloquear de forma remota sus dispositivos desde la aplicación del Portal de empresa para Windows 10. No se mostrará para el dispositivo local que usen activamente.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10--676546--"></a>Resolución más sencilla de los problemas de compatibilidad de la aplicación Portal de empresa para Windows 10<!--676546-->
Los usuarios finales que tengan dispositivos Windows podrán seleccionar el motivo de no compatibilidad en la aplicación Portal de empresa. Cuando sea posible, esta acción les llevará directamente a la ubicación correcta en la aplicación de configuración para solucionar el problema.

<!-- ########################## -->
## <a name="2017"></a>2017

<!-- ########################## -->
### <a name="december-2017"></a>Diciembre de 2017

#### <a name="new-automatic-redeployment-setting---1469168---"></a>Nueva configuración de la reimplementación automática<!-- 1469168 -->
La opción de configuración **Reimplementación automática** permite a los usuarios con derechos administrativos eliminar todos los datos de usuario y las opciones de configuración con **Ctrl + Win + R** en la pantalla de bloqueo del dispositivo. En este caso, el dispositivo se vuelve a configurar e inscribir automáticamente para la administración. Esta opción de configuración se puede encontrar en Windows 10 > Restricciones de dispositivos > General > Reimplementación automática. Para más detalles, consulte [Configuración de restricciones de dispositivo de Intune para Windows 10](../configuration/device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy----903672--1119689---"></a>Compatibilidad con las ediciones de origen adicionales en la directiva de actualización de edición de Windows 10 <!-- 903672,  1119689 -->
Ahora puede usar la directiva de actualización de edición de Windows 10 para actualizar desde ediciones de Windows 10 adicionales (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, etc.). Antes de esta versión, las rutas de actualización de edición admitidas estaban más limitadas. Para obtener más información, consulte [Configuración de actualizaciones de la edición de Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings---1335507---"></a>Nueva configuración del perfil de configuración de dispositivo del Centro de seguridad de Windows Defender (WDSC)<!-- 1335507 -->

Intune agrega una sección nueva de configuración del perfil de configuración de dispositivo en la protección del punto de conexión denominada **Centro de seguridad de Windows Defender**. Los administradores de TI pueden configurar a qué pilares de la aplicación Centro de seguridad de Windows Defender pueden acceder los usuarios finales. Si un administrador de TI oculta un pilar en la aplicación Centro de seguridad de Windows Defender, las notificaciones relativas al pilar oculto no se mostrarán en el dispositivo del usuario.

Estos son los pilares que los administradores pueden ocultar de la configuración del perfil de configuración de dispositivo del Centro de seguridad de Windows Defender:
- Protección contra amenazas y virus
- Mantenimiento y estado del dispositivo
- Firewall y protecciones de red
- Control de aplicaciones y explorador
- Opciones de familia

Los administradores de TI también pueden personalizar las notificaciones que recibirán los usuarios. Por ejemplo, puede configurar si los usuarios reciben todas las notificaciones que generan los pilares visibles en WDSC o solo las notificaciones críticas. Las notificaciones no críticas incluyen resúmenes periódicos de la actividad de Antivirus de Windows Defender y las notificaciones cuando se completan las detecciones. Todas las otras notificaciones se consideran críticas. Además, también puede personalizar el contenido mismo de la notificación. Por ejemplo, puede proporcionar la información de contacto de TI para insertarla en las notificaciones que aparecen en los dispositivos de los usuarios.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling---1361755---"></a>Compatibilidad de varios conectores con el control de certificados SCEP y PFX<!-- 1361755 -->

Los clientes que usan el conector NDES local para entregar los certificados a los dispositivos ahora pueden configurar varios conectores en un solo inquilino.

Esta funcionalidad nueva admite el siguiente escenario:

- **Alta disponibilidad**

Cada conector NDES extrae solicitudes de certificado desde Intune.  Si un conector NDES queda sin conexión, el otro puede seguir procesando las solicitudes.

#### <a name="customer-subject-name-can-use-aad_device_id-variable----1468599---"></a>El nombre de sujeto de cliente puede usar la variable AAD_DEVICE_ID <!-- 1468599 -->

Cuando se crea un perfil de certificado de SCEP en Intune, ahora puede usar la variable AAD_DEVICE_ID cuando se compila el nombre de sujeto personalizado.   Si se solicita el certificado con este perfil SCEP, la variable se reemplaza por el identificador de dispositivo de Azure AD del dispositivo que realiza la solicitud de certificado.

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747---"></a>Administración de dispositivos macOS inscritos en Jamf con el motor de conformidad de dispositivos de Intune<!-- 1592747 -->
Ahora puede usar Jamf para enviar la información del estado del dispositivo macOS a Intune, y este a continuación evaluará su conformidad con las directivas definidas en la consola de Intune. En función del estado de conformidad del dispositivo, así como otras condiciones tales como la ubicación, el riesgo del usuario, etc., el acceso condicional aplicará la conformidad para los dispositivos macOS que accedan a la nube y a aplicaciones locales conectadas a Azure AD, incluido Microsoft 365. Consulte más información sobre la [configuración de la integración de Jamf](../protect/conditional-access-integrate-jamf.md) y [la exigencia de compatibilidad para dispositivos administrados por Jamf](../protect/conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action-----1424701---"></a>Nueva acción de dispositivo iOS  <!-- 1424701 -->

Ahora puede apagar los dispositivos iOS 10.3 supervisados. Esta acción apaga inmediatamente el dispositivo sin enviar una advertencia al usuario final. La acción **Shut down (supervised only)** [Apagar (solo con supervisión)] se puede encontrar en las propiedades de dispositivos cuando se selecciona un dispositivo en la carga de trabajo del **dispositivo**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices---1468103---"></a>No permitir cambios de fecha y hora en dispositivos Samsung Knox<!-- 1468103 -->

Hemos agregado una nueva característica que permite bloquear los cambios de fecha y hora en los dispositivos Samsung Knox. Puede encontrarla en **Perfiles de configuración de dispositivo** > **Device restrictions (Android)** (Restricciones de dispositivos [Android]) > **General**.

#### <a name="surface-hub-resource-account-supported---1566442----"></a>Compatibilidad con la cuenta del recurso de Surface Hub<!-- 1566442  -->

Se ha agregado una nueva acción de dispositivo para que los administradores puedan definir y actualizar la cuenta del recurso asociada con Surface Hub.

Una instancia de Surface Hub usa la cuenta del recurso para autenticarse con Skype o Exchange y así poder unirse a una reunión. Puede crear una cuenta del recurso única para que Surface Hub aparezca en la reunión como la sala de conferencias. Por ejemplo, la cuenta del recurso puede aparecer como *Sala de conferencias B41/6233*. La cuenta del recurso (conocida como la cuenta del dispositivo) de Surface Hub habitualmente se debe configurar para la ubicación de la sala de conferencias y cuando sea necesario cambiar otros parámetros de la cuenta del recurso.

Cuando los administradores deseen actualizar la cuenta del recurso de un dispositivo, deben proporcionar las credenciales actuales de Active Directory o Azure Active Directory asociadas con el dispositivo. Si la rotación de contraseñas está activada en el dispositivo, los administradores deben ir a Azure Active Directory para encontrar la contraseña.

> [!NOTE]
> Todos los campos se envían en un conjunto y sobrescriben todos los campos que ya estaban configurados. Los campos vacíos también sobrescriben los campos existentes.

Los administradores pueden configurar los valores siguientes:

- **Cuenta del recurso**
  - **Usuario de Active Directory**

    NombreDeUsuario\nombredeusuario o nombre principal de usuario (UPN): user@domainname.com

  - **Contraseña**

- **Parámetros opcionales de la cuenta del recurso** (se deben establecer con la cuenta del recurso especificada)

  - **Período de rotación de contraseñas**

    Garantiza que Surface Hub actualice automáticamente la contraseña de la cuenta cada semana por motivos de seguridad. Para configurar cualquier parámetro una vez que esto esté habilitado, la cuenta en Azure Active Directory debe tener primero el restablecimiento de contraseña.

  - **Dirección de SIP (protocolo de inicio de sesión)**

    Solo se usa cuando se produce un error en la detección automática.

  - **Correo electrónico**

    Dirección de correo electrónico de la cuenta del recurso o dispositivo.

  - **Exchange Server**

    Solo se necesita cuando se produce un error en la detección automática.

  - **Sincronización de calendario**

    Especifica si la sincronización de calendario y otros servicios de Exchange Server están habilitados. Por ejemplo: sincronización de reunión.

#### <a name="install-office-apps-on-macos-devices---1494311---"></a>Instalación de aplicaciones de Office en dispositivos macOS<!-- 1494311 -->
Ahora podrá instalar aplicaciones de Office en dispositivos macOS. Este nuevo tipo de aplicación le permitirá instalar Word, Excel, PowerPoint, Outlook y OneNote. Estas aplicaciones también incluyen Microsoft AutoUpdater (MAU) para ayudar a mantener aplicaciones seguras y actualizadas.


#### <a name="delete-an-ios--volume-purchasing-program-token---820879---"></a>Eliminación de un token del programa de compras por volumen de iOS<!-- 820879 -->
Puede eliminar el token del programa de compras por volumen (VPP) de iOS con la consola. Esto puede resultar necesario cuando tiene instancias duplicadas de un token de VPP.

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data---1667026---"></a>Limitación de la nueva colección de entidades Usuario actual a los datos de los usuarios activos actualmente<!-- 1667026 -->

La colección de entidades **Usuarios** muestra todos los usuarios de Azure Active Directory (Azure AD) con licencias asignadas en la empresa. Por ejemplo, es posible que durante el último mes se haya agregado a un usuario a Intune y, luego, se haya eliminado. A pesar de que no esté presente a la hora de generar el informe, el usuario en cuestión y su estado sí que figuran en los datos. Una opción podría ser crear un informe que incluya el historial relativo a la duración de la presencia del usuario en sus datos.

Por otro lado, la nueva colección de entidades **Usuario actual** solo contiene los usuarios que no se hayan eliminado. En otras palabras, la colección de entidades **Usuario actual** solo contiene los usuarios que estén activos actualmente. Para obtener más información sobre la colección de entidades **Usuario actual**, consulte [Referencia de la entidad de usuario actual](../developer/reports-ref-data-model.md).

### <a name="updated-graph-apis---1736360---"></a>Actualización de las API Graph<!-- 1736360 -->

En esta versión, hemos actualizado algunas de las API Graph para Intune que están en versión beta. Consulte el [registro de cambios de API Graph](/graph/changelog) mensual para obtener más información.


#### <a name="intune-supports-windows-information-protection-wip-denied-apps---1479103---"></a>Intune admite aplicaciones denegadas de Windows Information Protection (WIP)<!-- 1479103 -->
En Intune puede especificar aplicaciones denegadas. Si una aplicación queda denegada, se la bloquea para que no pueda acceder a la información de la empresa, es decir, lo contrario a la lista de aplicaciones permitidas. Para obtener más información, consulte [Recommended deny list for Windows Information Protection](/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) (Recomendación de lista de aplicaciones denegadas para Windows Information Protection).

<!-- ########################## -->
### <a name="november-2017"></a>Noviembre de 2017

#### <a name="troubleshoot-enrollment-issues----746324---"></a>Solución de problemas de inscripción <!-- 746324 -->

En el área de trabajo **Solución de problemas** ahora se muestran los problemas de inscripción del usuario. Los detalles del problema y los pasos de corrección sugeridos pueden ayudar a los administradores y a los operadores del departamento de soporte técnico a solucionar los problemas. Ciertos problemas de inscripción no se capturan, y es posible que no se sugieran correcciones para algunos errores.

#### <a name="group-assigned-enrollment-restrictions---747598---"></a>Restricciones de inscripción asignada a grupos<!-- 747598 -->

Como administrador de Intune, ahora puede [crear restricciones de inscripción personalizadas de tipo de dispositivo y de límite de dispositivos para grupos de usuarios](../enrollment/enrollment-restrictions-set.md).

Azure Portal de Intune permite crear un máximo de 25 instancias de cada tipo de restricción que pueden asignarse luego a grupos de usuarios. Las restricciones asignadas por grupo invalidan las restricciones predeterminadas.

Todas las instancias de un tipo de restricción se mantienen en una lista ordenada de forma estricta. Este orden define un valor de prioridad para la resolución de conflictos. Un usuario afectado por más de una instancia de la restricción solo está limitado por la instancia con el valor de prioridad más alto. Para cambiar la prioridad de una determinada instancia, arrástrela a una posición diferente en la lista.

Esta funcionalidad se publicará con la migración de la configuración de Android for Work desde el menú de inscripción de Android for Work al menú de restricciones de inscripción. Puesto que esta migración puede tardar varios días, la versión de noviembre puede afectar primero a otras partes de su cuenta antes de habilitar la asignación de grupo para las restricciones de inscripción.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors---1528104---"></a>Compatibilidad con varios conectores de Servicio de inscripción de dispositivos de red (NDES)<!-- 1528104 -->

NDES permite que los dispositivos móviles que se ejecutan sin credenciales de dominio puedan obtener certificados a través del Protocolo de inscripción de certificados simple (SCEP).
Con esta actualización, se admiten varios conectores NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices---1490731-eeready--"></a>Administración independiente de dispositivos Android for Work y dispositivos Android<!-- 1490731 EEready-->

Intune admite la administración de inscripciones de dispositivos Android for Work independientemente de la plataforma Android. Esta configuración se administra en **Inscripción de dispositivos** > **Restricciones de inscripción** > **Restricciones de tipo de dispositivo**. (Anteriormente se encontraban bajo **Inscripción de dispositivos** > **Inscripción en Android for Work** > **Configuración de la inscripción de Android for Work**).

De forma predeterminada, la configuración de los dispositivos Android for Work es igual que la configuración de los dispositivos Android. Sin embargo, dejará de ser así tras modificar la configuración de Android for Work.

Si bloquea la inscripción de Android for Work personal, tan solo los dispositivos Android corporativos podrán inscribirse como Android for Work.

Cuando trabaje con la nueva configuración, tenga en cuenta estos puntos:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Si es la primera vez que incorpora inscripciones de Android for Work

La nueva plataforma Android for Work está bloqueada de manera predeterminada en Restricciones de tipo de dispositivo. Después de incorporar la característica, puede permitir que los dispositivos se inscriban con Android for Work. Para ello, cambie el valor predeterminado o cree una nueva restricción de tipo de dispositivo que sustituya a la predeterminada.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Si ya ha incorporado inscripciones de Android for Work

Si no es la primera que realiza una incorporación, su situación depende de la configuración elegida:

| Setting | Estado de Android for Work en el valor predeterminado de Restricción de tipo de dispositivo | Notas |
| --- | --- | --- |
| **Administrar todos los dispositivos como Android** | Bloqueado | Todos los dispositivos Android deben inscribirse sin Android for Work. |
| **Administrar los dispositivos compatibles como Android for Work** | Permitido | Todos los dispositivos que admiten Android for Work deben inscribirse con Android for Work. |
| **Administrar los dispositivos compatibles para usuarios solo en estos grupos como Android for Work** | Bloqueado | Para invalidar el valor predeterminado, se creó una directiva de restricción de tipo de dispositivo independiente. Esta directiva define los grupos que se seleccionaron previamente para permitir la inscripción de Android for Work. Los usuarios de los grupos seleccionados seguirán teniendo permiso para inscribir sus dispositivos Android for Work. Todos los demás usuarios tienen restringida la inscripción con Android for Work. |

En todos los casos, se conserva la normativa que haya previsto. No se requiere ninguna acción por su parte para seguir permitiendo Android for Work en su entorno, tanto de forma global como por grupo.

#### <a name="google-play-protect-support-on-android---908720---"></a>Compatibilidad con Google Play Protect en Android<!-- 908720 -->

Con el lanzamiento de Android Oreo, Google presenta un conjunto de características de seguridad denominado Google Play Protect que permite a los usuarios y las organizaciones ejecutar aplicaciones e imágenes de Android seguras. Intune ya admite las características de Google Play Protect, incluida la atestación remota de SafetyNet. Los administradores pueden establecer requisitos para directivas de cumplimiento que exijan que Google Play Protect esté configurado y en buen estado.
La opción **SafetyNet device attestation** (Atestación de dispositivo SafetyNet) requiere que el dispositivo se conecte con un servicio de Google para comprobar que se encuentra en buen estado y no está en riesgo. Los administradores también pueden establecer una opción en el perfil de configuración de Android for Work para requerir que se comprueben las aplicaciones instaladas por los servicios de Google Play. Si un dispositivo no es compatible con los requisitos de Google Play Protect, el acceso condicional puede impedir que los usuarios accedan a los recursos corporativos.

- Obtenga información sobre la [Creación de una directiva de cumplimiento de dispositivos para habilitar Google Play Protect](../protect/compliance-policy-create-android.md).

#### <a name="text-protocol-allowed-from-managed-apps---1414050----"></a>Protocolo de texto permitido en aplicaciones administradas<!-- 1414050  -->

Las aplicaciones administradas por Intune App SDK pueden enviar mensajes SMS.


#### <a name="app-install-report-updated-to-include-install-pending-status---1249446---"></a>Actualización del informe de instalación de aplicaciones para incluir el estado Instalación pendiente<!-- 1249446 -->  

El informe **Estado de instalación de la aplicación**, accesible para todas las aplicaciones a través de la lista **Aplicación** de la carga de trabajo **Aplicaciones cliente**, contiene ahora un recuento **Instalación pendiente** para usuarios y dispositivos.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection---1391759---"></a>API de inventario de aplicaciones iOS 11 para la detección de amenazas en dispositivos móviles<!-- 1391759 -->

Intune recopila la información de inventario de aplicaciones de los dispositivos personales y corporativos, y la pone a disposición de los proveedores de detección de amenazas en dispositivos móviles (MTD), como Lookout for Work. Puede recopilar un inventario de aplicaciones de los usuarios de dispositivos iOS 11 y posteriores.

**Inventario de aplicaciones**  
Los inventarios de los dispositivos iOS 11 y versiones posteriores, tanto de empresa como personales, se envían al proveedor de servicios MTD. El inventario de aplicaciones incluye los datos siguientes:

- Identificador de la aplicación
- Versión de la aplicación
- Nombre corto de la versión
- Nombre de la aplicación
- Tamaño del lote de aplicaciones
- Tamaño dinámico de la aplicación
- Aplicación validada o no validada
- Aplicación administrada o no administrada

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone---1463747-wnready---"></a>Migración de dispositivos y usuarios de MDM híbrida a Intune independiente<!-- 1463747 wnready -->
Ya hay disponibles nuevos procesos y herramientas para mover usuarios y sus dispositivos de MDM híbrida a Intune en Azure Portal, lo que le permitirá llevar a cabo las tareas siguientes:
- Copiar directivas y perfiles de la consola de Configuration Manager a Intune en Azure Portal
- Mover un subconjunto de usuarios a Intune en Azure Portal conservando el resto en MDM híbrida
- Migrar dispositivos a Intune en Azure Portal sin tener que volver a inscribirlos

#### <a name="on-premises-exchange-connector-high-availability-support----676614---"></a>Compatibilidad de alta disponibilidad de On-premises Exchange Connector <!-- 676614 -->
Una vez que el conector de Exchange cree una conexión a Exchange mediante el servidor de acceso de cliente (CAS) especificado, el conector tendrá la capacidad de detectar otros CAS. Si la CAS principal deja de estar disponible, el conector efectuará una conmutación por error en otra CAS, si está disponible, hasta que la CAS principal esté disponible. Para obtener más información, consulte [Compatibilidad de alta disponibilidad de On-premises Exchange Connector](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only---1424595---"></a>Reinicio remoto de dispositivos iOS (solo supervisado)<!-- 1424595 -->

Con una acción del dispositivo, ahora puede reiniciar un dispositivo supervisado de iOS 10.3 y versiones posteriores. Para obtener más información sobre el uso de la acción de reinicio del dispositivo, consulte [Reinicio remoto de los dispositivos con Intune](../remote-actions/device-restart.md).

> [!Note]
> Para usar este comando es necesario que el dispositivo esté supervisado y disponer del derecho de acceso **Bloqueo del dispositivo**. El dispositivo se reinicia inmediatamente. Después de un reinicio, los dispositivos iOS bloqueados mediante código de acceso no volverán a unirse a una red Wi-Fi y es posible que no puedan comunicarse con el servidor.

#### <a name="single-sign-on-support-for-ios---1333645---"></a>Compatibilidad del inicio de sesión único con iOS<!-- 1333645 -->  

En el caso de los usuarios de iOS, puede usar el inicio de sesión único. Las aplicaciones de iOS que están codificadas para buscar las credenciales de usuario en la carga de inicio de sesión único funcionarán con esta actualización de la configuración de carga. También puede utilizar el UPN y el identificador de dispositivo de Intune para configurar el nombre de la entidad de seguridad y el dominio Kerberos. Para obtener más información, consulte [Configuración del inicio de sesión único de Intune para dispositivos iOS](../configuration/ios-device-features-settings.md#single-sign-on).

#### <a name="add-find-my-iphone-for-personal-devices--1427287--"></a>Adición de "Buscar mi iPhone" para dispositivos personales<!--1427287-->
Ahora puede ver si los dispositivos iOS tienen activado el Boqueo de activación. Esta característica se encontraba anteriormente en Intune, en el portal clásico.

#### <a name="remotely-lock-managed-macos-device-with-intune---1437691---"></a>Bloqueo remoto de los dispositivos macOS administrados con Intune<!-- 1437691 -->

Si pierde un dispositivo macOS, puede bloquearlo y establecer un PIN de recuperación de seis dígitos. Una vez bloqueado, la hoja de **información general del dispositivo** muestra el PIN hasta que se envía otra acción de dispositivo.

Para obtener más información, consulte [Bloqueo remoto de los dispositivos administrados con Intune](../remote-actions/device-remote-lock.md).

#### <a name="new-scep-profile-details-supported---1559808---"></a>Nuevos detalles admitidos del perfil SCEP<!-- 1559808 -->

Ahora los administradores pueden establecer configuraciones adicionales al crear un perfil de SCEP en las plataformas Windows, iOS, macOS y Android.  Los administradores pueden establecer el IMEI, el número de serie o el nombre común, incluido el correo electrónico en el formato de nombre de sujeto.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset---1588489---"></a>Conservación de los datos durante un restablecimiento de fábrica <!--1588489 -->
Al restablecer la versión 1709 de Windows 10 y versiones posteriores a la configuración de fábrica, está disponible una nueva funcionalidad. Los administradores pueden especificar si la inscripción de dispositivos y otros datos aprovisionados se conservan en un dispositivo tras un restablecimiento de fábrica.

Los siguientes datos se conservan tras un restablecimiento de fábrica:
- Cuentas de usuario asociadas con el dispositivo
- Estado del equipo (unión a un dominio, unido a Azure Active Directory)
- Inscripción de MDM
- Aplicaciones instaladas por OEM (aplicaciones de Win32 y tienda)
- Perfil de usuario
- Datos de usuario fuera del perfil de usuario
- Inicio de sesión automático del usuario

Los datos siguientes no se conservan:
- Archivos de usuario
- Aplicaciones instaladas por el usuario (aplicaciones de Win32 y tienda)
- Configuración del dispositivo no predeterminada


#### <a name="window-10-update-ring-assignments-are-displayed---1621837---"></a>Se muestran las asignaciones del círculo de actualizaciones de Windows 10<!-- 1621837 -->
Cuando esté **solucionando problemas**, y en relación al usuario que está visualizando, puede ver las asignaciones de círculos de actualizaciones de Windows 10.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings----1455974----"></a>Configuración de la frecuencia de informes de Protección contra amenazas avanzada de Windows Defender <!-- 1455974  -->
El servicio Protección contra amenazas avanzada de Windows Defender (WDATP) permite a los administradores gestionar la frecuencia con la que se generan informes relativos a los dispositivos administrados. Con la nueva opción **Frecuencia de informes de telemetría urgentes**, WDATP recopila datos y evalúa los riesgos con una frecuencia mayor. El valor predeterminado para los informes optimiza el rendimiento y la velocidad. Aumentar la frecuencia de los informes puede ser muy útil para dispositivos de alto riesgo. Esta configuración puede encontrarse en el perfil **ATP de Windows Defender** en **Configuraciones de dispositivos**.

#### <a name="audit-updates---1412961---"></a>Actualizaciones de auditoría<!-- 1412961 -->  
La auditoría de Intune proporciona un registro de las operaciones que implican cambios en Intune.  Todas las operaciones de creación, actualización, eliminación y tareas remotas se registran y se conservan durante un año.  Azure Portal proporciona una vista filtrable de los datos auditados durante los últimos 30 días en cada carga de trabajo.  Con la correspondiente API de Graph es posible recuperar los datos de auditoría almacenados durante el último año.

La auditoría se encuentra en el grupo **MONITOR**. El elemento de menú **Registros de auditoría** está disponible para cada una de las carga de trabajo.

#### <a name="company-portal-app-for-macos-is-available--1541700--"></a>Aplicación Portal de empresa ya disponible para macOS<!--1541700-->
El Portal de empresa de Intune en macOS tiene una experiencia actualizada, que se ha optimizado para mostrar correctamente toda la información y las notificaciones de cumplimiento que los usuarios necesitan en todos los dispositivos que han inscrito. Además, una vez que Portal de empresa se haya implementado en un dispositivo, las actualizaciones se proporcionarán a través de Microsoft AutoUpdate para macOS. Inicie sesión en el sitio web del Portal de empresa de Intune desde un dispositivo macOS para descargar el nuevo Portal de empresa de Intune para macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps----1248473---"></a>Inclusión de Microsoft Planner en la lista de aplicaciones aprobadas para la administración de aplicaciones móviles (MAM) <!-- 1248473 -->
La aplicación de Microsoft Planner para iOS y Android ahora forma parte de las aplicaciones aprobadas para la administración de aplicaciones móviles (MAM). La aplicación puede configurarse para todos los inquilinos mediante la hoja Intune App Protection de Azure Portal.
- Para obtener más información, consulte la [lista de aplicaciones aprobadas para MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices-----1547061---"></a>Frecuencia de actualización de requisitos de VPN por aplicación en dispositivos iOS  <!-- 1547061 -->  
En el caso de las aplicaciones en dispositivos iOS, los administradores ahora pueden quitar los requisitos de VPN por aplicación. Los dispositivos afectados se actualizarán tras la siguiente validación de Intune, que por lo general se produce cada 15 minutos.  

#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector---885457---"></a>Compatibilidad con el módulo de administración de System Center Operations Manager para Exchange Connector<!-- 885457 -->
El módulo de administración de System Center Operations Manager para Exchange Connector ya está disponible para ayudarle a analizar los registros de Exchange Connector. Esta característica ofrece distintas maneras de supervisar el servicio cuando haya que resolver problemas.

#### <a name="co-management-for-windows-10-devices----1243445---"></a>Administración conjunta para dispositivos de Windows 10 <!-- 1243445 -->
La administración conjunta es una solución que sirve para ofrecer un vínculo entre la administración tradicional y la administración moderna. Además, le proporciona una guía para llevar a cabo la transición con un enfoque por fases. Básicamente, la administración conjunta es una solución en la que los dispositivos de Windows 10 se administran de forma simultánea mediante Configuration Manager y Microsoft Intune. También se unen a Active Directory (AD) y a Azure Active Directory (Azure AD).  Esta configuración proporciona un método para poder modernizar la administración con el tiempo, a la velocidad que sea adecuada para su organización si no puede moverlo todo a la vez.  

#### <a name="restrict-windows-enrollment-by-os-version---245498---"></a>Restricción de la inscripción de Windows según la versión del sistema operativo<!-- 245498 -->
Como administrador de Intune, ahora puede especificar una versión mínima y máxima de Windows 10 para poder inscribir dispositivos. Estas restricciones se pueden establecer en la hoja **Configuraciones de plataforma**.

Intune seguirá permitiendo la inscripción de teléfonos y equipos con Windows 8.1, pero solo se pueden establecer los límites mínimo y máximo de las versiones de Windows 10. Para permitir la inscripción de dispositivos 8.1, deje vacío el límite mínimo.

#### <a name="alerts-for-windows-autopilot-unassigned-devices----1631236---"></a>Alertas de dispositivos sin asignar de Windows Autopilot <!-- 1631236 -->
Hay una nueva alerta disponible relativa a los dispositivos sin asignar de Windows AutoPilot en la página **Microsoft Intune** > **Inscripción de dispositivos** > **Información general**. Esta alerta indica cuántos dispositivos del programa AutoPilot no tienen asignados perfiles de implementación de AutoPilot. Use la información provista en la alerta para crear perfiles y asignarlos a los dispositivos sin asignar. Al hacer clic en la alerta, verá una lista completa de dispositivos de Windows AutoPilot e información detallada sobre ellos. Para obtener más información, vea [Inscribir dispositivos mediante el programa Windows AutoPilot Deployment](../../autopilot/enrollment-autopilot.md).


#### <a name="refresh-button-for-devices-list------1333581---"></a>Botón Actualizar de la lista de dispositivos   <!-- 1333581 -->
La lista de dispositivos no se actualiza automáticamente, de modo que puede usar el nuevo botón Actualizar para actualizar los dispositivos que figuran en esa lista.

#### <a name="support-for-symantec-cloud-certification-authority-ca----1333638---"></a>Compatibilidad con la entidad de certificación (CA) en la nube de Symantec <!-- 1333638 -->    
Intune admite ahora la entidad de certificación en la nube de Symantec, que permite que Intune Certificate Connector emita certificados PKCS desde la entidad de certificación en la nube de Symantec para dispositivos administrados por Intune. Si ya usa Intune Certificate Connector con la entidad de certificación de Microsoft, puede usar la configuración existente de Intune Certificate Connector para agregar compatibilidad con la entidad de certificación de Symantec.

#### <a name="new-items-added-to-device-inventory----1404455---"></a>Nuevos elementos agregados al inventario de dispositivos  <!--1404455 -->
Los nuevos elementos que se indican a continuación ya están disponibles en el [inventario de los dispositivos inscritos](../remote-actions/device-inventory.md):

- Dirección MAC de Wi-Fi
- Espacio de almacenamiento total
- Espacio disponible total
- MEID
- Operador del suscriptor

#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Establecimiento del acceso para las aplicaciones mediante una revisión de seguridad mínima de Android en el dispositivo<!-- 1278463 -->   
Un administrador puede definir la revisión de seguridad mínima de Android que debe estar instalada en el dispositivo para poder obtener acceso a una aplicación administrada en una cuenta administrada.

> [!Note]  
> Esta característica solamente restringe las revisiones de seguridad publicadas por Google en dispositivos Android 6.0 y versiones posteriores.

#### <a name="app-conditional-launch-support---1193313---"></a>Compatibilidad con inicio condicional de aplicación<!-- 1193313 -->
Los administradores de TI ahora pueden establecer un requisito a través del portal de administración de Azure para exigir un código de acceso en lugar de un PIN numérico mediante la administración de aplicaciones móviles (MAM) cuando se inicia la aplicación. Si se configura, se le pide al usuario que establezca y use un código de acceso cuando se le solicite antes de obtener acceso a aplicaciones habilitadas para MAM. Un código de acceso se define como un PIN numérico con al menos un carácter especial o un carácter alfabético en mayúsculas/minúsculas. Esta versión de Intune habilitará esta característica **solo en iOS**. Intune admite un código de acceso de forma similar al PIN numérico. Establece una longitud mínima y permite la repetición de caracteres y secuencias. Esta característica requiere el uso de ciertas aplicaciones (es decir, WXP, Outlook, Managed Browser o Yammer) para integrar Intune App SDK con el código de esta y aplicar la configuración del código de acceso en las aplicaciones de destino.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report---1233999---"></a>Número de versión de la aplicación para línea de negocio en el informe de estado de instalación del dispositivo<!-- 1233999 -->
Con esta versión, el informe de estado de instalación del dispositivo mostrará el número de versión de aplicación de las aplicaciones de línea de negocio para iOS y Android. Puede usar esta información para solucionar problemas de las aplicaciones o buscar los dispositivos que ejecuten versiones obsoletas de la aplicación.

#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile---951708---"></a>Los administradores ya pueden configurar las opciones del firewall en un dispositivo mediante un perfil de configuración de dispositivo<!-- 951708 -->   
Los administradores pueden activar el firewall para los dispositivos y, además, configurar varios protocolos para redes públicas, privadas y de dominio.  Esta configuración del firewall se encuentra en el perfil "Endpoint Protection".

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization---958257---"></a>Protección de aplicaciones de Windows Defender ayuda a proteger los dispositivos de sitios web que no son de confianza, en función de la definición de la organización<!-- 958257 -->   
Los administradores pueden definir sitios como "de confianza" o "corporativos" mediante un flujo de trabajo de Windows Information Protection o el nuevo perfil de "límite de red" en las configuraciones del dispositivo. Si se visualizan con Microsoft Edge, todos los sitios que no aparezcan en un límite de red de confianza de un dispositivo de Windows 10 de 64 bits se abrirán en un explorador de un equipo virtual de Hyper-V.

La Protección de aplicaciones se encuentra en los perfiles de configuración del dispositivo, en el perfil "Endpoint Protection". Desde allí, los administradores pueden configurar la interacción entre el explorador virtualizado y el equipo host, los sitios que son y que no son de confianza, y el almacenamiento de datos generado en el explorador virtualizado. Para usar la Protección de aplicaciones en un dispositivo, debe configurarse primero un límite de red. Es importante definir un solo límite de red para un dispositivo.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps---1031096---"></a>Control de aplicaciones de Windows Defender en Windows 10 Enterprise ofrece el modo de confiar solo en aplicaciones autorizadas<!-- 1031096 -->    
Teniendo en cuenta que cada día se crean miles de archivos malintencionados, el uso de la detección antivirus basada en firma para luchar contra el malware podría ser insuficiente para proporcionar una defensa adecuada contra nuevos ataques. Mediante Windows Defender Application Control en Windows 10 Enterprise, puede cambiar la configuración del dispositivo de un modo en el que las aplicaciones son de confianza a menos que las bloquee un antivirus u otra solución de seguridad, a un modo en el que el sistema operativo solo confía en las aplicaciones autorizadas por la empresa. La confianza se asigna a las aplicaciones en Windows Defender Application Control.

Mediante Intune, puede configurar las directivas de control de aplicaciones en modo de "solo auditoría" o en el modo de uso forzoso. Las aplicaciones no se bloquean cuando se ejecutan en modo "Solo auditoría". El modo "Solo auditoría" registra todos los eventos en registros locales del cliente. También puede configurar si solo se pueden ejecutar componentes de Windows y aplicaciones de Microsoft Store, o si también se pueden ejecutar otras aplicaciones con buena reputación de acuerdo con la definición de Intelligent Security Graph.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10---1063615---"></a>Protección contra vulnerabilidades de seguridad de Windows Defender es un nuevo conjunto de funciones de prevención de intrusiones para Windows 10<!-- 1063615 -->   
La Protección contra vulnerabilidades de seguridad de Windows Defender incluye reglas personalizadas para reducir la explotabilidad de las aplicaciones. También impide las amenazas de macros y scripts, bloquea automáticamente las conexiones de red a direcciones IP de mala reputación y puede proteger los datos contra el ransomware y amenazas desconocidas. La Protección contra vulnerabilidades de seguridad de Windows Defender consta de los componentes siguientes:

- La **reducción de la superficie expuesta a ataques** proporciona reglas que permiten impedir las amenazas de macros, scripts y correos electrónicos.
- El **acceso controlado a carpetas** bloquea automáticamente el acceso a contenido en las carpetas protegidas.
- El **filtro de red** bloquea las conexiones salientes desde cualquier aplicación a IP o dominios de mala reputación.
- La **protección contra vulnerabilidades** proporciona restricciones de memoria, flujo de control y directivas que pueden usarse para proteger una aplicación contra las vulnerabilidades.

#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices---790537---"></a>Administrar scripts de PowerShell en Intune para dispositivos Windows 10<!-- 790537 -->

La extensión de administración de Intune permite cargar los scripts de PowerShell en Intune para ejecutarse en dispositivos Windows 10. Esta extensión complementa las capacidades de administración de dispositivos móviles (MDM) de Windows 10 y facilita la transición a una administración moderna. Para conocer más detalles, vea [Administrar scripts de PowerShell en Intune para dispositivos Windows 10](../apps/intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10--------1308850---"></a>Nueva configuración de restricciones de dispositivos para Windows 10     <!-- 1308850 -->
- Mensajería (solo móvil): deshabilitar pruebas o mensajes MMS
- Contraseña: configuración para habilitar FIPS y el uso de dispositivos secundarios Windows Hello para la autenticación 
- Pantalla: configuración para activar o desactivar el ajuste de escala de GDI para las aplicaciones heredadas

#### <a name="windows-10-kiosk-mode-device-restrictions---1308872---"></a>Restricciones de dispositivos Windows 10 a pantalla completa<!-- 1308872 -->   
Puede restringir usuarios de dispositivos Windows 10 a pantalla completa, lo que les limita a un conjunto de aplicaciones predefinidas.  Para ello, cree un perfil de restricción de dispositivo Windows 10 y defina la configuración de pantalla completa.

La pantalla completa admite dos modos: **aplicación única**, que permite que un usuario ejecute una sola aplicación, o **varias aplicaciones**, que permite el acceso a un conjunto de aplicaciones.  Para determinar las aplicaciones compatibles, debe definir la cuenta de usuario y el nombre del dispositivo.  Cuando el usuario ha iniciado sesión, verá únicamente las aplicaciones definidas.  Para obtener más información, vea [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp) (CSP AssignedAccess). 

La pantalla completa requiere lo siguiente:

- Intune debe ser la entidad de MDM.
- Las aplicaciones deben estar ya instaladas en el dispositivo de destino.
- El dispositivo debe estar [aprovisionado correctamente](/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries---1311967---"></a>Nuevo perfil de configuración de dispositivo para crear límites de red<!-- 1311967 -->   
En los otros perfiles de configuración de dispositivo encontrará un nuevo perfil de configuración de dispositivo llamado **Límite de red**. Use este perfil para definir los recursos en línea que quiere que se consideren corporativos y de confianza. Debe definir un límite de red para un dispositivo *antes* de que en el dispositivo se puedan usar características como la Protección de aplicaciones de Windows Defender y Windows Information Protection. Es importante definir un solo límite de red para cada dispositivo.

Puede definir los recursos de empresa en la nube, los intervalos de direcciones IP y los servidores proxy internos que quiere que se consideren de confianza. Una vez definidos, pueden usar el límite de red otras características como la Protección de aplicaciones de Windows Defender y Windows Information Protection.

#### <a name="two-additional-settings-for-windows-defender-antivirus---1338409---"></a>Dos opciones de configuración adicionales para Antivirus de Windows Defender<!-- 1338409 -->  
**Nivel de bloqueo de archivos**

| Configuración | Detalles |
|---|---|
| No configurado | **No configurado** usa el nivel de bloqueo predeterminado de Antivirus de Windows Defender y proporciona una detección segura sin aumentar el riesgo de detectar archivos legítimos. |
| Alto | **Alto** se aplica a un alto nivel de detección.
| Alto +  | **Alto +** proporciona el nivel Alto con medidas de protección adicionales que podrían afectar al rendimiento del cliente.
| Tolerancia cero  | **Tolerancia cero** bloquea todos los ejecutables desconocidos. |

Aunque es improbable, si se establece en **Alto** puede hacer que se detecten algunos archivos legítimos.
Se recomienda establecer el nivel de bloqueo de archivos en el valor predeterminado (**No configurado**).

**Ampliación del tiempo de espera para la detección de archivos en la nube**  

| Setting | Detalle |
|--|--|
| Número de segundos (0-50) | Especifique el tiempo máximo durante el que Antivirus de Windows Defender debe bloquear un archivo mientras espera un resultado de la nube. El valor predeterminado es de 10 segundos. El tiempo adicional que se especifique aquí (hasta 50 segundos) se agregará a los 10 segundos. En la mayoría de los casos, la detección tarda mucho menos que el tiempo máximo. Si amplía el tiempo, permitirá que la nube investigue a fondo los archivos sospechosos. Se recomienda que habilite esta opción y que especifique al menos 20 segundos adicionales. |

#### <a name="citrix-vpn-added-for-windows-10-devices---1512457---"></a>Adición de la VPN de Citrix a dispositivos Windows 10<!-- 1512457 -->  
Puede configurar la VPN de Citrix para sus dispositivos Windows 10. Puede elegir la VPN de Citrix en la lista *Seleccione un tipo de conexión* en la hoja **VPN base** al configurar una VPN para Windows 10 y versiones posteriores.

> [!Note]
> La configuración de Citrix ya existía para iOS y Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios---1550823---"></a>Las conexiones Wi-Fi admiten claves precompartidas en iOS<!-- 1550823 -->
Los clientes pueden configurar perfiles de Wi-Fi para usar claves precompartidas (PSK) en las conexiones WPA o WPA2 Personal en dispositivos iOS. Estos perfiles se insertan en el dispositivo del usuario al inscribirlo en Intune.

Cuando el perfil se haya insertado en el dispositivo, el siguiente paso dependerá de la configuración del perfil.  Si está establecido para conectarse automáticamente, lo hace cuando la red se necesite.  Cuando el perfil se conecta de forma manual, el usuario deberá activar manualmente la conexión.  

#### <a name="access-to-managed-app-logs-for-ios---1469920---"></a>Acceso a los registros de aplicación administrada de iOS<!-- 1469920 -->
Ahora, los usuarios finales que tengan Managed Browser instalado pueden ver el estado de administración de todas las aplicaciones publicadas de Microsoft y enviar registros para solucionar problemas con sus aplicaciones iOS administradas.

Para más información sobre cómo habilitar el modo de solución de problemas en Managed Browser en un dispositivo iOS, vea [Cómo tener acceso a los registros de aplicación administrada con Managed Browser en iOS](../apps/manage-microsoft-edge.md).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290---1417174---"></a>Mejoras en el flujo de trabajo de configuración de dispositivos en la versión 2.9.0 de Portal de empresa para iOS<!-- 1417174 -->

El flujo de trabajo de configuración de dispositivos se ha mejorado en la aplicación Portal de empresa para iOS. El lenguaje resulta más fácil de usar y se han combinado pantallas donde era posible. Además, hemos utilizado el nombre de su empresa en el texto del proceso de configuración para que el lenguaje sea más específico. Puede consultar el flujo de trabajo actualizado en la  [página de novedades de la interfaz de usuario de la aplicación](whats-new-app-ui.md).

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model---1544273---"></a>La entidad de usuario contiene los datos de usuario más recientes en el modelo de datos de Data Warehouse<!-- 1544273 -->
La primera versión del modelo de datos del Almacenamiento de datos de Intune solo contenía datos de Intune recientes e históricos. Los creadores de informes no podían capturar el estado actual de un usuario. En esta actualización, la **entidad de usuario** se rellena con los datos más recientes del usuario.

<!-- ########################## -->
### <a name="october-2017"></a>Octubre de 2017

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible---1380712---"></a>El número de versión de la aplicación de línea de negocio de Android y iOS es visible<!-- 1380712 -->

Las aplicaciones de Intune ahora muestran el número de versión para las aplicaciones de línea de negocio de iOS y Android. El número se muestra en la lista de aplicaciones de Azure Portal y en la hoja de información general de la aplicación. Los usuarios finales pueden ver este número en la aplicación Portal de empresa y en el portal web.

__Número de versión completo__ El número de versión completo identifica una versión específica de la aplicación. El número aparece como _versión_(_compilación_). Por ejemplo, 2.2(2.2.17560800).

El número de versión completo consta de dos componentes:

- **Versión**  
  El número de versión es el número que pueden ver los usuarios. Sirve para que los usuarios finales distingan las diferentes versiones de la aplicación.

- **Número de compilación**  
  El número de compilación es un número interno que puede usarse para la detección de la aplicación y para administrar la aplicación mediante programación. El número de compilación alude a una iteración de la aplicación que hace referencia a los cambios en el código.

Obtenga más información sobre los números de versión y el desarrollo de aplicaciones de línea de negocio en [Introducción al SDK para aplicaciones de Microsoft Intune](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers).

#### <a name="device-and-app-management-integration---677972---"></a>Integración de la administración de dispositivos y aplicaciones<!-- 677972 -->
Ahora que se puede acceder a la administración de dispositivos móviles (MDM) y a la administración de aplicaciones móviles (MAM) de Intune desde Azure Portal, Intune ha empezado a integrar la experiencia de administración de TI en torno a la administración de aplicaciones y dispositivos. Estos cambios están pensados para simplificar la experiencia de administración de dispositivos y aplicaciones.

Obtenga más información sobre los cambios anunciados en MDM y MAM en el [blog del equipo de soporte técnico de Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices---1471790---"></a>Nuevas alertas de inscripción de dispositivos de Apple<!-- 1471790 -->
En la página de información general de la inscripción se mostrarán alertas relacionadas con la administración de dispositivos de Apple que resultarán útiles para los administradores de TI. Las alertas se mostrarán en la página de información general cuando el certificado de inserción MDM de Apple esté a punto de expirar o ya lo haya hecho; cuando el token del Programa de inscripción de dispositivos vaya a expirar o ya lo haya hecho; y cuando haya dispositivos sin asignar en el Programa de inscripción de dispositivos.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment---1080364---"></a>Reemplazo de tokens en la configuración de aplicaciones sin inscripción de dispositivos<!-- 1080364 -->

Puede usar tokens para valores dinámicos de la configuración de las aplicaciones en dispositivos que no están inscritos. Para obtener más información, consulte [Agregar directivas de configuración para aplicaciones administradas sin inscripción de dispositivos](../apps/app-configuration-policies-managed-app.md).

#### <a name="updates-to-the-company-portal-app-for-windows-10--1299474--"></a>Actualizaciones de la aplicación Portal de empresa para Windows 10<!--1299474-->
La página Configuración de la aplicación de Portal de empresa para Windows 10 se ha actualizado para que las opciones y las acciones de usuario previstas sean más coherentes en relación con el resto de opciones de configuración. También se ha actualizado para que el diseño coincida con el de otras aplicaciones de Windows. Puede ver imágenes del antes y el después en la [página de novedades de la interfaz de usuario de la aplicación](whats-new-app-ui.md).

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices--1337920--"></a>Detalles para los usuarios finales sobre qué información del dispositivo se puede ver para dispositivos Windows 10<!--1337920-->
Se agregó **Tipo de propiedad** en la pantalla Detalles del dispositivo en la aplicación Portal de empresa para Windows 10. Esto permitirá que los usuarios obtengan más información sobre la privacidad directamente en esta página de los documentos para el usuario final de Intune. También se podrán encontrar estos detalles en la pantalla **Información**.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android--1165249--"></a>Solicitudes de comentarios sobre la aplicación Portal de empresa para Android<!--1165249-->
Ahora la aplicación Portal de empresa para Android solicita comentarios del usuario final. Estos comentarios se envían directamente a Microsoft, además de ofrecer a los usuarios finales una oportunidad para revisar la aplicación en Google Play Store público. Los comentarios no son obligatorios, por lo que los usuarios pueden descartarlos y continuar usando la aplicación.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android---1573324-1573150-1558616-1564878---"></a>Ayuda a los usuarios con la aplicación Portal de empresa para Android<!-- 1573324, 1573150, 1558616, 1564878 -->

La aplicación Portal de empresa para Android incorpora instrucciones adicionales para los usuarios finales con la finalidad de ayudarles a comprender y, siempre que sea posible, resolver por ellos mismos los nuevos casos de uso.
- Se guiará a los usuarios finales al [portal de Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) para quitar un dispositivo si han alcanzado el número máximo de dispositivos que pueden agregar.
- A los usuarios finales se les indican los pasos que deben seguir para ayudarles a [corregir errores de activación en dispositivos Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) o a [desactivar el modo de ahorro de energía](https://go.microsoft.com/fwlink/?linkid=2077422&clcid=0x409). Si ninguna de estas soluciones resuelve su problema, se proporcionará una explicación de cómo [enviar registros a Microsoft](../user-help/send-logs-to-microsoft-android.md).

#### <a name="new-resolve-action-available-for-android-devices---1583480---"></a>Nueva acción "Resolver" disponible para dispositivos Android<!-- 1583480 -->

La aplicación Portal de empresa para Android presenta una acción "Resolver" en la página _Actualizar configuración del dispositivo_. Si se selecciona esta opción, se remitirá al usuario final directamente a la configuración que causa el incumplimiento del dispositivo. La aplicación Portal de empresa para Android admite actualmente esta acción para las opciones de configuración [código de acceso de dispositivo](../user-help/set-your-pin-or-password-android.md), [depuración USB](../user-help/you-need-to-turn-off-usb-debugging-android.md) y [orígenes desconocidos](../user-help/you-need-to-turn-off-unknown-sources-android.md).

#### <a name="device-setup-progress-indicator-in-android-company-portal---1565657---"></a>Indicador de progreso de configuración de dispositivos en Portal de empresa para Android<!-- 1565657 -->
La aplicación Portal de empresa para Android muestra un indicador de progreso de instalación de dispositivos cuando un usuario inscribe sus dispositivos. El indicador muestra estados nuevos, comenzando con "Configurando el dispositivo...", sigue con "Registrando el dispositivo..." y "Finalizando el registro del dispositivo...", y acaba con "Finalizando la configuración del dispositivo...".

#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios--1029830--"></a>Compatibilidad con la autenticación basada en certificados en Portal de empresa para iOS<!--1029830-->
Se ha agregado compatibilidad con la autenticación basada en certificados (CBA) en la aplicación Portal de empresa para iOS. Los usuarios con CBA escriben su nombre de usuario y luego pulsan el vínculo “Iniciar sesión con un certificado”. CBA ya se admite en las aplicaciones del Portal de empresa de Android y Windows. Puede aprender más sobre la página de [inicio de sesión en la aplicación del Portal de empresa](../user-help/sign-in-to-the-company-portal.md).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment---1334712---"></a>Las aplicaciones que están disponibles con o sin inscripción ahora se pueden instalar sin que se les solicite la inscripción.<!-- 1334712 -->

Ahora, las aplicaciones de empresa que se han puesto a disposición de los usuarios con o sin inscripción en la aplicación de Portal de empresa de Android pueden instalarse sin necesidad de una solicitud de inscripción.

#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617----"></a>Compatibilidad del programa Windows AutoPilot Deployment en Microsoft Intune <!-- 747617  -->
Ahora puede usar Microsoft Intune con el programa Windows AutoPilot Deployment para que los usuarios puedan aprovisionar sus dispositivos de empresa sin necesidad de recurrir al departamento de TI. Puede personalizar la experiencia de configuración rápida y guiar a los usuarios durante la combinación de sus dispositivos con Azure AD y la inscripción en Intune. Al usar conjuntamente Microsoft Intune y Windows AutoPilot, se acaba con la necesidad de implementar, mantener y administrar imágenes del sistema operativo. Para obtener información, consulte [Inscribir dispositivos mediante el programa Windows AutoPilot Deployment](../../autopilot/enrollment-autopilot.md).

#### <a name="quickstart-for-device-enrollment----1425655---"></a>Inicio rápido para la inscripción de dispositivos <!-- 1425655 --> 
Ahora el inicio rápido está disponible en **Inscripción de dispositivos** y proporciona una tabla de referencias para administrar plataformas y configurar el proceso de inscripción. Para simplificar la iniciación, se ofrece documentación útil en forma de una breve descripción de cada elemento y enlaces a documentación con instrucciones paso a paso.

#### <a name="device-categorization---1427491---"></a>Categorización de dispositivos<!-- 1427491 -->
En el gráfico de la plataforma de dispositivos inscritos de la hoja **Dispositivos > Información general** se organizan los dispositivos por plataforma, incluidos Android, iOS, macOS, Windows y Windows Mobile.  Los dispositivos que ejecutan otros sistemas operativos se agrupan en "Otros",  por ejemplo, dispositivos fabricados por Blackberry, NOKIA u otros fabricantes.  

Para obtener información sobre los dispositivos que se ven afectados en el inquilino, elija **Administrar > Todos los dispositivos** y después use **Filtrar** para limitar el campo **Sistema operativo**.

#### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium: nuevo socio de defensa contra amenazas móviles  <!-- 954681 -->  
Puede controlar el acceso desde dispositivos móviles a recursos corporativos mediante el acceso condicional basado en la evaluación de riesgos efectuada por Zimperium, una solución de defensa contra amenazas móviles integrada en Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Funcionamiento de la integración con Intune
El riesgo se evalúa según la telemetría recopilada de dispositivos con Zimperium. Se pueden configurar directivas de acceso condicional de EMS según la evaluación de riesgos de Zimperium habilitada mediante las directivas de cumplimiento de los dispositivos de Intune, que puede usar para permitir o bloquear el acceso de los dispositivos no compatibles a los recursos corporativos en función de las amenazas detectadas.

#### <a name="new-settings-for-windows-10-device-restriction-profile----978575-1308849---"></a>Nueva configuración del perfil de restricción de dispositivos Windows 10 <!-- 978575, 1308849, -->  
Estamos agregando nuevas configuraciones al perfil de restricción de dispositivos Windows 10 en la categoría de SmartScreen de Windows Defender.

Para obtener información sobre el perfil de restricción de dispositivos Windows 10, vea [Configuración de restricciones de dispositivos Windows 10 y versiones posteriores](../configuration/device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Soporte remoto para dispositivos Windows y Windows Mobile  <!-- 1070473 -->  
Ahora Intune puede usar el software [TeamViewer](https://www.teamviewer.com), que se compra por separado, para que pueda ofrecer asistencia remota a los usuarios que estén ejecutando Windows y dispositivos Windows Mobile.

#### <a name="scan-devices-with-windows-defender---1280988--1280990-----"></a>Examen de dispositivos con Windows Defender<!-- 1280988  1280990   -->
Ahora puede ejecutar un **Examen rápido** y un **Examen completo**, además de **Actualizar firmas**, con el antivirus Windows Defender en los dispositivos Windows 10 administrados. En la hoja de información general del dispositivo, elija la acción que desea ejecutar en el dispositivo. Se le pide que confirme la acción antes de que el comando se envíe al dispositivo. 

**Examen rápido**: un examen rápido examina las ubicaciones donde el malware se registra para iniciarse, como las claves del Registro y las carpetas de inicio de Windows conocidas. Un examen rápido tarda de media cinco minutos. Al combinarlo con la opción **Always-on real-time protection** (Protección en tiempo real siempre activa), que examina los archivos cuando están abiertos o cerrados y siempre que un usuario navega a una carpeta, el examen rápido ayuda a proporcionar protección frente a malware que podría estar en el sistema o el kernel. Los usuarios ven los resultados del examen en sus dispositivos cuando termina. 

**Examen completo**: un examen completo puede resultar útil en los dispositivos que han encontrado una amenaza de malware para identificar si existe algún componente inactivo que requiera una limpieza más exhaustiva, además de para ejecutar exámenes a petición. El examen completo puede tardar una hora en ejecutarse. Los usuarios ven los resultados del examen en sus dispositivos cuando termina. 

**Actualizar firmas**: el comando de actualización de firmas actualiza las definiciones y las firmas de malware del antivirus de Windows Defender. Esto le ayuda a asegurarse de que el antivirus de Windows Defender es eficaz en la detección de malware. Esta característica es para dispositivos Windows 10 únicamente, está pendiente la conectividad a Internet de los dispositivos. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal----1400455---"></a>Se ha quitado el botón Habilitar/Deshabilitar de la página de la entidad emisora de certificados de Azure Portal de Intune <!-- 1400455 -->
 Se está eliminando un paso adicional para configurar el conector de certificados en Intune. Actualmente, descarga el conector del certificado y después lo habilita en la consola de Intune. En cambio, si deshabilita el conector en la consola de Intune, el conector sigue emitiendo certificados.

#### <a name="how-does-this-affect-me"></a>¿Cómo me afecta esto?
A partir de octubre, el botón Habilitar/Deshabilitar ya no aparecerá en la página de la entidad emisora de certificados en Azure Portal. La funcionalidad del conector sigue siendo la misma. Los certificados todavía se implementan en dispositivos inscritos en Intune. Puede continuar descargando e instalando el conector del certificado. Para detener la emisión de certificados, ahora deberá desinstalar el conector del certificado en vez de deshabilitarlo.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararme para este cambio?
Si actualmente tiene el conector del certificado deshabilitado, primero debe desinstalarlo.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-----1308838---"></a>Nueva configuración del perfil de restricción de dispositivo de Windows 10 Team  <!-- 1308838 -->
En esta versión, hemos agregado muchas nuevas configuraciones al perfil de restricción de dispositivo de Windows 10 Team para ayudarle a controlar los dispositivos de Surface Hub.

Para obtener más información sobre este perfil, vea [Configuración de restricciones de dispositivos Windows 10 Team en Microsoft Intune](../configuration/device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Impedir que los usuarios de dispositivos Android puedan cambiar la fecha y la hora de los dispositivos <!-- 1333292 -->
Puede usar una [directiva de dispositivo personalizada de Android](../configuration/custom-settings-android.md) para impedir que los usuarios de dispositivos Android cambien la fecha y la hora del dispositivo.

Para ello, configure una directiva personalizada de Android con el URI de configuración ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange. Establezca este parámetro en **TRUE** y luego asígnelo a los grupos requeridos.

#### <a name="bitlocker-device-configuration---1397398---"></a>Configuración de dispositivo de BitLocker<!-- 1397398 -->
La opción **Cifrado de Windows > Configuración base**  incluye el nuevo ajuste **Advertencia para otro cifrado de disco** que le permite deshabilitar el [mensaje de advertencia](/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) para otro cifrado de disco que podría estar en uso en el dispositivo del usuario.  El mensaje de advertencia requiere el consentimiento del usuario final antes de configurar BitLocker en el dispositivo y bloquea la instalación de BitLocker hasta que este la confirme.  La nueva configuración deshabilita la advertencia del usuario final.


#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant---800882---"></a>Ahora el programa de compras por volumen para las aplicaciones de empresa se sincronizará con el inquilino de Intune<!-- 800882 -->  
Los desarrolladores de terceros también pueden distribuir aplicaciones de forma privada a miembros autorizados del Programa de compras por volumen (VPP) para Empresas, especificados en iTunes Connect. Estos miembros pueden iniciar sesión en la tienda de aplicaciones del Programa de Compras por Volumen y comprar aplicaciones.

Con esta versión, el VPP para aplicaciones de empresa que haya comprado el usuario final se sincronizarán con sus inquilinos de Intune.

#### <a name="select-apple-countryregion-store-to-sync-vpp-apps----1332311---"></a>Selección de la instancia de App Store de Apple del país o región para la sincronización de aplicaciones de VPP <!-- 1332311 -->  
Puede configurar la instancia de App Store del país o la región para el Programa de Compras por Volumen de Apple (VPP) al cargar el token de VPP. Intune sincroniza las aplicaciones de VPP para todas las configuraciones regionales desde la instancia de App Store del país o la región de VPP especificada.

> [!NOTE]  
> En la actualidad, Intune solo sincroniza las aplicaciones de VPP de la instancia de App Store del país o la región de VPP que coinciden con la configuración regional de Intune en la que se creó el inquilino de Intune.


#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work---1098994---"></a>Bloqueo de las acciones de copiar y pegar entre perfiles profesionales y personales en Android for Work<!-- 1098994 -->
Con esta versión, es posible configurar el perfil del trabajo para Android for Work a fin de bloquear las acciones de copiar y pegar entre aplicaciones profesionales y personales. Puede encontrar esta nueva opción de configuración en el perfil **Restricciones de dispositivos** para la plataforma **Android for Work** en **Configuración del perfil de trabajo**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores---1281692---"></a>Creación de aplicaciones iOS limitada a determinadas instancias regionales de App Store de Apple<!-- 1281692 -->
Podrá especificar la configuración regional del país o la región durante la creación de una aplicación administrada de App Store de Apple.

> [!Note]  
> Actualmente, solo puede crear aplicaciones administradas del App Store de Apple que se encuentren en tiendas de Estados Unidos o la región.

#### <a name="update-ios-vpp-user-and-device-licensed-apps----1305564---"></a>Actualización de aplicaciones con licencia para dispositivos y usuarios de VPP de iOS <!-- 1305564 -->  
Podrá configurar el token de VPP de iOS para actualizar todas las aplicaciones adquiridas para ese token a través del servicio de Intune. Intune detectará las actualizaciones de la aplicación de VPP dentro de la App Store y las insertará automáticamente en el dispositivo cuando este se registra.

Para consultar los pasos necesarios para establecer un token de VPP y habilitar las actualizaciones automáticas, consulte [Administrar aplicaciones de iOS compradas a través de un programa de compras por volumen con Microsoft Intune] (../apps/vpp-apps-ios).


#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model---1187917---"></a>Colección de entidades de asociación de dispositivos de usuario agregada al modelo de datos Data Warehouse de Intune<!-- 1187917 -->
Ahora puede generar informes y visualizaciones de datos con la información de asociación de dispositivo de usuario que asocia las colecciones de la entidad de dispositivo y de usuario. Es posible tener acceso al modelo de datos a través del archivo de Power BI (PBIX) recuperado de la página de almacenamiento de datos de Intune, a través del punto de conexión de OData o mediante el desarrollo de un cliente personalizado.

#### <a name="review-policy-compliance-for-windows-10-update-rings---1067886---"></a>Revisión del cumplimiento de directivas para los anillos de actualizaciones de Windows 10<!-- 1067886 -->
Podrá revisar un informe de directiva para los círculos de actualizaciones de Windows 10 desde Actualizaciones de software > Estado de implementación por anillo de actualización. El informe de directiva incluye el estado de implementación para los anillos de actualización que ha configurado. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions-----1352223---"></a>Nuevo informe en el que se muestran los dispositivos iOS con versiones anteriores de iOS  <!-- 1352223 -->
El informe **Dispositivos iOS obsoletos** está disponible desde el área de trabajo **Actualizaciones de software**. En el informe, puede ver una lista de dispositivos iOS supervisados destinados mediante una directiva de actualización iOS y que tienen actualizaciones disponibles. Para cada dispositivo, puede ver un estado por el que el dispositivo no se ha actualizado automáticamente. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Visualización de las asignaciones de directivas de protección de aplicaciones para la solución de problemas<!--  1475003 -->
En la próxima versión, la opción **Directiva de protección de aplicaciones** se agregará a la lista desplegable **Asignaciones** disponible en la hoja de la solución de problemas. Ahora puede seleccionar las directivas de protección de aplicaciones para ver las directivas de protección de aplicaciones asignadas a los usuarios seleccionados.



#### <a name="improvements-to-device-setup-workflow-in-company-portal--1490692--"></a>Mejoras en el flujo de trabajo de configuración de dispositivos en el Portal de empresa<!--1490692-->
Se ha mejorado el flujo de trabajo de instalación de dispositivos en la aplicación del Portal de empresa para Android. El lenguaje es más fácil de usar y es específico de su empresa. Además, hemos combinado pantallas siempre que hemos podido. Puede ver estas mejoras en la página [Novedades de la interfaz de usuario de aplicaciones](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices--1484985--"></a>Instrucciones mejoradas sobre la solicitud de acceso a los contactos en dispositivos Android<!--1484985-->

La aplicación del Portal de empresa para Android requiere a menudo que el usuario final acepte el permiso de contactos. Si un usuario final no acepta este acceso, ahora verá una notificación en la aplicación en la que se le alerta de concederlo para el acceso condicional. 

#### <a name="secure-startup-remediation-for-android--1490712--"></a>Corrección del inicio seguro para Android<!--1490712-->

Los usuarios finales con dispositivos Android podrán pulsar en la razón de no compatibilidad en la aplicación del Portal de empresa. Cuando sea posible, esta acción les llevará directamente a la ubicación correcta en la aplicación de configuración para solucionar el problema. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo--1475932--"></a>Notificaciones de inserción adicionales para los usuarios finales en la aplicación Portal de empresa para Android Oreo<!--1475932-->

Los usuarios finales verán notificaciones adicionales que indican cuando la aplicación Portal de empresa para Android Oreo realiza tareas en segundo plano, como recuperar directivas desde el servicio Intune. Con esto se aumenta la transparencia para los usuarios finales con respecto a cuando Portal de empresa realiza tareas administrativas en el dispositivo. Esto forma parte de la optimización [general de la UI de Portal de empresa ](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) para la aplicación Portal de empresa para Android Oreo. 

Existen más optimizaciones para nuevos elementos de la IU que ya están habilitados para Android Oreo.  Los usuarios finales verán notificaciones adicionales en las que se les indicará el momento en el que la aplicación Portal de empresa esté realizando tareas en segundo plano, como la recuperación de directivas desde el servicio Intune.  Esto aumenta la transparencia para los usuarios finales sobre cuándo el Portal de empresa está realizando tareas administrativas en el dispositivo.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles---1485783---"></a>Nuevos comportamientos para la aplicación de Portal de empresa para Android con perfiles de trabajo<!-- 1485783 -->

Cuando inscribe un dispositivo de Android for Work con un perfil de trabajo, es la aplicación del Portal de empresa del perfil de trabajo la que realiza las tareas de administración en el dispositivo. 

A menos que vaya a usar una aplicación habilitada para MAM en el perfil personal, la aplicación del Portal de empresa para Android ya no satisface todos los usos. Para mejorar la experiencia del perfil de trabajo, Intune oculta automáticamente la aplicación personal del Portal de empresa después de una inscripción correcta del perfil de trabajo.

La aplicación del Portal de empresa para Android se puede habilitar en cualquier momento en el perfil personal; para ello, vaya al [Portal de empresa en Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) y pulse **Habilitar**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode--1428681--"></a>El Portal de empresa para Windows 8.1 y Windows Phone 8.1 se mueve al modo de mantenimiento<!--1428681-->

A partir de octubre de 2017, las aplicaciones del Portal de empresa para Windows 8.1 y Windows Phone 8.1 se moverán al modo de mantenimiento. Esto significa que las aplicaciones y los escenarios existentes, como inscripción y cumplimiento, se seguirán admitiendo en estas plataformas. Estas aplicaciones seguirán estando disponibles para su descarga mediante los canales de lanzamiento existentes, como Microsoft Store. 

Una vez que se encuentre en modo de mantenimiento, estas aplicaciones solo recibirán actualizaciones de seguridad críticas. No habrá actualizaciones adicionales ni se lanzarán características para ellas. En el caso de nuevas características, se recomienda actualizar los dispositivos a Windows 10 o Windows 10 Mobile. 


#### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Bloqueo de la inscripción de dispositivos Samsung KNOX no compatibles <!-- 1490695 -->

La aplicación del Portal de empresa solo intenta inscribir los dispositivos Samsung Knox compatibles. Para evitar errores de activación de Knox que impidan la inscripción de MDM, la inscripción de dispositivos solo se intenta si el dispositivo aparece en la [lista de dispositivos publicados por Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Los dispositivos Samsung pueden tener números de modelo que admitan Knox, mientras que otros no. Compruebe la compatibilidad de Knox con su revendedor de dispositivos antes de su compra e implementación. Encontrará la lista completa de dispositivos comprobados en la [configuración de directivas de Android y Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

#### <a name="end-of-support-for-android-43-and-lower---1171126-1326920---"></a>Finalización del soporte para Android 4.3 y versiones inferiores<!-- 1171126, 1326920 -->
Las aplicaciones administradas y la aplicación Portal de empresa para Android exigirán Android 4.4 y versiones posteriores para acceder a recursos de empresa. En diciembre, todos los dispositivos inscritos se eliminarán, lo que provocará su pérdida de acceso a los recursos de empresa. Si está usando directivas de protección de aplicaciones sin MDM, las aplicaciones no recibirán actualizaciones y la calidad de su experiencia empeorará con el tiempo.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices--1165314--"></a>Detalles para los usuarios finales sobre qué información del dispositivo se puede ver en los dispositivos inscritos<!--1165314-->
Se va a agregar la opción **Tipo de propiedad** a la pantalla Detalles del dispositivo en todas las aplicaciones del Portal de empresa. De esta manera, los usuarios podrán obtener más información sobre privacidad directamente en el artículo [¿Qué información puede ver mi empresa cuando inscribo mi dispositivo?](../user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md). Esta funcionalidad se implementará en todas las aplicaciones del Portal de empresa en un futuro cercano. Esto se anunció para iOS en [septiembre](#september-2017).

<!-- ########################## -->
### <a name="september-2017"></a>Septiembre de 2017

#### <a name="intune-supports-ios-11--1428975--"></a>Intune es compatible con iOS 11<!--1428975-->
Intune es compatible con iOS 11. Ya se anunció anteriormente en el [blog de soporte técnico de Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80---1164477---"></a>Finalización del soporte de iOS 8.0<!-- 1164477 -->
Las aplicaciones administradas y la aplicación Portal de empresa para iOS necesitan iOS 9.0 y posterior para poder acceder a los recursos de la empresa. Los dispositivos que no estén actualizados antes de septiembre de este año ya no podrán acceder a esas aplicaciones ni al Portal de empresa. 

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10--1132468--"></a>Adición de acción de actualización a la aplicación de Portal de empresa para Windows 10<!--1132468-->
La aplicación de Portal de empresa para Windows 10 permite a los usuarios actualizar los datos de la aplicación tirando para actualizar o, en equipos de escritorio, presionando F5.

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios--739894--"></a>Detalles para los usuarios finales sobre qué información del dispositivo se puede ver para iOS<!--739894-->

Hemos agregado **Tipo de propiedad** a la pantalla Detalles del dispositivo en la aplicación Portal de empresa para iOS. Esto permitirá que los usuarios obtengan más información sobre la privacidad directamente en esta página de los documentos para el usuario final de Intune. También se podrán encontrar estos detalles en la pantalla Información.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment--1169910--"></a>Permitir que los usuarios finales accedan a la aplicación Portal de empresa para Android sin inscripción<!--1169910-->

Pronto los usuarios finales no tendrán que inscribir sus dispositivos para acceder a la aplicación Portal de empresa para Android. Los usuarios finales de las organizaciones que usen directivas de protección de aplicaciones dejarán de recibir mensajes para inscribir sus dispositivos cuando abran la aplicación Portal de empresa. Los usuarios finales también podrán instalar aplicaciones desde el Portal de empresa sin inscribir el dispositivo. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android--1396349--"></a>Frases más fáciles de entender para la aplicación Portal de empresa para Android<!--1396349-->  

El proceso de inscripción de la aplicación Portal de empresa para Android se simplificó con texto nuevo para facilitar la inscripción de los usuarios finales. Si tiene documentación de inscripción personalizada, deberá actualizarla para reflejar las pantallas nuevas. Puede encontrar imágenes de ejemplo en la página [Actualizaciones de la interfaz de usuario para las aplicaciones de usuario final de Intune](whats-new-app-ui.md#week-of-september-11-2017).

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy---677129---"></a>Adición de la aplicación de Portal de empresa de Windows 10 a la directiva de permiso de Windows Information Protection<!-- 677129 -->

La aplicación Portal de empresa de Windows 10 se actualizó para admitir Windows Information Protection (WIP). La aplicación se puede agregar a la directiva de autorización de WIP. Con este cambio, ya no es necesario agregar la aplicación a la lista de **exentos**.


<!-- ########################## -->
### <a name="august-2017"></a>Agosto de 2017

#### <a name="improvements-to-device-overview---1404453---"></a>Mejoras en la información general de dispositivos<!-- 1404453 -->  
La información general de dispositivos ahora muestra los que están inscritos, pero excluye a los que administra Exchange ActiveSync. Los dispositivos de Exchange ActiveSync no ofrecen las mismas opciones de administración que los inscritos. Para ver el número de dispositivos inscritos y el de dispositivos inscritos por plataforma en la sección Intune de Azure Portal, vaya a **Dispositivos** > **Información general**.

#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Mejoras en el inventario de dispositivos recopilado mediante Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
En esta versión, hemos realizado las siguientes mejoras en la información de inventario que recopilan los dispositivos que administra:
 
- En dispositivos Android, ahora puede agregar una columna al inventario de dispositivos que muestra el nivel de revisión más reciente de cada uno. Agregue la columna **Nivel de revisión de seguridad** a la lista de dispositivos para verlo.
- Al filtrar la vista de dispositivos, podrá filtrarlos según su fecha de inscripción. Por ejemplo, puede mostrar solo los dispositivos que se hayan inscrito después de una fecha específica.
- Hemos realizado mejoras en el filtro que usa el elemento **Fecha de la última inserción**.
- En la lista de dispositivos, ahora puede mostrar el número de teléfono de los dispositivos corporativos.
Además, puede usar el panel de filtros para buscar dispositivos por el número de teléfono.

Para obtener más información sobre el inventario de dispositivos, consulte [Visualización del inventario de dispositivos de Intune](../remote-actions/device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Compatibilidad del acceso condicional con dispositivos macOS 
<!-- 720172 -->
Ahora puede establecer una directiva de acceso condicional que exija que los dispositivos Mac se inscriban en Intune y cumplan las directivas de cumplimiento de dispositivos. Por ejemplo, los usuarios pueden descargar la aplicación Portal de empresa de Intune para macOS e inscribir los dispositivos Mac en Intune. Intune evalúa si el dispositivo Mac es conforme o no con requisitos como el PIN, el cifrado, la versión del sistema operativo y la integridad del sistema.

- Obtenga más información sobre la [compatibilidad con el acceso condicional para dispositivos macOS](/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview--1484796--"></a>La aplicación Portal de empresa para macOS está en versión preliminar pública<!--1484796-->
La aplicación Portal de empresa para macOS ya está disponible como parte de la versión preliminar pública para el acceso condicional en Enterprise Mobility + Security. Esta versión admite macOS 10.11 y versiones posteriores. Obténgala en [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Nueva configuración de restricciones de dispositivos para Windows 10    
<!--1063965, 1308850  -->
En esta versión, se han agregado opciones nuevas para el [perfil de restricción de dispositivos Windows 10](/intune/device-restrictions-windows-10) en las siguientes categorías:

- SmartScreen de Windows Defender
- Tienda de aplicaciones

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Actualizaciones en el perfil de dispositivo de Endpoint Protection de Windows 10 para la configuración de BitLocker
<!--1459533 -->    
En esta versión, se han realizado las siguientes mejoras en el funcionamiento de la configuración de BitLocker en un perfil de dispositivo de Endpoint Protection de Windows 10:
 
- En **Configuración de BitLocker para unidades de sistema operativo**, en el ajuste **BitLocker con un chip TPM no compatible** BitLocker estaba permitido tras seleccionar **Bloquear**. Se ha corregido este problema para poder bloquear BitLocker cuando se selecciona.
- En **Configuración de BitLocker para unidades de sistema operativo**, en el ajuste **Agente de recuperación de datos basada en certificado**, ya puede bloquear explícitamente el agente de recuperación de datos basada en certificado. De forma predeterminada, el agente está permitido.
- En **Configuración de BitLocker para unidades de datos fijas**, en el ajuste **Agente de recuperación de datos**, ya puede bloquear explícitamente el agente de recuperación de datos.
Para obtener más información, vea [Endpoint protection settings for Windows 10 and later](../protect/endpoint-protection-windows-10.md) (Configuración de Endpoint Protection para Windows 10 y versiones posteriores).


#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users---621669---"></a>Nueva experiencia de sesión iniciada para los usuarios del Portal de empresa para Android y para los usuarios de las directivas de App Protection<!-- 621669 -->
Los usuarios finales pueden ahora examinar aplicaciones, administrar dispositivos y ver la información de contacto de TI mediante la aplicación del Portal de empresa de Android sin inscribir sus dispositivos Android. Además, si un usuario final ya usa una aplicación protegida por directivas de protección de aplicaciones de Intune y se inicia el Portal de empresa Android, el usuario final ya no recibirá un aviso para inscribir el dispositivo.

#### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization--1405990--"></a>Nueva configuración de la aplicación Portal de empresa para Android para alternar la optimización de la batería<!--1405990-->
La página **Configuración** de la aplicación Portal de empresa para Android tiene una nueva opción que permite a los usuarios desactivar fácilmente la optimización de la batería para las aplicaciones Portal de empresa y Microsoft Authenticator. El nombre de la aplicación que se muestra en la configuración variará dependiendo de qué aplicación administre la cuenta profesional. Recomendamos que los usuarios desactiven la optimización de la batería para obtener un rendimiento mejor de las aplicaciones de trabajo que sincronizan el correo electrónico y los datos. 

#### <a name="multi-identity-support-for-onenote-for-ios---1234281---"></a>Compatibilidad con varias identidades en OneNote para iOS<!-- 1234281 -->
Los usuarios finales ahora pueden usar cuentas diferentes (profesionales o educativas) en Microsoft OneNote para iOS. Las directivas de protección de aplicaciones se pueden aplicar a los datos corporativos en blocs de notas del trabajo sin que esto afecte a sus blocs de notas personales. Por ejemplo, una directiva puede permitir que un usuario busque información en blocs de notas del trabajo, pero impedir que copie datos corporativos desde un bloc de notas del trabajo a uno personal.
 
- Obtenga más información sobre las aplicaciones que admiten [protección de aplicaciones y varias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) con Intune.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nueva configuración para permitir y bloquear aplicaciones en dispositivos Samsung Knox Standard
<!-- 1305423 822899-->  
En esta versión, se ha agregado una nueva [configuración de restricción de dispositivos](../configuration/device-restrictions-android.md) que permite especificar las listas de aplicaciones siguientes:
 
- Aplicaciones que los usuarios pueden instalar
- Aplicaciones que los usuarios no pueden ejecutar
- Aplicaciones ocultas para el usuario en el dispositivo
 
Puede especificar la aplicación por dirección URL, nombre del paquete o desde la lista de aplicaciones que administra.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Nuevo vínculo de interfaz de usuario de la directiva de acceso condicional basado en la aplicación de Azure AD desde Intune
<!-- 1016201 -->
Ahora los administradores de TI pueden establecer directivas condicionales basadas en aplicaciones mediante la nueva interfaz de usuario de directivas de acceso condicional en la carga de trabajo de Azure AD. El acceso condicional basado en la aplicación de la sección de Intune App Protection en Azure Portal por el momento no se moverá y se aplicará en paralelo. También encontrará un práctico vínculo a la interfaz de usuario de la nueva directiva de acceso condicional en la carga de trabajo de Intune.

- Obtenga más información sobre el [acceso condicional basado en la aplicación en Azure AD](/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
### <a name="july-2017"></a>Julio de 2017

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version----1333256--1245463---"></a>Restricción de la inscripción de dispositivos Android e iOS por versión del SO <!-- 1333256,  1245463 -->
Intune ya permite restringir la inscripción de Android e iOS por número de versión del sistema operativo. En **Restricción de tipo de dispositivo**, los administradores de TI ahora pueden establecer una configuración de plataforma para restringir la inscripción entre un valor del sistema operativo mínimo y máximo. Las versiones del sistema operativo Android se deben especificar como Principal.Secundaria.Compilación.Revisión, donde Secundaria, Compilación y Revisión son opcionales. Las versiones de iOS deben especificarse como Principal.Secundaria.Compilación, donde Compilación es opcional. Obtenga más información sobre las [restricciones de inscripción de dispositivos](../enrollment/enrollment-restrictions-set.md).

>[!NOTE]
>No se restringe la inscripción a través de los programas de inscripción de Apple o Apple Configurator.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment----1333272--1333275-1245709---"></a>Restricción de la inscripción de dispositivos Android, iOS y macOS de propiedad personal <!-- 1333272,  1333275, 1245709 -->
Intune puede restringir la inscripción de dispositivos personales al incluir los números IMEI de los dispositivos corporativos en la lista aprobada. Intune ha ampliado esta funcionalidad para iOS, Android y macOS con números de serie del dispositivo. Al cargar los números de serie en Intune, puede declarar los dispositivos como de propiedad corporativa. Con las restricciones de inscripción puede bloquear los dispositivos de propiedad personal (BYOD), lo que permitiría la inscripción de dispositivos de propiedad corporativa únicamente. Obtenga más información sobre las [restricciones de inscripción de dispositivos](../enrollment/enrollment-restrictions-set.md).

Para importar números de serie, vaya a **Inscripción de dispositivos** > **Identificadores de dispositivo corporativos** y haga clic en **Agregar**; luego, cargue un archivo .CSV (sin encabezado, dos columnas para el número de serie y detalles como los números IMEI). Para restringir dispositivos de propiedad personal, vaya a **Inscripción de dispositivos** > **Restricciones de inscripción**. En **Restricciones de tipo de dispositivo**, seleccione **Predeterminado** y luego **Configuraciones de plataforma**. Puede **Permitir** o **Bloquear** dispositivos de propiedad personal iOS, Android y macOS.


#### <a name="new-device-action-to-force-devices-to-sync-with-intune---711369---"></a>Nueva acción de dispositivo para forzar la sincronización de los dispositivos con Intune<!-- 711369 -->
En esta versión, se ha agregado una nueva acción de dispositivo que fuerza al dispositivo seleccionado a registrarse inmediatamente en Intune. Cuando un dispositivo se registra, recibe de inmediato las acciones o las directivas pendientes que se le han asignado.  Esta acción puede ayudarle a validar y a solucionar problemas de directivas que se le hayan asignado inmediatamente, sin tener que esperar al siguiente registro programado.
Para obtener detalles, vea [Synchronize device](../remote-actions/device-sync.md) (Sincronizar dispositivos).

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update---777100---"></a>Forzar a los dispositivos iOS supervisados a instalar automáticamente la última actualización de software disponible<!-- 777100 -->
En el área de trabajo Actualizaciones de software hay disponible una nueva directiva que permite forzar a los dispositivos iOS supervisados a instalar automáticamente la última actualización de software disponible. Para obtener información detallada, consulte [Configure iOS update policies](/intune/software-updates-ios) (Configuración de directivas de actualización de iOS).

#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>SandBlast Mobile de Check Point: nuevo socio de defensa contra amenazas móviles <!-- 954651, 1172027 -->
Puede controlar el acceso desde dispositivos móviles a recursos corporativos mediante el acceso condicional basado en la evaluación de riesgos efectuada por SandBlast Mobile de Check Point, una solución de defensa contra amenazas móviles integrada en Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Funcionamiento de la integración con Intune
El riesgo se evalúa según la telemetría recopilada de dispositivos que ejecutan SandBlast Mobile de Check Point. Puede configurar directivas de acceso condicional de EMS basadas en la evaluación de riesgos de SandBlast Mobile de Check Point habilitada mediante las directivas de cumplimiento de los dispositivos de Intune. Puede permitir o bloquear el acceso de dispositivos no compatibles a recursos corporativos en función de las amenazas detectadas.


#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business---748101---"></a>Implementación de una aplicación como disponible en Microsoft Store para Empresas<!-- 748101 -->
Con esta versión, ahora los administradores pueden asignar la Tienda Microsoft para Empresas como disponible. Cuando se establece como disponible, los usuarios finales pueden instalar la aplicación desde la aplicación de Portal de empresa o un sitio web sin que se les redirija a Microsoft Store.

#### <a name="ui-updates-to-the-company-portal-website--1313244-part-1--"></a>Actualizaciones de la interfaz de usuario en el sitio web del Portal de empresa<!--1313244 part 1-->
Hemos realizado varias actualizaciones en la interfaz de usuario del [sitio web del portal de empresa](https://portal.manage.microsoft.com) para mejorar la experiencia del usuario final.

- __Mejoras en los iconos de aplicación__:  los iconos de aplicación ahora se muestran con un fondo generado automáticamente según el color dominante del icono (si se puede detectar). Si procede, este fondo reemplaza el borde gris que antes era visible en los iconos de aplicación.

    En una próxima versión, el sitio web del Portal de empresa mostrará iconos grandes siempre que sea posible. Recomendamos que los administradores de TI publiquen aplicaciones con iconos de alta resolución, con un tamaño mínimo de 120 x 120 píxeles. 

- __Cambios de navegación__: los elementos de barra de navegación se han movido al menú lateral de la parte superior izquierda. Se ha quitado la página Categorías. Los usuarios ahora pueden filtrar el contenido por categoría durante la exploración.

- __Actualizaciones de aplicaciones destacadas__: Hemos agregado una página dedicada al sitio donde los usuarios pueden buscar aplicaciones que ha decidido presentar, y hemos realizado algunos ajustes a la interfaz de usuario de la sección Destacado en la página principal.

#### <a name="ibooks-support-for-the-company-portal-website--1231841--"></a>Compatibilidad de iBooks con el sitio web del Portal de empresa<!--1231841-->
Hemos agregado una página dedicada al sitio web del Portal de empresa que permite a los usuarios buscar y descargar iBooks. 


#### <a name="additional-help-desk-troubleshooting-details----applies-to-1263399-1326964-1341642---"></a>Detalles adicionales para la solución de problemas del departamento de soporte técnico<!--  Applies to 1263399, 1326964, 1341642 -->
Intune ha actualizado la visualización de información para la solución de problemas, y la ha agregado a la información que se proporciona a los administradores y al personal del departamento de soporte técnico. Ahora puede consultar la tabla **Asignaciones**, en la que se resumen todas las asignaciones para el usuario en función de la pertenencia al grupo. La lista incluye lo siguiente:
- Aplicaciones móviles
- Directivas de cumplimiento
- Perfiles de configuración

Además, en la tabla **Dispositivos** se incluyen ahora las columnas **Tipo de combinación de Azure AD** y **Conforme con Azure AD**. Para obtener más información, consulte [Help users troubleshoot problems (Ayudar a los usuarios a solucionar problemas)](help-desk-operators.md).



#### <a name="intune-data-warehouse-public-preview"></a>Almacenamiento de datos de Intune (versión preliminar pública)
El Almacenamiento de datos de Intune muestrea los datos a diario para proporcionar una vista histórica del inquilino. Puede tener acceso a los datos mediante un archivo de Power BI (PBIX), un vínculo de OData que es compatible con muchas herramientas de análisis o al interactuar con la API de REST. Para obtener más información, vea [Usar el Almacenamiento de datos de Intune](../developer/reports-nav-create-intune-reports.md).


#### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10--676547--"></a>Modos claro y oscuro disponibles para la aplicación Portal de empresa para Windows 10<!--676547-->
Los usuarios finales podrán personalizar el modo de color de la aplicación Portal de empresa para Windows 10. El usuario puede realizar el cambio en la sección Configuración de la aplicación Portal de empresa. El cambio aparecerá una vez que el usuario haya reiniciado la aplicación. En Windows 10 versión 1607 y posteriores, el valor predeterminado del modo de la aplicación es la configuración del sistema. En Windows 10 versión 1511 y anteriores, el valor predeterminado del modo de la aplicación es el modo claro.

#### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10--807046--"></a>Permitir que los usuarios finales etiqueten su grupo de dispositivos en la aplicación Portal de empresa para Windows 10<!--807046-->
Los usuarios finales ahora pueden seleccionar el grupo al que pertenece su dispositivo al etiquetarlo directamente desde la aplicación de portal de empresa para Windows 10.

<!-- ########################## -->
### <a name="june-2017"></a>Junio de 2017

#### <a name="new-role-based-administration-access-for-intune-admins-----1099990---"></a>Nuevo acceso de administración basada en roles para los administradores de Intune  <!-- 1099990 -->  
Se va a agregar un nuevo rol de administrador de acceso condicional para ver, crear, modificar y eliminar directivas de acceso condicional de Azure AD. Anteriormente, solo los administradores globales y de seguridad tenían este permiso. Se puede conceder a los administradores de Intune el permiso de este rol para que tengan acceso a las directivas de acceso condicional.


#### <a name="tag-corporate-owned-devices-with-serial-number---1215070---"></a>Etiquetado de los dispositivos corporativos con el número de serie<!-- 1215070 -->  
Intune ahora admite la carga de números de serie de iOS, macOS y Android como identificadores de dispositivos corporativos. No puede usar en este momento números de serie para impedir que los dispositivos personales se inscriban, ya que los números de serie no se comprueban durante la inscripción. Próximamente se podrán bloquear los dispositivos personales por el número de serie.


#### <a name="new-remote-actions-for-ios-devices---854689---"></a>Nuevas acciones remotas para dispositivos iOS<!-- 854689 -->
En esta versión, hemos agregado dos nuevas acciones de dispositivo remoto para los dispositivos iPad compartidos que administran la aplicación Classroom de Apple:

- [Cerrar sesión del usuario actual](../remote-actions/device-logout-user.md): cierra la sesión del usuario actual del dispositivo iOS que seleccione.
- [Quitar usuario](../remote-actions/device-remove-user.md): elimina un usuario que seleccione de la memoria caché local en un dispositivo iOS.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app---1044681---"></a>Compatibilidad con dispositivos iPad compartidos con la aplicación Aula de iOS<!-- 1044681 -->
En esta versión, hemos ampliado la compatibilidad con la administración de la aplicación Classroom en iOS, a fin de incluir a los estudiantes que se registran en dispositivos iPad compartidos con sus identificadores de Apple administrados.


#### <a name="changes-to-intune-built-in-apps---1332306---"></a>Cambios en las aplicaciones integradas de Intune<!-- 1332306 -->
Anteriormente, Intune tenía numerosas aplicaciones integradas que se podían asignar rápidamente. Basándonos en los comentarios de los usuarios, hemos quitado esta lista y ya no se verán las aplicaciones integradas.
Sin embargo, si las aplicaciones integradas ya están asignadas, seguirán mostrándose en la lista de aplicaciones. Las aplicaciones podrán seguir asignándose según se necesite.
En una versión posterior, vamos a agregar un método sencillo para seleccionar y asignar aplicaciones integradas de Azure Portal.

#### <a name="easier-installation-of-microsoft-365-apps---1121362---"></a>Instalación más sencilla de las aplicaciones de Microsoft 365<!-- 1121362 -->
El nuevo tipo de aplicación **Aplicaciones de Microsoft 365 para empresas** facilita la asignación de Aplicaciones de Microsoft 365 para empresas a dispositivos que administre con la versión más reciente de Windows 10. Además, también puede instalar Microsoft Project y Microsoft Visio si dispone de licencias para ellos. Las aplicaciones que quiera se agrupan y aparecen como una única aplicación en la lista de aplicaciones de la consola de Intune.
Para obtener más información, consulte el artículo sobre [cómo agregar aplicaciones de Microsoft 365 para Windows 10](../apps/apps-add-office365.md).


#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---777044---"></a>Compatibilidad con aplicaciones sin conexión de Microsoft Store para Empresas<!-- 777044 -->
Las aplicaciones sin conexión que ha adquirido en la Tienda Microsoft para Empresas ahora se sincronizarán con Azure Portal. Así, puede implementar estas aplicaciones en grupos de usuarios o grupos de dispositivos. Las aplicaciones sin conexión no se instalan desde la Tienda, sino mediante Intune.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps-----1257019---"></a>Microsoft Teams ahora forma parte de la lista de CA basada en aplicación de aplicaciones aprobadas  <!-- 1257019 -->
La aplicación Microsoft Teams para iOS y Android ahora forma parte de las aplicaciones aprobadas para las directivas de acceso condicional basado en la aplicación en Exchange y SharePoint Online. La aplicación puede configurarse para todos los inquilinos mediante la hoja Intune App Protection de Azure Portal en estos momentos mediante el acceso condicional basado en la aplicación.

#### <a name="managed-browser-and-app-proxy-integration---1287310---"></a>Integración de Proxy de aplicación y Managed Browser<!-- 1287310 -->
Intune Managed Browser ahora puede integrarse con el servicio de Azure AD Application Proxy para permitir que los usuarios tengan acceso a los sitios web internos incluso cuando están trabajando en remoto. Los usuarios del explorador simplemente especifican la URL del sitio como lo harían normalmente y Managed Browser enruta la solicitud mediante la puerta de enlace web de Application Proxy. Para obtener más información, vea [Administrar el acceso a Internet mediante directivas de Managed Browser](../apps/manage-microsoft-edge.md).

#### <a name="new-app-configuration-settings-for-the-intune-managed-browser---682951---"></a>Nuevas opciones de configuración de aplicaciones para Intune Managed Browser<!-- 682951 -->
En esta versión, hemos agregado más configuraciones para la aplicación Intune Managed Browser para iOS y Android. Ahora puede usar una directiva de configuración de aplicaciones para configurar la página principal predeterminada y los marcadores para el explorador.
Para obtener más información, vea [Administrar el acceso a Internet mediante directivas de Managed Browser](../apps/manage-microsoft-edge.md).

#### <a name="bitlocker-settings-for-windows-10----951707---"></a>Configuración de BitLocker para Windows 10 <!-- 951707 -->
Ahora puede configurar las opciones de BitLocker para dispositivos Windows 10 con un nuevo perfil de dispositivo de Intune. Por ejemplo, puede que necesite que los dispositivos estén cifrados, y también configurar más opciones que se apliquen cuando BitLocker esté activado.
Para obtener más información, vea [Endpoint protection settings for Windows 10 and later](../protect/endpoint-protection-windows-10.md) (Configuración de Endpoint Protection para Windows 10 y versiones posteriores).

#### <a name="new-settings-for-windows-10-device-restriction-profile---978527--978550-978569-1050031-1058611----"></a>Nueva configuración del perfil de restricción de dispositivos Windows 10<!-- 978527,  978550, 978569, 1050031, 1058611,  -->
En esta versión, hemos agregado nuevas opciones para el perfil de restricción de dispositivos Windows 10, en las categorías siguientes:

- Windows Defender
- Red de telefonía móvil y conectividad
- Experiencia de pantalla bloqueada
- Privacidad
- Búsqueda
- Contenido destacado de Windows
- Explorador Microsoft Edge

Para obtener más información sobre la configuración de Windows 10, vea [Configuración de restricciones de dispositivos Windows 10 y versiones posteriores](../configuration/device-restrictions-windows-10.md).


#### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies--1305217--"></a>La aplicación Portal de empresa para Android ahora tiene una nueva experiencia de usuario final para las directivas App Protection<!--1305217-->
Basándonos en los comentarios de los clientes, hemos modificado la aplicación del portal de empresa para Android para mostrar un botón **Acceso al contenido de la empresa**. El objetivo es impedir que los usuarios finales pasen innecesariamente por el proceso de inscripción cuando solo necesitan tener acceso a las aplicaciones que admiten directivas de protección de aplicaciones, una característica de administración de aplicaciones móviles de Intune. Puede ver estos cambios en la página [Novedades en la interfaz de usuario de la aplicación](whats-new-app-ui.md).

#### <a name="new-menu-action-to-easily-remove-company-portal--1164569--"></a>Nueva acción de menú para quitar fácilmente Portal de empresa<!--1164569-->
Según los comentarios de los usuarios, se agregó una nueva acción de menú en la aplicación Portal de empresa de Intune para Android con el fin de iniciar su eliminación del dispositivo. Con esta acción se quita el dispositivo de administración de Intune para que la aplicación se pueda quitar del dispositivo por parte del usuario. Puede ver estos cambios en la página de [novedades en la UI de la aplicación](whats-new-app-ui.md) y en la [documentación para el usuario final de Android](../user-help/unenroll-your-device-from-intune-android.md).

#### <a name="improvements-to-app-syncing-with-windows-10-creators-update--676505--"></a>Mejoras en la sincronización de aplicaciones con Windows 10 Creators Update<!--676505-->
La aplicación Portal de empresa de Intune para Windows 10 ahora iniciará automáticamente una sincronización de las solicitudes de instalación de aplicaciones para dispositivos con Windows 10 Creators Update (versión 1709). De esta forma, se reducirá el problema de estancamiento de las instalaciones de aplicaciones durante el estado "Pending Sync" (Sincronización pendiente). Además, los usuarios podrán iniciar manualmente la sincronización desde dentro de la aplicación. Puede ver estos cambios en la página [Novedades en la interfaz de usuario de la aplicación](whats-new-app-ui.md).

#### <a name="new-guided-experience-for-windows-10-company-portal--1058938--"></a>Nueva experiencia guiada del Portal de empresa de Windows 10<!--1058938-->
La aplicación del Portal de empresa para Windows 10 incluirá la experiencia de un tutorial de Intune guiado para dispositivos que no se han identificado ni inscrito. La nueva experiencia proporciona instrucciones paso a paso que llevan al usuario por el registro en Azure Active Directory (que es necesario para las características de acceso condicional) y la inscripción en MDM (que es necesaria para las características de administración de dispositivos). La experiencia guiada será accesible desde la página principal del Portal de empresa. Los usuarios pueden seguir utilizando la aplicación si no completan el registro y la inscripción, pero experimentarán una funcionalidad limitada.

Esta actualización solo es visible en dispositivos que ejecuten la Actualización de aniversario de Windows 10 (compilación 1607) o superior. Puede ver estos cambios en la página [Novedades en la interfaz de usuario de la aplicación](whats-new-app-ui.md).


#### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Las consolas de administración de Microsoft Intune y Acceso condicional están disponibles con carácter general
Se anuncia la disponibilidad general de la nueva consola de administración tanto de Intune en Azure Portal como de Acceso condicional. A través de Intune en Azure Portal, ahora puede administrar todas las funcionalidades MAM y MDM de Intune en una experiencia de administración consolidada y aprovechar la agrupación y la selección de destino de Azure AD. Acceso condicional de Azure reúne las amplias funcionalidades de Azure AD e Intune en una consola unificada. Y, desde una experiencia administrativa, migrar a la plataforma Azure permite usar exploradores modernos.

Intune ya está visible sin la etiqueta de **versión preliminar** en Azure portal en portal.azure.com.

No es necesario que los clientes existentes tomen ninguna medida en este momento, a menos que se haya recibido un mensaje de una serie de estos en el centro de mensajes en el que se le solicite llevar a cabo una acción para que sea posible migrar sus grupos. Es posible que también haya recibido una notificación del centro de mensajes en el que se le informe que la migración está tardando más de lo debido producto de errores en nuestro lado. Seguimos trabajando con diligencia para migrar cualquier cliente afectado.

#### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Mejoras de los iconos de aplicación en la aplicación Portal de empresa de Intune para iOS
Se ha actualizado el diseño de los iconos de aplicación en la página principal para reflejar el color de personalización de marca que establezca para el Portal de empresa. Para más información, consulte las [novedades en la UI de la aplicación](whats-new-app-ui.md).

#### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Ahora el selector de cuenta está disponible en la aplicación Portal de empresa de Intune para iOS
Los usuarios de dispositivos iOS pueden ver el nuevo selector de cuenta cuando inician sesión en Portal de empresa de Intune si usan su cuenta profesional o educativa para iniciar sesión en otras aplicaciones de Microsoft. Para más información, consulte las [novedades en la UI de la aplicación](whats-new-app-ui.md).

<!-- ########################## -->
### <a name="may-2017"></a>Mayo de 2017

#### <a name="change-your-mdm-authority-without-unenrolling-managed-devices--1103950--"></a>Cambio de la entidad de MDM sin anular la inscripción de dispositivos administrados<!--1103950-->
Ahora puede cambiar la entidad de MDM sin tener que ponerse en contacto con el Soporte técnico de Microsoft y sin necesidad de anular la inscripción ni de volver a inscribir los dispositivos administrados existentes. En la consola de Configuration Manager, puede cambiar la entidad de MDM de Configurar como Configuration Manager (híbrido) a Microsoft Intune (independiente), o viceversa.


#### <a name="improved-notification-for-samsung-knox-startup-pins--1087143--"></a>Notificación mejorada para PIN de inicio en Samsung Knox<!--1087143-->
Si los usuarios finales necesitan establecer un PIN de inicio en dispositivos Samsung Knox a efectos de compatibilidad con el cifrado, cuando dichos usuarios pulsen en la notificación que aparece, se les remitirá al lugar exacto de la aplicación de configuración.  Anteriormente, la notificación remitía al usuario final a la pantalla de cambio de contraseña.

#### <a name="apple-school-manager-asm-support-with-shared-ipad---748864-770395--"></a>Compatibilidad de Apple School Manager (ASM) con iPad compartido<!-- 748864, 770395-->

Intune ahora admite el uso de Apple School Manager (ASM) en lugar del Programa de inscripción de dispositivos de Apple para permitir la inscripción inmediata de dispositivos iOS. Es necesario incorporar ASM para usar la aplicación Classroom para Shared iPads, así como habilitar la sincronización de datos de ASM en Azure Active Directory mediante Microsoft School Data Sync (SDS). Para más información, consulte el artículo sobre la [habilitación de la inscripción de dispositivos iOS con Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md).

> [!NOTE]
> Configurar iPad compartidos para que funcionen con la aplicación Classroom requiere configuraciones de dispositivos iOS para Education en Azure que todavía no están disponibles.  Esta funcionalidad se agregará pronto.

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer---675418---"></a>Asistencia remota para dispositivos Android con TeamViewer<!-- 675418 -->

Intune ahora puede usar el software [TeamViewer](https://www.teamviewer.com), que se compra de forma independiente, para permitirle ofrecer asistencia remota a los usuarios que ejecutan dispositivos Android. Para más información, consulte [Asistencia remota para dispositivos Android administrados con Intune](../remote-actions/teamviewer-support.md).

#### <a name="new-app-protection-policies-conditions-for-mam---679864---"></a>Nuevas condiciones de las directivas de protección de aplicaciones para MAM<!-- 679864 -->

Ahora puede establecer un requisito para MAM sin inscripción de usuarios que exige las siguientes directivas:

- Versión mínima de la aplicación
- Versión mínima del sistema operativo
- Versión mínima del SDK para aplicaciones de Intune de la aplicación de destino (solo iOS)

Esta característica está disponible en iOS y Android. Intune admite el cumplimiento del requisito de versiones mínimas de la plataforma de SO, las aplicaciones y el SDK para aplicaciones de Intune. En iOS, las aplicaciones que tienen el SDK integrado también pueden establecer el cumplimiento de una versión mínima a nivel del SDK. El usuario no podrá acceder a la aplicación de destino si no se cumplen los requisitos mínimos a través de la directiva de protección de aplicaciones a los tres niveles distintos mencionados anteriormente. En este punto, el usuario puede quitar la cuenta (en aplicaciones con varias identidades), cerrar la aplicación o actualizar la versión del SO o de la aplicación.

También puede configurar valores adicionales para proporcionar una notificación sin bloqueo que recomienda una actualización del SO o de la aplicación. Puede cerrar esta notificación, y la aplicación puede usarse de la forma habitual.

Para más información, consulte [Configuración de directivas de protección de aplicaciones de iOS](../apps/app-protection-policy-settings-ios.md) y [Configuración de directivas de protección de aplicaciones de Android](../apps/app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work---621621---"></a>Configuración de aplicaciones para Android for Work<!-- 621621 -->
Algunas aplicaciones Android de la tienda admiten opciones de configuración administradas que permiten que un administrador de TI controle cómo se ejecuta la aplicación en el perfil de trabajo. Con Intune, ahora puede ver las configuraciones que son compatibles con una aplicación y configurarlas desde Azure Portal con un diseñador de configuración o un editor de JSON. Para más información, consulte el artículo sobre el [uso de configuraciones de aplicación para Android for Work](../apps/app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment---677969---"></a>Nueva funcionalidad de configuración de aplicaciones para MAM sin inscripción<!-- 677969 -->
Ahora puede crear directivas de configuración de aplicación a través de MAM sin canal de inscripción. Esta característica es equivalente a las directivas de configuración de aplicación disponibles en la configuración de aplicación de administración de dispositivos móviles (MDM). Si desea un ejemplo de configuración de aplicación con MAM sin inscripción, consulte [Administrar el acceso a Internet mediante directivas de Managed Browser con Microsoft Intune](../apps/manage-microsoft-edge.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser---682960---"></a>Configuración de las listas de direcciones URL permitidas y bloqueadas para Managed Browser<!-- 682960 -->
Ahora puede configurar una lista de direcciones URL y dominios permitidos y bloqueados para Intune Manager Browser con los valores de configuración de aplicación en Azure Portal. Estos valores se pueden configurar independientemente de si se usa en un dispositivo administrado o no administrado. Para más información, consulte [Administrar el acceso a Internet mediante directivas de Managed Browser con Microsoft Intune](../apps/manage-microsoft-edge.md).

#### <a name="app-protection-policy-helpdesk-view---1069473---"></a>Vista de departamento de soporte técnico de directiva de protección de aplicaciones<!-- 1069473 -->
Los usuarios del departamento de soporte técnico de TI ahora pueden comprobar el estado de la licencia de usuario y el estado de las aplicaciones de directiva de protección de aplicaciones asignadas a los usuarios en la hoja Solución de problemas. Para información detallada, consulte [Solución de problemas](./help-desk-operators.md).

#### <a name="control-website-visits-on-ios-devices---723832---"></a>Control de las visitas a sitios web en dispositivos iOS<!-- 723832 -->
Ahora puede controlar qué sitios web pueden visitar los usuarios de dispositivos iOS mediante uno de los dos métodos siguientes:

- Agregar direcciones URL permitidas y bloqueadas mediante el filtro de contenido web integrado de Apple.

- Permitir que el explorador Safari acceda solo a sitios web especificados. Se crean marcadores en Safari para cada sitio que especifique.

Para más información, consulte [Configuración de filtro de contenido web para dispositivos iOS](../configuration/ios-device-features-settings.md#web-content-filter).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps---621614---"></a>Configuración previa de permisos de dispositivo para aplicaciones de Android for Work<!-- 621614 -->
En el caso de las aplicaciones implementadas en perfiles de trabajo de dispositivos Android for Work, ahora puede configurar el estado de los permisos en cada aplicación.  De forma predeterminada, las aplicaciones de Android que requieren permisos de dispositivo como el acceso a la ubicación o la cámara del dispositivo solicitarán a los usuarios que acepten o denieguen permisos.  Por ejemplo, si una aplicación usa el micrófono del dispositivo, se solicita al usuario final que conceda a la aplicación el permiso para usar el micrófono. Esta característica le permite definir permisos en nombre del usuario final.  Ahora puede configurar permisos para a) denegar automáticamente sin notificar al usuario, b) aprobar automáticamente sin notificar al usuario, o c) pedirle al usuario que acepte o deniegue los permisos. Para más información, consulte [Configuración de restricciones de dispositivos Android for Work en Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices---728976-1102534---"></a>Establecimiento de un PIN específico de la aplicación para dispositivos Android for Work<!-- 728976, 1102534 -->
Los dispositivos Android 7.0 y versiones posteriores con un perfil de trabajo administrado como un dispositivo Android for Work permiten que el administrador defina una directiva de código de acceso que solo se aplique a aplicaciones del perfil de trabajo.  Las opciones son:

- Definir una contraseña de código de acceso a nivel de dispositivo: se trata del código de acceso que el usuario debe usar para desbloquear todo el dispositivo.
- Definir una directiva de código de acceso solo a nivel de perfil de trabajo: a los usuarios se les pedirá que escriban un código de acceso cada vez que se abra cualquier aplicación del perfil de trabajo.
- Definir una directiva para el dispositivo y el perfil de trabajo: el administrador de TI tiene la opción de definir una directiva de código de acceso para el dispositivo y otra para el perfil de trabajo con diferentes intensidades (por ejemplo, un PIN de cuatro dígitos para desbloquear el dispositivo y uno de seis para abrir cualquier aplicación de trabajo).

Para más información, consulte [Configuración de restricciones de dispositivos Android for Work en Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

> [!NOTE]
> Esta opción solo está disponible en Android 7.0 y versiones posteriores.  De forma predeterminada, el usuario final puede usar los dos PIN definidos por separado o de optar por combinar los dos en el más seguro de ellos.

#### <a name="new-settings-for-windows-10-devices---978585---"></a>Nuevas opciones de configuración para dispositivos Windows 10<!-- 978585 -->
Agregamos una nueva [configuración de restricción de dispositivos Windows](../configuration/device-restrictions-windows-10.md) que controla características como la proyección inalámbrica, la detección de dispositivos, la conmutación de tareas y los mensajes de error de tarjetas SIM.

#### <a name="updates-to-certificate-configuration---918991-and-823198---"></a>Actualizaciones de la configuración de certificados<!-- 918991 and 823198 -->
Cuando crea un perfil de certificado SCEP, en el <strong>formato del nombre del sujeto</strong>, la opción <strong>Personalizar</strong> está disponible para dispositivos iOS, Android y Windows. Antes de esta actualización, el campo <strong>Personalizar</strong> solo estaba disponible para dispositivos iOS. Para obtener más información, vea [Creación de un perfil de certificado SCEP](../protect/certificates-profile-scep.md).

Cuando crea un perfil de certificado PKCS, en el **nombre alternativo del sujeto**, está disponible la opción **Atributo de Azure AD personalizado**. La opción **Departamento** está disponible cuando se selecciona **Atributo de Azure AD personalizado**. Para obtener más información, vea [Creación de un perfil de certificado PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode---662059---"></a>Configuración de varias aplicaciones que se pueden ejecutar cuando un dispositivo Android está en el modo de pantalla completa<!-- 662059 -->
Si un dispositivo Android está en el modo de pantalla completa, anteriormente solo podía configurar una aplicación que se podía ejecutar. Ahora puede configurar varias aplicaciones con el id. de la aplicación, la dirección URL de la tienda o seleccionando una aplicación Android que ya administra. Para más información, consulte [Configuración del modo de pantalla completa](../configuration/device-restrictions-android.md#kiosk).

<!-- ########################## -->
### <a name="april-2017"></a>Abril de 2017

#### <a name="support-for-managing-the-apple-classroom-app"></a>Compatibilidad para administrar la aplicación Classroom de Apple
Ahora puede administrar la aplicación Classroom de iOS en dispositivos iPad. Configure la aplicación Classroom en el iPad de los profesores con los datos correctos de la clase y los estudiantes y, a continuación, configure los iPad de los estudiantes registrados en la clase, de modo que pueda controlarlos mediante la aplicación.
Para obtener más detalles, vea [Configuración de dispositivos iOS para el entorno educativo](education-settings-configure-ios.md).

#### <a name="support-for-managed-configuration-options-for-android-apps---621621---"></a>Compatibilidad con las opciones de configuración administradas para aplicaciones Android<!-- 621621 -->
Intune ahora puede configurar las aplicaciones Android de Play Store que admiten opciones de configuración administradas.  Esta característica permite a TI ver la lista de valores de configuración que admite una aplicación y proporciona una interfaz de usuario guiada y de primera clase que permite configurar esos valores.

#### <a name="new-android-policy-for-complex-pins---722069---"></a>Nueva directiva de Android para PIN complejos<!-- 722069 -->
Ahora puede establecer un tipo de [contraseña](../configuration/device-restrictions-android.md#password) obligatoria de complejo numérico en un perfil de dispositivo Android para dispositivos que ejecutan Android 5.0 y versiones posteriores.  Utilice esta opción para impedir que los usuarios de dispositivos creen un PIN que contenga números repetidos o consecutivos, como 1111 o 1234.

#### <a name="additional-support-for-android-for-work-devices"></a>Soporte adicional para dispositivos Android for Work
- **Administración de la configuración del perfil de trabajo y la contraseña**<!-- 612808 -->

  Esta nueva directiva de restricción de dispositivos Android for Work ahora permite administrar la configuración del perfil de trabajo y la contraseña en los dispositivos Android for Work que administre.

- **Permitir uso compartido de datos entre perfiles de trabajo y perfiles personales**<!-- 1045102 -->

Este perfil de restricción de dispositivos Android for Work ahora tiene opciones nuevas que le ayudarán a configurar el uso compartido de datos entre el perfil profesional y el perfil personal.

- **Restricción de las acciones de copiar y pegar entre perfiles profesionales y personales**<!-- 1046094 -->

  Un perfil de dispositivo personalizado para dispositivos Android for Work ahora permite restringir si se permiten las acciones de copiar y pegar entre aplicaciones profesionales y personales.

Para más información, consulte [Restricciones de dispositivos para Android for Work](../configuration/device-restrictions-android-for-work.md).

#### <a name="assign-lob-apps-to-ios-and-android-devices---1057568---"></a>Asignación de aplicaciones de LOB a dispositivos iOS y Android<!-- 1057568 -->
Ahora puede asignar aplicaciones de línea de negocio para [iOS](../apps/lob-apps-ios.md) (archivos .ipa) y [Android](../apps/lob-apps-android.md) (archivos .apk) a usuarios o dispositivos.


#### <a name="new-device-policies-for-ios---723774-723815-723826-723830---"></a>Nuevas directivas de dispositivo para iOS<!-- 723774, 723815, 723826, 723830 -->
- **Aplicaciones en la pantalla principal**: controla qué aplicaciones ven los usuarios en la [pantalla principal de sus dispositivos iOS](../configuration/ios-device-features-settings.md#home-screen-layout). Esta directiva cambia el diseño de la pantalla principal, pero no implementa ninguna aplicación.

- **Conexiones con dispositivos AirPrint**: controla a qué [dispositivos AirPrint](../configuration/ios-device-features-settings.md#airprint) (impresoras de red) se pueden conectar los usuarios finales de dispositivos iOS.

- **Conexiones con dispositivos AirPlay**: controla a qué [dispositivos AirPlay](../configuration/ios-device-features-settings.md) (como Apple TV) se pueden conectar los usuarios finales de dispositivos iOS.

- **Mensaje personalizado de la pantalla de bloqueo**: configurar un mensaje personalizado que verán los usuarios en la pantalla de bloqueo de sus dispositivos iOS y que reemplaza al mensaje predeterminado de esa pantalla. Para más información, consulte [Activación del modo perdido en dispositivos iOS](../remote-actions/device-lost-mode.md)

#### <a name="restrict-push-notifications-for-ios-apps---723767---"></a>Restricción de las notificaciones de inserción para aplicaciones iOS<!-- 723767 -->
En un perfil de restricción de dispositivos de Intune, ahora puede configurar los siguientes [ajustes de notificación](../configuration/ios-device-features-settings.md#app-notifications) para dispositivos iOS:

- Activar o desactivar totalmente la notificación para una aplicación especificada.
- Activar o desactivar la notificación en el centro de notificaciones para una aplicación especificada.
- Especificar el tipo de alerta como **None** (Ninguna), **Banner** (Mensaje emergente) o **Modal Alert** (Alerta modal).
- Especificar si se permiten los distintivos para esta aplicación.
- Especificar si se permiten los sonidos de notificaciones.

#### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously---737837---"></a>Configuración de aplicaciones iOS para que se ejecuten en el modo de aplicación única de forma autónoma<!-- 737837 -->
Puede usar un perfil de dispositivo de Intune para configurar dispositivos iOS de modo que ejecuten aplicaciones especificadas en [modo de aplicación única autónoma](../configuration/device-restrictions-ios.md#autonomous-single-app-mode-asam). Cuando se configura este modo y se ejecuta la aplicación, el dispositivo se bloquea para que solo pueda ejecutar esa aplicación. Un ejemplo es cuando se configura una aplicación que permite a los usuarios hacer un examen en el dispositivo. Cuando se completan las acciones de la aplicación, o quita esta directiva, el dispositivo vuelve a su estado normal.

#### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices---723765---"></a>Configuración de dominios de confianza para el correo electrónico y la exploración web en dispositivos iOS<!-- 723765 -->
Desde un perfil de restricción de dispositivos iOS, ahora puede configurar los [valores de dominio](../configuration/device-restrictions-ios.md#domains) siguientes:

- **Dominios de correo electrónico sin marcar**: los correos electrónicos que el usuario envía o recibe y no coinciden con los dominios que especifique aquí se marcarán como que no son de confianza.

- **Dominios web administrados**: los documentos que se descargan de las direcciones URL que especifique aquí se considerarán administrados (solo en Safari).  

- **Dominios de relleno automático de contraseña de Safari**: los usuarios pueden guardar en Safari las contraseñas solo de las direcciones URL que coincidan con los patrones que especifique aquí. Para usar esta opción, el dispositivo debe estar en modo supervisado y no estar configurado para varios usuarios. (iOS 9.3 y versiones posteriores)


#### <a name="vpp-apps-available-in-ios-company-portal---748782---"></a>Aplicaciones de PCV disponibles en el Portal de empresa de iOS<!-- 748782 -->
Ahora puede asignar aplicaciones de compras por volumen (PCV) de iOS como instalaciones **Disponibles** para usuarios finales. Los usuarios finales necesitarán una cuenta de Apple Store para instalar la aplicación.

#### <a name="synchronize-ebooks-from-apple-vpp-store---800878---"></a>Sincronización de libros electrónicos de la tienda de compras por volumen de Apple<!-- 800878 -->
Ahora puede [sincronizar los libros](../apps/vpp-apps-ios.md) que haya adquirido a través de la tienda del Programa de Compras por Volumen de Apple con Intune y asignarlos a los usuarios.

#### <a name="multi-user-management-for-samsung-knox-standard-devices---971988---"></a>Administración de varios usuarios para dispositivos Samsung Knox Standard<!-- 971988 -->
Intune es compatible ahora con dispositivos que ejecutan Samsung Knox Standard para la [administración de varios usuarios](../enrollment/android-enroll.md). Esto significa que los usuarios finales pueden iniciar y cerrar sesión en el dispositivo con sus credenciales de Azure Active Directory, y que el dispositivo se administra centralmente tanto si está en uso como si no.  Cuando los usuarios finales inician sesión, tienen acceso a las aplicaciones y se les aplican las directivas. Cuando los usuarios cierran sesión, se borran todos los datos de la aplicación.

#### <a name="additional-windows-device-restriction-settings---818566---"></a>Configuración adicional de restricción de dispositivos Windows<!-- 818566 -->
Hemos agregado compatibilidad con [opciones de configuración adicionales de restricción de dispositivos Windows](../configuration/device-restrictions-windows-10.md), como la compatibilidad adicional con el explorador Microsoft Edge, la personalización de la pantalla de bloqueo del dispositivo, las personalizaciones del menú Inicio, el papel tapiz del conjunto de búsqueda de Contenido destacado de Windows y la configuración de proxy.

#### <a name="multi-user-support-for-windows-10-creators-update---822547---"></a>Compatibilidad con varios usuarios para Windows 10 Creators Update<!-- 822547 -->
Hemos agregado compatibilidad para la [administración de varios usuarios](../enrollment/windows-enroll.md) en dispositivos que ejecutan Windows 10 Creators Update y están unidos al dominio de Azure Active Directory. Esto significa que cuando varios usuarios estándar inicien sesión en el dispositivo con sus credenciales de Azure AD, recibirán las aplicaciones y las directivas que se hayan asignado a sus nombres de usuario. Actualmente, los usuarios no puede usar Portal de empresa para escenarios de autoservicio, como la instalación de aplicaciones.

#### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start para equipos con Windows 10<!-- 1004830 -->
Ahora hay disponible una nueva [acción de dispositivo Fresh Start](../remote-actions/device-fresh-start.md) para equipos Windows 10.  Cuando se lleva a cabo esta acción, se quitan las aplicaciones que hubiera instaladas en el equipo y este se actualiza automáticamente a la versión más reciente de Windows. Esto puede servir para ayudar a quitar las aplicaciones de OEM preinstaladas que a menudo se entregan con los nuevos PC. Puede configurar si se conservan los datos de usuario cuando se lleva a cabo esta acción de dispositivo.

#### <a name="additional-windows-10-upgrade-paths---903672---"></a>Rutas de actualización adicionales de Windows 10<!-- 903672 -->
Ahora puede crear una [directiva de actualización de edición para actualizar los dispositivos](../configuration/edition-upgrade-configure-windows-10.md) a las siguientes ediciones adicionales de Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

#### <a name="bulk-enroll-windows-10-devices---747607---"></a>Inscripción masiva de dispositivos Windows 10<!-- 747607 -->
Ahora puede unir grandes cantidades de dispositivos que ejecutan Windows 10 Creator Update a Azure Active Directory e Intune con Windows Configuration Designer (WCD). Para habilitar la [inscripción masiva de MDM](../enrollment/windows-bulk-enroll.md) para el inquilino de Azure AD, cree un paquete de aprovisionamiento que una dispositivos al inquilino de Azure AD a través de Windows Configuration Designer y aplique el paquete a los dispositivos corporativos que desea inscribir y administrar de forma masiva. Una vez que el paquete se aplica a los dispositivos, se unirán a Azure AD, se inscribirán en Intune y estarán listos para que los usuarios de Azure AD inicien sesión.  Los usuarios de Azure AD son usuarios estándar en estos dispositivos y reciben las aplicaciones requeridas y las directivas asignadas. En este momento, no se admiten los escenarios de autoservicio ni de portal de empresa.

#### <a name="new-mam-settings-for-pin-and-managed-storage-locations---581122-736644---"></a>Nueva configuración de MAM para PIN y ubicaciones de almacenamiento administrado<!-- 581122, 736644 -->
Ahora hay disponibles dos nuevas opciones de configuración de aplicaciones que le ayudarán con los escenarios de administración de aplicaciones móviles (MAM):

- **Disable app PIN when device PIN is managed (Deshabilitar el PIN de aplicación cuando se administra el PIN del dispositivo)** : detecta si hay un PIN de dispositivo en el dispositivo inscrito y, si es así, omite el PIN de aplicación desencadenado por las directivas de protección de aplicaciones. Esta configuración permitirá reducir el número de veces que se muestra una solicitud de PIN a los usuarios que abran una aplicación habilitada para MAM en un dispositivo inscrito. Esta característica está disponible para iOS y Android.

- **Seleccione en qué servicios de almacenamiento se puede guardar datos empresariales**: permite especificar en qué ubicaciones de almacenamiento quiere guardar los datos corporativos. Los usuarios pueden guardar en los servicios de ubicación de almacenamiento seleccionados, lo que implica que se bloquearán todos los demás servicios de ubicación de almacenamiento no indicados.

  Lista de servicios de ubicación de almacenamiento compatibles:

  - OneDrive
  - OneDrive para la Empresa/SharePoint Online
  - Almacenamiento local

#### <a name="help-desk-troubleshooting-portal---907448---"></a>Portal de solución de problemas del departamento de soporte técnico<!-- 907448 -->
El nuevo [portal de solución de problemas](help-desk-operators.md) permite que los operadores del departamento de soporte técnico y los administradores de Intune vean a los usuarios y sus dispositivos y, además, realicen tareas para solucionar problemas técnicos de Intune.

<!-- ########################## -->
### <a name="march-2017"></a>Marzo de 2017

#### <a name="support-for-ios-lost-mode--431695--"></a>Compatibilidad con Modo Perdido de iOS<!--431695-->
En iOS 9.3 y dispositivos posteriores, Intune agrega compatibilidad con **Modo Perdido**. Ahora puede bloquear un dispositivo para evitar su uso, así como mostrar un mensaje y llamar al número de teléfono de la pantalla de bloqueo del dispositivo.

El usuario final no podrá desbloquear el dispositivo hasta que un administrador deshabilite Modo Perdido. Cuando está activado el Modo Perdido, puede usar la acción **Buscar dispositivo** para ver la ubicación geográfica del dispositivo en un mapa en la consola de Intune.

El dispositivo debe ser un dispositivo iOS de la empresa, inscrito mediante DEP, que esté en modo supervisado.

Para obtener más información, consulte [¿Qué es la administración de dispositivos de Microsoft Intune?](../remote-actions/device-management.md)

#### <a name="improvements-to-device-actions-report--677150--"></a>Mejoras en los informes de las acciones del dispositivo<!--677150-->
Hemos realizado mejoras en el informe de las acciones del dispositivo para mejorar el rendimiento. Además, ahora puede filtrar el informe por estado. Por ejemplo, puede filtrar el informe para mostrar únicamente las acciones de dispositivo que se han completado."

#### <a name="custom-app-categories--748805--"></a>Categorías de aplicaciones personalizadas<!--748805-->
Ahora puede crear, editar y asignar categorías a las aplicaciones que agregue a Intune. En estos momentos, las categorías solo pueden especificarse en inglés.
Consulte [How to add an app to Intune](../apps/apps-add.md) (Cómo agregar una aplicación a Intune).

#### <a name="assign-lob-apps-to-users-with-unenrolled-devices--748823--"></a>Asignación de aplicaciones de LOB a usuarios con dispositivos no inscritos<!--748823-->
Ahora puede asignar aplicaciones de línea de negocio desde la tienda a usuarios tengan o no inscritos sus dispositivos con Intune. Si el dispositivo de los usuarios no está inscrito con Intune, deben ir al sitio web del Portal de empresa para instalarlo, en lugar de a la aplicación del Portal de empresa.

#### <a name="new-compliance-reports--846671--"></a>Nuevos informes de cumplimiento<!--846671-->
Ahora dispone de informes de cumplimiento que proporcionan la posición de cumplimiento de los dispositivos de su empresa y le permiten solucionar rápidamente los problemas relacionados con el cumplimiento detectados por los usuarios. Puede ver información acerca de

- Estado de cumplimiento general de los dispositivos
- Estado de cumplimiento de una configuración individual
- Estado de cumplimiento de una directiva individual

También puede usar estos informes para profundizar en un dispositivo individual para ver la configuración específica y las directivas que afectan a dicho dispositivo.

<!-- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N -->

#### <a name="direct-access-to-apple-enrollment-scenarios--951869--"></a>Acceso directo a los escenarios de inscripción de Apple<!--951869-->
Para las cuentas de Intune creadas después de enero de 2017, Intune habilitó el acceso directo a los escenarios de inscripción de Apple mediante la carga de trabajo de inscripción de dispositivos en Azure Portal. Anteriormente, la vista preliminar de inscripción de Apple solo era accesible desde los vínculos de Azure Portal. Las cuentas de Intune creadas antes de enero de 2017 requerirán una migración única antes de que estas características estén disponibles en Azure. Aún no se ha anunciado la programación para la migración, pero pronto habrá detalles disponibles. Se recomienda encarecidamente crear una cuenta de prueba para probar la nueva experiencia si su cuenta no tiene acceso a la versión preliminar.


<!-- ########################## -->
### <a name="february-2017"></a>Febrero de 2017

#### <a name="ability-to-restrict-mobile-device-enrollment--747600-795782--"></a>Capacidad para restringir la inscripción de dispositivos móviles<!--747600, 795782-->
Intune está agregando nuevas restricciones de inscripción que controlan qué plataformas de dispositivos móviles pueden inscribir. Intune separa las plataformas de dispositivos móviles como iOS, Mac OS, Android, Windows y Windows Mobile.

- La restricción la inscripción de dispositivos móviles no restringe la inscripción del cliente de PC.  
- Solo para iOS y Android, hay una opción adicional para bloquear la inscripción de dispositivos de propiedad personal.

Intune marca todos los dispositivos nuevos como personal a menos que el administrador de TI tome la medida de marcarlos como propiedad de la empresa, como se explica en [este artículo](../enrollment/device-enrollment.md).

#### <a name="view-all-actions-on-managed-devices--677150--"></a>Visualización de todas las acciones en los dispositivos administrados<!--677150-->
Un nuevo informe __Acciones de dispositivo__ muestra quién ha realizado acciones remotas como el restablecimiento de fábrica en dispositivos y, además, muestra el estado de esa acción. Vea [¿Qué es la administración de dispositivos?](../remote-actions/device-management.md).

#### <a name="non-managed-devices-can-access-assigned-apps--664691--"></a>Los dispositivos no administrados pueden acceder a aplicaciones asignadas<!--664691-->
Como parte de los cambios de diseño en el sitio web del portal de empresa, los usuarios de iOS y Android podrán instalar aplicaciones asignadas a ellos como "disponibles sin inscripción" en sus dispositivos no administrados. Con sus credenciales de Intune, los usuarios podrán iniciar sesión en el sitio web del portal de empresa y ver la lista de aplicaciones asignadas. Los paquetes de aplicación de las aplicaciones "disponibles sin inscripción" se encuentran disponibles para descargar a través del sitio web del portal de empresa. Las aplicaciones que requieren la inscripción para la instalación no se ven afectadas por este cambio, ya que se les pedirá a los usuarios que inscriban su dispositivo si quieren instalar esas aplicaciones.

#### <a name="custom-app-categories--748805--"></a>Categorías de aplicaciones personalizadas<!--748805-->
Ahora puede crear, editar y asignar categorías a las aplicaciones que agregue a Intune. En estos momentos, las categorías solo pueden especificarse en inglés.
Consulte [How to add an app to Intune](../apps/apps-add.md) (Cómo agregar una aplicación a Intune).

#### <a name="display-device-categories--814654--"></a>Representación de categorías de dispositivos<!--814654-->
Ahora puede ver la categoría del dispositivo como una columna en la lista de dispositivos. También puede editar la categoría desde la sección de propiedades de la hoja de propiedades del dispositivo. Consulte [How to add an app to Intune](../apps/apps-add.md) (Cómo agregar una aplicación a Intune).

#### <a name="configure-windows-update-for-business-settings--776716--"></a>Configuración de Windows Update para empresas<!--776716-->

Windows como servicio es la nueva forma de proporcionar actualizaciones para Windows 10. A partir de Windows 10, todas las nuevas actualizaciones de calidad y características contienen las actualizaciones anteriores. Es decir, siempre que haya instalado la más reciente, sabrá que sus dispositivos Windows 10 están completamente actualizados. A diferencia de las versiones anteriores de Windows, ahora debe instalar la actualización completa en lugar de una parte.

Gracias a Windows Update para empresas, puede simplificar la administración de actualizaciones, ya que no tendrá que aprobar actualizaciones individuales para grupos de dispositivos. Todavía puede administrar los riesgos en sus entornos configurando una estrategia de implementación de actualizaciones; Windows Update se asegurará de que las actualizaciones se instalen en el momento oportuno. Microsoft Intune ofrece la posibilidad de configurar las actualizaciones en los dispositivos y de aplazar su instalación. Intune no almacena las actualizaciones, sino únicamente la asignación de las directivas de actualización. Los dispositivos acceden a Windows Update directamente para instalar las actualizaciones. Use Intune para configurar y administrar los **anillos de actualización de Windows 10**. Un anillo de actualización contiene un grupo de opciones que configuran cuándo y cómo se instalan las actualizaciones de Windows 10. Para obtener más información, consulte [Configuración de Windows Update para empresas](../protect/windows-update-for-business-configure.md).
