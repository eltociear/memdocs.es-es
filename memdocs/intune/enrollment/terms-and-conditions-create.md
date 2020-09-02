---
title: Definir los términos y condiciones en Microsoft Intune
titleSuffix: ''
description: Establezca los términos y condiciones que los usuarios ven en el Portal de empresa de Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure;seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3d0ae7f0ec42cef3ba792b5c0bf3c913bb9e63e
ms.sourcegitcommit: 0c7e6b9b47788930dca543d86a95348da4b0d902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88906861"
---
# <a name="terms-and-conditions-for-user-access"></a>Términos y condiciones para el acceso de los usuarios

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como administrador de Intune, puede requerir que los usuarios acepten los términos y condiciones de su empresa antes de usar Portal de empresa para:
- Inscribir dispositivos.
- Acceder a recursos como el correo electrónico y las aplicaciones de la empresa.

La configuración de términos y condiciones es opcional.

Puede crear varios conjuntos de términos y asignarlos a grupos distintos, como para admitir distintos lenguajes.

Hay dos maneras de crear los términos y condiciones de su empresa:
- Con Intune, tal y como se describe en este artículo.
- Con la [característica de términos de uso de Azure Active Directory](/azure/active-directory/governance/active-directory-tou).

Para saber qué método es el más adecuado para usted, revise la entrada de blog sobre la [elección de la solución de términos adecuada para la organización](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Creación de términos y condiciones
Complete estos pasos para crear los términos y condiciones. El nombre para mostrar y la descripción son para uso administrativo mientras las propiedades de términos se muestran a los usuarios en el Portal de empresa.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Administración de inquilinos** > **Términos y condiciones**.
2. Elija **Crear**.
3. En la página **Aspectos básicos**, especifique la información siguiente:

   - **Nombre**: nombre de los términos en Azure Portal. Los usuarios no ven este nombre.
   - **Descripción**: detalles opcionales que le ayudan a identificar este conjunto de términos en Azure Portal.

    ![Captura de pantalla de Azure Portal que muestra la página Aspectos básicos de los términos y condiciones](./media/terms-and-conditions-create/terms-basics-page.png)

4. Elija **Siguiente** para ir a la página **Términos** y escriba la información siguiente:

   - **Título**: el nombre de los términos que los usuarios ven en Portal de empresa sobre el **resumen**.
   - **Términos y condiciones**: los términos y condiciones que los usuarios ven y deben aceptar o rechazar.
   - **Resumen de términos**: texto que explica lo que significa que los usuarios acepten los términos. Por ejemplo, "Al inscribir el dispositivo, acepta los términos de uso establecidos por Contoso. Lea los términos detenidamente antes de continuar".

5. Elija **Siguiente** para ir a la página **Etiquetas de ámbito**.

6. Elija **Seleccionar etiquetas de ámbito**, seleccione las etiquetas de ámbito que quiere asignar a estos términos y condiciones y, luego, elija **Seleccionar**. 

7. Elija **Siguiente** para ir a la página **Asignaciones** y elija una de las opciones siguientes **Asignar a**:
    - **Todos los usuarios**: elija esta opción para asignar estos términos y condiciones a todos los usuarios.
    - **Seleccionar grupos**: elija esta opción para asignar estos términos y condiciones a todos los miembros de los grupos que identifique al elegir **Seleccionar grupos para incluir**.

8. Elija **Siguiente** > **Crear**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Cómo los usuarios ven los términos
El ejemplo siguiente muestra el **título** y el **resumen de términos** en la consola de administración y Portal de empresa de Intune.

![Captura de pantalla del título y el resumen de términos en la consola de administración y Portal de empresa de Intune.](./media/terms-and-conditions-create/terms-summary-terms.png)

Los ejemplos siguientes muestran los términos y condiciones en la consola de administración y Portal de empresa de Intune.

![Captura de pantalla de los términos y condiciones en la consola de administración y Portal de empresa de Intune.](./media/terms-and-conditions-create/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Supervisión de términos y condiciones

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Administración de inquilinos** > **Términos y condiciones**.
2. En la lista de términos y condiciones, elija los términos para los que quiere ver la aceptación > **Informes de aceptación**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Trabajar con varias versiones de los términos y las condiciones
Puede editar los términos y condiciones y administrar sus versiones. Cada vez que realice un cambio significativo en los términos y condiciones, debe:
- Aumentar el número de versión.
- Exigir que los usuarios acepten los nuevos términos y condiciones.

Si va a corregir errores tipográficos o cambiar el formato, por ejemplo, mantenga el número de versión actual.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Administración de inquilinos** > **Términos y condiciones** > elija los términos y condiciones que quiera modificar > **Propiedades**.

2. En el panel **Propiedades**, elija **Términos y condiciones** y, luego, modifique el **Título**, el **Resumen de los términos** y los **Términos y condiciones**, según corresponda. Si los cambios hacen que los usuarios tengan que volver a aceptar los términos nuevos, elija **Solicite a los usuarios que acepten de nuevo los términos e incremente el número de versión a**.

3. Elija **Aceptar** > **Guardar**.

Los usuarios solo deben aceptar una vez los términos y condiciones actualizados. No es necesarios que los usuarios con varios dispositivos acepten los términos y condiciones en cada uno de los dispositivos.