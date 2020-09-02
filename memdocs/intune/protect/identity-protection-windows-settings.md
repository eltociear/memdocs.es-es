---
title: 'Configuración de Windows Hello para empresas en Microsoft Intune: Azure | Microsoft Docs'
description: Consulte una lista de todas las opciones de configuración de PIN, biometría y protección contra suplantación de identidad en un perfil de protección de identidad para usar y configurar Windows Hello para empresas en dispositivos Windows 10 en Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: ce4795dd060d29b62887fbf5496b2f2706ba954f
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88909115"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Configuración de dispositivos Windows 10 para habilitar Windows Hello para empresas en Intune

En este artículo se enumeran y describen las opciones de configuración de Windows Hello para empresas que puede controlar en los dispositivos Windows 10 en Intune. Como administrador de Intune, puede configurar estas opciones y asignarlas a dispositivos Windows 10 como parte de la solución de administración de dispositivos móviles (MDM). 

Puede encontrar información adicional sobre estas opciones en [Configuración de las directivas de Windows Hello para empresas](/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings), en la documentación de Windows Hello.


Para más información sobre los perfiles de Windows Hello para empresas en Intune, consulte la [configuración de protección de identidad](identity-protection-configure.md).

## <a name="before-you-begin"></a>Antes de comenzar

