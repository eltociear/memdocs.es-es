---
title: Preparación de aplicaciones para la administración de aplicaciones móviles con Microsoft Intune
description: La información de este tema le ayuda a decidir cuándo se debe usar la herramienta de ajuste de aplicaciones y el SDK de aplicaciones para permitir que las aplicaciones personalizadas de línea de negocio usen las directivas de administración de aplicaciones móviles.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/27/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 739ebebe18628279e5242ab227cf0f43993eff08
ms.sourcegitcommit: 42a4a4454e56fa681f0ad39f5e585492dfbad286
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84330872"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>Preparar aplicaciones de línea de negocio para las directivas de protección de aplicaciones

Puede habilitar las aplicaciones para que usen directivas de protección de aplicaciones mediante la herramienta de ajuste de aplicaciones de Intune o el SDK para aplicaciones de Intune. Use esta información para conocer sobre estos dos métodos y cuándo usarlos.

## <a name="intune-app-wrapping-tool"></a>Herramienta de ajuste de aplicaciones de Intune

La Herramienta de ajuste de aplicaciones se usa principalmente para aplicaciones **internas** de línea de negocio (LOB). Esta herramienta es una aplicación de línea de comandos que crea un contenedor en torno a la aplicación que luego permite administrarla mediante una directiva de protección de aplicaciones de Intune. Al proteger una aplicación proporcionada por un fabricante de software independiente, es importante aclarar si este proveedor seguirá admitiendo la aplicación ajustada.

