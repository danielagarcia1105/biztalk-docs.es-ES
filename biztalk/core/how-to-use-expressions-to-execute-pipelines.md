---
title: Cómo usar expresiones para ejecutar canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ExecuteReceivePipeline() method
- pipelines, schema resolution
- ExecuteSendPipeline() method
- SendPipelineInputMessages class
- pipelines, restrictions
- pipelines, errors
- XLANGPipelineManager class
- receive pipelines, orchestrations
- ReceivePipelineOutputMessages class
- orchestrations, pipelines
- pipelines, component types
- send pipelines, orchestrations
- pipelines, states
- pipelines, executing
- Microsoft.XLANGs.Pipeline namespace
- pipelines, transactional
- pipelines, orchestrations
- Message Assignment shape [Orchestration Designer], pipelines
ms.assetid: f947fa73-526c-4747-8de7-df557a93056c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08f5933d3592d391087196f31185e279c40c4836
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974658"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a>Cómo usar expresiones para ejecutar canalizaciones
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene la capacidad de llamar de forma sincrónica a una canalización desde una orquestación. Esto permite a las orquestaciones aprovechar el procesamiento de mensajes encapsulado en una canalización (tanto envío como recepción) frente a un conjunto de datos sin tener que enviar los datos a través de la infraestructura de mensajería.  
  
 Puede usar esta característica para permitir que una orquestación llame a una canalización de envío a fin de agregar varios mensajes en un único intercambio de salida. A la inversa, una orquestación podría llamar a una canalización de recepción para descodificar y desensamblar un intercambio obtenido fuera de la infraestructura de mensajería, sin incurrir en los costos de procesamiento derivados de atravesar el cuadro de mensajes.  
  
## <a name="details"></a>Detalles  
 Las orquestaciones utilizan métodos en el **XLANGPipelineManager** clase (en el **Microsoft.XLANGs.Pipeline** espacio de nombres) para llamar a send o canalizaciones de recepción.  Una canalización de recepción consume un solo mensaje o un intercambio y produce cero o más mensajes, del mismo modo que cuando la canalización se ejecuta al recibir un mensaje dentro de la mensajería de BizTalk. Una canalización de envío consume uno o más mensajes y produce un solo mensaje o intercambio, también del mismo modo que cuando la canalización se ejecuta al enviar un mensaje dentro de la mensajería de BizTalk.  
  