[Cree un perfil de configuración](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello para empresas
- **Configurar Windows Hello para empresas**:
  - **Sin configurar**: seleccione esta opción si no quiere usar Intune para controlar la configuración de Windows Hello para empresas. No se cambiará ninguna de las opciones de configuración de Windows Hello para empresas en los dispositivos Windows 10. Todas las demás configuraciones del panel no están disponibles.

  - **Deshabilitado**: si no quiere usar Windows Hello para empresas, seleccione esta opción. De esta manera, todas las demás configuraciones en pantalla se deshabilitan.
  - **Habilitado**: seleccione esta opción si quiere configurar Windows Hello para empresas.  
  
  **Valor predeterminado**: No configurado

  Cuando se establece en *Habilitado*, están disponibles las opciones siguientes:

  - **Longitud mínima del PIN**  
    Especifique una longitud de PIN mínima para los dispositivos, con el fin de ayudar a proteger la información de inicio de sesión. Los valores predeterminados de los dispositivos Windows son de seis caracteres, pero esta opción puede aplicar un mínimo de 4 a 127 caracteres. 

    **Valor predeterminado**: *No configurado*.

  - **Longitud máxima del PIN**  
  Especifique una longitud de PIN máxima para los dispositivos, con el fin de ayudar a proteger la información de inicio de sesión. Los valores predeterminados de los dispositivos Windows son de seis caracteres, pero esta opción puede aplicar un mínimo de 4 a 127 caracteres.  

    **Valor predeterminado**: *No configurado*.  

  - **Letras minúsculas en el PIN**  
    puede exigir un PIN más seguro solicitando a los usuarios finales que incluyan letras minúsculas. Las opciones son:

    - **No permitido**: impide que los usuarios usen minúsculas en el PIN. Este comportamiento también se produce si el valor de configuración no está configurado.
    - **Permitido**: esta opción permite a los usuarios usar letras minúsculas en el PIN, pero no es obligatorio.
    - **Requerido**: los usuarios deben incluir al menos una letra minúscula en el PIN. Por ejemplo, una práctica habitual consiste en obligar a usar como mínimo una mayúscula y un carácter especial.

  - **Letras mayúsculas en el PIN**  
    puede exigir un PIN más seguro solicitando a los usuarios finales que incluyan letras mayúsculas. Las opciones son:

    - **No permitido**: impide que los usuarios usen mayúsculas en el PIN. Este comportamiento también se produce si el valor de configuración no está configurado.
    - **Permitido**: esta opción permite a los usuarios utilizar letras mayúsculas en el PIN, pero no es obligatorio.
    - **Requerido**: los usuarios deben incluir al menos una letra mayúscula en el PIN. Por ejemplo, una práctica habitual consiste en obligar a usar como mínimo una mayúscula y un carácter especial.

  - **Caracteres especiales en el PIN**  
    puede exigir un PIN más seguro solicitando a los usuarios finales que incluyan caracteres especiales. Entre los caracteres especiales se incluyen los siguientes: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  

    Las opciones son:
    - **No permitido**: impide que los usuarios usen caracteres especiales en el PIN. Este comportamiento también se produce si el valor de configuración no está configurado.
    - **Permitido**: esta opción permite a los usuarios utilizar letras mayúsculas en el PIN, pero no es obligatorio.
    - **Requerido**: los usuarios deben incluir al menos una letra mayúscula en el PIN. Por ejemplo, una práctica habitual consiste en obligar a usar como mínimo una mayúscula y un carácter especial.

    **Valor predeterminado**: No permitido

  - **Expiración del PIN (días)**  
    Se recomienda especificar un período de expiración del PIN, transcurrido el cual hay que cambiarlo. El valor predeterminado de los dispositivos Windows es de 41 días.

    **Valor predeterminado**: No configurado

  - **Recordar historial de PIN**  
    Restringe la reutilización de los PIN usados anteriormente. Los dispositivos Windows tienen como valor predeterminado impedir la reutilización de los cinco últimos PIN.  

    **Valor predeterminado**: No configurado  

  - **Habilitar la recuperación del PIN**   
    Permite al usuario usar el servicio de recuperación de PIN de Windows Hello para empresas. 
    
    - **Habilitado**: el secreto de recuperación del PIN se almacena en el dispositivo y el usuario puede cambiar su PIN si es necesario.  
    - **Deshabilitado**: no se crea ni se almacena un secreto de recuperación del PIN.

    **Valor predeterminado**: No configurado

  - **Usar un Módulo de plataforma segura (TPM)**    
    Un chip de TPM ofrece una capa adicional de seguridad de datos.  

    - **Habilitado**: solo los dispositivos con un TPM accesible pueden aprovisionar Windows Hello para empresas.
    - **Sin configurar**: los dispositivos intentan primero usar un TPM. Si no está disponible, pueden usar el cifrado de software.
    
    **Valor predeterminado**: No configurado

  - **Permitir autenticación biométrica**  
     Habilita la autenticación biométrica, como el reconocimiento facial o la huella digital, como alternativa a un PIN para Windows Hello para empresas. Los usuarios todavía deben configurar un PIN de trabajo por si produce un error en la autenticación biométrica. Elija de entre las siguientes opciones:

    - **Habilitar**: Windows Hello para empresas permite la autenticación biométrica.
    - **Sin configurar**: Windows Hello para empresas impide la autenticación biométrica (para todos los tipos de cuenta).

    **Valor predeterminado**: No configurado

  - **Usar tecnología mejorada contra la suplantación de identidad, cuando esté disponible**  
    Establece si se van a usar las características contra la suplantación de identidad de Windows Hello en los dispositivos que lo permitan (por ejemplo, cuando se detecte una fotografía de un rostro en lugar de un rostro real).  
    - **Habilitar**: Windows requiere que, cuando se admita, todos los usuarios utilicen tecnología contra la suplantación de identidad para las características faciales.
    - **Sin configurar**: Windows respeta las configuraciones de suplantación de identidad en el dispositivo.

    **Valor predeterminado**: No configurado

  - **Certificado para recursos locales**  

    - **Habilitar**: permite que Windows Hello para empresas use certificados para autenticarse en los recursos locales.
    - **Sin configurar**: impide que Windows Hello para empresas use certificados para autenticarse en los recursos locales. En su lugar, los dispositivos usan el comportamiento predeterminado de *autenticación local de claves de confianza*. Para más información, vea [Usa el certificado para la autenticación local](/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) en la documentación de Windows Hello.  

  **Valor predeterminado**: No configurado

- **Utilice las claves de seguridad para el inicio de sesión**  
  Esta opción está disponible para los dispositivos que ejecutan Windows 10, versión 1903 o una posterior. Úsela para administrar la compatibilidad con el uso de las claves de seguridad de Windows Hello para el inicio de sesión.  

  - **Habilitado**: los usuarios pueden usar una clave de seguridad de Windows Hello como credencial de inicio de sesión para los equipos a los que está destinada esta directiva. 
  - **Deshabilitado**: las claves de seguridad están deshabilitadas y los usuarios no pueden usarlas para iniciar sesión en los equipos.   

  **Valor predeterminado**: No configurado

## <a name="next-steps"></a>Pasos siguientes

[Asigne el perfil](../configuration/device-profile-assign.md) y [supervise el estado](../configuration/device-profile-monitor.md).