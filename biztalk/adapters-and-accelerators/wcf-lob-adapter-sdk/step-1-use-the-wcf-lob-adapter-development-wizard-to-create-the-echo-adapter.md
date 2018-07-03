---
title: 'Paso 1: Usar el Asistente para desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de Echo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 634a6498-55b0-462d-a5ca-16507b3787f5
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b55bdfe771eb571a999668fc8ef7d2003ddf56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976917"
---
# <a name="step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter-project"></a>Paso 1: Usar al Asistente para desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de Echo
![Paso 1 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  

 **Tiempo en completarse:** 15 minutos  

 En este paso, creará un proyecto con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] le guiará a través de los pasos necesarios para desarrollar un adaptador personalizado para el sistema. Recopila información sobre los patrones de intercambio de mensajes, funciones de metadatos, las propiedades de adaptador y las propiedades de conexión. Una vez que el asistente finalice correctamente, genera un conjunto de archivos.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe poseer el conocimiento que se describe en [antes de comenzar el Tutorial](../../core/before-you-begin-the-tutorial.md) y configurado correctamente el equipo para el desarrollo de adaptadores mediante el uso de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  

## <a name="choose-wcf-lob-adapter-plug-in-in-visual-studio"></a>Elija el adaptador LOB de WCF complemento en Visual Studio  

1.  Inicie Visual Studio y, a continuación, en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  

2.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **adaptador LOB de WCF**.|  
    |**Nombre**|Tipo **EchoAdapter**.|  
    |**Ubicación**|Tipo **C:\Tutorials**.|  
    |**Crear directorio para la solución**|Seleccione esta casilla para crear un directorio para los archivos de la solución.|  
    |**Nombre de solución**|Tipo **EchoAdapterSampleV2**.|  

     La siguiente ilustración muestra el **nuevo proyecto** cuadro de diálogo.  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3a349be4-1a7d-480a-8e9d-cfcba63cd14a.gif "3a349be4-1a7d-480a-8e9d-cfcba63cd14a")  

3.  Haga clic en **Aceptar**.  

4.  En el **bienvenida** página, haga clic en **siguiente**. La siguiente ilustración muestra el **bienvenida** página.  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0b8ef97f-044d-481f-8c7c-0d034fdba37d.gif "0b8ef97f-044d-481f-8c7c-0d034fdba37d")  

5.  Haga clic en **Siguiente**.  

## <a name="enter-the-scheme-and-namespace-information"></a>Escriba la información de esquema y espacio de nombres  

1.  En el **esquema, Namespace y la información de URI** página, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Esquema**|Tipo **echov2**.|  
    |**Espacio de nombres del proyecto**|Tipo **Microsoft.Adapters.Samples.EchoV2**.|  

     La siguiente ilustración muestra el **esquema, Namespace y la información de URI** página.  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0d72dab2-7992-47e4-bc4e-3e720b1cde38.gif "0d72dab2-7992-47e4-bc4e-3e720b1cde38")  

2.  Haga clic en **Siguiente**.  

## <a name="enter-the-data-flow-and-metadata-features"></a>Especifique las características de los metadatos y de flujo de datos  

1.  En el **fluyen los datos** y **funciones de metadatos** página, realice lo siguiente:  

     **Patrones de intercambio de mensajes**  

    |Use|Para|  
    |--------------|----------------|  
    |**Sincrónico saliente**|Seleccione la casilla de verificación.|  
    |**Sincrónico entrante**|Seleccione la casilla de verificación.|  

     **Funciones de metadatos**  

    |Use|Para|  
    |--------------|----------------|  
    |**Recuperación**|Seleccione la casilla de verificación.|  
    |**Examinar**|Seleccione la casilla de verificación.|  
    |**Buscar**|Seleccione la casilla de verificación.|  

    > [!NOTE]
    >  Los flujos de datos en este contexto significa lo mismo que los patrones de intercambio de mensajes, el término que se usa en los temas conceptuales.  

     La siguiente ilustración muestra el **fluyen los datos** y **funciones de metadatos** página.  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4fa6f67d-4703-41db-b5f3-28cf9d6a40d2.gif "4fa6f67d-4703-41db-b5f3-28cf9d6a40d2")  

2.  Haga clic en **Siguiente**.  

## <a name="enter-the-adapter-properties"></a>Escriba las propiedades del adaptador  

1. En el **propiedades del adaptador** página, realice lo siguiente:  

