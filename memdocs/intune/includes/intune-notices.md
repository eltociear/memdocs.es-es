---
title: archivo include
description: Archivo de inclusión
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 08/10/2020
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: e63bb965b8fed4c0266e359493bbfa67100862cb
ms.sourcegitcommit: f575b13789185d3ac1f7038f0729596348a3cf14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "90045122"
---
Estos avisos proporcionan información importante que puede ayudarle a prepararse para las características y los cambios futuros de Intune.

### <a name="updated-end-user-experience-for-android-device-administrator-wi-fi-profiles---7662680----"></a>Actualización de la experiencia del usuario final para perfiles de Wi-Fi de administrador de dispositivos Android<!-- 7662680  -->
Debido a un cambio realizado por Google, la experiencia del usuario final en nuevos perfiles de Wi-Fi es significativamente diferente a partir de la versión de octubre de la aplicación Portal de empresa. Los usuarios deberán aceptar permisos adicionales y aceptar explícitamente las configuraciones de Wi-Fi cuando se hayan implementado. Las configuraciones de Wi-Fi no aparecerán en la lista de redes Wi-Fi conocidas, pero se conectarán automáticamente cuando estén dentro del alcance. El comportamiento de los perfiles de Wi-Fi existentes no experimenta ningún cambio, ni tampoco la experiencia de administración en el centro de administración de Endpoint Manager.

Se aplica a:
- Administrador de dispositivos de Android, Android 10 y versiones posteriores

### <a name="microsoft-intune-ends-support-for-windows-phone-81-and-windows-10-mobile---3544938-3544909---"></a>Fin de la compatibilidad de Microsoft Intune con Windows Phone 8.1 y Windows 10 Mobile<!-- 3544938, 3544909 -->
El soporte estándar de Microsoft para Windows Phone 8.1 finalizó en julio de 2017 y el soporte ampliado en junio de 2019. La aplicación Portal de empresa para Windows Phone 8.1 está en modo de mantenimiento desde octubre de 2017. Además, Microsoft Intune ha finalizado el soporte técnico para Windows Phone 8.1 el 20 de febrero de 2020. 

El soporte técnico estándar de Microsoft para Windows 10 Mobile finalizó en diciembre de 2019. Como se ha mencionado en esta declaración de soporte técnico, los usuarios de Windows 10 Mobile dejarán de recibir de Microsoft nuevas actualizaciones de seguridad, revisiones no relacionadas con la seguridad, opciones gratuitas de soporte técnico asistido o actualizaciones de contenido técnico en línea. En función del soporte técnico general del sistema operativo Mobile, el 10 de agosto de 2020 Microsoft Intune finalizará el soporte técnico del Portal de empresa de la aplicación de Windows 10 Mobile y del sistema operativo Windows 10 Mobile.

A partir del 10 de agosto, se producirá un error en las inscripciones de los dispositivos Windows Phone 8.1 y Windows 10 Mobile, y se quitarán los tipos de perfil de Windows Mobile de la interfaz de usuario de Intune. Los dispositivos ya inscritos no se registrarán en el servicio de Intune y se eliminarán los datos de directivas y dispositivos.

### <a name="end-of-support-for-legacy-pc-management"></a>Fin de la compatibilidad con la administración heredada de equipos

La administración heredada de equipos dejará de ser compatible el 15 de octubre de 2020. Actualice los dispositivos a Windows 10 y vuelva a inscribirlos como dispositivos de administración de dispositivos móviles (MDM) para administrarlos por Intune.

