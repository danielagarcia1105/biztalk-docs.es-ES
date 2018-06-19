---
title: 'Paso 1: Utilizar el Asistente para desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de eco | Documentos de Microsoft'
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
ms.openlocfilehash: ffad8f817cf3a13b3d3af3264438bafa639181a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227332"
---
# <a name="step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter-project"></a>Paso 1: Utilizar al Asistente para desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de eco
![Paso 1 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")  
  
 **Tiempo en completarse:** 15 minutos  
  
 En este paso, creará un proyecto con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] le guiará a través de los pasos necesarios para desarrollar un adaptador personalizado para el sistema. Recopila información sobre los patrones de intercambio de mensajes, funciones de metadatos, propiedades del adaptador y propiedades de conexión. Una vez que el asistente se complete correctamente, genera un conjunto de archivos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe poseer el conocimiento que se describe en [antes de empezar el Tutorial](../../core/before-you-begin-the-tutorial.md) y ha configurado correctamente el equipo para el desarrollo de adaptadores mediante el uso de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
## <a name="choose-wcf-lob-adapter-plug-in-in-visual-studio"></a>Elija el adaptador LOB de WCF complemento en Visual Studio  
  
1.  Inicie Visual Studio y, a continuación, en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **adaptador LOB de WCF**.|  
    |**Nombre**|Tipo de **EchoAdapter**.|  
    |**Ubicación**|Tipo de **C:\Tutorials**.|  
    |**Crear directorio para la solución**|Seleccione esta casilla para crear un directorio para los archivos de la solución.|  
    |**Nombre de solución**|Tipo de **EchoAdapterSampleV2**.|  
  
     La siguiente ilustración muestra la **nuevo proyecto** cuadro de diálogo.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3a349be4-1a7d-480a-8e9d-cfcba63cd14a.gif "3a349be4-1a7d-480a-8e9d-cfcba63cd14a")  
  
3.  Haga clic en **Aceptar**.  
  
4.  En el **bienvenida** página, haga clic en **siguiente**. La siguiente ilustración muestra la **bienvenida** página.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0b8ef97f-044d-481f-8c7c-0d034fdba37d.gif "0b8ef97f-044d-481f-8c7c-0d034fdba37d")  
  
5.  Haga clic en **Siguiente**.  
  
## <a name="enter-the-scheme-and-namespace-information"></a>Escriba la información de esquema y espacio de nombres  
  
1.  En el **esquema, Namespace y la información del identificador URI** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Esquema**|Tipo de **echov2**.|  
    |**Espacio de nombres de proyecto**|Tipo de **Microsoft.Adapters.Samples.EchoV2**.|  
  
     La siguiente ilustración muestra la **esquema, Namespace y la información del identificador URI** página.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0d72dab2-7992-47e4-bc4e-3e720b1cde38.gif "0d72dab2-7992-47e4-bc4e-3e720b1cde38")  
  
2.  Haga clic en **Siguiente**.  
  
## <a name="enter-the-data-flow-and-metadata-features"></a>Especifique las características de metadatos y el flujo de datos  
  
1.  En el **datos fluyen** y **funciones de metadatos** página, realice lo siguiente:  
  
     **Patrones de intercambio de mensajes**  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Sincrónico saliente**|Active la casilla de verificación.|  
    |**Sincrónico entrante**|Active la casilla de verificación.|  
  
     **Funciones de metadatos**  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Recuperación**|Active la casilla de verificación.|  
    |**Examinar**|Active la casilla de verificación.|  
    |**Buscar**|Active la casilla de verificación.|  
  
    > [!NOTE]
    >  Flujos de datos en este contexto significa lo mismo que patrones de intercambio de mensajes, el término que se usa en los temas conceptuales.  
  
     La siguiente ilustración muestra la **datos fluyen** y **funciones de metadatos** página.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/4fa6f67d-4703-41db-b5f3-28cf9d6a40d2.gif "4fa6f67d-4703-41db-b5f3-28cf9d6a40d2")  
  
2.  Haga clic en **Siguiente**.  
  