2. Agregar una propiedad denominada **recuento**. Este número se usa por todas las operaciones del adaptador de echo. Cada operación devolverá el valor de entrada la **recuento** veces.  


   |     Use      |               Para               |
   |-------------------|----------------------------------------|
   | **Nombre de la propiedad** |            Tipo **recuento**.             |
   |   **Data type**   |        Seleccione **System.Int32**.        |
   | **Valor predeterminado** |              Tipo **5**.               |
   |      **Agregar**      | Haga clic para agregar la nueva propiedad de adaptador. |


3. Agregar una propiedad denominada **EnableConnectionPooling**. Esta marca se usa por la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para habilitar o deshabilitar la agrupación de conexiones en tiempo de ejecución.  


   |     Use      |               Para               |
   |-------------------|----------------------------------------|
   | **Nombre de la propiedad** |   Tipo **EnableConnectionPooling**.    |
   |   **Data type**   |       Seleccione **System.Boolean**.       |
   | **Valor predeterminado** |             Tipo **true**.             |
   |      **Agregar**      | Haga clic para agregar la nueva propiedad de adaptador. |


4. Agregar una propiedad denominada **InboundFileFilter**. Esta propiedad se usa por la clase FileSystemWatcher para supervisar los archivos de esta extensión. Esta propiedad es aplicable para el escenario de entrada.  


   |     Use      |               Para               |
   |-------------------|----------------------------------------|
   | **Nombre de la propiedad** |      Tipo **InboundFileFilter**.       |
   |   **Data type**   |       Seleccione **System.String**.        |
   | **Valor predeterminado** |            Tipo  **\*.txt**.            |
   |      **Agregar**      | Haga clic para agregar la nueva propiedad de adaptador. |


5. Agregar una propiedad denominada **InboundFileSystemWatcherFolder**. Esta propiedad se usa para establecer la carpeta donde se van a quitar los archivos de FileSystemWatcher generar la notificación al adaptador. Esta propiedad es aplicable para el escenario de entrada.  

   |Use|Para|  
   |--------------|----------------|  
   |**Nombre de la propiedad**|Tipo **InboundFileSystemWatcherFolder**.|  
   |**Data type**|Seleccione **System.String**.|  
   |**Valor predeterminado**|Tipo **C:\\\inbound\\\watcher**.|  
   |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  

    La siguiente ilustración muestra el **propiedades del adaptador** página.  

    ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/84de11a5-a737-4aa5-96c8-61922e704f2b.gif "84de11a5-a737-4aa5-96c8-61922e704f2b")  

6. Haga clic en **Siguiente**.  

## <a name="enter-the-connection-properties"></a>Especifique las propiedades de conexión  

1.  En el **las propiedades de conexión** página, realice lo siguiente:  

2.  Agregar una propiedad denominada **aplicación**. Esta propiedad es solo con fines ilustrativos. El adaptador de echo no implica ningún sistema de LOB.  

    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo **aplicación**.|  
    |**Data type**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo **lobapplication**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  

3.  Agregar una propiedad denominada **EnableAuthentication**. Cuando `true`, el adaptador espera un valor en el campo de nombre de usuario dentro de las credenciales del cliente.  

    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo **EnableAuthentication**.|  
    |**Data type**|Seleccione **System.Boolean**.|  
    |**Valor predeterminado**|Tipo **false**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  

4.  Agregar una propiedad denominada **HostName**. Esta propiedad es fines ilustrativos únicamente, similar a la propiedad **aplicación**.  

    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo **Hostname**.|  
    |**Data type**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo **lobhostname**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  

5.  Agregar una propiedad denominada **EchoInUpperCase**. Esta propiedad controla si conversión algunas operaciones hacer eco de las cadenas a mayúsculas o dejarlos en su formato original.  

    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo **EchoInUpperCase**.|  
    |**Data type**|Seleccione **System.Boolean**.|  
    |**Valor predeterminado**|Tipo **False**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  

6.  Haga clic en **Siguiente**.  

## <a name="end-the-wizard"></a>Finalizar el Asistente  

1.  En el **resumen** página, haga clic en **finalizar**. La siguiente ilustración muestra **el Explorador de soluciones** con el **EchoAdapter** proyecto.  

     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/06b45c3e-d056-48f4-a246-642d9ac5e23e.gif "06b45c3e-d056-48f4-a246-642d9ac5e23e")  

     El proyecto debe contener los mismos archivos. Si no es así, salir de Visual Studio, elimine la **EchoAdapterSampleV2** carpeta y, a continuación, reinicie este paso del tutorial.  

