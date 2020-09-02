---
title: Información general sobre el ciclo de vida de MDM de Microsoft Intune
description: 'Obtenga información sobre cómo Intune le ayuda a administrar dispositivos a lo largo de su ciclo de vida: desde la inscripción hasta su posible retirada, pasando por la configuración.'
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 64e15e05ba7613b8bf2941d00a48c19292fafc90
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88909761"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Información general sobre el ciclo de vida de administración de dispositivos móviles (MDM) de Microsoft Intune

Todos los dispositivos que administra tienen un *ciclo de vida*. Intune puede ayudarle a administrar su ciclo de vida: desde la inscripción, pasando por la configuración y la protección, hasta la retirada del dispositivo cuando ya no resulte necesario. Por ejemplo, si la empresa compra un iPad, primero hay que inscribirlo con una cuenta de Microsoft Intune para que la empresa pueda administrarlo; después, debe configurarse para adaptarlo a las necesidades de la empresa; luego, hay que proteger los datos que el usuario almacena en el iPad; y por último, cuando ya no se necesite el iPad, habrá que [retirar o borrar](../remote-actions/devices-wipe.md) todos los datos confidenciales que contenga el dispositivo.

![Ciclo de vida del dispositivo](./media/device-lifecycle/device-lifecycle.png "Ciclo de vida del dispositivo Intune")

## <a name="enroll"></a>Inscribir

Las estrategias actuales de administración de dispositivos móviles (MDM) se aplican a diferentes teléfonos, tabletas y equipos (iOS/iPadOS, Android, Windows y Mac OS X). Si tiene que administrar el dispositivo, lo que suele ser el caso de los dispositivos corporativos, el primer paso es [configurar la inscripción del dispositivo](../enrollment/device-enrollment.md). También puede administrar equipos Windows si los inscribe con Intune (MDM) o [instala el software cliente de Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Configurar

La inscripción de los dispositivos es solo el primer paso. Para aprovechar todas las posibilidades que ofrece Intune y asegurarse de que los dispositivos sean seguros y conformes con los estándares de la empresa, puede elegir entre una amplia gama de directivas. Estas permiten configurar prácticamente todos los aspectos del funcionamiento de los dispositivos administrados. Por ejemplo, si los usuarios deben tener contraseñas en los dispositivos que contienen datos empresariales. Puede hacer que sea necesario disponer de una. ¿Tiene Wi-Fi corporativa? Puede configurarla automáticamente. Estos son los tipos de opciones de configuración disponibles:

- [**Configuración de dispositivos**](../configuration/device-profiles.md). Estas directivas permiten configurar las características y las funcionalidades de los dispositivos administrados. Por ejemplo, se podría exigir el uso de una contraseña en teléfonos Android o deshabilitar el uso de la cámara en dispositivos iPhone.
- [**Acceso a los recursos de la empresa**](../configuration/device-profiles.md). El hecho de permitir a los usuarios acceder al trabajo desde sus dispositivos personales puede plantear retos. Por ejemplo, ¿cómo se garantiza que todos los dispositivos que necesitan acceder al correo electrónico de la empresa estén configurados correctamente? ¿Cómo se puede garantizar que los usuarios puedan tener acceso a la red corporativa con una conexión VPN si no conocen valores complejos? Intune puede ayudar a reducir esta carga; para conseguirlo, configura automáticamente los dispositivos administrados para acceder a recursos comunes de la empresa.
- [**Directivas de administración de equipos Windows (con el software cliente de Intune)** ](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Aunque la inscripción de los equipos Windows con Intune ofrece el máximo de funcionalidades de administración de dispositivos, Intune sigue siendo compatible con la administración de equipos Windows con el software cliente de Intune. Si necesita información sobre algunas de las tareas que puede realizar con los equipos, empiece aquí.

## <a name="protect"></a>Protección

En el actual sector de las TI, la protección de los dispositivos frente al acceso no autorizado es una de las tareas más importantes que se realizan. Además de los elementos del paso **Configurar** del ciclo de vida del dispositivo, Intune proporciona más funcionalidades que ayudan a proteger los dispositivos que se administran frente al acceso no autorizado o a los ataques malintencionados:

- [**Autenticación multifactor**](../enrollment/multi-factor-authentication.md). La presencia de una capa adicional de autenticación para inicios de sesión de usuario puede ayudar a proteger aún más los dispositivos. Muchos dispositivos admiten la autenticación multifactor, que exige un segundo nivel de autenticación, como una llamada de teléfono o un mensaje de texto, para que los usuarios puedan acceder.
- [**Configuración de Windows Hello para empresas**](../protect/windows-hello.md). Windows Hello para empresas es un método alternativo de inicio de sesión que permite a los usuarios usar un *gesto*, como una huella digital o Windows Hello, para iniciar sesión sin necesidad de una contraseña.
- [**Directivas para proteger equipos Windows (con el software cliente de Intune)** ](policies-to-protect-windows-pcs-in-microsoft-intune.md). Al administrar equipos Windows con el software cliente de Intune, hay disponibles directivas que permiten controlar la configuración de Endpoint Protection, de las actualizaciones de software y de Firewall de Windows en los equipos que administra.

## <a name="retire"></a>Retirar

Cuando un dispositivo se pierde o es robado, cuando es necesario reemplazarlo o cuando el usuario cambia de cargo en la empresa, suele ser necesario [retirar o borrar](../remote-actions/device-management.md) el dispositivo. Hay varias maneras de hacerlo, como restablecer el dispositivo, quitarlo de la administración o borrar los datos corporativos que contiene.

## <a name="next-steps"></a>Pasos siguientes

- Obtenga información sobre la [administración de dispositivos de Microsoft Intune](../remote-actions/device-management.md)