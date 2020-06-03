---
title: Guía de pruebas del SDK de aplicaciones de Microsoft Intune para Android
description: La guía de pruebas de Microsoft Intune App SDK para Android le ayuda a probar su aplicación Android administrada por Intune.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/26/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6875dc873d44b77a24fe68f637d9329c9f5e1d9c
ms.sourcegitcommit: 118587ddb31ce26b27801839db9b3b59f1177f0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84165607"
---
# <a name="microsoft-intune-app-sdk-for-android-testing-guide"></a>Guía de pruebas del SDK de aplicaciones de Microsoft Intune para Android

Esta guía ayuda a los desarrolladores a probar sus aplicaciones Android administradas por Intune.  

## <a name="prerequisite-test-accounts"></a>Requisitos previos de cuentas de prueba
Puede crear cuentas con o sin datos generados previamente. Para crear una cuenta:
1. Vaya al sitio de [demostraciones de Microsoft](https://demos.microsoft.com/environments/create/tenant). 
2. [Configure Intune](../fundamentals/setup-steps.md) para habilitar la administración de dispositivos móviles (MDM).
3. [Cree usuarios](../fundamentals/users-add.md).
4. [Crear grupos](../fundamentals/groups-add.md).
5. [Asigne licencias](../fundamentals/licenses-assign.md) según corresponda para las pruebas.


## <a name="azure-portal-policy-configuration"></a>Configuración de directivas de Azure Portal
[Cree y asigne directivas de protección de aplicaciones](../apps/app-protection-policies.md) en la [hoja Intune de Azure Portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). También se puede crear y asignar la [directiva de configuración de aplicaciones](../apps/app-configuration-policies-overview.md) en la hoja Intune.

> [!NOTE]
> Si la aplicación no aparece en Azure Portal, puede seleccionarla como destino con una directiva seleccionando la opción de **más aplicaciones** y proporcionando el nombre del paquete en el cuadro de texto.

## <a name="test-cases"></a>Casos de prueba

En los siguientes casos de prueba se ofrecen los pasos de configuración y confirmación. Use esta guía como ayuda para la solución de problemas de aplicaciones Android administradas por Intune.

### <a name="required-pin-and-corporate-credentials"></a>Credenciales corporativas y PIN necesarios

Puede requerir un PIN para acceder a recursos corporativos. Además, puede exigir autenticación de la organización para que los usuarios pueden usar aplicaciones administradas. Le mostramos cómo:

1. Configure **Requerir PIN para acceder** y **Requerir credenciales corporativas para el acceso** en **Sí**. Para más información, vea [Configuración de directivas de protección de aplicaciones Android en Microsoft Intune](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Confirme las condiciones siguientes:
    - El inicio de la aplicación debe presentar una solicitud de entrada del PIN o el usuario de producción que se usó durante la inscripción en el Portal de empresa.
    - El hecho de no que no se presente una solicitud de inicio de sesión válida se podría deber a un manifiesto de Android configurado de forma incorrecta, en concreto los valores de integración de la Biblioteca de autenticación de Active Directory (ADAL) (SkipBroker, ClientID y Autoridad).
    - La falta de presentación de una solicitud puede deberse a un valor `MAMActivity` incorrectamente integrado. Para más información sobre `MAMActivity`, vea [Guía para desarrolladores de Android acerca del SDK para aplicaciones de Microsoft Intune](app-sdk-android.md).

> [!NOTE] 
> Si la prueba anterior no funciona, es probable que se produzcan errores en las siguientes. Revise la integración del [SDK](app-sdk-android.md#sdk-integration) y [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Restricción de la transferencia y recepción de datos con otras aplicaciones
Puede controlar la transferencia de datos entre aplicaciones administradas corporativas como sigue:

1. Establezca **Permitir a la aplicación transferir datos a otras aplicaciones** en **Aplicaciones administradas por directivas**.
2. Establezca **Permitir a la aplicación recibir datos de otras aplicaciones** en **Todas las aplicaciones**. El uso de intenciones y los proveedores de contenido resultan afectados por estas directivas.
3. Confirme las condiciones siguientes:
    - La apertura de una aplicación no administrada en la aplicación funciona correctamente.
    - Se permite el uso compartido de contenido entre aplicaciones administradas.
    - Se bloquea el uso compartido de aplicaciones administradas con aplicaciones no administradas (por ejemplo, Chrome).

### <a name="restrict-cut-copy-and-paste"></a>Limitar funciones Cortar, Copiar y Pegar
Puede restringir el Portapapeles del sistema a las aplicaciones administradas como sigue:

1. Establezca **Restringir cortar, copiar y pegar con otras aplicaciones** en **Aplicaciones administradas por directivas con pegar**.
2. Confirme las condiciones siguientes:
    - Se bloquea la copia de texto de la aplicación en una aplicación no administrada (por ejemplo, mensajes).

### <a name="prevent-save"></a>Impedir guardar
Puede controlar la funcionalidad de **Guardar como** como sigue:

1. Si la aplicación requiere [controles "Guardar como" integrados](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), establezca **Impedir "Guardar como"** en **Sí**.
2. Confirme las condiciones siguientes:
    - La operación de guardar se restringe únicamente a las ubicaciones administradas adecuadas.

### <a name="file-encryption"></a>Cifrado de archivos
Puede cifrar los datos en el dispositivo como sigue:

1. Establezca **Cifrar datos de aplicación** en **Sí**.
2. Confirme las condiciones siguientes:
    - El comportamiento normal de la aplicación no se ve afectado.

### <a name="prevent-android-backups"></a>Impedir copias de seguridad de Android
Puede controlar la copia de seguridad de aplicaciones como sigue:

1. Si ha establecido [restricciones de copia de seguridad integradas](app-sdk-android.md#protecting-backup-data), configure **Impedir copias de seguridad de Android** en **Sí**.
2. Confirme las condiciones siguientes:
    - Las copias de seguridad están restringidas.

### <a name="unenrollment"></a>Anulación de inscripciones
Puede borrar de forma remota las aplicaciones administradas que contengan correo electrónico y documentos corporativos, y los datos personales se descifran cuando ya no se administran. Le mostramos cómo:

1. Desde Azure Portal, [emita una acción de borrado](../apps/apps-selective-wipe.md).
2. Si la aplicación no se registra con los controladores de borrado, confirme las condiciones siguientes:
    - Se produce un borrado completo de la aplicación.
3. Si la aplicación se ha registrado con `WIPE_USER_DATA` o `WIPE_USER_AUXILARY_DATA`, confirme las condiciones siguientes:
    - El contenido administrado se quita de la aplicación. Para más información, vea [la sección de borrado selectivo de la guía para desarrolladores del SDK de aplicaciones de Intune para Android](app-sdk-android.md#selective-wipe).

### <a name="multi-identity-support"></a>Compatibilidad con varias identidades
La integración de [compatibilidad con varias identidades](app-sdk-android.md#multi-identity-optional) es un cambio de alto riesgo que deberá probarse detenidamente. Los problemas más comunes se deben a una configuración incorrecta de la identidad (contexto frente a nivel de amenaza) y al seguimiento de los archivos (`MAMFileProtectionManager`).

Como mínimo, confirme lo siguiente:

- La directiva **Guardar como** funciona correctamente para las identidades administradas.
- Las restricciones de copiar y pegar se aplican correctamente desde identidades administradas a personales.
- Solo se cifran los datos que pertenecen a la identidad administrada, y los archivos personales no se modifican.
- El borrado selectivo durante la anulación de inscripción solo quita los datos de identidad administrada.
- Al cambiar de una cuenta no administrada a una administrada (solo la primera vez), se le pide al usuario que la inicie de forma condicional.

### <a name="app-configuration-optional"></a>Configuración de aplicaciones (opcional)
Puede configurar el comportamiento de las aplicaciones administradas. Si la aplicación consume alguna opción de configuración de la aplicación, debe comprobar que esta controla correctamente todos los valores que (como administrador) puede establecer. En Intune puede crear y asignar [directivas de configuración de aplicaciones](../apps/app-configuration-policies-overview.md).

## <a name="next-steps"></a>Pasos siguientes

- [Incorporación de una aplicación de línea de negocio de Android a Microsoft Intune](../apps/lob-apps-android.md)
