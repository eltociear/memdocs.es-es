---
title: Quitar un dispositivo de la administración si ha rechazado los términos de uso | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: end-user-help
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 59a257dd51ef08079d1cd563f5d645f5017a55d3
ms.sourcegitcommit: a77ba49424803fddcaf23326f1befbc004e48ac9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83881637"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Quitar un dispositivo de la administración si ha rechazado los "términos de uso"

Si rechazó los términos de uso al intentar iniciar sesión en la aplicación Portal de empresa, se le impedirá iniciar sesión en dicha aplicación en futuros intentos, por lo que necesita seguir estas instrucciones alternativas para quitar el dispositivo de Intune.

Cuando se desinstala la aplicación Portal de empresa, también se quita el dispositivo de Intune. El dispositivo ya no puede acceder a los recursos de la empresa. Para obtener más información sobre lo que ocurre cuando se deja de administrar un dispositivo, vea [¿Qué ocurre cuando se anula la inscripción de un dispositivo de Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

Para poder desinstalar la aplicación Portal de empresa, debe ir a la opción **Administradores de dispositivos** y desactivar **Portal de empresa**. Los pasos pueden ser algo distintos, en función del dispositivo Android que tenga.

## <a name="removing-the-device-from-the-company-portal-app"></a>Quitar un dispositivo de la aplicación Portal de empresa

Para quitar un dispositivo de Intune y desinstalar la aplicación Portal de empresa:

1. Vaya a **Configuración** &gt; **Seguridad &amp; Bloqueo de pantalla** &gt; **Administradores de dispositivos**.

    Al completar este se anula la inscripción del dispositivo de forma inmediata.

2. Desactive el **Portal de empresa** o la casilla situada a su lado.

    Ahora puede desinstalar la aplicación Portal de empresa.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Eliminación de datos recopilados por la aplicación Portal de empresa

Para quitar todos los datos que la aplicación Portal de empresa para Android almacena en el dispositivo:

- Para borrar los datos de la aplicación, vaya a Aplicaciones, haga clic en la aplicación y luego en el botón "Borrar datos".
- Elimine la carpeta "\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal".


¿Aún necesita ayuda? Póngase en contacto con el equipo de soporte técnico de su empresa (visite el [sitio web del Portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obtener la información de contacto), o escriba al <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">equipo de Microsoft Android</a>.