[Más información](https://go.microsoft.com/fwlink/?linkid=2107122).

### <a name="move-to-the-microsoft-endpoint-manager-admin-center-for-all-your-intune-management"></a>Cambio al Centro de administración de Microsoft Endpoint Manager para toda la administración de Intune
En MC208118, publicado el pasado marzo, se presentó una nueva dirección URL sencilla para la administración de Intune en Microsoft Endpoint Manager: [https://endpoint.microsoft.com](https://endpoint.microsoft.com). Microsoft Endpoint Manager es una plataforma unificada que incluye Microsoft Intune y Configuration Manager. **A partir del 1 de agosto de 2020**, quitaremos la administración de Intune de [https://portal.azure.com](https://portal.azure.com). Recomendamos usar en su lugar [https://endpoint.microsoft.com](https://endpoint.microsoft.com) para toda la administración de puntos de conexión. 


### <a name="decreasing-support-for-android-device-administrator--7371518--"></a>Reducción de la compatibilidad con el administrador de dispositivos Android<!--7371518-->
La administración de administradores de dispositivos Android se incluyó en Android 2.2 como una manera de administrar dispositivos Android. A partir de Android 5, se incluyó el marco de administración más moderno de [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (para dispositivos que pueden establecer una conexión de confianza con Google Mobile Services). Para fomentar que se abandone la administración de administradores de dispositivos, Google está reduciendo la compatibilidad de administración en las nuevas versiones de Android.

#### <a name="how-does-this-affect-me"></a>¿Cómo me afecta esto?
Debido a estos cambios que ha introducido Google, en octubre de 2020, ya no dispondrá de funciones de administración tan amplias en los dispositivos administrados por el administrador de dispositivos que se han visto afectados. 

> [!NOTE]
> Inicialmente se comunicó que esto se produciría el cuarto trimestre de 2020, pero la fecha ha cambiado según la [información más reciente de Google](https://www.blog.google/products/android-enterprise/da-migration/).

##### <a name="device-types-that-will-be-impacted"></a>Tipos de dispositivos que se verán afectados
Los dispositivos que se verán afectados por la menor compatibilidad con el administrador de dispositivos son los que cumplen estas tres condiciones:
- Están inscritos en la administración de administradores de dispositivos.
- Ejecutan Android 10 o una versión posterior.
- Todos los fabricantes de dispositivos Android, excepto Samsung.

Los dispositivos con las características siguientes no se verán afectados:
- No están inscritos con la administración de administradores de dispositivos.
- Ejecutan una versión de Android anterior a Android 10.
- Son dispositivos Samsung. Los dispositivos Samsung Knox no se verán afectados en este período de tiempo porque el soporte extendido se proporciona a través de la integración de Intune con la plataforma Knox. Esto le proporciona un tiempo adicional para planear la transición desde la administración de administradores de dispositivos en el caso de los dispositivos Samsung.

##### <a name="settings-that-will-be-impacted"></a>Opciones de configuración que se verán afectadas
La [menor compatibilidad de Google con el administrador de dispositivos](https://developers.google.com/android/work/device-admin-deprecation) impide que la configuración de estas opciones se aplique a los dispositivos afectados.

###### <a name="configuration-profile-device-restriction-settings"></a>Configuración de restricciones del dispositivo en el perfil de configuración

- Bloquear la **Cámara**
- Establecer la **Longitud mínima de la contraseña**
- Establecer el **Número de errores de inicio de sesión antes de borrar el dispositivo** (no se aplicará a los dispositivos sin contraseña establecida, pero sí a los dispositivos con contraseña)
- Establecer los **Días hasta la expiración de la contraseña**
- Establecer el **Tipo de contraseña requerida**
- Establecer **Impedir la reutilización de contraseñas anteriores**
- Bloquear **Smart Lock y otros agentes de confianza**

###### <a name="compliance-policy-settings"></a>Configuración de directivas de cumplimiento

- Establecer el **Tipo de contraseña requerida**
- Establecer la **Longitud mínima de la contraseña**
- Establecer el **Número de días hasta que expire la contraseña**
- Establecer el **Número de contraseñas anteriores que no se pueden reutilizar**


![Captura de pantalla de la página de la directiva de cumplimiento de Android](../fundamentals/media/notices/android-compliance-settings.png)

#### <a name="user-experience-of-impacted-settings-on-impacted-devices"></a>Experiencia del usuario con relación a las opciones afectadas en los dispositivos afectados

Opciones de configuración afectadas:
- En el caso de los dispositivos inscritos que ya tenían aplicadas las opciones, se seguirán aplicando las opciones de configuración afectadas.
- En el caso de los dispositivos recién inscritos, las opciones de configuración recién asignadas y las opciones de configuración actualizadas, no se aplicarán las opciones afectadas (pero sí las demás).

Opciones de cumplimiento afectadas:
- En el caso de los dispositivos inscritos en los que ya se ha aplicado la configuración, las opciones de cumplimiento afectadas se seguirán mostrando como motivos de incumplimiento en la página "Actualizar configuración del dispositivo". El dispositivo no será compatible y los requisitos de contraseña se seguirán aplicando en la aplicación de configuración.
- En el caso de los dispositivos recién inscritos, las opciones de configuración recién asignadas y las opciones de configuración actualizadas, las opciones de cumplimiento afectadas se seguirán mostrando como motivos de incumplimiento en la página "Actualizar configuración del dispositivo". El dispositivo no será compatible, pero no se aplicarán requisitos de contraseña más estrictos en la aplicación de configuración.

Otro cambio en la experiencia del usuario para perfiles Wi-Fi:
- Los usuarios deberán aceptar permisos adicionales y aceptar explícitamente las configuraciones de Wi-Fi cuando se hayan implementado. Las configuraciones de Wi-Fi no aparecerán en la lista de redes Wi-Fi conocidas, pero se conectarán automáticamente cuando estén dentro del alcance. El comportamiento de los perfiles de Wi-Fi existentes no experimenta ningún cambio, ni tampoco la experiencia de administración en el centro de administración de Endpoint Manager.  

#### <a name="cause-of-impact"></a>Causa de la afectación 
Los dispositivos comenzarán a verse afectados en octubre de 2020. En ese momento, habrá una actualización de la aplicación Portal de empresa que aumentará el destino de la API de Portal de empresa del nivel 28 al 29 ([como requiere Google](https://www.blog.google/products/android-enterprise/da-migration/)). 

En ese momento, los dispositivos administrados por el administrador de dispositivos que no estén fabricados por Samsung se verán afectados una vez que el usuario lleve a cabo estas dos acciones:
- Actualizar a Android 10 o una versión posterior.
- Actualizar la aplicación Portal de empresa a la versión que tiene como destino la API de nivel 29.

#### <a name="additional-impacts-based-on-android-os-version"></a>Otras consecuencias en función de la versión del sistema operativo Android 
**Android 10**: en todos los dispositivos administrados por el administrador de dispositivos (incluidos los Samsung) que ejecutan Android 10 y versiones posteriores, Google ha restringido a los agentes de administración del administrador de dispositivos, como el Portal de empresa, el acceso a la información de identificación del dispositivo. Esta restricción afecta a las siguientes características de Intune después de que un dispositivo se actualice a Android 10 o una versión posterior: 
- El control de acceso a la red de VPN dejará de funcionar. 
- La identificación de los dispositivos como propiedad de la empresa con el número IMEI o el número de serie no marcará automáticamente los dispositivos como propiedad de la empresa. 
- El número IMEI y el número de serie ya no serán visibles para los administradores de TI en Intune. 

**Android 11**: estos son los cambios que afectarán al dispositivo administrado por el administrador de dispositivos cuando se actualice a Android 11: 
- En el caso de los dispositivos del administrador de dispositivos (excepto Samsung) que ejecutan Android 11 y versiones posteriores, Google quitó la capacidad de los agentes de administración como Portal de empresa de forzar el bloqueo de la cámara antes de que la aplicación de Portal de empresa se actualizara en octubre. Se seguirán aplicando las directivas de bloqueo de la cámara que se aplican a los dispositivos antes de que se actualicen a Android 11.  
- Con Android 11, ya no se pueden implementar certificados raíz de confianza en dispositivos inscritos con el administrador de dispositivos (excepto en dispositivos Android). Los usuarios deben instalar manualmente el certificado raíz de confianza en el dispositivo. Con el certificado raíz de confianza instalado manualmente en un dispositivo, puede usar SCEP para aprovisionar certificados en el dispositivo. En este caso, sigue teniendo que crear e implementar una directiva de certificado de confianza en el dispositivo y vincularla al perfil del certificado SCEP. 
    - Si el certificado raíz de confianza está en el dispositivo, el perfil de certificado SCEP se instalará correctamente.  
    - Si no se encuentra el certificado de confianza, se producirá un error en el perfil de certificado SCEP. 


#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararme para este cambio?
Para evitar la reducción de la funcionalidad que tendrá lugar en octubre de 2020, siga estas recomendaciones:
- **Nuevas inscripciones**: incorpore los nuevos dispositivos en la administración de [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (si está disponible) o en [directivas de protección de aplicaciones](../apps/app-protection-policies.md). Evite incorporar nuevos dispositivos a la administración de administradores de dispositivos. 
- **Dispositivos ya inscritos**: si un dispositivo administrado por el administrador de dispositivos ejecuta Android 10 o una versión posterior, o bien puede actualizarse a Android 10 o una versión posterior (especialmente si no es un dispositivo Samsung), cámbielo de la administración de administradores de dispositivos a la administración de [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) o a las [directivas de protección de aplicaciones](../apps/app-protection-policies.md). Puede aprovechar el flujo simplificado para [trasladar dispositivos Android del administrador de dispositivos a la administración de perfiles de trabajo](../enrollment/android-move-device-admin-work-profile.md).
- **Configuración de la complejidad de la contraseña**: en el caso de los dispositivos afectados que ejecuten Android 10 y versiones posteriores, podrá seguir aplicando las restricciones y el cumplimiento de las contraseñas en una configuración futura llamada Complejidad de la contraseña. Complejidad de la contraseña es una forma de medir la seguridad de la contraseña, que incluye el tipo, la longitud y la calidad de la contraseña.

#### <a name="what-if-i-have-non-samsung-devices-that-cannot-move-to-android-enterprise"></a>¿Qué ocurre si tengo dispositivos que no son de Samsung que no se pueden migrar a Android Enterprise? 
Algunos dispositivos no se pueden migrar del administrador de dispositivos a la administración de Android Enterprise. Por ejemplo, [Google no ha lanzado Android Enterprise en todos los mercados](https://support.google.com/work/android/answer/6270910?hl=en). Puede seguir usando Intune para administrar dispositivos que no son de Samsung con el administrador de dispositivos, pero se aplicarán los cambios en la funcionalidad mencionados en esta publicación. Para obtener instrucciones sobre la administración de dispositivos cuando Android Enterprise no está disponible, vea [Uso de Intune en entornos sin Google Mobile Services](../apps/manage-without-gms.md). 


#### <a name="additional-information"></a>Información adicional
- [Traslado de dispositivos Android del administrador de dispositivos a la administración de perfiles de trabajo](../enrollment/android-move-device-admin-work-profile.md)
- [Configuración de la inscripción de dispositivos del perfil de trabajo de Android Enterprise](../enrollment/android-work-profile-enroll.md)
- [Configuración de la inscripción de dispositivos dedicados de Android Enterprise](../enrollment/android-kiosk-enroll.md)
- [Configuración de la inscripción de dispositivos totalmente administrados de Android Enterprise](../enrollment/android-fully-managed-enroll.md)
- [Creación y asignación de directivas de protección de aplicaciones](../apps/app-protection-policies.md)
- [Uso de Intune en entornos sin Google Mobile Services](../apps/manage-without-gms.md)
- [Descripción de las directivas de protección de aplicaciones y los perfiles de trabajo en dispositivos de Android Enterprise](../apps/android-deployment-scenarios-app-protection-work-profiles.md)
- [Blog de Google dedicado a lo que necesita saber sobre el desuso del administrador de dispositivos](https://www.blog.google/products/android-enterprise/da-migration/)
- [Guía de Google para la migración desde el administrador de dispositivos a Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Documentación de Google sobre las API del administrador de dispositivos en desuso](https://developers.google.com/android/work/device-admin-deprecation)


### <a name="plan-for-change-intune-enrollment-flow-update-for-apples-automated-device-enrollment-for-iosipados"></a>Plan de cambio: actualización del flujo de inscripción de Intune para la inscripción de dispositivos automatizada de Apple para iOS/iPadOS
En la versión de julio del Portal de empresa, cambiaremos el flujo de inscripción de iOS/iPadOS para la inscripción de dispositivos automatizada de Apple (antes conocida como DEP). El cambio del flujo de inscripción solo se produce durante el flujo "Inscribir con afinidad de usuario". Anteriormente, si se establecía la opción "Instalar el Portal de empresa" en "No" como parte de la configuración, los usuarios todavía podían instalar la aplicación de Portal de empresa desde la tienda, lo que desencadenaba la inscripción, en la que el usuario agregaba en el número de serie adecuado. Con la próxima versión del Portal de empresa, quitaremos esta pantalla de confirmación del número de serie. Probablemente le interese crear una directiva de configuración de aplicaciones y enviarla junto con el Portal de empresa para asegurarse de que los usuarios puedan inscribirse correctamente, o bien prefiera establecer la opción "Instalar el Portal de empresa" en "Sí" como parte de la configuración. 
 - Vea la entrada publicada [aquí](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-enrollment-flow-update-for-apple-s-automated-device/ba-p/1431629) para obtener más información.
