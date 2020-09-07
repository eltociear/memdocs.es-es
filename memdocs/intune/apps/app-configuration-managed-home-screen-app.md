---
title: Configuración de la aplicación Managed Home Screen de Microsoft
titleSuffix: Microsoft Intune
description: Obtenga información sobre cómo configurar la aplicación Managed Home Screen de Microsoft.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/01/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0279a85d0eb3bac7d222c27ce15203f58fd4ede6
ms.sourcegitcommit: ded11a8b999450f4939dcfc3d1c1adbc35c42168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "89281173"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Configuración de la aplicación Managed Home Screen de Microsoft para Android Enterprise

Managed Home Screen es la aplicación que se usa para dispositivos Android Enterprise corporativos dedicados inscritos mediante Intune y que se ejecutan en modo de pantalla completa con varias aplicaciones. Para estos dispositivos, Managed Home Screen actúa como el iniciador de otras aplicaciones aprobadas para que se ejecuten sobre ella. Managed Home Screen proporciona a los administradores de TI la capacidad de personalizar sus dispositivos y de restringir las funcionalidades a las que puede acceder el usuario final. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Cuándo configurar la aplicación Managed Home Screen de Microsoft

Normalmente, si las opciones están disponibles a través de Configuración del dispositivo, configúrelas ahí. De esta forma ahorra tiempo, minimiza los errores y obtendrá una mejor experiencia de soporte técnico de Intune. Sin embargo, actualmente algunas de las opciones de Managed Home Screen solo están disponibles a través del panel **Directivas de configuración de aplicaciones** de la consola de Intune. Use este documento para obtener información sobre cómo configurar las distintas opciones mediante el Diseñador de configuraciones o un script JSON. 

