---
title: Adición y asignación de aplicaciones Win32 a Microsoft Intune
titleSuffix: ''
description: Obtenga información sobre cómo agregar, asignar y administrar aplicaciones Win32 con Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2020
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5266f354ea5806743813d1aeb4c456890fa46b19
ms.sourcegitcommit: 4b8c317c71535c2d464f336c03b5bebdd2c6d4c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90083954"
---
# <a name="add-assign-and-monitor-a-win32-app-in-microsoft-intune"></a>Adición, asignación y supervisión de una aplicación Win32 en Microsoft Intune

Después de haber [preparado una aplicación Win32 para cargarla en Intune](apps-win32-prepare.md) mediante la [herramienta de preparación de contenido de Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730), puede agregarla a Intune. Para más información sobre la preparación de una aplicación Win32 para su carga, consulte [Preparación del contenido de una aplicación Win32 para la carga](apps-win32-prepare.md).

## <a name="prerequisites"></a>Requisitos previos

Para usar la administración de aplicaciones Win32, asegúrese de cumplir los criterios siguientes:

- Use Windows 10 versión 1607 o posteriores (versiones Enterprise, Pro y Education).
- Los dispositivos deben estar unidos a Azure Active Directory (Azure AD) y haberse inscrito automáticamente. La extensión de administración de Intune admite dispositivos unidos a Azure AD, unidos a un dominio híbrido e inscritos en una directiva de grupo. 
  > [!NOTE]
  > En el escenario de inscripción en una directiva de grupo, el usuario usa la cuenta de usuario local para unir a Azure AD su dispositivo Windows 10. El usuario debe iniciar sesión en el dispositivo con su cuenta de usuario de Azure AD e inscribirse en Intune. Intune instalará la extensión de administración de Intune en el dispositivo si un script de PowerShell o una aplicación Win32 tiene como destino el usuario o dispositivo.
- El tamaño de la aplicación Windows está limitado a 8 GB por aplicación.

De forma bastante similar a una aplicación estándar de línea de negocio (LOB), puede agregar una aplicación Win32 a Microsoft Intune. Este tipo de aplicación se escribe normalmente de forma interna o se encarga a un tercero. 

## <a name="process-flow-to-add-a-win32-app-to-intune"></a>Flujo del proceso para agregar una aplicación Win32 a Intune

<img alt="Flow chart of the process to add a Win32 app to Intune." src="./media/apps-win32-app-management/add-win32-app.svg" width="500">

## <a name="add-a-win32-app-to-intune"></a>Adición de una aplicación Win32 a Intune

Los siguientes pasos le ayudarán a agregar una aplicación de Windows a Intune:

