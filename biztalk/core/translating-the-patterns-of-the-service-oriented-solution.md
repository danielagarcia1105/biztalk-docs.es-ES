---
title: Traducir los patrones del servicio en la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], translating patterns to orchestration shapes
- artifacts, patterns
- orchestrations, patterns
- patterns [process management solutions], connections
- patterns [service solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to orchestrations
- orchestrations, boundaries
- patterns [service solutions], translating patterns to artifacts
ms.assetid: ff17cc41-2a7b-4304-b5bd-96b1174cea7f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95285c93bdb290adbee988305dbcd365e4e729a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280004"
---
# <a name="translating-the-patterns-of-the-service-oriented-solution"></a>Traducir los patrones del servicio en la solución orientada a servicios
En esta sección se describe cómo traduce la solución el diagrama de patrones en artefactos de BizTalk Server.  
  
 ![Servicio &#45; patrones de la solución orientada a](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
## <a name="connections-and-completeness-conditions"></a>Conexiones y condiciones de finalización  
 Sería posible comenzar este apartado traduciendo los patrones en componentes de BizTalk Server. No obstante, dado que las conexiones entre los componentes constituyen en realidad su infraestructura, aquéllas se convierten también en un punto de partida adecuado. Además, en lo que respecta al patrón de agregación, también se debe considerar cómo indicarle que posee en sí mismo toda la información que necesita. Esto afecta tanto a sus conexiones con otros componentes como a su diseño.  
  
 La solución debe proporcionar un modo de uso adecuado y uniforme. La interfaz de servicios especifica cómo pueden utilizarla otras aplicaciones. Dado que la solución debe establecer comunicación con una aplicación antigua mediante IBM WebSphere MQ, IBM WebSphere MQ debe formar parte de la interfaz de servicios. Sin embargo, en aplicaciones más nuevas, un interfaz de servicio Web parece una opción obvia. Una interfaz de servicio Web proporciona flexibilidad máxima para el resto de aplicaciones que utilicen el servicio. En este caso, es posible utilizar la flexibilidad de BizTalk Server para disponer de una interfaz de servicios doble. Para obtener información acerca de cómo exponer orquestaciones como servicios Web, consulte [cómo orquestaciones de mapa a los servicios Web](../core/how-to-map-orchestrations-to-web-services.md).  
  
 Las conexiones restantes son aquellas que se producen entre la interfaz de servicios y la lista de destinatarios, entre la lista de destinatarios y las aplicaciones de servidor y entre las aplicaciones de servicios, el patrón de agregación y la interfaz de servicios.  
  
 Si la conexión con la lista de destinatarios es sincrónica, la solución no tiene que utilizar las correlaciones para garantizar que todos los mensajes dirigidos a la lista de destinatarios se envían y se reciben. Por la misma razón, las conexiones entre las aplicaciones de servidor y el patrón de agregación pueden ser sincrónicas. El patrón de agregación necesita las respuestas de las tres aplicaciones de servidor para completar la respuesta de las consultas. Entonces, los tiempos de respuesta deben ser breves para que las conexiones sincrónicas sean adecuadas y simplifiquen la solución.  
  
 Por regla general, en el patrón de agregación existe una condición de finalización. Por ejemplo, en los casos en los que existan varios servidores y los tiempos de respuesta sean lentos, la condición de finalización podría darse al recibir al menos una respuesta en un período de tiempo determinado. Esta solución orientada a servicios requiere las tres respuestas para construir el mensaje final. En este caso, la condición de finalización consistiría en recibir las tres respuestas.  
  
> [!NOTE]
>  Al recibir las solicitudes a través de IBM WebSphere MQ, la solución agrega un identificador de correlación copiando el **MQMD_MsgId** valor para el **MQMD_CorrelId** del mensaje de respuesta. Esto forma parte del empleo estándar del adaptador de MQSeries en los procedimientos de solicitud-respuesta para evitar posibles condiciones de anticipación. Para obtener más información, consulte [correlación de solicitud y respuesta utilizando mensajes](../core/correlating-messages-using-request-reply.md).  
  
## <a name="determining-orchestration-boundaries"></a>Determinar los límites de la orquestación  
 La solución debe permitir las solicitudes procedentes de la cola de IBM WebSphere MQ y de la interfaz de servicios Web. Al colocar la interfaz de servicios en una orquestación, la entrada IBM WebSphere MQ en otra y el total del procesamiento en una tercera, se logra mantener la comunicación externa aislada del procesamiento.  
  
## <a name="translating-the-components-into-orchestration-shapes"></a>Traducir los componentes en formas de orquestación  
 En la solución definitiva, los patrones para traducir a formas se encontrarán en una única orquestación. Existen muchas formas de crear en BizTalk Server un enrutador basado en el contenido que incluya la creación de suscripciones de cuadro de mensajes. En la solución, el enrutamiento emplea suscripciones de cuadro de mensajes. Una forma de expresión evalúa si el mensaje incluye o no los valores de los campos obligatorios. Una forma de decisión evalúa el conjunto de variables de la forma de expresión y selecciona la ruta a través de la orquestación.  
  
 El **CustomerService** orquestación usa la forma paralela para enviar mensajes a las aplicaciones de servidor y recibir respuestas al mismo tiempo. No tiene que esperar a que una aplicación termine antes de realizar la siguiente solicitud. Si el número de aplicaciones cambiara con frecuencia o las conexiones con las aplicaciones no fueran de confianza, la orquestación tendría que traducir el patrón de otra forma.  
  
 En la solución, el patrón de agregación debe combinar los elementos de los tres mensajes de respuesta. Mediante el empleo de la forma paralela se garantiza que la comunicación con los sistemas de servidor es paralela. Además, dado que la forma no finaliza hasta que se reciben todas las respuestas o un tiempo de espera, el patrón de agregación sabrá siempre cuándo puede continuar. La orquestación utiliza una forma de transformación que asigna elementos de los mensajes de respuesta de servidor y del mensaje de solicitud original a los elementos del mensaje de respuesta.  
  
> [!NOTE]
>  Las comunicaciones con los sistemas de servidor también pueden agotar el tiempo de espera. Puede establecer el período de tiempo de espera, incluya el **recepción** forma un **ámbito** forma y estableciendo el **tiempo de espera** propiedad del ámbito.  
  
 Para obtener una lista completa de las formas de orquestación, consulte [formas de orquestación](../core/orchestration-shapes.md).  
  
## <a name="see-also"></a>Vea también  
 [Patrones en la solución orientada a servicios](../core/patterns-in-the-service-oriented-solution.md)   
 [Solución orientada a servicios de componentes del servicio](../core/components-of-the-service-oriented-solution.md)