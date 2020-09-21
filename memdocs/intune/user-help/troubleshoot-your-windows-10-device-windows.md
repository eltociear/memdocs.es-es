---
title: Solución de problemas de acceso de dispositivo Windows 10 a las cuentas profesionales o educativas | Microsoft Intune
description: Resuelva los problemas de acceso o conexión a las cuentas en dispositivos Windows 10 inscritos.
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
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope:
- User help
ROBOTS: ''
ms.reviewer: amanh
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 7c96bef7c1be004714f0b06dd47c9c28850118da
ms.sourcegitcommit: d4ed7b4369389fd8ab07d28a7fa507797b6c6e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89643434"
---
# <a name="troubleshoot-windows-10-device-access"></a>Solución de problemas de acceso de dispositivos Windows 10
En este artículo se describe cómo resolver los problemas de acceso de dispositivos Windows 10 inscritos. 

## <a name="check-wi-fi-connection"></a>Comprobación de la conexión Wi-Fi  

Se necesita una conexión Wi-Fi para acceder a recursos profesionales o educativos. Compruebe que está conectado a la red Wi-Fi y, luego, intente acceder de nuevo a los recursos.  

## <a name="add-work-or-school-account-in-settings-app"></a>Adición de una cuenta profesional o educativa en la aplicación de configuración  
Estos pasos son los mismos que se usarían para inscribir el dispositivo. Sin embargo, si la cuenta no aparece en **Configuración**, es necesario volver a ejecutar estos pasos.  

1. Abra la aplicación **Configuración**. 
2. Seleccione **Cuentas**.
3. El siguiente paso varía en función de la versión de Windows 10 que use. 
    * Versión 1607 y posteriores: Seleccione **Acceso profesional o educativo**.
    * Versión 1511 y anteriores: Seleccione **Acceso al trabajo**.  
4. Compruebe su cuenta. Si no aparece, seleccione el botón con el signo de más **Conectar** para agregarla. 
5. Inicie sesión con las credenciales de su trabajo o escuela. 
6. Para finalizar la conexión, siga las indicaciones en pantalla.  
7. Cuando haya finalizado, la cuenta se agregará como una conexión. Tendrá acceso a los recursos que la organización ponga a su disposición.   

## <a name="contact-it-support-for-access-requirements"></a>Contacto con el servicio de soporte técnico de TI para conocer los requisitos de acceso  
Si ve su cuenta profesional o educativa en la aplicación de configuración, el dispositivo y la cuenta ya están conectados. Póngase en contacto con el personal de soporte técnico de TI para que le ayude con los problemas de acceso. Puede que tengan restricciones o requisitos que impidan el acceso a determinados recursos.  

## <a name="error-messages"></a>Mensajes de error  

### <a name="we-couldnt-auto-discover-a-management-endpoint-matching-the-username-entered-please-check-your-username-and-try-again-if-you-know-the-url-to-your-management-endpoint-please-enter-it"></a>No pudimos detectar automáticamente un extremo de administración que coincida con el nombre de usuario escrito. Compruebe su nombre de usuario y vuelva a intentarlo. Si conoces la dirección URL para el extremo de administración, escríbela.

**Causa**: no se pudo comprobar la cuenta junto con la dirección URL proporcionada (que también se conoce como punto de conexión de administración).  

#### <a name="resolution"></a>Solución
1. Vuelva a escribir su nombre de usuario y contraseña. 
2. Si sigue sin funcionar, póngase en contacto con el personal de soporte técnico de TI para obtener la dirección URL correcta (por ejemplo, www.yourcompany.onmicrosoft.com). 
3. Cuando se le solicite, escriba la dirección URL proporcionada. 

### <a name="it-looks-like-youre-not-connected-make-sure-youre-connected-to-the-network"></a>It looks like you're not connected. Make sure you're connected to the network (Parece que no está conectado. Asegúrese de que está conectado a la red).

**Causa**: el dispositivo no está conectado a la red Wi-Fi y hace falta una conexión para agregar una cuenta profesional o educativa.     

#### <a name="resolution"></a>Solución
1. En la barra de herramientas o en la configuración del dispositivo, seleccione el icono de globo **Estado de red**.
2. Seleccione una red Wi-Fi > **Conectar**.  
3. Intente volver a conectar su cuenta.  


## <a name="next-steps"></a>Pasos siguientes  

¿Aún necesita ayuda? Póngase en contacto con el personal de soporte técnico de TI. Para averiguar su información de contacto, vaya al [sitio web del portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