## <a name="calling-a-receive-pipeline"></a>Llamar a una canalización de recepción  
 Para poder llamar a una canalización de recepción desde una orquestación, la aplicación llama el **ExecuteReceivePipeline()** método de la **XLANGPipelineManager** clase.  Este método consume un intercambio único y devuelve una colección de cero o más mensajes (incluidos en una instancia de la **ReceivePipelineOutputMessages** clase). La sintaxis de este método se detalla en la referencia de biblioteca de clases de .NET para la **XLANGPipelineManager** clase.  
  
 La interfaz API para ejecutar una canalización de recepción desde una orquestación es la siguiente:  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 Una llamada a una canalización de recepción se suele realizar un **expresión** forma dentro de la orquestación.  
  
 Para llamar a una canalización de recepción desde una orquestación, el programador debe hacer referencia al ensamblado de canalización en el proyecto de orquestación. A continuación se muestra un ejemplo de una orquestación que llama a una canalización de recepción:  
  
 ![Pantalla de canalización de recepción de llamada](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")  
  
 Para obtener un ejemplo más detallado, vea el ejemplo SDK [compuesto por el procesador de mensajes (ejemplo de BizTalk Server)](../core/composed-message-processor-biztalk-server-sample.md).  
  
> [!NOTE]
>  Una variable de tipo **ReceivePipelineOutputMessages** puede declararse solo dentro de un ámbito atómico en una orquestación.  Esto se debe a que las variables de este tipo no son serializables y, por lo tanto, no sobrevivirían a la persistencia de la orquestación. Además, las orquestaciones nunca persisten al ejecutarse en un ámbito atómico.  Esto significa que una canalización de recepción solo se puede ejecutar en un ámbito atómico.  
  
> [!NOTE]
>  Al llamar a **PassThruReceive** canalización o componente de canalización personalizado desde dentro de una orquestación, debe declarar el tipo de variable para el mensaje entrante como System.Xml.XmlDocument, independientemente del tipo de mensaje entrante es XML o no . Por lo tanto, puede producirse una excepción si intenta trabajar con él si el mensaje entrante no es un mensaje XML, como un mensaje de archivo de texto sin formato. Esto se debe a que el motor de orquestaciones pretende usar System.Xml.XmlDocument para cualquier tipo de mensaje entrante en el escenario descrito anteriormente.  
  
## <a name="calling-a-send-pipeline"></a>Llamar a una canalización de envío  
 Para llamar a una canalización de envío desde una orquestación, la aplicación llama el **ExecuteSendPipeline()** método de la **XLANGPipelineManager** clase. Este método consume una colección de uno o más mensajes (incluidos en una instancia de la **SendPipelineInputMessages** clase) y devuelve un único intercambio. La sintaxis de este método se detalla en la referencia de biblioteca de clases de .NET para la **XLANGPipelineManager** clase.  Dado que la ejecución de una canalización de envío produce un nuevo intercambio, la llamada a **ExecuteSendPipeline()** método debe realizarse dentro de una forma de asignación de mensajes, como por ejemplo:  
  
 La interfaz API para ejecutar una canalización de envío desde una orquestación es:  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 Una llamada a una canalización de envío debe realizarse dentro de un **asignación de mensajes** forma dentro de la orquestación.  
  
 Para llamar a una canalización de envío desde una orquestación, el programador debe hacer referencia al ensamblado de canalización en el proyecto de orquestación.  A continuación se muestra un ejemplo de una orquestación que llama a una canalización de envío:  
  
 ![Pantalla de canalización de envío llamada](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")  
  
> [!NOTE]
>  Al llamar a la canalización XMLTransmit predeterminada, debe establecer la propiedad de contexto de mensaje XMLNORM.EnvelopeSpecName en el nombre completo del esquema de sobres. Por ejemplo:  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 Para obtener un ejemplo más detallado, vea el ejemplo SDK [agregador (ejemplo de BizTalk Server)](../core/aggregator-biztalk-server-sample.md).  
  
## <a name="pipeline-execution---behavioral-differences"></a>Ejecución de canalización: diferencias de comportamiento  
 La ejecución de una canalización de envío o recepción llamada por una orquestación es, en gran parte, la misma que cuando la misma canalización se ejecuta en una infraestructura de mensajería (es decir, en la ubicación de recepción o en el puerto de envío).  No obstante, hay algunas diferencias de comportamiento que se detallan a continuación.  
  
### <a name="differences-within-pipeline-stages"></a>Diferencias dentro de las fases de canalización  
 La ejecución de las fases dentro de una canalización de envío o recepción a la que se llama desde una orquestación es prácticamente idéntica a la ejecución de dichas fases cuando se llama a la canalización desde la infraestructura de mensajería de BizTalk, con las excepciones que se apuntan a continuación.  
  
-   Ensamblador/desensamblador: El ensamblador y desensamblador no procesarán **perfil de seguimiento** datos.  
  
-   Codificador y descodificador: El codificador MIME firma digitalmente los mensajes mediante el certificado configurado en el host al que está asociado el host.  El codificador SMIME cifra mensajes mediante el certificado en el contexto del mensaje pasado a la canalización.  
  
### <a name="schema-resolution"></a>Resolución de esquemas  
 Hay dos algoritmos de búsqueda de esquemas que son compatibles al ejecutar una canalización desde una orquestación:  
  
-   Resolución por tipo  
  
-   Resolución por nombre  
  
 En los casos en los que se implementan esquemas duplicados, la lógica del algoritmo para seleccionar el esquema adecuado es idéntica a la usada al ejecutarlo en el contexto de la infraestructura de mensajería.  
  
### <a name="transactional-pipelines"></a>Canalizaciones transaccionales  
 Las canalizaciones cuyas etapas llaman a componentes transaccionales no tendrán un contexto transaccional disponible.  Todas las llamadas a **Ipipelinecontext.getTransaction** producirá **NotSupportedException**.  Esto no impide la ejecución de tal tipo de canalizaciones desde una orquestación. No obstante, significa que la canalización tendrá que detectar y controlar esta situación.  
  
### <a name="message-destination"></a>Destino de mensaje  
 En este contexto, no se admite controlar el destino de mensaje mediante componentes de canalización.  Establecer las propiedades de contexto **MessageDestination** o **SuspendOnRoutingFailure** provocará una **XLANGPipelineManagerException** que se produzca.  
  
### <a name="pipeline-component-types"></a>Tipos de componentes de canalización  
 Los componentes de canalización deben estar basados en el siguiente orden para poder ser llamados desde una orquestación:  
  
-   .NET Framework v1.1  
  
-   .NET Framework v2.0  
  
-   .NET Framework v3.0  
  
-   .NET Framework v3.5  
  
-   .NET Framework v4.0  
  
-   .NET Framework v2.0  
  
-   COM  
  
## <a name="restrictions"></a>Restricciones  
 Los siguientes tipos de canalizaciones **no** ejecutarse desde una orquestación:  
  
-   Canalizaciones transaccionales.  
  
-   Canalizaciones recuperables  
  
-   Canalizaciones que llaman a la API de interceptor de BAM (un **NotSupportedException** se inicia).  
  
-   La misma instancia de canalización no se puede ejecutar en distintas ramas de la forma paralela a menos que esté colocada en un ámbito sincronizado en cada rama.  
  
-   Canalizaciones existentes (ensamblados) que se generaron en el SDK de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].  
  
## <a name="failure-modes-and-effects"></a>Modos de error y efectos  
 Cualquier error en la ejecución de canalizaciones que podría haber tenido como consecuencia un mensaje suspendido si se hubiese llamado a esta canalización desde la infraestructura de mensajería de BizTalk Server, generará una excepción en su lugar.  La excepción generada es del tipo **Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**.  Esta excepción generada se puede controlar en un bloque de filtrado dentro de la orquestación que llama.  Si la orquestación no filtra la excepción generada, el motor XLANGs notifica un error cuyo texto incluye la información de excepción en la excepción generada.  
  
 La excepción da formato a los mensajes de error generados por los componentes de la canalización.  
  
 El **mensaje** propiedad de la **XLANGPipelineManagerException** clase contiene detalles del error de ejecución de la canalización. Estos datos tienen el siguiente formato:  
  
-   Se produjo un error al ejecutar canalización \<tipo de canalización\>.  Detalles del error \<con el formato de mensaje de error\>.  
  
 En este mensaje, \<tipo de canalización\> es el nombre de la clase de canalización y \<con el formato de mensaje de error\> es una descripción del error específico que se produjeron durante la ejecución de la canalización.  
  
 Por ejemplo, si una orquestación llama a una canalización de recepción y se produce un error en la ejecución de dicha canalización porque ninguno de los componentes de la canalización reconoce el mensaje, los valores de la **XLANGPipelineManagerException**de propiedades sería puede:  
  
|Propiedad XLANGPipelineManagerException|Valor|  
|--------------------------------------------|-----------|  
|de mensaje|Error al ejecutar la canalización de recepción "MyPipelines.ReceivePipeline". Detalles del error: "no existe ningún componente de la fase Desensamblar puede reconocer los datos.|  
|Componente|String.Empty|  
  
 Otro ejemplo, si una orquestación llama a una canalización de envío y se produce un error en la ejecución de dicha canalización porque hay un error de validación, el texto de la **mensaje** propiedad de **XLANGPipelineManagerException**sería:  
  
|Propiedad XLANGPipelineManagerException|Valor|  
|--------------------------------------------|-----------|  
|de mensaje|Error al ejecutar la canalización de envío "MyPipelines.SendPipeline".  Detalles del error: "no se pudo validar el documento:" la \<nombre del elemento\> elemento no es válido - el valor \<valor del elemento\> no es válido según su tipo de datos 'String': la restricción de patrón no se pudo. ""|  
|Componente|“Microsoft.BizTalk.Component.XmlValidator”|