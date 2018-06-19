---
title: Compone el procesador de mensajes (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3097ef6a0da695c3b07cf68182a374eabed11b5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975282"
---
# <a name="composed-message-processor-biztalk-server-sample"></a>Procesador de mensajes compuestos  (ejemplo de BizTalk Server)
Este ejemplo tiene como finalidad crear una aplicación de procesador de mensajes compuestos que procese elementos de línea individuales a partir de mensajes agregados.  
  
 De forma más específica, crearemos una programación de orquestación que:  
  
1.  Reciba un mensaje de intercambio por lotes compuesto de varios pedidos.  
  
2.  Desensamble el mensaje de intercambio en documentos de pedido individuales.  
  
3.  Procese cada documento: convierta cada pedido en un mensaje de factura.  
  
4.  Ensamble todos los mensajes de factura en un intercambio por lotes.  
  
 El paso 3 se simplifica para el ejemplo. Por ejemplo, en aplicaciones más complejas, una orquestación puede enviar pedidos desensamblados a distintos sistemas de servidor de inventario y después tras recopilar todas las respuestas, agregarlos en un mensaje de factura por lotes.  
  
 Para obtener más información sobre el patrón del procesador de mensajes compuestos, vea [1].  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Existen dos proyectos dentro de la solución de ejemplo, que se describen de forma detallada en las secciones siguientes.  
  
### <a name="pipelines-and-schemas"></a>Canalizaciones y esquemas  
 El proyecto de canalizaciones y esquemas contiene:  
  
-   Esquemas de archivos sin formato para el intercambio de pedidos de entrada y el intercambio de facturas de salida.  
  
-   Asignación para transformar el documento de pedido en un documento de factura.  
  
-   Canalizaciones de envío y recepción.  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a>Esquemas de archivos sin formato para los intercambios de entrada y de salida  
 Nuestra aplicación de ejemplo funcionará con los intercambios en el formato de archivos sin formato. A continuación, se indican los ejemplos del intercambio de pedidos y el intercambio de facturas:  
  
 Intercambio de pedidos (CMPInput.txt):  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
PO1999-10-21  
US    John Dow       123 Elm Street      Mill Valley    CA 90952  
US    July Dow       8 Pine Avenue       Old Town       PA 95819  
Please ship it urgent!  
ITEMS,ITEM398-BB|Tire|4|324.99|Wrap them up nicely,ITEM201-BB|Engine Oil|1|12.99|SAE10W30|1999-05-22  
PO1999-10-23  
US    John Connor    123 Cedar Street    Mill Valley    CA 90952  
US    Sarah Connor   8 Grass Avenue      Old Town       PA 95819  
Use cheapest shipping method.  
ITEMS,ITEM101-TT|Plastic flowers|10|4.99|Fragile handle with care,ITEM202-RR|Fertilizer|1|10.99|Lawn fertilizer,ITEM453-XS|Weed killer|1|5.99|Lawn weed killer|1999-05-25  
```  
  
 El intercambio, o el documento de pedido, tiene un encabezado que identifica el tipo de documentos que contiene:  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 Este intercambio se compone de tres documentos de pedido. Una instancia consta de la información que se muestra abajo. Como se puede apreciar, contiene información como la dirección de facturación y envío, así como la lista de artículos que se han pedido.  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 El intercambio de facturas que queremos generar para esto debería tener el siguiente aspecto:  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
INVOICE1999-10-21  
BILLTO,US,John Dow,123 Elm Street,Mill Valley,CA,90952  
398-BB    Tire              4    324.99    Wrap them up nicely  
201-BB    Engine Oil        1    12.99     SAE10W30  
INVOICE1999-10-20  
BILLTO,US,John Connor,123 Cedar Street,Mill Valley,CA,90952  
101-TT    Plastic flowers   10   4.99      Fragile handle with care  
202-RR    Fertilizer        1    10.99     Lawn fertilizer  
453-XS    Weed killer       1    5.99      Lawn weed killer  
```  
  
 Este intercambio contiene un subconjunto de información que se encontraba en el intercambio de pedidos y, además, el formato del intercambio y el formato del encabezado son diferentes.  
  
 El encabezado es el siguiente:  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 Además, la instancia del documento incluye lo siguiente:  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 Primero tenemos que crear los esquemas de archivo sin formato para:  
  
-   El documento de pedido (PO.xsd)  
  
-   El documento de factura (Invoice.xsd)  
  
-   El encabezado del pedido (POHeader.xsd)  
  
-   El encabezado de la factura (InvoiceHeader.xsd)  
  
 Para este ejemplo, no vamos a explicar el proceso de creación de esquemas de archivos sin formato. Para aprender a crear esquemas de archivos sin formato a partir de instancias de documentos, vea la sección "Crear esquemas de archivos sin formato a partir de instancias de documentos" de la documentación.  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a>Asignación para transformar documentos de pedido en documentos de factura  
 La asignación (PO2Invoice.btm) transforma una instancia del pedido en un documento de factura.  
  
#### <a name="receive-and-send-pipelines"></a>Canalizaciones de envío y recepción  
 La canalización de recepción (FFReceivePipeline.btp) contiene un componente desensamblador de archivos sin formato que se emplea para procesar un intercambio de pedidos. En concreto, para el intercambio en el archivo CMPInput.txt, quita el encabezado del intercambio y genera tres documentos XML correspondientes a tres pedidos.  
  
 El desensamblador de archivos sin formato de la canalización de recepción se configura como se indica a continuación:  
  
-   **Esquema de documento:** PipelinesAndSchemas.PO  
  
-   **Esquema de encabezado:** PipelinesAndSchemas.POHeader  
  
-   **Conservar encabezado:** False  
  
-   **Intercambio recuperable:** False  
  
-   **Esquema de finalizador:** (ninguno)  
  
-   **Validar la estructura del documento:** False  
  
 La canalización de envío (FFSendPipeline.btp) contiene un componente ensamblador de archivos sin formato que se emplea para crear un intercambio de facturas agregadas.  
  
 El ensamblador de archivos sin formato de la canalización de envío se configura como se indica a continuación:  
  
-   **Esquema de documento:** PipelinesandSchemas.Invoice  
  
-   **Esquema de encabezado:** PipelinesAndSchemas.InvoiceHeader  
  
-   **Conservar marca de orden de bytes:** False  
  
-   **Juego de caracteres de destino:** (ninguno)  
  
-   **Esquema de finalizador:** (ninguno)  
  
### <a name="orchestration-schedule"></a>Programación de orquestación  
 La programación de orquestación (CMP.odx) es el lugar en que se produce todo el procesamiento principal. En concreto, se llevan a cabo las acciones siguientes:  
  
-   Se ejecuta la canalización de recepción para desensamblar el intercambio de pedidos.  
  
-   Se transforman todos los mensajes de salida de la canalización de recepción.  
  
-   Se ejecuta la canalización de envío para ensamblar el intercambio de facturas.  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a>Crear la programación de orquestación y definir variables globales  
 Nuestra orquestación recibirá un intercambio de archivos sin formato como entrada y enviará un intercambio de archivos sin formato como salida. Debido a esto, es preciso definir los mensajes de entrada y salida (denominados InputInterchange y OutputInterchange, respectivamente) como de tipo independiente (es decir, que tienen el tipo System.Xml.XmlDocument).  
  
 Además, hay que definir un ámbito atómico en el que se procesarán los mensajes. Esto es necesario porque la canalización de recepción se puede ejecutar en un ámbito atómico.  
  
#### <a name="executing-receive-pipeline"></a>Ejecutar canalización de recepción  
 Como siguiente paso, agregaremos lógica para ejecutar una canalización de recepción correspondiente al mensaje que se ha recibido en la orquestación. Para ello, declararemos una variable (con el nombre RcvPipeOutput) de tipo Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages dentro del ámbito. Esta variable es un enumerador que permite el desplazamiento por los mensajes de salida de la canalización de recepción. Tenga en cuenta que, para obtener acceso a este tipo, así como a los demás tipos para la ejecución de canalizaciones a partir de la orquestación, es preciso agregar referencias a los ensamblados siguientes:  
  
-   Microsoft.XLANGs.Pipeline.dll  
  
-   Microsoft.BizTalk.Pipeline.dll  
  
 No hay ninguna garantía de que la canalización de recepción siempre se ejecute correctamente. En ocasiones, el formato de los mensajes puede ser incorrecto, lo que originaría errores en el procesamiento de la canalización. Cuando la ejecución de una canalización genera errores en la orquestación, se inicia una excepción que se puede capturar y se puede realizar la lógica de control de errores. Para capturar la excepción iniciada por la canalización, hay que ejecutar la canalización dentro de un ámbito no atómico con un control de excepciones. El código real para ejecutar la canalización se invoca desde una forma de expresión dentro de dicho ámbito.  
  
 En la forma de expresión ExecuteRcvPipe, escriba la siguiente línea de código para ejecutar la canalización de recepción:  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 Vamos a analizar esta línea de código de forma detallada. Como se puede apreciar, se llama a un método estático ExecuteReceivePipeline que toma como parámetro un tipo de canalización de recepción para su ejecución y un mensaje de entrada. Como resultado, genera un objeto enumerador con el conjunto de mensajes de salida. El resultado se asigna a una variable de tipo ReceivePipelineOutputMessages que se había definido anteriormente en este ámbito.  
  
 También se ha incluido un bloque de control de excepciones para el ámbito de ejecución de la canalización. Este bloque capta la excepción de tipo XLANGPipelineManagerException y después, para simplificar, termina una instancia de orquestación con el mensaje de error personalizado.  
  
 En escenarios más complejos, aquí se puede realizar un control de errores adicional, como la generación o el mensaje de notificación de error y su envío a un usuario empresarial o al administrador mediante el correo electrónico.  
  
#### <a name="transforming-pipeline-output-messages"></a>Transformar mensajes de salida de la canalización  
 Después de que se haya ejecutado la canalización y se haya generado el conjunto de mensajes desensamblados, es preciso transformar cada mensaje de salida en un formato distinto.  
  
 Para usar la transformación en la orquestación, hay que definir dos mensajes: entrada y salida de la transformación. Dichos mensajes se definirán dentro del ámbito atómico. El mensaje de entrada de la transformación, que recibe el nombre TmpMessageIn, será del tipo PipelinesAndSchemas.PO, mientras que el mensaje de salida de la transformación, que recibe el nombre TmpMessageOut, será del tipo PipelinesAndSchemas.Invoice. Aplicaremos la asignación PO2Invoice.btm que está definida en el proyecto PipelinesAndSchemas.  
  
 Puesto que queremos asignar cada mensaje de salida de la canalización, tenemos que realizar la transformación en el bucle. Usaremos una forma Bucle con la condición de salida como se indica a continuación:  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 El método MoveNext() es un método estándar de la interfaz IEnumerator .NET que permite desplazarse dentro de la colección de mensajes de salida de la canalización. Cuando lleva al final de la colección, devuelve el valor False.  
  
 La primera forma Construir se usa para construir un mensaje de orquestación TmpMessageIn fuera del mensaje de salida de la canalización.  
  
 El código en la forma Construir es:  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 En este código, primero se inicializa el mensaje de orquestación como Null y luego se establece como el mensaje actual desde la colección de mensajes de salida de la canalización.  
  
 En la segunda forma Construir, se lleva a cabo la transformación real de TmpMessageIn y se construye el mensaje TmpMessageOut de tipo PipelinesAndSchemas.Invoice.  
  
#### <a name="executing-send-pipeline"></a>Ejecutar una canalización de envío  
 El último paso del procesamiento en la orquestación consiste en ejecutar la canalización de envío de archivos sin formato para ensamblar todos los mensajes xml transformados en un intercambio de archivos sin formato.  
  
 A fin de ejecutar una canalización de envío, hay que usar una variable de tipo Microsoft.XLANGs.Pipeline.SendPipelineInputMessages, denominada SendPipeInput, que contendrá una colección de mensajes de orquestación que deben procesarse en una canalización de envío.  
  
 En la última expresión del bucle donde se ha realizado la transformación, escribiremos un código que agregará cada mensaje transformado a una colección de mensajes para la canalización de envío:  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 De forma similar a la parte donde se ejecuta la canalización de recepción, el código para la ejecución de la canalización de envío se coloca dentro de un ámbito no atómico con el bloque de control de excepciones. El código de ejecución de la canalización de envío se encuentra en la forma Asignación de mensajes del bloque Construir.  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 El bloque Construir se usa para construir un mensaje de salida de la canalización OutputInterchange de tipo independiente (es decir, System.Xml.XmlDocument). Después en la forma Asignación de mensajes, el mensaje recién construido se inicializa como Null. Después , se invoca al método estático ExecuteSendPipeline para ejecutar una canalización de envío. Este método toma como parámetro un tipo de la canalización de envío para su ejecución, el mensaje de entrada y la referencia al mensaje de salida cuando se almacene la salida de la canalización.  
  
 Al igual que ocurre con la ejecución de la canalización de recepción, aquí tenemos un bloque de control de excepciones para el ámbito de ejecución de la canalización. Este bloque capta la excepción de tipo XLANGPipelineManagerException y después, para simplificar, termina una instancia de orquestación con el mensaje de error personalizado.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 En la tabla siguiente se enumeran los archivos que se usan en el ejemplo.  
  
|Archivos|Description|  
|---------------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global (GAC).<br /><br /> Quita los puertos de envío y recepción.<br /><br /> Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario.|  
|ComposedMessageProcessor.sln|Archivo de solución de Visual Studio para el ejemplo.|  
|ComposedMessageProcessorBinding.xml|Archivo de enlace para el ejemplo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|En la carpeta Orchestration:<br /><br /> CMP.odx|Orquestación que ejecuta la canalización de recepción para el mensaje del desensamblador, transforma cada mensaje desensamblado y, después, ejecuta la canalización de envío para ensamblar mensajes en un intercambio.|  
|En la carpeta Orchestration:<br /><br /> Orchestration.btproj|Proyecto de BizTalk para la orquestación.|  
|En la carpeta Orchestration:<br /><br /> SuspendMessage.odx|Orquestación usada para suspender mensajes que generan errores en el procesamiento de la canalización.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> CMPInput.xml, CMPOutput.xml|Instancias de documentos de entrada y salida para el ejemplo.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> FFReceivePipeline.btp, FFSendPipeline.btp|Canalizaciones de recepción y envío con componentes de archivos sin formato. Estas canalizaciones se ejecutan dentro de la orquestación.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> Invoice.xsd, InvoiceHeader.xsd|Esquemas de archivos sin formato para el encabezado y el documento de salida.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PO.xsd, POHeader.xsd|Esquemas de archivos sin formato para el encabezado y el documento de entrada.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PropertySchema.xsd|Esquema de propiedad del ejemplo.|  
  
## <a name="building-and-initializing-the-sample"></a>Crear e inicializar el ejemplo  
 Utilice el siguiente procedimiento para crear e inicializar el ejemplo de composición.  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>Para crear e inicializar el ejemplo de composición  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<Ejemplos de ruta de acceso\>\Pipelines\ComposedMessageProcessor  
  
2.  Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
    -   Crea las carpetas de entrada (In) y de salida (Out) de este ejemplo en la carpeta:  
  
         \<Ejemplos de ruta de acceso\>\Pipelines\ComposedMessageProcessor  
  
    -   Compila los proyectos de Visual Studio para este ejemplo.  
  
    -   Crea una aplicación nueva llamada "CMP Sample" e implementa los ensamblados de ejemplo en ella.  
  
    -   Crea y enlaza la ubicación de recepción de BizTalk Server y los puertos de envío y recepción.  
  
    -   Da de alta e inicia la orquestación, habilita la ubicación de recepción e inicia el puerto de envío.  
  
         Si opta por abrir y crear los proyectos en este ejemplo sin ejecutar el archivo Setup.bat, primero debe crear un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice que este par de claves se usa para firmar los ensamblados resultantes.  
  
3.  Antes de tratar de ejecutar este ejemplo, confirme que BizTalk Server no ha informado de ningún error durante el proceso de generación e inicialización.  
  
     Para deshacer los cambios realizados por Setup.bat, debe llevar a cabo lo siguiente:  
  
    1.  Detenga y reinicie la instancia de host desde la consola de administración de BizTalk Server.  
  
    2.  Ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Utilice el siguiente procedimiento para ejecutar el ejemplo ComposedMessageProcessor.  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a>Para ejecutar el ejemplo ComposedMessageProcessor  
  
1.  Copie el archivo de texto CMPInput.txt ubicado en la carpeta PipelinesAndSchemas. Pegue el archivo en la carpeta In.  
  
2.  Observe el archivo de texto que se ha creado en la carpeta Out. El archivo contiene los mismos registros que CMPInput.txt, pero el formato de datos del archivo es diferente.  
  
     A medida que el mensaje pasa a través de BizTalk Server, ocurre lo siguiente:  
  
    1.  El mensaje se desensambla y se convierte en mensajes XML. Cada mensaje se asigna a un formato diferente.  
  
    2.  Todos los mensajes asignados se ensamblan juntos y se convierten a archivos sin formato.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)