No se necesita el código fuente para usar la herramienta, pero se necesitan credenciales de firma. Para obtener más información sobre las credenciales de firma, vea el [blog de Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Para obtener documentación sobre la herramienta de ajuste de aplicaciones, consulte [Herramienta de ajuste de aplicaciones para Android](app-wrapper-prepare-android.md) y [Herramienta de ajuste de aplicaciones para iOS](app-wrapper-prepare-ios.md).

La herramienta de ajuste de aplicaciones **no** admite aplicaciones de App Store de Apple ni de Google Play Store. Tampoco admite ciertas características que requieren la integración del desarrollador (consulte la siguiente tabla de comparación de características).

Para obtener más información sobre la herramienta de ajuste de aplicaciones para directivas de protección de aplicaciones en dispositivos que no están inscritos en Intune, consulte [Proteger aplicaciones y datos de línea de negocio en dispositivos no inscritos en Microsoft Intune](../apps/apps-add.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Razones para usar la herramienta de ajuste de aplicaciones

* La aplicación no tiene funciones de protección de datos integradas.
* La aplicación se implementa internamente.
* No tiene acceso al código fuente de la aplicación
* No ha desarrollado la aplicación.
* La aplicación tiene experiencias de autenticación de usuario mínimas.

### <a name="supported-app-development-platforms"></a>Plataformas de desarrollo de aplicaciones compatibles

|**Herramienta de ajuste de aplicaciones** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Sí|Sí|
|**Android**|No: usar [Xamarin Bindings del SDK de aplicaciones de Intune](app-sdk-xamarin.md).|Sí|

## <a name="intune-app-sdk"></a>SDK para aplicaciones de Intune

El SDK de aplicaciones está diseñado principalmente para clientes que tienen aplicaciones en App Store de Apple o Google Play Store y quieren administrar las aplicaciones con Intune. Pero cualquier aplicación puede aprovechar la integración del SDK, incluso las aplicaciones de línea de negocio.

Para obtener más información sobre el SDK, consulte la [Introducción](app-sdk.md). Para empezar a usar el SDK, consulte [Introducción al SDK para aplicaciones de Microsoft Intune](app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>Razones para usar el SDK

* La aplicación no tiene funciones de protección de datos integradas.
* La aplicación se implementa en una tienda de aplicaciones pública como Google Play o el App Store de Apple.
* Es un desarrollador de aplicaciones y tiene la experiencia técnica para usar el SDK.
* La aplicación tiene otras integraciones de SDK.
* La aplicación se actualiza con frecuencia.

### <a name="supported-app-development-platforms"></a>Plataformas de desarrollo de aplicaciones compatibles

|**SDK de aplicaciones de Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Sí: usar [Xamarin Bindings del SDK de aplicaciones de Intune](app-sdk-xamarin.md).|No|
|**Android**| Sí: usar [Xamarin Bindings del SDK de aplicaciones de Intune](app-sdk-xamarin.md).|No|

## <a name="not-using-an-app-development-platform-listed-above"></a>¿No usa una plataforma de desarrollo de aplicaciones de entre las indicadas arriba?

El equipo de desarrollo del SDK de Intune comprueba y mantiene de forma activa la compatibilidad con las aplicaciones creadas con las plataformas nativas de Android, iOS (Obj-C, Swift), Xamarin y Xamarin.Forms. Aunque algunos clientes han podido integrar con éxito el SDK de Intune con otras plataformas como React Native y NativeScript, no proporcionamos instrucciones explícitas o complementos para desarrolladores de aplicaciones que no utilicen nuestras plataformas compatibles. 

## <a name="feature-comparison"></a>Comparación de características

En esta tabla se indican los valores que se habilitan si una aplicación usa App SDK o App Wrapping Tool. Algunas características exigen que los desarrolladores de aplicaciones apliquen cierta lógica fuera de la integración básica con Intune SDK y, por eso, no se habilitan si la aplicación usa App Wrapping Tool. 

|Característica|SDK para aplicaciones|Herramienta de ajuste de aplicaciones|
|-----------|---------------------|-----------|
|Restringir contenido web para mostrar en un explorador administrado corporativo|X|X|
|Impedir copias de seguridad de Android, iTunes o iCloud|X|X|
|Permitir que la aplicación transfiera datos a otras aplicaciones|X|X|
|Permitir que la aplicación reciba datos de otras aplicaciones|X|X|
|Restringir cortar, copiar y pegar con otras aplicaciones|X|X|
|Especifique el número de caracteres que se pueden cortar o copiar de una aplicación administrada|X|X|
|Requerir PIN simple en acceso|X|X|
|Especificar el número de intentos antes de restablecer el PIN|X|X|
|Permitir desbloqueo mediante huellas digitales en lugar de mediante PIN|X|X|
|Permitir el reconocimiento facial en lugar de PIN (solo iOS)|X|X|
|Requerir credenciales corporativas en acceso|X|X|
|Establecer una expiración de PIN|X|X|
|Bloquear la ejecución de aplicaciones administradas en dispositivos liberados o modificados|X|X|
|Cifrar datos de aplicación|X|X|
|Volver a comprobar los requisitos de acceso tras un número especificado de minutos|X|X|
|Especificar el período de gracia sin conexión|X|X|
|Bloquear captura de pantalla (solo Android)|X|X|
|Compatibilidad con MAM sin la inscripción de dispositivos|X|X|
|Borrado completo de datos de aplicaciones|X|X|
|Borrado selectivo de datos profesionales y educativos en escenarios de varias identidades <br><br>**Nota:** Para iOS/iPadOS, cuando se quita el perfil de administración, también se quita la aplicación.|X||
|Impedir "Guardar como"|X||
|Configuración de aplicación de destino (o configuración de aplicación a través del "canal de MAM")|X|X|
|Compatibilidad con aplicaciones de identidades múltiples|X||
|Estilo personalizable |X|||
|Conexiones VPN de aplicación a petición con Citrix mVPN|X|X| 
|Deshabilitar la sincronización de contactos|X|X|
|Deshabilitar la impresión|X|X|
|Requerir la versión mínima de la aplicación|X|X|
|Requiere el sistema operativo mínimo|X|X|
|Requerir la versión mínima de la revisión de seguridad de Android (solo Android)|X|X|
|Requerir el SDK de Intune mínimo para iOS (solo iOS)|X|X|
|Atestación de dispositivo SafetyNet (solo Android)|X|X|
|Examen de amenazas en las aplicaciones (solo Android)|X|X|
|Requerir nivel de riesgo máximo del dispositivo del proveedor de Mobile Threat Defense|X||
|Configuración del contenido de las notificaciones de una aplicación para las cuentas de organización|X|X|
|Requerir uso de teclados aprobados (solo Android)|X|X|
|Requerir directiva de protección de aplicaciones (acceso condicional)|X||

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre las directivas de protección de aplicaciones y Intune, consulte los temas siguientes:

- [Herramienta de ajuste de aplicaciones para Android](app-wrapper-prepare-android.md)<br>
- [Herramienta de ajuste de aplicaciones para iOS](app-wrapper-prepare-ios.md)<br>
- [Usar el SDK para habilitar aplicaciones para la administración de aplicaciones móviles)](app-sdk.md)
