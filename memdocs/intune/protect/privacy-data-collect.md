---
title: Recopilación de datos en Intune
titleSuffix: Microsoft Intune
description: Obtenga más información sobre cómo se recopilan los datos personales en Intune.
keywords: privacy, personal data
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/01/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bcd7ff1ae51314bc57be2bed39c7fe8ca7114d82
ms.sourcegitcommit: e2deac196e5e79a183aaf8327b606055efcecc82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90076114"
---
# <a name="data-collection-in-intune"></a>Recopilación de datos en Intune

Cuando los usuarios inscriben sus dispositivos personales o corporativos mediante Intune, Intune recopila, procesa y comparte algunos datos personales para permitir las operaciones empresariales, realizar negocios con el cliente y respaldar el servicio. Intune recopila datos personales de los siguientes orígenes:

- El uso de Intune de los administradores en el Centro de administración de Microsoft Endpoint Manager.
- Dispositivos de usuario final (cuando los dispositivos se inscriben para la administración de Intune y durante el uso).
- Cuentas de clientes en servicios de terceros (según las instrucciones del administrador).
- Información de diagnóstico, rendimiento y uso.

A partir de estos orígenes, Intune recopila información que pertenece a las dos categorías siguientes: [requerida](#required-data) y [opcional](#optional-data). En cada una de las categorías, los datos se dividen además en datos del cliente, datos personales, datos de diagnóstico y datos generados por el servicio. 

> [!NOTE]
> No vendemos ningún dato recogido por nuestro servicio a terceros por ningún motivo.

## <a name="required-data"></a>Datos necesarios

Los datos de la categoría requerida constan de datos que son necesarios para que el servicio funcione según lo previsto por el cliente. La mayoría de los datos recopilados por Intune son datos requeridos. Estos datos están asociados a un usuario, dispositivo o aplicación, y son esenciales para la naturaleza de la administración. Los datos recopilados contienen datos personales y datos no personales. Los datos personales incluyen datos identificables, que pueden identificar directamente al usuario final, o datos seudonimizados con un identificador único generado por el sistema, que se usan para prestar a los usuarios el servicio empresarial y proporcionar datos de soporte técnico y datos de cuentas. Los datos no personales incluyen metadatos del sistema generados por el servicio e información de la organización o del inquilino. Intune también recopila datos de control de acceso para administrar el acceso a las funciones y roles administrativos mediante características como [Control de acceso basado en rol](../fundamentals/role-based-access-control.md).

Los datos requeridos recopilados por Intune pueden incluir, entre otros: 

- Información de usuario
  - Nombre del propietario o nombre para mostrar del usuario (el nombre registrado en Azure del usuario identificado por AzureUserID)
  - Nombre principal de usuario o dirección de correo electrónico
  - Número de teléfono
  - Identificador de usuario de terceros (como AppleID)
- Información de inventario de hardware
  - Nombre del dispositivo
  - Fabricante
  - Sistema operativo
  - Número de serie
  - Número IMEI.
  - Dirección IP
  - MacAddress Wi-Fi
  - ICCID
- Información de registro de auditoría, incluidos los datos sobre las siguientes actividades
  - Administración
  - Crear
  - Actualización (edición)
  - Eliminar
  - Asignar
  - Tareas remotas
- Información de soporte técnico
  - Información de contacto (nombre, número de teléfono, dirección de correo electrónico)
  - Conversaciones de correo electrónico miembros del equipo de experiencia del usuario, de producto o de soporte técnico de Microsoft
- Información de control de acceso 
  - Autenticadores estáticos (contraseña del cliente)
  - Claves de privacidad para los certificados 
- Información de cuenta y de administrador
  - Nombre y apellidos del usuario administrador
  - Nombre de usuario del administrador
  - UPN (correo electrónico)
  - Número de teléfono
  - Dirección de correo electrónico del propietario de la cuenta
  - Identificador de Active Directory de cada administrador de TI del cliente
  - Datos de facturación de los clientes de pago
  - Clave de suscripción
- Inventario de aplicaciones, como
  - nombre de la aplicación
  - Versión
  - identificador de la aplicación
  - tamaño
  - ubicación de instalación
  - Los datos de inventario de aplicaciones solo se recopilan cuando están marcados por el administrador como un dispositivo corporativo o si la característica de aplicación compatible está activada.  
- Identificadores de inquilino de terceros del cliente (como el identificador de Apple)
- Datos del dispositivo
  - Identificador de dispositivo de Intune.
  - Id. de dispositivo de Azure Active Directory
  - Id. de administración de dispositivos de Intune
  - Identificador de inquilino
  - Id. de cuenta
  - Id. del dispositivo EAS
  - Identificadores específicos de la plataforma
  - AppleID para dispositivos iOS/iPadOS
  - Dirección MAC para dispositivos Mac
  - Id. de Windows para dispositivos Windows
- Información de la aplicación administrada
  - Id. de la aplicación administrada
  - Etiqueta de dispositivo de la aplicación administrada
  - Id. de administración de dispositivos de Intune
  - Id. de dispositivo de Azure Active Directory
  - Claves de cifrado
- Datos de uso del administrador de todos los inquilinos de Intune (por ejemplo, los controles de administración seleccionados al interactuar con la consola de administración)
- Información de la cuenta de inquilino (estos datos están disponibles en la hoja de Intune)
  - Número de dispositivos o usuario inscritos
  - Número de plataformas de dispositivo identificadas  
  - Número de dispositivos instalados
  - installedDeviceCount: Número de dispositivos en los que está instalada la aplicación.
  - notApplicableDeviceCount: Número de dispositivos para los que la aplicación no está disponible.
  - notInstalledDeviceCount: Número de dispositivos para los que la aplicación está disponible, pero no está instalada.
  - pendingInstallDeviceCount: Número de dispositivos para los que la aplicación está disponible y la instalación está pendiente.

## <a name="optional-data"></a>Datos opcionales

Los datos de la categoría opcional no son esenciales para la experiencia del producto o servicio. Los clientes pueden controlar la recopilación de datos opcionales. Intune permite a los clientes incluirse o excluirse de la recopilación de datos opcionales. Entre los ejemplos de datos opcionales están los datos que Intune recopila para el diagnóstico y la telemetría. Aunque creemos que existen razones de peso para que los usuarios compartan estos datos opcionales, puesto que crean oportunidades para experiencias nuevas y enriquecidas, comprendemos la importancia de que sean los usuarios los que decidan hacerlo por sí mismos. 

Entre los ejemplos de datos de diagnóstico opcionales pueden incluirse los datos de uso de la aplicación, la información de errores y los datos de rendimiento. Todos los datos de diagnóstico que Microsoft recopila durante el uso de cualquier aplicación Microsoft 365 para aplicaciones y servicios empresariales se seudonimizan, tal y como se define en el estándar ISO/IEC 19944:2017 (sección 8.3.3).

## <a name="certain-end-user-data-or-content-is-never-collected"></a>Algunos datos o contenido de usuario final nunca se recopilan

Intune no recopila ni permite que un administrador vea el historial de llamadas o de exploración web de los usuarios finales, ni el correo electrónico personal, los mensajes de texto, los contactos, las contraseñas de cuentas personales, los eventos de calendario o las fotos, tanto las de aplicaciones de fotografía como las que proceden de una cámara de fotos. Consulte [Introducción a la inscripción de dispositivos](../enrollment/device-enrollment.md).

Consulte [Cómo categoriza Microsoft los datos para servicios online](https://www.microsoft.com/trust-center/privacy/customer-data-definitions) para más información sobre los tipos y la definición de datos. 

## <a name="next-steps"></a>Pasos siguientes

Obtenga más información sobre cómo Intune [almacena y procesa](privacy-data-store-process.md), y [comparte](privacy-data-secure-share.md) los datos personales. 
