---
title: "Depuración de errores en tiempo de ejecución de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87a47c5b2ee432059365c6f9046a75bb5775fc02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="debugging-orchestration-runtime-errors"></a>Depurar errores en tiempo de ejecución de orquestaciones
Esta sección contiene una serie de preguntas y respuestas diseñadas para ayudarle a solucionar problemas en tiempo de ejecución con las orquestaciones.  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a>¿Por qué aparecen errores de suscripción intermitentes cuando se envía a una orquestación secundaria que acaba de iniciar la primaria?  
 El error de suscripción que indica que no se ha encontrado la suscripción es resultado de una condición de anticipación. Una condición de anticipación se produce cuando el resultado de un proceso depende del orden determinado en el que tiene lugar el proceso. En este caso, la condición se produce cuando la orquestación secundaria no se ha iniciado a tiempo para recibir el mensaje que envió la primaria.  
  
 Para evitar este problema, la orquestación secundaria podría devolver un mensaje a la primaria cuando se haya iniciado y preparado para recibir un mensaje. De este modo, la orquestación primaria que se inició sabría que hay un receptor antes de enviar un mensaje.  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a>¿Por qué aparecen errores cuando adjunto un puerto de envío dinámico a un puerto lógico?  
 No se ha diseñado un puerto dinámico para que herede todos los atributos y características del puerto asignado a él. Un puerto dinámico obtiene solo una dirección; no hereda el resto de la información asociada al puerto lógico.  
  
 Por ejemplo, si adjunta un puerto de envío dinámico a un puerto lógico con Notificación de entrega = Transmitido, el tiempo de ejecución no entregará una notificación de entrega. El tiempo de ejecución de XLANGs solo escuchará una notificación de entrega si el puerto se ha configurado realmente para ello de forma estática.  
  
> [!NOTE]
>  En XLANGs, los puertos se comportarán solo como se hayan configurado de forma estática.  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a>¿Por qué aparece el error "No se encontró el nombre de archivo o de ensamblado o una de sus dependencias" cuando intento ejecutar la aplicación tras implementar una orquestación con componentes personalizados?  
 Normalmente, este error significa que el motor de orquestaciones de BizTalk no puede localizar el componente personalizado. Debe instalar todos los ensamblados que se incluyen en una aplicación de BizTalk dentro de la caché de ensamblados global del equipo que aloja la aplicación.  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a>Se produce un error de tipo "La propiedad de contexto AssemblyName no era válida", cuando se envía un documento a un servicio Web mediante una orquestación  
  
### <a name="problem"></a>Problema  
 Al enviar un documento a un servicio Web mediante una orquestación, se produce un error "La propiedad de contexto AssemblyName no era válida".  
  
### <a name="cause"></a>Causa  
 La aplicación de BizTalk se diseñó, en un principio, mediante una aproximación de "mensajería" sin una orquestación que interviniera. Este tipo de solución usa un filtro de puerto de envío para vincular el puerto de recepción al puerto de envío; de este modo, el documento se transmite al puerto de envío cuando se recibe. Posteriormente, se modificó la solución para incluir una orquestación que se enlazó al puerto de envío.  
  
### <a name="resolution"></a>Solución  
 Quite el filtro del puerto de envío. Si aplica un filtro a un puerto de envío que esté enlazado a una orquestación, los mensajes evitarán, a menudo, la orquestación y provocarán el error de propiedad de contexto.  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a>Se produce un error "WrongBodyPartException" cuando se controla un mensaje MIME de varias partes en una orquestación  
  
### <a name="problem"></a>Problema  
 Recibir un mensaje MIME de varias partes en una orquestación da como resultado un **WrongBodyPartException** excepción.  
  
### <a name="cause"></a>Causa  
 Este error puede producirse si se especifica de forma incorrecta el orden de las partes o los mensajes no se ajustan a las posiciones de las partes que ha especificado. Por ejemplo, si especifica que la tercera partes es una parte del cuerpo pero los mensajes llegan con una parte del encabezado en la tercera posición.  
  
### <a name="resolution"></a>Solución  
 Compruebe que la configuración del índice de las partes del cuerpo es correcta y, a continuación, asegúrese de que todos los mensajes que llegan a través del adaptador son coherentes con la configuración. Puede inspeccionar el contenido de los mensajes MIME que dan error dentro de una orquestación si detiene la orquestación (pero la mantiene dada de alta); esto obligará a que se publique el mensaje de modo que pueda examinarlo mediante la consola de administración y comprobar el orden de las partes.  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a>No se encuentran partes del mensaje MIME de varias partes  
  
### <a name="problem"></a>Problema  
 Intenta recuperar un MIME del mensaje parte con un valor de índice mayor que 0 resultados en el tiempo de ejecución de BizTalk Server produce un error similar a "no se puede encontrar el mensaje de varias partes con índice = \<valor\>".  
  
### <a name="cause"></a>Causa  
 Las razones más comunes para que se produzca este error son las siguientes:  
  
-   El mensaje MIME tiene menos partes que las esperadas.  
  
-   No se puede analizar por completo el mensaje MIME.  
  
### <a name="resolution"></a>Solución  
 Puede solucionar este problema asegurándose de que el código recupera solo partes de mensaje que se encuentran dentro del intervalo esperado del origen del mensaje. En caso de que se produzca un problema de análisis, debería comprobar que el mensaje MIME original está construido de forma adecuada y coherente en cuanto a la estructura. Si espera encontrarse con problemas de análisis ocasionales, asegúrese de que la orquestación tiene controladores de excepción adecuados.  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a>Recibe el error "The FILE send adapter cannot open file for writing" al realizar un envío mediante un puerto de envío dinámico.  
  
### <a name="problem"></a>Problema  
 Recibirá una "el adaptador de envío de archivo no puede abrir el archivo  *\<filename\>*  para escritura" error en el registro de eventos de servidor BizTalk Server al enviar una opción dinámica de puerto de envío.  
  
 Este problema se produce cuando el **BTS. OutBoundTransportLocation** propiedad se define en una expresión de orquestación y se especifica el transporte de archivo, por ejemplo, las siguientes expresiones provocará este error en tiempo de ejecución:  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 \- O bien  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a>Causa  
 Este problema se produce porque en tiempo de ejecución, el motor de orquestaciones quita el texto "**file://"** desde la dirección URL especificada. Por lo tanto, si usa los ejemplos anteriores, "file:///c:/test/out" se evalúa como \c:\test\out y "file://mymachine/test/out" se evalúa como mymachine\test\out.  
  
### <a name="resolution"></a>Solución  
 Cuando especifique la dirección URL para el **BTS. OutBoundTransportLocation** propiedad en una expresión, agregar o quitar caracteres "/" según sea necesario. Con los ejemplos anteriores el **BTS. OutBoundTransportLocation** propiedad debe definirse como "file://c:/test/out", que se evaluaría en c:\test\out o "file:///mymachine/test/out", que se evaluaría en \\\mymachine\test\out.