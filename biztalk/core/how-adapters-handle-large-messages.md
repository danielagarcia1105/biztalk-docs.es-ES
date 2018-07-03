---
title: Cómo controlan los adaptadores mensajes de gran tamaño | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c48671fd-b6cf-4507-92b4-35a4cd135714
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a0d4260274354ce68992ddf30e07dcc74991b8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987349"
---
# <a name="how-adapters-handle-large-messages"></a>Cómo controlan los adaptadores mensajes de gran tamaño
El motor de mensajería de BizTalk puede procesar mensajes muy grandes; no imponen restricción alguna al tamaño máximo de un mensaje. Sin embargo, debería considerar la limitación del tamaño de los mensajes para mantener una administración de recursos y un rendimiento óptimos. A medida que aumenta el tamaño de los mensajes, disminuye el número de mensajes procesados por segundo. Tenga en cuenta el tamaño promedio de mensaje, el tipo de mensaje y el número de mensajes que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa para diseñar el escenario y planear la capacidad.  
  
## <a name="stream-based-processing"></a>Procesamiento basado en secuencias  
 Es importante tener en cuenta el control de mensajes de gran tamaño al desarrollar adaptadores. No es nada aconsejable cargar la totalidad de la secuencia de datos en memoria independientemente de su tamaño, puesto que, con ello, podría detenerse el proceso de BizTalk Server. Dependiendo del número y el tamaño de los mensajes que procesa el motor en un momento dado, una memoria virtual baja podría constituir un problema. En lugar de ello, los mensajes deberían procesarse por secuencias del modo siguiente:  
  
- **Los mensajes entrantes.** En lo que respecta a los mensajes de entrada, el adaptador de recepción adjunta la secuencia de red al mensaje de BizTalk, dejando al motor de mensajería de BizTalk la “extracción” de la secuencia.  
  
- **Mensajes salientes.** En cuanto a los mensajes de salida, el adaptador es el responsable de la extracción de la secuencia. Con ello, se extrae eficazmente la secuencia desde la base de datos de cuadro de mensajes y a través de la canalización de envío. El adaptador debería enviar los datos por secuencias por la red.  
  
  La siguiente ilustración muestra el procesamiento basado en secuencias en el lado de recepción del motor de mensajería.  
  
  ![](../core/media/streambasedprocessing.gif "Streambasedprocessing")  
  
  Cuando un adaptador envía un mensaje al motor, debería adjuntar su secuencia de datos al mensaje de BizTalk. En el caso de algunos adaptadores, esto puede significar la implementación de una secuencia de red. Cuando se envía el mensaje, el motor ejecuta la canalización de recepción. Durante la ejecución de la canalización, los componentes de canalización que quieran cambiar los datos clonan el mensaje, con lo que se conecta la secuencia del nuevo mensaje a la secuencia del mensaje anterior. Después de haber ejecutado la canalización, el motor de mensajería extrae un mensaje de la canalización y ejecuta un bucle leyendo la secuencia del mensaje. Esta lectura de la secuencia invoca una lectura de la secuencia anterior que, a su vez, invoca una lectura de la secuencia anterior, y así sucesivamente hacia atrás hasta llegar a la secuencia de red. El motor vacía los datos periódicamente en el cuadro de mensajes para mantener un modelo de memoria con el volumen adecuado.  
  
  **Sugerencia de solución de problemas:** en el lado de envío, el adaptador es responsable de leer la secuencia. Si el adaptador de envío desea leer alguna propiedad de contexto de mensaje promocionada o escrita en la canalización de envío, puede que esta propiedad no se escriba hasta que se lea la totalidad de la secuencia. Únicamente al efectuarse por completo la lectura de la secuencia, puede asegurarse el adaptador de que todos los componentes de canalización han terminado su ejecución.  
  
## <a name="locating-a-specific-byte-in-the-stream"></a>Localizar un byte específico en la secuencia  
 Hay escenarios en los que un adaptador puede tener que localizar el inicio de la secuencia para controlar mensajes con errores que deben suspenderse. Un ejemplo de ello es un adaptador de HTTP que recibe datos mediante la codificación fragmentada a fin de enviar el mensaje de respuesta en un par de petición-respuesta.  
  
 Sin embargo, es posible que en muchos escenarios no pueda efectuar un seguimiento de la secuencia de datos. Por ejemplo, considere un adaptador de HTTP que recibe datos mediante codificación fragmentada. Para que la secuencia de datos que es preciso diseñar para encontrar los mensajes con errores, el adaptador tendría que almacenar los datos en caché a medida que se leen, bien en la memoria, bien en disco. Obviamente, esto no resulta óptimo y requiere recursos adicionales. Además, muchos de los componentes de canalización predeterminados funcionan por secuencias progresivas. Para estos escenarios, BaseAdapter en SDK utiliza una clase auxiliar denominada **VirtualStream**. El archivo que contiene esta funcionalidad se denomina VirtualStream.cs.  
  
> [!NOTE]
>  El archivo VirtualStream.cs se encuentra en dos ubicaciones en los ejemplos de SDK: SDK\Samples\Pipelines\ArbitraryXPathPropertyHandler y SDK\Samples\Pipelines\SchemaResolverComponent\SchemaResolverFlatFileDasm.  
  
 La idea que subyace a una secuencia virtual es el almacenamiento en caché de los datos de la secuencia en una secuencia de memoria hasta que alcance un umbral, superado el cual los datos se desbordan en una ubicación segura del disco. El archivo de disco se elimina automáticamente después de que se cierre la secuencia. Las secuencias progresivas pueden diseñarse de esta forma.