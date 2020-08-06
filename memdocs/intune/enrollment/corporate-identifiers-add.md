---
title: Agregar identificadores corporativos a Intune
titleSuffix: ''
description: Aprenda a agregar identificadores corporativos (método de inscripción, números IMEI y de serie) a Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure;seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b90051e9062978fbc016e461d67fbf081f50c616
ms.sourcegitcommit: 5a58af4f7d40bbde88a273fba859bf69eeff6107
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "87473685"
---
# <a name="identify-devices-as-corporate-owned"></a>Identificar dispositivos como corporativos

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como administrador de Intune, puede identificar dispositivos como propiedad de la empresa para restringir la identificación y administración. Intune puede realizar tareas de administración adicionales y recopilar información adicional, como el número de teléfono completo y un inventario de las aplicaciones de dispositivos propiedad de la empresa. También puede establecer restricciones de dispositivos para bloquear la inscripción de dispositivos que no sean propiedad de la empresa.

A la hora de efectuar la inscripción, Intune asigna de forma automática estados de propiedad de la empresa a los dispositivos que cumplan los siguientes criterios:

- Se ha inscrito con una cuenta de [administrador de inscripción de dispositivos](device-enrollment-manager-enroll.md) (todas las plataformas).
- Se ha inscrito mediante el [Programa de inscripción de dispositivos](device-enrollment-program-enroll-ios.md) de Apple, [Apple School Manager](apple-school-manager-set-up-ios.md) o [Apple Configurator](apple-configurator-enroll-ios.md) (solo iOS).
- [Se ha identificado como corporativo antes de la inscripción](#identify-corporate-owned-devices-with-imei-or-serial-number) mediante un número de identidad internacional de dispositivos móviles IMEI (todas las plataformas con números IMEI) o un número de serie (iOS y Android).
- Se ha unido a Azure Active Directory con credenciales profesionales o educativas. [Los dispositivos Azure Active Directory registrados](https://docs.microsoft.com/azure/active-directory/devices/overview) se marcarán como personales.
- Se ha establecido como corporativo en la [lista de propiedades del dispositivo](#change-device-ownership).

Una vez realizada la inscripción, [podrá cambiar la opción de propiedad](#change-device-ownership) entre **Personal** y **Corporativo**.

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identificar dispositivos corporativos con número de serie IMEI

Los administradores de Intune pueden crear e importar un archivo de valores separados por comas (.csv) que muestre los números de serie o IMEI de catorce dígitos. Intune usa estos identificadores para especificar que la propiedad de los dispositivos es corporativa durante la inscripción del dispositivo. Cada número IMEI o de serie puede tener detalles especificados en la lista para fines administrativos.

Esta característica es compatible con las siguientes plataformas:

| Plataforma | Números IMEI | Números de serie |
|---|---|---|
| Windows | Compatible (Windows Phone) | No compatible |
| iOS/macOS | No compatible (consulte Importante a continuación)  | Compatible. |
| Administrador de dispositivos del sistema operativo Android v10 administrado | No compatible | No compatible |
| Perfil de trabajo de Android Enterprise | No compatible | Compatible. |
| Android Enterprise totalmente administrado | No compatible | Compatible |
| Dispositivos Android Enterprise dedicados | No compatibles | No compatible |
| Perfil de trabajo corporativo de Android Enterprise | No compatible | Compatible. |

<!-- When you upload serial numbers for corporate-owned iOS/iPadOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple's Automated Device Enrollment or Apple Configurator to have them appear as corporate-owned. -->

[Obtenga información sobre cómo buscar el número de serie de un dispositivo de Apple](https://support.apple.com/HT204308).<br>
[Obtenga información sobre cómo buscar el número de serie del dispositivo de Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Agregar identificadores corporativos usando un archivo .csv
Para crear la lista, cree una lista de dos columnas de valores separados por comas (.csv) sin un encabezado. Agregue los números de serie o IMEI de catorce dígitos en la columna izquierda y los detalles en la columna derecha. Solo puede importarse un tipo de identificador, número IMEI o de serie en un único archivo .csv. Los detalles están limitados a 128 caracteres y son solo de uso administrativo. Los detalles no se muestran en el dispositivo. El límite actual es 5000 filas por archivo. csv.

**Cargar un archivo .csv con números de serie**: cree una lista de valores separados por comas (.csv) de dos columnas sin encabezado y limítela a 5000 dispositivos o a 5 MB por archivo .csv.

Este archivo .csv, cuando se ve en un editor de texto, aparece como:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Algunos dispositivos Android y iOS/iPadOS tienen varios números IMEI. Intune solo lee un número IMEI por dispositivo inscrito. Si importa un número IMEI, pero no es el que ha inventariado Intune, el dispositivo se clasificará como dispositivo personal en lugar de como dispositivo propiedad de la empresa. Si importa varios números IMEI de un dispositivo, en el estado de inscripción de los números no inventariados se mostrará **Desconocido**.<br>
>Tenga en cuenta: Los números de serie son la forma de identificación recomendada de los dispositivos iOS e iPadOS.
>No se garantiza que los números de serie de Android sean únicos o estén presentes. Póngase en contacto con el proveedor del dispositivo para saber si el número de serie es un identificador de dispositivo de confianza.
>Los números de serie que el dispositivo notifica a Intune podrían no coincidir con el identificador que aparece en los menús del dispositivo Configuración de Android/Acerca de. Compruebe el tipo de número de serie que ha notificado el fabricante del dispositivo.
>Al intentar cargar un archivo con números de serie que contengan puntos (.), se producirán errores de carga. Los números de serie con puntos no se admiten.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Actualizar una lista en formato .csv de identificadores corporativos

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Dispositivos** > **Inscribir dispositivos** > **Identificadores de dispositivo corporativos** > **Agregar** > **Cargar un archivo CSV**.

2. En la hoja **Agregar identificadores**, especifique el tipo de identificador: **IMEI** o **de serie**.

3. Haga clic en el icono de la carpeta y especifique la ruta de acceso de la lista que quiera importar. Vaya al archivo .csv y elija **Agregar**. 

4. Si el archivo .csv contiene identificadores corporativos que ya están en Intune, pero con detalles distintos, aparece el menú emergente **Revisar los identificadores duplicados**. Seleccione los identificadores que quiera sobrescribir en Intune y elija **Aceptar** para agregarlos. En cada identificador solo se comparará el primer duplicado.

## <a name="manually-enter-corporate-identifiers"></a>Especificar identificadores corporativos manualmente

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Dispositivos** > **Inscribir dispositivos** > **Identificadores de dispositivo corporativos** > **Agregar** > **Especificar manualmente**.

2. En la hoja **Agregar identificadores**, especifique el tipo de identificador: **IMEI** o **de serie**.

3. Escriba el **identificador** y los **detalles** de cada identificador que quiera agregar. Cuando haya terminado de especificar los identificadores, elija **Agregar**.

5. Si ha especificado identificadores corporativos que ya están en Intune, pero con detalles distintos, aparece el menú emergente **Revisar los identificadores duplicados**. Seleccione los identificadores que quiera sobrescribir en Intune y elija **Aceptar** para agregarlos. En cada identificador solo se comparará el primer duplicado.

Puede hacer clic en **Actualizar** para ver los nuevos identificadores de dispositivo.

Los dispositivos importados no tienen por qué inscribirse. Además, pueden tener un estado **Inscrito** o **Sin contacto**. **No contactado** significa que el dispositivo nunca se ha comunicado con el servicio Intune.

## <a name="delete-corporate-identifiers"></a>Eliminación de identificadores corporativos

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **Dispositivos** > **Inscribir dispositivos** > **Identificadores de dispositivo corporativos**.
2. Seleccione los identificadores de dispositivo que quiera eliminar y elija **Eliminar**.
3. Confirme la eliminación.

Eliminar un identificador corporativo de un dispositivo inscrito no modifica su propiedad. Para modificar la propiedad de un dispositivo, vaya a **Dispositivos**, seleccione el dispositivo, elija **Propiedades** y cambie **Propiedad del dispositivo**.

## <a name="imei-specifications"></a>Especificaciones de IMEI
Para obtener especificaciones detalladas sobre identificadores internacionales de equipos móviles, consulte [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Cambiar la propiedad del dispositivo

Las propiedades del dispositivo muestran **Propiedad** en los registros de Intune para cada dispositivo. Como administrador, puede especificar un dispositivo como **Personal** o **Corporativo**. Cuando se cambia el tipo de propiedad de un dispositivo de Corporativa a Personal, Intune elimina toda la información de la aplicación previamente recopilada de ese dispositivo en un plazo de siete días. Si es necesario, Intune también eliminará el número de teléfono registrado. 

**Para cambiar la propiedad del dispositivo:**
1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), elija **Dispositivos** > **Todos los dispositivos** y seleccione el dispositivo.
2. Seleccione **Propiedades**.
3. Establezca **Propiedad del dispositivo** como **Personal** o **Corporativo**.

   ![Propiedades del dispositivo con las opciones Categoría de dispositivo y Propiedad del dispositivo](./media/corporate-identifiers-add/device-properties.png)

Se puede configurar una notificación de inserción para enviársela a los usuarios del Portal de empresa de Android e iOS cuando el tipo de propiedad del dispositivo cambie de **Personal** a **Corporativo** como gesto de cortesía hacia su privacidad. 

Cuando se cambia el tipo de propiedad de un dispositivo de Corporativa a Personal, Intune elimina toda la información de la aplicación previamente recopilada de ese dispositivo en un plazo de siete días. Si es necesario, Intune también eliminará el número de teléfono registrado. Intune seguirá recopilando un inventario de las aplicaciones que instale el administrador de TI en el dispositivo y un número de teléfono parcial para el dispositivo una vez que se haya marcado como personal.

Para encontrar esta opción en Microsoft Endpoint Manager, seleccione **Administración de inquilinos** > **Personalización**. Para obtener más información, vea [Portal de empresa: configuración](../apps/company-portal-app.md#configuration).