## <a name="enter-the-adapter-properties"></a>Escriba las propiedades del adaptador  
  
1.  En el **propiedades del adaptador** página, realice lo siguiente:  
  
2.  Agregue una propiedad denominada **recuento**. Este número se usa por todas las operaciones del adaptador de eco. Cada operación devolverá el valor de entrada del **recuento** número de veces.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **recuento**.|  
    |**Tipo de datos**|Seleccione **System.Int32**.|  
    |**Valor predeterminado**|Tipo de **5**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
3.  Agregue una propiedad denominada **EnableConnectionPooling**. Esta marca se usa por la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para habilitar o deshabilitar la agrupación de conexiones en tiempo de ejecución.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **EnableConnectionPooling**.|  
    |**Tipo de datos**|Seleccione **System.Boolean**.|  
    |**Valor predeterminado**|Tipo de **true**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
4.  Agregue una propiedad denominada **InboundFileFilter**. Esta propiedad se utiliza por la clase FileSystemWatcher para supervisar los archivos de esta extensión. Esta propiedad es aplicable para el escenario de entrada.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **InboundFileFilter**.|  
    |**Tipo de datos**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo de  **\*.txt**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
5.  Agregue una propiedad denominada **InboundFileSystemWatcherFolder**. Esta propiedad se usa para establecer la carpeta donde se colocarán los archivos para que FileSystemWatcher generar la notificación al adaptador. Esta propiedad es aplicable para el escenario de entrada.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **InboundFileSystemWatcherFolder**.|  
    |**Tipo de datos**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo de **C:\\\inbound\\\watcher**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
     La siguiente ilustración muestra la **propiedades del adaptador** página.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/84de11a5-a737-4aa5-96c8-61922e704f2b.gif "84de11a5-a737-4aa5-96c8-61922e704f2b")  
  
6.  Haga clic en **Siguiente**.  
  
## <a name="enter-the-connection-properties"></a>Especifique las propiedades de conexión  
  
1.  En el **propiedades de conexión** página, realice lo siguiente:  
  
2.  Agregue una propiedad denominada **aplicación**. Esta propiedad es solo con fines ilustrativos. El adaptador de eco no implica ningún sistema LOB.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **aplicación**.|  
    |**Tipo de datos**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo de **lobapplication**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
3.  Agregue una propiedad denominada **EnableAuthentication**. Cuando `true`, el adaptador espera un valor en el campo de nombre de usuario dentro de las credenciales del cliente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **EnableAuthentication**.|  
    |**Tipo de datos**|Seleccione **System.Boolean**.|  
    |**Valor predeterminado**|Tipo de **false**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
4.  Agregue una propiedad denominada **HostName**. Esta propiedad es solo con fines ilustrativos es similar a la propiedad **aplicación**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **Hostname**.|  
    |**Tipo de datos**|Seleccione **System.String**.|  
    |**Valor predeterminado**|Tipo de **lobhostname**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
5.  Agregue una propiedad denominada **EchoInUpperCase**. Esta propiedad controla si convierten algunas operaciones muestra las cadenas en mayúsculas o dejarlos en su formato original.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de la propiedad**|Tipo de **EchoInUpperCase**.|  
    |**Tipo de datos**|Seleccione **System.Boolean**.|  
    |**Valor predeterminado**|Tipo de **False**.|  
    |**Agregar**|Haga clic para agregar la nueva propiedad de adaptador.|  
  
6.  Haga clic en **Siguiente**.  
  
## <a name="end-the-wizard"></a>Finalice el Asistente  
  
1.  En el **resumen** página, haga clic en **finalizar**. La siguiente ilustración muestra **el Explorador de soluciones** con el **EchoAdapter** proyecto.  
  
     ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/06b45c3e-d056-48f4-a246-642d9ac5e23e.gif "06b45c3e-d056-48f4-a246-642d9ac5e23e")  
  
     El proyecto debe contener los mismos archivos. Si no es así, salga de Visual Studio, elimine la **EchoAdapterSampleV2** carpeta y, a continuación, reinicie este paso del tutorial.  
  
