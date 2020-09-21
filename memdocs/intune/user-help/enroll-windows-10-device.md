---
title: Inscribir dispositivos Windows 10 en Portal de empresa de Intune | Microsoft Docs
description: Pasos para inscribir dispositivos Windows 10 en Portal de empresa de Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/09/2020
ms.topic: end-user-help
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: amanh
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 46f8d7d46e376d2fb8f1cab1b3d0b3bc583bdeed
ms.sourcegitcommit: d4ed7b4369389fd8ab07d28a7fa507797b6c6e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89643500"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Inscribir dispositivos Windows 10 en Portal de empresa de Intune

Use Portal de empresa de Intune para inscribir un dispositivo Windows 10 administrado por la organización. En este artículo se explica cómo inscribir dispositivos con la versión 1607 y posteriores y la versión 1511 y anteriores de Windows 10. Antes de comenzar, asegúrese de [comprobar la versión del dispositivo](windows-enrollment-company-portal.md#find-windows-10-version-number) para poder seguir los pasos correctos.  

Windows 10 es compatible con distintos tipos de dispositivos, incluidos equipos de escritorio, teléfonos y tabletas. Los pasos de inscripción son los mismos sea cual sea el dispositivo que use, aunque la pantalla puede variar un poco con respecto a las imágenes mostradas en este artículo.  
</br>
> [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Inscribir un dispositivo de la versión 1607 y posteriores de Windows 10 
Estos pasos explican cómo inscribir un dispositivo con Windows 10, versión 1607 y posteriores.  

1. Vaya a **Inicio**. 

2. Abra la aplicación **Configuración**. Si la aplicación no está disponible en la lista de aplicaciones, vaya a la barra de búsqueda y escriba "configuración".

3. Seleccione **Cuentas** > **Obtener acceso a trabajo o escuela** > **Conectar**.  


    ![Seleccionar cuenta Obtener acceso a trabajo o escuela](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Para ir a la página de inicio de sesión de Intune de su organización, escriba su dirección de correo electrónico profesional o educativa. A continuación, seleccione **Siguiente**.  


   ![Escriba su cuenta profesional o educativa](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Inicie sesión en Intune con su cuenta profesional o educativa.  


    ![Agregar una cuenta profesional o educativa](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Al final verá un mensaje en el que se indica que la empresa o escuela están registradas en el dispositivo.

6. Si la organización exige que configure un PIN para Windows Hello, se le pide que escriba un código de verificación. Escriba el código y continúe con los pasos en pantalla para crear un PIN.  

7. En la pantalla **Todo listo** , seleccione **Listo**. El dispositivo ya está inscrito.  

8. Para volver a comprobar la conexión, vuelva a **Configuración** > **Cuentas** > **Obtener acceso a trabajo o escuela**.  Ahora debe aparecer la cuenta.  


## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Inscribir un dispositivo de la versión 1511 y anteriores de Windows 10  
Estos pasos explican cómo inscribir un dispositivo con Windows 10, versión 1511 y anteriores.  

1. Vaya a **Inicio**. 

2. Abra la aplicación **Configuración**. Si la aplicación no está disponible en la lista de aplicaciones, vaya a la barra de búsqueda y escriba "configuración".

3. Seleccione **Cuentas** > **Su cuenta**.  


    ![Seleccionar la cuenta](./media/W10-enroll-2-accounts-your-account.png)  

5. Seleccione **Agregar una cuenta profesional o educativa**.  


    ![Seleccionar agregar una cuenta profesional o educativa](./media/w10-enroll-3-add-work-school-acct.png)  

6. Inicie sesión con las credenciales de su trabajo o escuela.  


    ![Iniciar sesión](./media/W10-enroll-4-sign-in.png)  


## <a name="troubleshooting"></a>Solución de problemas 
Puede encontrar una lista no exhaustiva de mensajes de error y otras soluciones de conexión en [Solución de problemas de acceso de dispositivos Windows 10](troubleshoot-your-windows-10-device-windows.md).  


## <a name="it-administrator-support"></a>Soporte técnico para administradores de TI   

Si es administrador de TI y detecta problemas al inscribir dispositivos, vea [Solucionar problemas de inscripción de dispositivos de Windows de Microsoft Intune](https://support.microsoft.com/help/4469913). En este artículo se enumeran errores habituales, sus causas y los pasos para resolverlos. 

## <a name="next-steps"></a>Pasos siguientes  
Si necesita ayuda con la inscripción o Portal de empresa, póngase en contacto con el equipo de soporte técnico de TI de la organización. Puede encontrar la información de contacto en el [sitio web Portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980). Inicie sesión en el sitio con la cuenta profesional o educativa.  

 