2.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  

    > [!NOTE]
    >  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 2: clasificar las propiedades de conexión y adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).  

## <a name="what-did-i-just-do"></a>¿Qué simplemente hacer?  
 En este paso, ha creado la solución del adaptador de echo mediante Visual Studio y el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]. En la tabla siguiente contiene el conjunto de archivos y lo que cada archivo para.  

|**Nombre de archivo**|**Descripción**|  
|-------------------|---------------------|  
|EchoAdapter.cs|Esta es la clase principal del adaptador que se hereda de `Microsoft.ServiceModel.Channels.Common.Adapter`.<br /><br /> No hay cambios son necesarios para el adaptador de echo.|  
|EchoAdapterBinding.cs|Se trata de la clase se usa al crear un enlace para un adaptador.<br /><br /> No hay cambios son necesarios para el adaptador de echo.|  
|EchoAdapterBindingCollectionElement.cs|Esta es la clase de elemento de enlace de la colección que implementa el `System.ServiceModel.Configuration.StandardBindingCollectionElement`.<br /><br /> No hay cambios son necesarios para el adaptador de echo.|  
|EchoAdapterBindingElement.cs|Esto proporciona una clase base para los elementos de configuración.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de echo, siga [paso 2: clasificar las propiedades de conexión y adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterBindingElementExtensionElement.cs|Esta clase se proporciona para representar el adaptador como un elemento de enlace, por lo que se puede usar dentro de un enlace personalizado de WCF definido por el usuario.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de echo, siga [paso 2: clasificar las propiedades de conexión y adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterHandlerBase.cs|Se trata de la clase base para los controladores que se usa para almacenar las funciones comunes de las propiedades/aplicación auxiliar expuestas por la clase base.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de echo, siga [paso 2: clasificar las propiedades de conexión y adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterConnection.cs|Esto define la conexión al sistema de destino.<br /><br /> Para permitir la conexión del adaptador de echo en el sistema de destino, seguir [paso 3: implementar la conexión para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).|  
|EchoAdapterConnectionFactory.cs|Esto define el generador de conexión para el sistema de destino.<br /><br /> Para permitir la conexión del adaptador de echo en el sistema de destino, seguir [paso 3: implementar la conexión para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).|  
|EchoAdapterConnectionUri.cs|Esta es la clase para representar un Uri de conexión del adaptador.<br /><br /> Para permitir la conexión del adaptador de echo en el sistema de destino, seguir [paso 3: implementar la conexión para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)).|  
|EchoAdapterMetadataBrowseHandler.cs|Esta clase se utiliza al realizar una exploración basada en la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir la funcionalidad para el adaptador de echo de exploración de metadatos, siga [paso 4: implementar el controlador de examinar los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).|  
|EchoAdapterMetadataSearchHandler.cs|Esta clase se utiliza para realizar una búsqueda basada en la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir los metadatos de búsqueda de la capacidad para el adaptador de echo, siga [paso 5: implementar el controlador de búsqueda de metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).|  
|EchoAdapterMetadataResolve.cs|Esta clase se utiliza para realizar una recuperación basada en la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir los metadatos de resolución de capacidad para el adaptador de echo, siga [paso 6: implementar el controlador de resolver los metadatos para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).|  
|EchoAdapterOutboundHandler.cs|Esta clase se utiliza para enviar datos al sistema de destino.<br /><br /> Para admitir el intercambio de mensajes salientes para el adaptador de echo, siga [paso 7: implementar el controlador de salida sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).|  
|EchoAdapterInboundHandler.cs|Esta clase implementa una interfaz para escucha o sondeo para los datos.<br /><br /> Para admitir el intercambio de mensajes entrantes para el adaptador de echo, siga [paso 8: implementar el controlador de entrada sincrónico para el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).|  
|EchoAdapterTrace.cs|Esta clase implementa el seguimiento del adaptador, para la depuración y solución de problemas.|  

## <a name="next-steps"></a>Pasos siguientes  
 Clasificar las propiedades de adaptador y conexión para su agrupación lógica de la interfaz de usuario y, a continuación, implemente la conexión, explorar los metadatos, buscar y resolver las capacidades y los intercambios de mensajes entrantes y salientes. Por último, compilar e implementar el adaptador de echo.  

## <a name="see-also"></a>Vea también  
 [Paso 2: Clasificar el adaptador y las propiedades de conexión](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)   
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)