2.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
    > [!NOTE]
    >  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso, se crea la solución del adaptador de eco mediante Visual Studio y la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]. En la tabla siguiente contiene el conjunto de archivos y qué es cada archivo.  
  
|**Nombre de archivo**|**Description**|  
|-------------------|---------------------|  
|EchoAdapter.cs|Ésta es la clase de adaptador principal que se hereda de `Microsoft.ServiceModel.Channels.Common.Adapter`.<br /><br /> No hay cambios son necesarios para el adaptador de eco.|  
|EchoAdapterBinding.cs|Se trata de la clase que se usa al crear un enlace para un adaptador.<br /><br /> No hay cambios son necesarios para el adaptador de eco.|  
|EchoAdapterBindingCollectionElement.cs|Ésta es la clase de elemento de la colección de enlace que implementa el `System.ServiceModel.Configuration.StandardBindingCollectionElement`.<br /><br /> No hay cambios son necesarios para el adaptador de eco.|  
|EchoAdapterBindingElement.cs|Esto proporciona una clase base para los elementos de configuración.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de eco, siga [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterBindingElementExtensionElement.cs|Esta clase se proporciona para representar el adaptador como un elemento de enlace, por lo que se puede utilizar dentro de un enlace personalizado de WCF definido por el usuario.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de eco, siga [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterHandlerBase.cs|Se trata de la clase base para los controladores que se usa para almacenar las funciones comunes de propiedades/auxiliar expuestas por la clase base.<br /><br /> Para clasificar las propiedades de adaptador y la conexión del adaptador de eco, siga [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).|  
|EchoAdapterConnection.cs|Esto define la conexión al sistema de destino.<br /><br /> Para admitir la conexión del adaptador de eco al sistema de destino, siga [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).|  
|EchoAdapterConnectionFactory.cs|Esto define el generador de conexiones para el sistema de destino.<br /><br /> Para admitir la conexión del adaptador de eco al sistema de destino, siga [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).|  
|EchoAdapterConnectionUri.cs|Se trata de la clase para representar un Uri de conexión del adaptador.<br /><br /> Para admitir la conexión del adaptador de eco al sistema de destino, siga [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)).|  
|EchoAdapterMetadataBrowseHandler.cs|Esta clase se utiliza al realizar una exploración según la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir la capacidad para el adaptador de eco de exploración de metadatos, siga [paso 4: implementar el controlador de examinar de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).|  
|EchoAdapterMetadataSearchHandler.cs|Esta clase se utiliza para realizar una búsqueda según la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir los metadatos de búsqueda de capacidad para el adaptador de eco, siga [paso 5: implementar el controlador de búsqueda de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).|  
|EchoAdapterMetadataResolve.cs|Esta clase se utiliza para realizar una recuperación según la conexión de metadatos desde el sistema de destino.<br /><br /> Para admitir los metadatos de resolución de capacidad para el adaptador de eco, siga [paso 6: implementar el controlador de resolver metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).|  
|EchoAdapterOutboundHandler.cs|Esta clase se utiliza para enviar datos al sistema de destino.<br /><br /> Para admitir el intercambio de mensajes salientes para el adaptador de eco, siga [paso 7: implementar el controlador de salida sincrónica para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).|  
|EchoAdapterInboundHandler.cs|Esta clase implementa una interfaz para la escucha o sondeo para los datos.<br /><br /> Para admitir el intercambio de mensajes entrantes para el adaptador de eco, siga [paso 8: implementar el controlador de entrada sincrónica para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).|  
|EchoAdapterTrace.cs|Esta clase implementa el seguimiento del adaptador, para la depuración y solución de problemas.|  
  
## <a name="next-steps"></a>Pasos siguientes  
 Clasificar las propiedades de conexión y el adaptador para su agrupación lógica de la interfaz de usuario y, a continuación, implemente la conexión, explorar metadatos, buscar y resolver las capacidades y los intercambios de mensajes entrantes y salientes. Por último, generará e implementará el adaptador de eco.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Clasificar los adaptadores y las propiedades de conexión](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)   
 [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)