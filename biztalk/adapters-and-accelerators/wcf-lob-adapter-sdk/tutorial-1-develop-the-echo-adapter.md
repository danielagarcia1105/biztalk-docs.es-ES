---
title: 'Tutorial 1: Desarrollar el adaptador de eco | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffb0df3c-cd07-4bcf-af69-971065081fd6
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 484452dc4ee624f4fa41e9387098f6f792c1de28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-develop-the-echo-adapter"></a>Tutorial 1: Desarrollar el adaptador de eco
En este tutorial, desarrollará una adaptadores funcional con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. El adaptador simula las operaciones de un sistema de línea de negocio ficticio para ilustrar muchas de las características claves del SDK de adaptador LOB de WCF, incluyendo:  
  
-   Sincrónico de entrada  
  
-   Sincrónico saliente  
  
-   Exploración de metadatos  
  
-   Búsqueda de metadatos  
  
-   Resolución de metadatos  
  
 Esta sección contiene varias características admitidas por el adaptador de eco. Únicamente son intercambio de mensajes, los metadatos de operación, propiedades de conexión y propiedades del adaptador.  
  
## <a name="message-exchange-patterns"></a>Patrones de intercambio de mensajes  
 El adaptador de eco admite los siguientes patrones de intercambio de dos mensajes:  
  
-   Sincrónico salientes, es decir, el consumo cliente envía el mensaje de solicitud WCF a través del adaptador al sistema de destino y, a continuación, espera hasta recibir un mensaje de respuesta WCF desde el sistema de destino a través del adaptador. Este es el patrón de intercambio de mensajes más comunes para un adaptador. Para admitir sincrónico implemente saliente, el `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interfaz.  
  
-   Sincrónica de entrada, es decir, la escucha de cliente usado para datos o eventos del sistema de destino a través del adaptador. Para admitir el implementan entrada sincrónica la `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interfaz.  
  
 Para obtener más información acerca de los patrones de intercambio de mensajes, vea [Introducción a la arquitectura](architecture-overview-of-the-wcf-lob-adapter-sdk.md).  
  
> [!NOTE]
>  La [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] muestra el patrón de intercambio de mensajes como flujo de datos en la interfaz de usuario.  
  
## <a name="metadata-support"></a>Compatibilidad con metadatos  
 El adaptador de eco admite metadatos exploración, búsqueda y resolver las capacidades. Normalmente, la exploración y búsqueda recuperan operaciones desde un sistema LOB. Para el adaptador de eco, un sistema LOB es un conjunto de operaciones predefinidas, como se muestra a continuación:  
  
```  
EchoMainCategory  
        Echo/EchoStrings  
        Echo/EchoGreetings  
        Echo/EchoCustomGreetingFromFile  
        Echo/OnReceiveEcho  
```  
  
 La siguiente es la definición de cada operación:  
  
|**Nombre**|**Definición de operación**|**Description**|**Dirección**|  
|--------------|------------------------------|---------------------|-------------------|  
|EchoMainCategory|Categoría|Clasifica las operaciones.|N/D|  
|Eco/EchoStrings|String [] EchoStrings(string data)|Devuelve la cadena de entrada de un número especificado de veces que el cliente que realiza la llamada.|Salida|  
|Eco/EchoGreetings|Saludo [] EchoGreetings(Greeting greeting)|Devuelve el objeto de saludo un número especificado de veces que el cliente que realiza la llamada entrante.|Salida|  
|Eco/EchoCustomGreetingFromFile|CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)|Devuelve el objeto de saludo al leer su instancia de un archivo. Metadatos del objeto de saludo se obtienen desde un archivo XSD predefinido.|Salida|  
|Eco/OnReceiveEcho|void OnReceiveEcho (ruta de acceso Uri, contenido long)|Devuelve la ubicación y la longitud de un archivo que se hayan colocado en la carpeta especificada.|Entrada|  
  
## <a name="adapter-properties"></a>Propiedades de adaptador  
 El adaptador expone las siguientes propiedades del adaptador.  
  