> [!NOTE]
> Actualmente es posible, y recomendable, establecer las aplicaciones permitidas y los vínculos web anclados a través de **Aplicaciones** y **Configuración del dispositivo**. Para obtener la lista completa de opciones disponibles en **Configuración del dispositivo** que afectan a Managed Home Screen, vea [ Configuración del dispositivo dedicado](../configuration/device-restrictions-android-for-work.md#device-experience).  

En primer lugar, vaya al [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y seleccione **Aplicaciones** > **Directivas de configuración de aplicaciones**. Agregue una directiva de configuración para **Dispositivos administrados** que se ejecutan en **Android** y elija **Managed Home Screen** como la aplicación asociada. Haga clic en **Opciones de configuración** para configurar las distintas opciones disponibles de Managed Home Screen. 

## <a name="choosing-a-configuration-settings-format"></a>Selección de un formato de opciones de configuración

Puede usar dos métodos para definir opciones de configuración para Managed Home Screen:

- El **Diseñador de configuraciones** permite configurar las opciones con una interfaz de usuario fácil de usar que le permite activar o desactivar características y establecer valores. En este método, hay algunas claves de configuración deshabilitadas con el tipo de valor `BundleArray`. Estas claves de configuración solo se pueden configurar mediante la especificación de datos JSON. 
- Los **datos JSON** permiten definir todas las claves de configuración posibles mediante un script JSON. 

Si agrega propiedades con el Diseñador de configuraciones, las puede convertir de forma automática en JSON si selecciona **Especificar datos JSON** en la lista desplegable **Formato de opciones de configuración**.

![Captura de pantalla de las opciones de Formato de opciones de configuración](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Uso del Diseñador de configuraciones

El Diseñador de configuraciones le permite seleccionar opciones preestablecidas y sus valores asociados. 

![Captura de pantalla de las opciones de configuración agregadas](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

En la tabla siguiente se enumeran las claves de configuración disponibles de Managed Home Screen, los tipos de valor, los valores predeterminados y sus descripciones. La descripción proporciona el comportamiento esperado del dispositivo según los valores seleccionados. En la tabla no se muestran las claves de configuración deshabilitadas en el Diseñador de configuraciones.

| Clave de configuración | Tipo de valor | Valor predeterminado | Descripción |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Definir tamaño de la cuadrícula | string | Auto | Permite establecer el tamaño de la cuadrícula para las aplicaciones que se van a colocar en la pantalla principal administrada. Puede establecer el número de filas y columnas de la aplicación para definir el tamaño de la cuadrícula en el formato siguiente, `columns;rows`. Si define el tamaño de la cuadrícula, el número máximo de aplicaciones que se mostrarán en una fila de la pantalla principal será el número de filas que establezca, y el número máximo de aplicaciones que se mostrarán en una columna de la pantalla principal será el número de columnas que establezca. |
| Habilitar la señal de notificaciones | bool | FALSE | Permite la señal de notificación para los iconos de aplicación que muestra el número de notificaciones nuevas en la aplicación. Si habilita esta opción, los usuarios finales verán señales de notificación en las aplicaciones que tienen notificaciones sin leer. Si mantiene deshabilitada esta configuración clave, el usuario final no verá ninguna notificación señalada para las aplicaciones que podrían tener notificaciones sin leer. |
| Bloquear la pantalla de inicio | bool | TRUE | Impide al usuario final mover los iconos de las aplicaciones en la pantalla principal. Si habilita esta clave de configuración, se bloquearán los iconos de las aplicaciones en la pantalla principal y el usuario final no podrá arrastrarlos y colocarlos en otras posiciones de la cuadrícula de la pantalla principal. Si se establece en `false`, los usuarios finales podrán mover los iconos de las aplicaciones y los vínculos web en Managed Home Screen.  |
| Establecer el fondo de pantalla del dispositivo | string | Predeterminado | Le permite establecer el fondo de pantalla que elija si escribe la dirección URL de la imagen que quiera establecer como fondo de pantalla. |
| Establecer el tamaño del icono de la aplicación | integer | 2 | Le permite establecer el tamaño de icono para las aplicaciones que se muestran en la pantalla principal. Puede elegir los valores siguientes en esta configuración para diferentes tamaños: 0 (el más pequeño), 1 (pequeño), 2 (estándar), 3 (grande) y 4 (el más grande). |
| Establecer el icono de la carpeta de aplicación | integer | 0 | Le permite definir la apariencia de las carpetas de aplicación en la pantalla principal. Puede elegir la apariencia entre los valores siguientes: Dark Square(0); Dark Circle(1); Light Square(2); Light Circle(3). |
| Establecer la orientación de la pantalla | integer | 1 | Le permite establecer la orientación de la pantalla principal en modo vertical, horizontal o permitir el giro automático. Puede establecer la orientación si escribe los valores 1 (para el modo vertical), 2 (para el modo horizontal), 3 (para Girar automáticamente). |
| Establecer aplicaciones permitidas | bundleArray | FALSE | Le permite definir el conjunto de aplicaciones visibles en la pantalla principal de entre las instaladas en el dispositivo. Para definir las aplicaciones, escriba el nombre del paquete de aplicación de las aplicaciones que le gustaría hacer visibles; por ejemplo, com.microsoft.emmx hará que se pueda acceder a la configuración desde la pantalla principal. Las aplicaciones que incluya en la lista de permitidas en esta sección ya deben estar instaladas en el dispositivo para que se vean en la pantalla principal. |
| Establecer vínculos web anclados | bundleArray | FALSE | Le permite anclar sitios web como iconos de inicio rápido en la pantalla principal. Con esta configuración, puede definir la dirección URL y agregarla a la pantalla principal para que el usuario final inicie el explorador con un solo toque. Nota: Se recomienda crear, asignar y aprobar [vínculos web de Google Play administrados](./apps-add-android-for-work.md#managed-google-play-web-links) para los dispositivos, que se tratan como aplicaciones permitidas. |
| Habilitar protector de pantalla | bool | FALSE | Para habilitar o no el modo de protector de pantalla. Si se establece en true, puede configurar **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver** y **media_detect_screen_saver**. |
| Imagen del protector de pantalla | string |   | Establezca la dirección URL de la imagen del protector de pantalla. Si no se establece ninguna dirección URL, los dispositivos mostrarán la imagen del protector de pantalla predeterminada cuando se active el protector de pantalla. La imagen predeterminada muestra el icono de la aplicación Managed Home Screen.  |
| Mostrar hora del protector de pantalla | integer | 0 | Ofrece la opción de establecer la cantidad de tiempo en segundos que el dispositivo mostrará el protector de pantalla durante el modo de protector de pantalla. Si se establece en 0, el protector de pantalla se mostrará en modo de protector de pantalla indefinidamente hasta que el dispositivo se active.  |
| Tiempo de inactividad para habilitar el protector de pantalla | integer | 30 | El número de segundos que el dispositivo está inactivo antes de desencadenar el protector de pantalla. Si se establece en 0, el dispositivo nunca pasará al modo de protector de pantalla. |
| Detectar medios antes de mostrar el protector de pantalla | bool | TRUE | Elija si en la pantalla del dispositivo se debe mostrar el protector de pantalla cuando se reproduce audio o vídeo en el dispositivo. Si se establece en true, el dispositivo no reproducirá audio o vídeo, con independencia del valor de **inactive_time_to_show_scree_saver**. Si se establece en false, en la pantalla del dispositivo se mostrará el protector de pantalla según el valor establecido en **inactive_time_to_show_screen_saver**.   |
| Habilitar botón de inicio virtual | bool | FALSE | Establezca esta opción en `True` para permitir que el usuario final tenga acceso a un botón de inicio de Managed Home Screen que lo devolverá a la pantalla de la aplicación desde la tarea actual en la que se encuentre.  |
| Tipo de botón de inicio virtual | string | Swipe_up | Use **swipe_up** para acceder al botón de inicio con un gesto de deslizar rápidamente hacia arriba. Use **float** para acceder a un botón de inicio fijo y persistente que el usuario final pueda mover por la pantalla. |
| Barra indicadora de la batería y la intensidad de la señal | bool | True  | Al establecer esta opción en `True` se muestra la barra indicadora de la batería y la intensidad de la señal. |
| Contraseña para salir del modo de bloqueo de tareas | string |   | Escriba un código de 4-6 dígitos para salir temporalmente del modo de bloqueo de tareas para solucionar problemas. |
| Mostrar configuración administrada | bool | TRUE | "Configuración administrada" es una aplicación Managed Home Screen que solo aparece si se ha configurado algún valor de acceso rápido, como **Mostrar configuración de Wi-Fi**, **Mostrar configuración de Bluetooth**, **Mostrar configuración de volumen** y **Mostrar configuración de linterna**. También se puede acceder a esta configuración deslizando el dedo hacia abajo en la pantalla. Establezca esta clave en `False` para ocultar la aplicación "Configuración administrada" y que los usuarios finales solo puedan acceder a la configuración si deslizan el dedo hacia abajo.    |
| Habilitar el menú Depurar de acceso fácil | bool | FALSE | Establezca esta opción en `True` para acceder al menú Depurar desde la aplicación Configuración administrada o al deslizar el dedo hacia abajo en Managed Home Screen. El menú Depurar es actualmente donde reside la capacidad de salir del modo de quiosco y se tiene acceso a él haciendo clic en el botón Atrás aproximadamente 15 veces. Mantenga este valor en `False` para que el punto de entrada al menú Depurar solo sea accesible mediante el botón Atrás.   |
| Mostrar configuración de Wi-Fi | bool | FALSE | Al establecer esta opción en `True` se permite al usuario final activar o desactivar la conexión Wi-Fi, o bien conectarse a otras redes Wi-Fi.  |
| Habilitar la lista de permitidos de Wi-Fi | bool | FALSE | Establezca esta opción en `True` y rellene la clave **Lista de permitidos de Wi-Fi** para restringir las redes Wi-Fi que se muestran en Managed Home Screen. Defínala como `False` para mostrar todas las redes Wi-Fi disponibles que el dispositivo ha detectado. Tenga en cuenta que esta configuración solo es pertinente si **Mostrar configuración de Wi-Fi** se ha establecido en `True` y se ha rellenado la **Lista de permitidos de Wi-Fi**.   |
| Lista de permitidos de Wi-Fi| bundleArray | FALSE | Permite mostrar una lista de todos los SSID de las redes Wi-Fi que quiere que el dispositivo muestre en Managed Home Screen. Esta lista solo es relevante si **Mostrar configuración de Wi-Fi** y **Habilitar la lista de permitidos de Wi-Fi** se han establecido en `True`. Si alguna de ellas se ha establecido en `False`, no es necesario modificar esta configuración.    |
| Mostrar la configuración de Bluetooth | bool | FALSE | Al establecer esta opción en `True` se permite al usuario final activar o desactivar Bluetooth, o bien conectarse a otros dispositivos compatibles con Bluetooth.   |
| Mostrar configuración de volumen | bool | FALSE | El establecimiento de esta opción en `True` permite al usuario final acceder a un control deslizante de volumen para ajustar el volumen del elemento multimedia.   |
| Mostrar configuración de linterna | bool | FALSE | El establecimiento de esta opción en `True` permite al usuario final activar o desactivar la linterna del dispositivo. Si el dispositivo no admite una linterna, este valor no aparecerá aunque se configure como `True`.   |
| Mostrar configuración de información del dispositivo | bool | FALSE | El establecimiento de esta opción en `True` permite al usuario final acceder a información rápida sobre el dispositivo desde la aplicación Configuración administrada o al deslizar el dedo hacia abajo. La información accesible incluye la marca, el modelo y el número de serie del dispositivo.   |
| Las aplicaciones de la carpeta se ordenan por nombre. | bool | TRUE | Si selecciona `False`, los elementos de una carpeta aparecerán en el orden en que se hayan especificado. En caso contrario, aparecerán en la carpeta ordenados alfabéticamente.   |
| Orden de la aplicación habilitada | bool | FALSE | Si selecciona `True`, podrá establecer el orden de las aplicaciones, los vínculos web y las carpetas en la aplicación Managed Home Screen. Una vez habilitada, establezca el orden con **app_order**.   |
| Orden de la aplicación | bundleArray | FALSE | Permite especificar el orden de las aplicaciones, los vínculos web y las carpetas en la aplicación Managed Home Screen. Para usar esta configuración, **Bloquear pantalla de inicio** debe estar habilitada, **Definir tamaño de la cuadrícula** deben estar definido y **Orden de la aplicación habilitada** debe establecerse en `True`.   |

## <a name="enter-json-data"></a>Especificar datos JSON

Especifique datos JSON para configurar todas las opciones disponibles para Managed Home Screen, así como las opciones deshabilitadas en el **Diseñador de configuraciones**.

![Captura de pantalla de los datos JSON agregados](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Además de la lista de opciones configurables enumeradas en la tabla del **Diseñador de configuraciones** (anterior), en la tabla siguiente se proporcionan las claves de configuración que solo se pueden configurar a través de datos JSON.

|    Clave de configuración    |    Tipo de valor    |    Valor predeterminado    |    Descripción    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Establecer aplicaciones permitidas    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Le permite definir el conjunto de aplicaciones visibles en la pantalla principal de entre las instaladas en el dispositivo. Para definir las aplicaciones, escriba el nombre del paquete de aplicación de las aplicaciones que le gustaría hacer visibles; por ejemplo, com.android.settings hará que se pueda acceder a la configuración desde la pantalla principal. Las aplicaciones que incluya en la lista de permitidas en esta sección ya deben estar instaladas en el dispositivo para que se vean en la pantalla principal.    |
|    Establecer vínculos web anclados    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Le permite anclar sitios web como iconos de inicio rápido en la pantalla principal. Con esta configuración, puede definir la dirección URL y agregarla a la pantalla principal para que el usuario final inicie el explorador con un solo toque. Nota: Se recomienda crear, asignar y aprobar [vínculos web de Google Play administrados](./apps-add-android-for-work.md#managed-google-play-web-links) para los dispositivos, que se tratan como aplicaciones permitidas.    |
|    Crear carpeta administrada para agrupar aplicaciones    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Le permite crear carpetas y asignarles un nombre, y agrupar aplicaciones dentro de estas carpetas. Los usuarios finales no podrán mover las carpetas, cambiarlas de nombre ni mover las aplicaciones dentro de las carpetas.   Las carpetas aparecerán en el orden en el que se hayan creado, y las aplicaciones dentro de las carpetas aparecerán en orden alfabético.         Nota: Todas las aplicaciones que quiera agrupar en carpetas se deben asignar como requeridas en el dispositivo y se deben haber agregado a Managed Home Screen.     |

Este es un ejemplo de script JSON con todas las claves de configuración disponibles incluidas:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "app package name here"
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": "link here"
                        },
                        {
                            "key": "label",
                            "valueString": "weblink label here"
                        }
                    ]
                }
            ]
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "show_flashlight_setting",
            "valueBool": false
        },
        {
            "key": "show_volume_setting",
            "valueBool": false
        },
        {
            "key": "show_device_info_setting",
            "valueBool": false
        },
        {
            "key": "show_managed_setting",
            "valueBool": false
        },
        {
            "key": "enable_easy_access_debugmenu",
            "valueBool": false
        },
        {
            "key": "enable_wifi_allowlist",
            "valueBool": false
        },
        {
            "key": "wifi_allowlist",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "SSID",
                            "valueString": "name of Wi-Fi network 1 here"
                        }
                    ]
                },   
                {
                    "managedProperty": [
                        {
                            "key": "SSID",
                            "valueString": "name of Wi-Fi network 2 here"
                        }
                    ]
                }  
            ]
        },
        {
            "key": "grid_size",
            "valueString": "4;5"
        },
        {
            "key": "app_order_enabled",
            "valueBool": true
        },
        {
            "key": "apps_in_folder_ordered_by_name",
            "valueBool": true
        },
        {
            "key": "app_orders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.Microsoft.emmx"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 1
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Work"
                        },
                        {
                            "key": "type",
                            "valueString": "managed_folder"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 2
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.microsoft.launcher.enterprise"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "class",
                            "valueString": "com.microsoft.launcher.launcher"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 3
                        }
                    ]
                }
            ]
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="googles-android-device-policy-app"></a>Aplicación de directiva de dispositivo Android de Google
La aplicación de Pantalla principal administrada ahora proporciona acceso a la aplicación de directiva de dispositivo Android de Google. La aplicación de Pantalla principal administrada es un iniciador personalizado que se usa para dispositivos inscritos en Intune, como dispositivos dedicados de Android Enterprise (AE) que usan el modo de pantalla completa de varias aplicaciones. Puede acceder a la aplicación de directiva de dispositivo Android o guiar a los usuarios a esta aplicación, con fines de soporte técnico y depuración. Esta capacidad de inicio está disponible en el momento en que el dispositivo se inscribe y se bloquea en la Pantalla principal administrada. No se necesitan instalaciones adicionales para usar esta funcionalidad.

## <a name="managed-home-screen-debug-screen"></a>Pantalla de depuración de Managed Home Screen
Para acceder a la pantalla de depuración de Managed Home Screen, haga clic en el botón **atrás** hasta que se muestre la pantalla de depuración (haga clic en el botón **atrás** 15 veces o más). En esta pantalla de depuración, puede iniciar la aplicación de directivas de dispositivos Android, ver y cargar registros o pausar temporalmente la pantalla completa para actualizar el dispositivo. Para más información sobre cómo pausar el modo de pantalla completa, consulte el elemento **Salir del modo de pantalla completa,** en la [configuración de dispositivo dedicada](../configuration/device-restrictions-android-for-work.md#device-experience) de Android Enterprise. Si quiere que resulte más fácil acceder al menú Depurar de Managed Home Screen, puede establecer **Habilitar el menú Depurar de acceso fácil** en `True` con directivas de configuración de aplicación. 

## <a name="next-steps"></a>Pasos siguientes

- Para más información sobre los dispositivos dedicados de Android Enterprise, vea [Configuración de la inscripción en Intune de dispositivos dedicados de Android Enterprise](../enrollment/android-kiosk-enroll.md).