1. Inicie sesión en el [Centro de administración del Administrador de puntos de conexión de Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Aplicaciones** > **Todas las aplicaciones** > **Agregar**.
3. En el panel **Seleccionar un tipo de aplicación**, en **Otros** tipos de aplicaciones, seleccione **Aplicación de Windows (Win32)** .

    > [!IMPORTANT]
    > Asegúrese de usar la versión más reciente de la herramienta de preparación de contenido Win32 de Microsoft. Si no usa la versión más reciente, verá una advertencia que indica que la aplicación se ha empaquetado con una versión anterior de la herramienta. 

4. Haga clic en **Seleccionar**. Aparecen los pasos de **Agregar aplicación**.

## <a name="step-1-app-information"></a>Paso 1: Información de la aplicación

### <a name="select-the-app-package-file"></a>Selección del archivo de paquete de aplicaciones

1. En el panel **Agregar aplicación**, haga clic en **Seleccionar un archivo del paquete de aplicaciones**. 
2. En el panel **Archivo del paquete de aplicaciones**, seleccione el botón Examinar. Después seleccione un archivo de instalación de Windows con la extensión *.intunewin*.
   Aparecen los detalles de la aplicación.
3. Cuando haya terminado, seleccione **Aceptar** en el panel **Archivo del paquete de aplicaciones**.

### <a name="set-app-information"></a>Establecimiento de la información de la aplicación

En la página **Información de la aplicación**, agregue los datos de su aplicación. Dependiendo de la aplicación que haya elegido, algunos de los valores de esta página podrían rellenarse automáticamente.

- **Nombre**: escriba el nombre de la aplicación tal como aparece en el portal de empresa. Asegúrese de que todos los nombres de aplicación que usa son únicos. Si el mismo nombre de aplicación existe dos veces, solo aparece una de las aplicaciones en el portal de empresa.
- **Descripción**: escriba una descripción de la aplicación. La descripción aparece en el portal de empresa.
- **Publicador**: Escriba el nombre del publicador de la aplicación.
- **Categoría**: seleccione una o varias de las categorías de aplicaciones integradas o seleccione una categoría que haya creado. Las categorías facilitan a los usuarios encontrar la aplicación cuando exploran el portal de empresa.
- **Mostrar como aplicación destacada en el Portal de empresa**: Muestra la aplicación de forma destacada en la página principal del portal de empresa cuando los usuarios buscan aplicaciones.
- **Dirección URL de información**: Opcionalmente, escriba la dirección URL de un sitio web que contenga información sobre esta aplicación. La dirección URL aparece en el portal de empresa.
- **Dirección URL de privacidad**: Opcionalmente, escriba la dirección URL de un sitio web que contenga información de privacidad sobre esta aplicación. La dirección URL aparece en el portal de empresa.
- **Desarrollador**: opcionalmente, escriba el nombre del desarrollador de la aplicación.
- **Propietario**: opcionalmente, escriba un nombre para el propietario de esta aplicación. Un ejemplo es **Departamento de Recursos Humanos**.
- **Notas**: escriba las notas que desea asociar a esta aplicación.
- **Logotipo**: cargue un icono que esté asociado a la aplicación. Este icono se muestra con la aplicación cuando los usuarios examinan el portal de empresa.

Seleccione **Siguiente** para mostrar la página **Programa**.

## <a name="step-2-program"></a>Paso 2: Programa

En la página **Programa**, configure los comandos de instalación y eliminación para la aplicación:

- **Comando de instalación**: Para instalar la aplicación, agregue la línea de comandos para completar la instalación. 

    Por ejemplo, si el nombre de archivo de la aplicación es **MyApp123**, agregue lo siguiente:

    `msiexec /p "MyApp123.msp"`
    
    Si la aplicación es `ApplicationName.exe`, el comando sería el nombre de la aplicación seguido de los argumentos del comando (modificadores) que admita el paquete. Por ejemplo:

    `ApplicationName.exe /quiet`
    
    En el comando anterior, el paquete `ApplicationName.exe` admite el argumento de comando `/quiet`. 
    
    Para conocer los argumentos específicos que admite el paquete de aplicación, póngase en contacto con el proveedor de la aplicación.

    > [!IMPORTANT]
    > Los administradores deben tener cuidado al usar las herramientas de comandos. Se pueden pasar comandos inesperados o perjudiciales a través de los campos **Comando de instalación** y **Comando de desinstalación**.

- **Comando de desinstalación**: agregue la línea de comandos completa para desinstalar la aplicación por su GUID. 

    Por ejemplo:
    
    `msiexec /x "{12345A67-89B0-1234-5678-000001000000}"`

- **Comportamiento de instalación**: establezca el comportamiento de instalación en **Sistema** o **Usuario**.

    > [!NOTE]
    > Puede configurar una aplicación Win32 para instalarla en un contexto de **usuario** o **sistema**. El contexto de **usuario** solo hace referencia a un usuario determinado. El contexto de **sistema** hace referencia a todos los usuarios de un dispositivo Windows 10.
    >
    > Los usuarios no tienen que iniciar sesión en el dispositivo para instalar las aplicaciones Win32.
    > 
    > La instalación y desinstalación de las aplicaciones Win32 tiene lugar de acuerdo con el privilegio de administración (de manera predeterminada) cuando la aplicación está establecida para instalarse en el contexto del usuario y el usuario del dispositivo tiene privilegios de administración.
    
- **Comportamiento de reinicio de dispositivo**: Seleccione una de las siguientes opciones:
    - **Determinar comportamiento en función de códigos de retorno**: elija esta opción para reiniciar el dispositivo en función de los códigos de retorno.
    - **Ninguna acción específica**: elija esta opción para suprimir los reinicios de dispositivos durante la instalación de aplicaciones basadas en MSI.
    - **La instalación de la aplicación puede forzar un reinicio del dispositivo**: elija esta opción para permitir que la instalación de la aplicación finalice sin suprimir los reinicios.
    - **Intune forzará un reinicio obligatorio del dispositivo**: elija esta opción para reiniciar siempre el dispositivo después de una instalación correcta de la aplicación.

- **Especifique códigos de retorno para indicar el comportamiento posterior a la instalación**: agregue los códigos de retorno que se usan para especificar el comportamiento de reintento de instalación de la aplicación o el comportamiento posterior a la instalación. Las entradas del código de retorno se agregan de forma predeterminada durante la creación de la aplicación. Sin embargo, puede agregar más códigos de retorno o cambiar los existentes.
    1. En la columna **Tipo de código**, establezca el **Tipo de código** en una de las opciones siguientes:
        - **Error**: valor devuelto que indica un error de instalación de la aplicación.
        - **Reinicio en frío**: el código de retorno del reinicio en frío no permite que se instalen más aplicaciones Win32 en el cliente sin llevar a cabo un reinicio. 
        - **Reinicio en caliente**: el código de retorno del reinicio en caliente permite que la siguiente aplicación Win32 se instale sin que el cliente se tenga que reiniciar. Es necesario llevar a cabo un reinicio para completar la instalación de la aplicación actual.
        - **Reintentar**: el agente de código de retorno de reintento intentará instalar la aplicación tres veces, con un intervalo de cinco minutos entre un intento y el siguiente. 
        - **Correcto**: el valor devuelto que indica que la aplicación se ha instalado correctamente.
    2. Si es necesario, seleccione **Agregar** para agregar más códigos de retorno o modificar los existentes.

Seleccione **Siguiente** para mostrar la página **Requisitos**.    

## <a name="step-3-requirements"></a>Paso 3: Requisitos

En la página **Requisitos**, especifique los requisitos que deben cumplir los dispositivos antes de instalar la aplicación:

- **Arquitectura del sistema operativo**: elija las arquitecturas necesarias para instalar la aplicación.
- **Versión mínima del sistema operativo**: seleccione el sistema operativo necesario para instalar la aplicación.
- **Espacio en disco necesario (MB)** : también puede agregar el espacio libre en disco necesario en la unidad del sistema para instalar la aplicación.
- **Memoria física requerida (MB)** : también puede agregar la memoria física (RAM) necesaria para instalar la aplicación.
- **Número mínimo de procesadores lógicos necesarios**: también puede agregar el número mínimo de procesadores lógicos necesarios para instalar la aplicación.
- **Velocidad de CPU mínima requerida (MHz)** : opcionalmente, puede agregar la velocidad de CPU mínima necesaria para instalar la aplicación.
- **Configurar reglas de requisitos adicionales**: 
    1. Seleccione **Agregar** para mostrar el panel **Agregar una regla de requisitos** y configurar más reglas de requisitos. Seleccione el valor **Tipo de requisito** para elegir el tipo de regla que se va a utilizar para determinar cómo se valida un requisito. Las reglas de requisitos se pueden basar en la información del sistema de archivos, los valores del Registro o los scripts de PowerShell. 
        - **Archivo**: cuando se elige **Archivo** como **Tipo de requisito**, la regla de requisitos debe detectar un archivo o carpeta, la fecha, la versión o el tamaño. 
            - **Ruta de acceso**: ruta de acceso completa de la carpeta que contiene el archivo o la carpeta que se va a detectar.
            - **Archivo o carpeta**: el archivo o la carpeta que se va a detectar.
            - **Propiedad**: seleccione el tipo de regla usado para validar la presencia de la aplicación.
            - **Asociado a una aplicación de 32 bits en clientes de 64 bits**: seleccione **Sí** para expandir cualquier variable de entorno de ruta de acceso del contexto de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para expandir cualquier variable de ruta de acceso en el contexto de 64 bits en clientes de 64 bits. Los clientes de 32 bits siempre usan el contexto de 32 bits.
        - **Registro**: cuando se elige **Registro** como **Tipo de requisito**, la regla de requisitos debe detectar una configuración del Registro en función del valor, la cadena, el entero o la versión.
            - **Ruta de acceso de la clave**: la ruta de acceso completa de la entrada del Registro que contiene el valor que se va a detectar.
            - **Nombre de valor**: el nombre del valor del Registro que se va a detectar. Si este valor está vacío, la detección se realizará en la clave. El valor (predeterminado) de una clave se usará como valor de detección si el método de detección no es la existencia del archivo o de la carpeta.
            - **Requisito de clave de registro**: seleccione el tipo de comparación de la clave del Registro utilizado para determinar cómo se valida la regla de requisitos.
            - **Asociado a una aplicación de 32 bits en clientes de 64 bits**: seleccione **Sí** (valor predeterminado) para buscar el registro de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para buscar el registro de 64 bits en clientes de 64 bits. Los clientes de 32 bits siempre buscan el registro de 32 bits.
        - **Script**: elija **Script** como valor de **Tipo de requisito** cuando no se pueda crear una regla de requisitos basada en un archivo, el Registro o cualquier otro método disponible en la consola de Intune.
            - **Archivo de script**: en el caso de una regla basada en un requisito de script de PowerShell, si el código existente es 0, la salida estándar (STDOUT) se detectará con más detalle. Por ejemplo, podemos detectar STDOUT como un entero que tiene un valor de 1.
            - **Ejecutar script como proceso de 32 bits en clientes de 64 bits**: seleccione **Sí** para ejecutar el script en un proceso de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para ejecutar el script en un proceso de 64 bits en clientes de 64 bits. Los clientes de 32 bits ejecutan el script en un proceso de 32 bits.
            - **Ejecutar este script con las credenciales de inicio de sesión**: seleccione **Sí** para ejecutar el script mediante las credenciales del dispositivo que ha iniciado la sesión.
            - **Exigir comprobación de firma del script**: seleccione **Sí** para comprobar que un editor de confianza ha firmado el script, lo que permitirá que este se ejecute sin que se muestren mensajes ni advertencias. El script se ejecutará desbloqueado. Seleccione **No** (valor predeterminado) para ejecutar el script con una confirmación del usuario sin comprobación de firmas.
            - **Seleccionar los tipos de datos de salida**: seleccione el tipo de datos que se usa para determinar la coincidencia con una regla de requisitos.
    2. Cuando haya terminado de establecer las reglas de requisitos, seleccione **Aceptar**.

Seleccione **Siguiente** para mostrar la página **Reglas de detección**. 

## <a name="step-4-detection-rules"></a>Paso 4: Reglas de detección

En la página **Reglas de detección**, configure las reglas para detectar la presencia de la aplicación:
    
- **Formato de las reglas**: seleccione cómo se detectará la presencia de la aplicación. Puede optar por configurar manualmente las reglas de detección o por usar un script personalizado para detectar la presencia de la aplicación. Debe elegir una regla de detección como mínimo. 

  > [!NOTE]
  > En el panel **Reglas de detección**, puede agregar varias reglas. Deben cumplirse las condiciones de *todas* las reglas para detectar la aplicación.
  >
  > Si Intune detecta que la aplicación no está presente en el dispositivo, Intune le ofrecerá de nuevo la aplicación después de 24 horas. Esto solo se producirá en el caso de aplicaciones dirigidas con la intención requerida.

- **Configurar manualmente las reglas de detección**: puede seleccionar una de los siguientes tipos de reglas:
    - **MSI**: verificación basada en una comprobación de la versión de MSI. Esta opción solo puede agregarse una vez. Al elegir este tipo de regla, tiene dos opciones:
        - **Código de producto de MSI**: agregue un código de producto de MSI válido para la aplicación.
        - **Comprobación de versión del producto MSI**: seleccione **Sí** para comprobar la versión del producto MSI junto con su código correspondiente.
    - **Archivo**: comprobación basada en la fecha, la versión, el tamaño o la detección de la carpeta o del archivo.
        - **Ruta de acceso**: escriba la ruta de acceso completa de la carpeta que contiene el archivo o la carpeta que se van a detectar.
        - **Archivo o carpeta**: escriba el archivo o la carpeta que se van a detectar.
        - **Método de detección**: seleccione el tipo de método de detección que se usa para validar la presencia de la aplicación.
        - **Asociado a una aplicación de 32 bits en clientes de 64 bits**: seleccione **Sí** para expandir cualquier variable de entorno de ruta de acceso del contexto de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para expandir cualquier variable de ruta de acceso en el contexto de 64 bits en clientes de 64 bits. Los clientes de 32 bits siempre usan el contexto de 32 bits.
            
        **Ejemplos de detección basada en archivos**

        Compruebe que el archivo existe.
         
        ![Captura de pantalla del panel Regla de detección: existencia del archivo.](./media/apps-win32-app-management/apps-win32-app-03.png)
        
        Compruebe que la carpeta existe.
        
        ![Captura de pantalla del panel Regla de detección: existencia de la carpeta.](./media/apps-win32-app-management/apps-win32-app-04.png)
        
    - **Registro**: comprobación basada en el valor, la cadena, el entero o la versión.
        - **Ruta de acceso de la clave**: la ruta de acceso completa de la entrada del Registro que contiene el valor que se va a detectar. Una sintaxis válida es HKEY_LOCAL_MACHINE\Software\WinRAR o HKLM\Software\WinRAR.
        - **Nombre de valor**: el nombre del valor del Registro que se va a detectar. Si este valor está vacío, la detección se realizará en la clave. El valor (predeterminado) de una clave se usará como valor de detección si el método de detección no es la existencia del archivo o de la carpeta.
        - **Método de detección**: seleccione el tipo de método de detección que se usa para validar la presencia de la aplicación.
        - **Asociado a una aplicación de 32 bits en clientes de 64 bits**: seleccione **Sí** (valor predeterminado) para buscar el registro de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para buscar el registro de 64 bits en clientes de 64 bits. Los clientes de 32 bits siempre buscan el registro de 32 bits.
            
        **Ejemplos para la detección basada en registros**
        
        compruebe si existe la clave del Registro.
            
        ![Captura de pantalla del panel Regla de detección: la clave del Registro existe.](./media/apps-win32-app-management/apps-win32-app-05.png)    
            
        Compruebe si existe el valor del Registro.
        
        ![Captura de pantalla del panel Regla de detección: el valor del Registro existe.](./media/apps-win32-app-management/apps-win32-app-06.png)    
        
        Compruebe si la cadena de valores de registro son iguales.
        
        ![Captura de pantalla del panel Regla de detección: la cadena del valor del Registro es igual.](./media/apps-win32-app-management/apps-win32-app-07.png)    
     
- **Usar un script de detección personalizado**: especifique el script de PowerShell que se usará para detectar esta aplicación. 
    
   - **Archivo de script**: seleccione un script de PowerShell que detectará la presencia de la aplicación en el cliente. La aplicación se detectará cuando el script devuelva un código de salida de valor **0** y escriba un valor de cadena en STDOUT.

   - **Ejecutar script como proceso de 32 bits en clientes de 64 bits**: seleccione **Sí** para ejecutar el script en un proceso de 32 bits en clientes de 64 bits. Seleccione **No** (valor predeterminado) para ejecutar el script en un proceso de 64 bits en clientes de 64 bits. Los clientes de 32 bits ejecutan el script en un proceso de 32 bits.

   - **Exigir comprobación de firma del script**: seleccione **Sí** para comprobar que un editor de confianza ha firmado el script, lo que permitirá que este se ejecute sin que se muestren mensajes ni advertencias. El script se ejecutará desbloqueado. Seleccione **No** (valor predeterminado) para ejecutar el script con una confirmación del usuario sin comprobación de firmas.
    
   El agente de Intune comprueba los resultados del script. Lee los valores escritos por el script en la secuencia de STDOUT, la secuencia de error estándar (STDERR) y el código de salida. Si el script sale con un valor distinto de cero, se produce un error en el script y el estado de detección de la aplicación es no instalada. Si el código de salida es cero y STDOUT contiene datos, el estado de detección de la aplicación es "Instalada". 

   > [!NOTE]
   > Se recomienda codificar el script como UTF-8. Cuando el script existe con el valor de **0**, significa que el script se ha ejecutado correctamente. El segundo canal de salida indica que se ha detectado la aplicación. Los datos de STDOUT indican que la aplicación se encontró en el cliente. No se busca una cadena concreta de STDOUT.

Cuando haya agregado las reglas, seleccione **Siguiente** para mostrar la página **Dependencias**.

## <a name="step-5-dependencies"></a>Paso 5: Dependencias

Las dependencias de aplicaciones son aplicaciones que se deben instalar antes de que se puede instalar la aplicación Win32. Se puede requerir que otras aplicaciones estén instaladas como dependencias. 

En concreto, el dispositivo debe instalar las aplicaciones dependientes antes de que se instale la aplicación Win32. Hay un máximo de 100 dependencias, que incluye las dependencias de cualquier dependencia incluida, así como la propia aplicación. 

Se pueden agregar las dependencias de aplicaciones Win32 solo después de que se haya agregado y cargado la aplicación Win32 en Intune. Una vez agregada la aplicación Win32, verá la opción **Dependencias** en el panel de dicha aplicación. 

Cualquier dependencia de la aplicación Win32 debe ser también una aplicación Win32. No se admite la dependencia de otros tipos de aplicaciones, como aplicaciones de línea de negocio MSI o aplicaciones de Microsoft Store.

Al agregar una dependencia de aplicación, puede realizar búsquedas por el nombre y el editor de la aplicación. Asimismo, se pueden ordenar las dependencias que se han agregado en función del nombre y editor de la aplicación. Las dependencias de aplicaciones agregadas anteriormente no se pueden seleccionar en la lista de dependencias de aplicaciones agregadas. 

Puede elegir si quiere instalar de forma automática o no cada aplicación dependiente. De forma predeterminada, la opción **Instalación automática** está establecida en **Sí** para cada dependencia. Al instalar automáticamente una aplicación dependiente, incluso si dicha aplicación dependiente no está destinada al usuario o dispositivo, Intune instalará la aplicación en el dispositivo para satisfacer la dependencia antes de instalar la aplicación Win32. 

Es importante tener en cuenta que una dependencia puede tener dependencias secundarias recurrentes, y que cada dependencia secundaria se instalará antes de instalarse la dependencia principal. Además, la instalación de dependencias no sigue un orden específico en un nivel de dependencia.

### <a name="select-the-dependencies"></a>Selección de las dependencias

En la página **Dependencias**, seleccione las aplicaciones que se deben instalar antes de que se pueda instalar la aplicación Win32:
1. Seleccione **Agregar** para mostrar el panel **Agregar dependencia**.
3. Agregue las aplicaciones dependientes y, luego, haga clic en **Seleccionar**.
4. Elija si quiere instalar automáticamente las aplicaciones dependientes seleccionando **Sí** o **No** en la columna **Instalación automática**.

Después de seleccionar las dependencias, elija **Siguiente** para mostrar la página **Etiquetas de ámbito**.

### <a name="understand-additional-dependency-details"></a>Descripción de detalles de dependencia adicionales

El usuario verá las notificaciones del sistema de Windows que indican que las aplicaciones dependientes se van a descargar e instalar como parte del proceso de instalación de la aplicación Win32. Además, si una aplicación dependiente no está instalada, el usuario verá con frecuencia una de las notificaciones siguientes:
- No se han podido instalar una o varias aplicaciones dependientes.
- No se han cumplido uno o varios de los requisitos de las aplicaciones dependientes.
- Una o varias aplicaciones dependientes están pendientes de un reinicio del dispositivo.

Si decide no colocar una dependencia en la columna **Instalar automáticamente**, no se intentará la instalación de la aplicación Win32. Asimismo, los informes de aplicaciones mostrarán que la dependencia se ha marcado como `failed` y proporcionarán un motivo del error. Para ver el error en la instalación de la dependencia, seleccione uno de los errores (o advertencia) proporcionados en los [detalles de instalación](troubleshoot-app-install.md#win32-app-installation-troubleshooting) de la aplicación Win32.

Cada dependencia se ajustará a la lógica de reintento de las aplicaciones Win32 de Intune (tres intentos de instalación después de esperar cinco minutos) y a la programación de reevaluación global. Además, las dependencias solo son aplicables en el momento de la instalación de la aplicación Win32 en el dispositivo. Las dependencias no son aplicables para desinstalar una aplicación Win32. Para eliminar una dependencia, debe seleccionar el botón de puntos suspensivos (tres puntos) a la izquierda de la aplicación dependiente que se encuentra al final de la fila de la lista de dependencias. 

## <a name="step-6-select-scope-tags-optional"></a>Paso 6: Selección de Etiquetas de ámbito (opcional)
Puede usar las etiquetas de ámbito para determinar quién puede ver información de la aplicación cliente en Intune. Para obtener más información sobre las etiquetas de ámbito, consulte [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Uso del control de acceso basado en roles y de las etiquetas de ámbito para la TI distribuida).

Si quiere, haga clic en **Seleccionar etiquetas de ámbito** para agregar etiquetas de ámbito para la aplicación. Luego, seleccione **Siguiente** para abrir la página **Asignaciones**.

## <a name="step-7-assignments"></a>Paso 7: Assignments

Puede seleccionar las asignaciones de grupo **Requerido**, **Disponible para dispositivos inscritos** o **Desinstalar** para la aplicación. Para más información, consulte [Agregar grupos para organizar usuarios y dispositivos](../fundamentals/groups-add.md) y [Asignación de aplicaciones a grupos con Microsoft Intune](apps-deploy.md).

1. Para la aplicación específica, seleccione un tipo de asignación:
    - **Requerido**: la aplicación se instala en los dispositivos de los grupos seleccionados.
    - **Disponible para dispositivos inscritos**: los usuarios instalan la aplicación desde la aplicación o el sitio web del Portal de empresa.
    - **Desinstalar**: la aplicación se desinstala de dispositivos de los grupos seleccionados.
2. Seleccione **Agregar grupo** y asigne los grupos que usarán esta aplicación.
3. En el panel **Seleccionar grupos**, seleccione los grupos que se asignarán en función de los usuarios o los dispositivos.
4. Después de haber seleccionado los grupos, también puede establecer las opciones **Notificaciones del usuario final**, **Disponibilidad** y **Fecha límite de instalación**. Para más información, consulte [Establecimiento de la disponibilidad y las notificaciones de las aplicaciones Win32](apps-win32-app-management.md#set-win32-app-availability-and-notifications).
5. Si no quiere que esta asignación de aplicaciones afecte a los grupos de usuarios, seleccione **Incluido** en la columna **MODO**. En el panel **Editar asignación**, cambie el valor de **modo** de **Incluido** a **Excluido**. Seleccione **Aceptar** para cerrar el panel **Editar asignación**.
6. En la sección **Configuración de la aplicación**, seleccione el valor de **Prioridad de optimización de distribución** de la aplicación. Esta configuración determinará cómo se descargará el contenido de la aplicación. Puede optar por descargar el contenido de la aplicación en segundo plano o en primer plano en función de la asignación. 

Cuando termine de configurar las asignaciones de las aplicaciones, seleccione **Siguiente** para mostrar la página **Revisar y crear**.

## <a name="step-8-review-and-create"></a>Paso 8: Revisión y creación

1. Revise los valores y la configuración que especificó para la aplicación. Compruebe que configuró correctamente la información de la aplicación.
2. Seleccione **Crear** para agregar la aplicación a Intune.

    Aparece el panel **Información general** de la aplicación de línea de negocio.

Llegados a este punto, ya ha finalizado los pasos para agregar una aplicación Win32 a Intune. Para obtener información sobre la supervisión y la asignación de aplicaciones, vea [Asignación de aplicaciones a grupos con Microsoft Intune](apps-deploy.md) y [Supervisión de información y asignaciones de aplicaciones con Microsoft Intune](apps-monitor.md).

## <a name="next-steps"></a>Pasos siguientes

- [Supervisión de información y asignaciones de aplicaciones con Microsoft Intune](apps-monitor.md)
- [Solucionar los problemas de aplicaciones Win32](apps-win32-troubleshoot.md)
