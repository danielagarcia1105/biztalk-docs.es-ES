---
title: Ejemplo DynamicReceive (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa7c934-7ec3-45ad-b226-c8c53934ecb1
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af89bac79614268f4648f688d8cabfc913ed2277
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974133"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a>Ejemplo DynamicReceive (ejemplo de BizTalk Server)
En el ejemplo DynamicReceive se muestra cómo recibir mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de una cola de MQSeries cuando el URI para la cola de MQSeries se especifica de forma dinámica.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo crea dinámicamente una cola de MQSeries según lo especificado por el **queueManager**, **cola**, y **server** variables. Permite a una dinámica escenario de recepción y obtiene [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mensajes de la cola de MQSeries especificada de forma dinámica según los criterios de filtro especificados en el **MQMD_MsgId** y **MQMD_CorrelId** propiedades del mensaje.  
  
## <a name="how-this-sample-was-designed-and-why"></a>Cómo y por qué se ha diseñado este ejemplo  
 El adaptador MQSeries puede recibir mensajes de forma dinámica desde una cola de MQSeries mediante la especificación de la dirección de URI de la cola en la orquestación. Esta funcionalidad se consigue mediante un puerto de envío de petición-respuesta en la orquestación.  
  
 Para recibir dinámicamente mensajes, especifique lo siguiente en un **expresión** forma en la orquestación:  
  
1. Habilite la recepción dinámica mediante el establecimiento de la siguiente propiedad en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mensaje: **MQSeries.DynamicReceive** = `'Yes'`  
  
2. Especifique la dirección a partir de la que obtener los mensajes mediante la configuración del puerto URI. Puede especificar opcionalmente lo siguiente:  
  
   -   Especificar el intervalo de espera antes de obtener los mensajes mediante el uso de la **MQSeries.WaitInterval** propiedad en el mensaje.  
  
   -   Especificar los criterios de coincidencia para los mensajes de recepción. Las opciones de criterios de coincidencia son **Id. de mensaje**, **CorrelationID**, **GroupID**, y **MessageSequenceNumber**. Consulte "Propiedades relacionadas al servidor BizTalk Server" en [ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396) para obtener más detalles.  
  
   Después de que se cree el mensaje con estas propiedades, se envía a la cola de MQSeries mediante un puerto de envío de petición-respuesta. El puerto especifica el adaptador para recibir mensajes a partir de la URI especificada con las opciones de coincidencia indicada. Se producen las siguientes acciones:  
  
- Si los criterios de filtro para obtener un mensaje se satisfacen, el mensaje se recupera de la cola y se vuelve a enviar a la orquestación.  
  
- Si los criterios de filtro para obtener un mensaje no se satisfacen, se devuelve una respuesta ficticia. Esta es una indicación de que las opciones especificadas no han devuelto ningún mensaje de la cola.  
  
  La funcionalidad de recepción dinámica proporciona una flexibilidad adicional debido a que no es necesaria una ubicación de recepción fija. En algunos casos, puede que no conozca el URI hasta el tiempo de ejecución. La funcionalidad de recepción dinámica permite determinar de forma dinámica de dónde obtener los mensajes. También significa que no necesita implementar un contrato de cola dentro de una orquestación.  Puede esperar a obtener mensajes mediante la utilización de un URI dinámico especificado de una cola de MQSeries que se base en los criterios de coincidencia especificados.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|||  
|-|-|  
|Archivo|Descripción|  
|DynamicReceive.btproj,<br /><br /> DynamicReceive.sln|Archivos de proyectos y soluciones para la aplicación.|  
|DynamicReceive e.odx|El archivo de orquestación de BizTalk para la aplicación.|  
|Setup.bat|Archivo por lotes para crear el archivo de clave, compilar el proyecto e implementarlo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Especifique el **Microsoft.XLANGs.BaseTypes.Address** eso tiene sentido para su solución. Cambiar el **MQSeries.WaitInterval** para especificar cuándo espera recibir los mensajes de respuesta. Actualizar (o agregue) las opciones de coincidencia, o quítelas si va a obtener todos los mensajes.  
  
## <a name="building-and-running-the-sample"></a>Generar y ejecutar el ejemplo  
  
#### <a name="to-create-the-sample"></a>Para crear el ejemplo  
  
1. Cree un nuevo proyecto de orquestación en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2. Operación de recepción de habilitar dinámico estableciendo el **MQSeries.DynamicReceive** propiedad en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de mensajes `'Yes'`.  
  
3. Especifique la dirección desde la que se va a obtener los mensajes estableciendo el **puerto URI**.  
  
4. Puede especificar, de forma opcional, las siguientes dos propiedades:  
  
   1.  Especificar un intervalo de espera antes de obtener los mensajes mediante el uso de la **MQSeries.WaitInterval** propiedad en el mensaje.  
  
   2.  Especificar los criterios de coincidencia para los mensajes de recepción. Vea la ayuda "Opciones de coincidencia" para obtener más detalles.  
  
5. Cambie las siguientes variables en la orquestación para especificar de dónde obtener el mensaje:  
  
   -   **Cola**, **queueManager**, y **server**. Se utilizan para generar el URI en el **expresión** forma.  
  
6. Modificar el **expresión** forma para marcar como comentario las opciones de creación y coincidencia de cola dinámica según sea necesario.  
  
7. Puede generar e implementar el proyecto de las siguientes formas:  
  
   -   Abra la solución, haga clic en el proyecto en el Explorador de soluciones y haga clic en **propiedades** para ver las propiedades del proyecto. En la ficha firma, haga clic en **\<nuevo... \>** en el **elegir un archivo de clave de nombre seguro** cuadro de lista desplegable. A continuación, proporcione un nombre de archivo de clave e impleméntelo.  
  
   -   Como método alternativo, ejecute el archivo setup.bat que crea el archivo de clave, genera el proyecto y lo implementa.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Enlace la orquestación con el host de BizTalk.  
  
2.  Habilite el puerto de recepción de archivos creado mediante la orquestación. Cambiar el archivo recibe la ubicación de **c:\temp\in** a la carpeta adecuada de los archivos.  
  
3.  Dé de alta e inicie los dos puertos de envío que se han creado.  U puerto es un tipo de puerto de petición-respuesta, mientras que el otro es un puerto de envío de archivos y es la cola a la que se van a enviar los mensajes. Asegúrese de que se establece en la ubicación correcta.  
  
4.  Para iniciar la orquestación, coloque un archivo en la carpeta de entrada. Esto invoca el adaptador de MQSeries y llama el **MQSAgent2** componente COM + en el servidor para obtener el mensaje especificado. El mensaje recibido aparece en la ubicación de carpeta especificada en el puerto de envío de archivos.  
  
5.  Si se encuentra ningún mensaje que coincide con los criterios especificados en el **expresión** forma, un mensaje ficticio que se coloca en la carpeta de salida. Para deshabilitar las opciones de coincidencia, en comentario las dos últimas líneas en el **expresión** forma.  
  
## <a name="comments"></a>Comentarios  
  
-   Si la cola se está creando de forma dinámica, pero no se elimina, pueden producirse errores cuando se active la siguiente instancia de orquestación.  
  
-   No hay otras formas de configurar dinámicamente el URI, este ejemplo especifica solo una opción. Por ejemplo, el URI puede establecerse mediante la lectura de algunas propiedades en el contexto del mensaje.  
  
-   Si no hay mensajes en la cola que satisfagan las opciones de coincidencia, se devuelve un mensaje ficticio.  
  
-   Ya que este ejemplo utiliza puertos de envío dinámicos, puede ser necesario especificar otras opciones, como el reintento y las transacciones. Utilice las propiedades de contexto que expone el adaptador para configurar estas opciones antes de enviar el mensaje al puerto de petición-respuesta dinámico.  
  
-   Las colas de MQSeries se pueden crear y eliminar dinámicamente mediante el **MQSAdapterAdmin2** interfaz. Para obtener un ejemplo de cómo crear dinámicamente las colas de MQSeries, vea "Support for Queue Management" en [ http://go.microsoft.com/fwlink/?LinkId=89400 ](http://go.microsoft.com/fwlink/?LinkId=89400).