|**Nombre**|**Categoría**|**Tipo de datos**|**Description**|  
|--------------|------------------|-------------------|---------------------|  
|Count|Varios|System.Int32|Se utiliza para hacer eco de la entrada del número de veces especificado para el cliente que realiza la llamada.<br /><br /> Valor predeterminado = 5|  
|EnableConnectionPooling|Varios|System.Boolean|Se utiliza para habilitar o deshabilitar la agrupación de conexiones para el adaptador.<br /><br /> Valor predeterminado = true, lo que significa que la agrupación de conexiones está habilitada en el motor en tiempo de ejecución de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].|  
|InboundFileFilter|Entrada|System.String|Utilizado para el escenario de entrada y utiliza la clase FileSystemWatcher para supervisar los archivos de la extensión.<br /><br /> Valor predeterminado = * .txt|  
|InboundFileSystemWatcherFolder|Entrada|System.String|Se usa para establecer la carpeta donde se colocarán los archivos para que FileSystemWatcher generar la notificación al adaptador.<br /><br /> Valor predeterminado = c:\inbound\watcher.|  
  
## <a name="connection-properties"></a>Propiedades de conexión  
 El adaptador de eco expone las siguientes propiedades de conexión.  
  
|**Nombre**|**Tipo de datos**|**Description**|  
|--------------|-------------------|---------------------|  
|Aplicación|System.String|El nombre de la aplicación dentro del sistema LOB. Esta propiedad es con propósitos ilustrativos. El adaptador de eco no implica ningún sistema LOB.<br /><br /> Valor predeterminado = lobapplication|  
|EnableAuthentication|System.Boolean|Cuando sea true, el adaptador espera un valor en el campo de nombre de usuario dentro de las credenciales del cliente.<br /><br /> Valor predeterminado = false|  
|Hostname|System.String|El nombre del servidor donde reside un sistema LOB. Esta propiedad es con propósitos ilustrativos. El adaptador de eco no implica ningún sistema LOB.<br /><br /> Valor predeterminado = lobhostname|  
  
## <a name="interface-implementation"></a>Implementación de interfaz  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] define una colección de clases e interfaces que deben implementarse para admitir características específicas del adaptador. La tabla siguiente describen esas clases y interfaces, sus descripciones y cuándo implementarlos.  
  
|**Clase o interfaz**|**Cuándo implementar**|**Description**|  
|--------------------------|---------------------------|---------------------|  
|Microsoft.ServiceModel.Channels.Common.IConnection|Si tiene que definir la conexión con el sistema de destino.|Define la conexión al sistema de destino.|  
|Microsoft.ServiceModel.Channels.Common.IConnectionFactory|Si necesita crear una conexión con el sistema de destino.|Crea la conexión con el sistema de destino.|  
|Microsoft.ServiceModel.Channels.Common.ConnectionUri|Si tiene que administrar un Uri de conexión.<br /><br /> Si necesita clasificar la propiedad de conexión dentro de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] herramienta.|Administra un Uri de conexión para el sistema de destino.|  
|Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler|El adaptador debe admitir la capacidad de resolución de metadatos.|Resuelve la operación y el tipo de metadatos.|  
|Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler|Si el adaptador es compatible con la capacidad de búsqueda de metadatos.|Busca las operaciones en el sistema de destino.|  
|Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler|El adaptador debe admitir la capacidad de examinar|Examina para las operaciones en el sistema de destino.|  
|Microsoft.ServiceModel.Channels.Common.IOutboundHandler|Si el adaptador normalmente debe admitir la capacidad de salida.|Transforma el mensaje de solicitud entrante de WCF en un mensaje del sistema de destino, invoca la función específica del sistema de destino y, a continuación, transforma la respuesta en un mensaje de respuesta saliente de WCF.|  
|Microsoft.ServiceModel.Channels.Common.IInboundHandler|Si el adaptador es compatible con la capacidad de entrada.|Realiza escuchas para los datos o eventos del sistema de destino.|  
  
 Para simplificar el desarrollo de adaptadores, utilice la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] para generar el proyecto de adaptador, que crea un conjunto de clases derivadas adaptados a las características del adaptador.  
  
 Para personalizar las propiedades de adaptador y la conexión a través de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas, modifique los siguientes archivos generados por [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].  
  
-   {Projectname} BindingElement.cs  
  
-   {Projectname} BindingElementExtensionElement.cs  
  
-   {Projectname} ConnectionUri.cs  
  
 Para obtener más información acerca de cómo hacerlo, consulte [paso 2: clasificar las propiedades de conexión y el adaptador](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales para obtener información sobre el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)