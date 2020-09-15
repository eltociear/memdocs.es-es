---
title: 'Firma y cifrado de correo electrónico mediante S/MIME - Microsoft Intune: Azure | Microsoft Docs'
description: Aprenda a usar los certificados digitales de Microsoft Intune para firmar y cifrar el correo electrónico en los dispositivos. Estos certificados se denominan S/MIME y se configuran mediante perfiles de configuración de dispositivo. Los certificados de firma y cifrado usan PKCS, o certificados privados, y un conector para importar certificados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5bf1150a32db213c2c8b697625076a601377c1e6
ms.sourcegitcommit: b95eac00a0cd979dc88be953623c51dbdc9327c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "89423771"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Información general sobre S/MIME para firmar y cifrar el correo electrónico en Intune

Los certificados de correo electrónico, también conocidos como certificados S/MIME, proporcionan seguridad adicional a las comunicaciones de correo electrónico mediante el cifrado y el descifrado. Microsoft Intune puede usar certificados S/MIME para firmar y cifrar el correo electrónico de los dispositivos móviles con las siguientes plataformas:

- Android
- iOS/iPadOS
- macOS
- Windows 10 y versiones posteriores

En los dispositivos iOS/iPadOS, puede crear un perfil de correo electrónico administrado por Intune que use S/MIME y certificados para firmar y cifrar los mensajes de correo electrónico entrantes y salientes. Para otras plataformas, es posible que S/MIME sea o no compatible. Si se admite, instale certificados que usen cifrado y firma S/MIME. Luego, el usuario final puede habilitar S/MIME en su aplicación de correo electrónico.

Para obtener más información sobre la firma y el cifrado de correo electrónico con S/MIME, vea [S/MIME para la firma y el cifrado de mensajes](/Exchange/policy-and-compliance/smime).

En este artículo se proporciona información general sobre el uso de certificados S/MIME para firmar y cifrar el correo electrónico de los dispositivos.

## <a name="signing-certificates"></a>Certificados de firma

Los certificados que se usan para la firma permiten que la aplicación de correo electrónico cliente se comunique de forma segura con el servidor de correo electrónico.

Para usar certificados de firma, cree una plantilla centrada en la firma en la entidad de certificación (CA). En la entidad de certificación de Microsoft Active Directory, en [Configurar la plantilla de certificado de servidor](/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) se enumeran los pasos para crear plantillas de certificado.

Los certificados de firma en Intune usan certificados PKCS. En [Configuración y uso de certificados PKCS con Intune](certficates-pfx-configure.md) se describe cómo implementar y usar el certificado PKCS en el entorno de Intune. Estos pasos incluyen:

- Descargar e instalar el conector de certificados PFX para admitir las solicitudes de certificado PKCS. El conector tiene los mismos requisitos de red que los [dispositivos administrados](../fundamentals/intune-endpoints.md#access-for-managed-devices).
  > [!IMPORTANT]
  > A partir de la versión 6.2008.60.607 (agosto de 2020) del conector de certificados PFX, este conector admite la implementación de certificados para las solicitudes de certificados PCKS #12 y administra solicitudes de archivos PFX importados a Intune para el cifrado de correo electrónico S/MIME para un usuario específico. Ya no es necesario usar el conector de Microsoft Intune al usar perfiles de certificado PKCS.
  > 
  > Para obtener más información, vea [Conectores de certificados](certificate-connectors.md).
- Crear un perfil de certificado raíz de confianza para los dispositivos. Este paso incluye el uso de certificados raíz de confianza e intermedios para la entidad de certificación y, después, la implementación del perfil en los dispositivos.
- Crear un perfil de certificado PKCS mediante la plantilla de certificado que se creó. Este perfil emite certificados de firma para los dispositivos e implementa el perfil de certificado PKCS en los dispositivos.

También se puede importar un certificado de firma para un usuario específico. El certificado de firma se implementa en todos los dispositivos inscritos por un usuario. Para importar certificados en Intune, use los [cmdlets de PowerShell de GitHub](https://github.com/Microsoft/Intune-Resource-Access). Para implementar un certificado PKCS importado en Intune que se va a usar para la firma de correo electrónico, siga los pasos descritos en [Configuración y uso de certificados PKCS con Intune](certficates-pfx-configure.md). Estos pasos incluyen:

- Descargar e instalar el Conector de certificado PFX para Microsoft Intune. Este conector proporciona certificados PKCS importados a los dispositivos.
- Importar certificados de firma de correo electrónico S/MIME a Intune.
- Crear un perfil de certificado PKCS importado. Este perfil proporciona los certificados PKCS importados a los dispositivos del usuario adecuado.

## <a name="encryption-certificates"></a>Certificados de cifrado

Los certificados que se usan para el cifrado confirman que un correo electrónico cifrado solo se puede descifrar por el destinatario previsto. El cifrado S/MIME es una capa adicional de seguridad que se puede usar en las comunicaciones por correo electrónico.

Al enviar un correo electrónico cifrado a otro usuario, se obtiene la clave pública del certificado de cifrado de ese usuario y se cifra el correo electrónico que se envía. El destinatario descifra el correo electrónico con la clave privada en su dispositivo. Los usuarios pueden tener un historial de los certificados usados para cifrar el correo electrónico. Cada uno de esos certificados se debe implementar en todos los dispositivos de un usuario específico para que su correo electrónico se descifre de forma correcta.

Se recomienda que los certificados de cifrado de correo electrónico no se creen en Intune. Aunque Intune es compatible con la emisión de certificados PKCS que admiten el cifrado, Intune crea un certificado único por dispositivo. Un certificado único por dispositivo no es ideal para un escenario de cifrado S/MIME, donde el certificado de cifrado se debe compartir entre todos los dispositivos del usuario.

Para implementar certificados S/MIME con Intune, debe importar a Intune todos los certificados de cifrado de un usuario. Luego Intune implementa todos esos certificados en cada dispositivo que el usuario inscribe. Para importar certificados en Intune, use los [cmdlets de PowerShell de GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Para implementar un certificado PKCS importado en Intune que se usa para el cifrado de correo electrónico, siga los pasos descritos en [Configuración y uso de certificados PKCS con Intune](certficates-pfx-configure.md). Estos pasos incluyen:

- Descargar e instalar el Conector de certificado PFX para Microsoft Intune. Este conector proporciona certificados PKCS importados a los dispositivos.
- Importar los certificados de cifrado de correo electrónico S/MIME a Intune.
- Crear un perfil de certificado PKCS importado. Este perfil proporciona los certificados PKCS importados a los dispositivos del usuario adecuado.

 > [!NOTE]
 > Intune elimina los certificados S/MIME importados cuando se quitan los datos de la empresa, o bien cuando se anula la inscripción de los usuarios de la administración. Pero los certificados no se revocan en la entidad de certificación.

## <a name="smime-email-profiles"></a>Perfiles de correo electrónico S/MIME

Después de crear los perfiles de certificado de firma y cifrado S/MIME, puede [habilitar S/MIME para el correo electrónico nativo de iOS/iPadOS](../configuration/email-settings-ios.md).

## <a name="next-steps"></a>Pasos siguientes

- [Uso de SCEP para los certificados](certificates-scep-configure.md)
- [Usar certificados PKCS](certficates-pfx-configure.md)
- [Usar una entidad de certificación asociada](certificate-authority-add-scep-overview.md)
- [Emitir certificados PKCS desde un servicio web de administración de PKI de Symantec](certificates-digicert-configure.md)