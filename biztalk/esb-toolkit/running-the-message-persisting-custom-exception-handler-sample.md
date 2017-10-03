---
title: Ejecuta el mensaje de ejemplo del controlador de excepciones personalizadas de conservar | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0a4c819-f6bd-4dea-8be9-e3006337665f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6d7927357e4c2be03ecd8b2e77d45558b5bc692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-message-persisting-custom-exception-handler-sample"></a>Ejecuta el mensaje conservar ejemplo del controlador de excepciones personalizadas
El ejemplo de controlador de excepciones de personalizada de conservación de mensaje muestra un controlador de acoplamiento flexible, genérico que recibe mensajes de error, extrae los mensajes que contienen y se escribe como archivos de disco en el sistema de archivos de Microsoft BizTalk.  
  
 El ejemplo muestra cómo puede utilizar un controlador de excepciones personalizado en una orquestación. Cuando un proceso en la orquestación (EAIProcess.odx) encuentra un error, el controlador de excepciones genera y publica un mensaje de error ESB. Este mensaje de error que incluye en su carga de los mensajes (incluidos sus propiedades de contexto relacionadas con BizTalk) que estaban "en proceso" cuando se produjo la excepción, así como la instancia actual de System.Exception detectada por el motor de orquestación de BizTalk. Cuando esto ocurre, un mensaje de "Denegado" y un mensaje de "Aprobado" se conservan con el mensaje de error.  
  
 Una segunda orquestación denominada EAIGenericHandler.odx, que se implementa de manera desacoplada y actúa como un controlador de excepciones personalizado, se suscribe al código de error concreto generado en la orquestación EAIGenericHandler.odx y consume el mensaje de error. Este controlador de excepciones extrae los mensajes originales (como documentos sin tipo) y las instancias de System.Exception originalmente se conservan en el mensaje de error.  
  
 El ejemplo del controlador de excepción de personalizado de conservación de mensaje difiere de la muestra de reparación y volver a enviar controlador de excepciones personalizado en que la orquestación EAIGenericHandler.odx usada en este ejemplo no tiene una dependencia en los esquemas utilizados en la publicación de error proceso de orquestación (EAIProcess.odx). En concreto, la orquestación EAIGenericHandler.odx recupera los mensajes originales desde el mensaje de error como System.Xml.XmlDocument instancias en lugar de mensajes con tipo en función de los esquemas utilizados en la orquestación EAIProcess.odx. También devuelve los mensajes como una colección que fácilmente puede mostrar el código.  
  
 El controlador de excepciones personalizado (EAIGenericHandler.odx), a continuación, escribe "Denegado" y los mensajes de "Aprobado" en el archivo sistema ubicación \Source\Samples\Exception Handling\Test\Filedrop\EAIGenericHandler.PostTmpMsg.  
  
 Además, hay un puerto de envío genérico llamado todos. Exceptions_FILE configurado para usar la canalización de GlobalFaultProcessor instalada como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] marco de administración de excepciones. Este puerto se suscribe a todas las excepciones en el sistema, ambos BizTalk no pudo mensaje enrutamiento de mensajes y mensajes de error ESB. El marco de trabajo de administración de excepción normaliza ellos todo ello en un único formato y serializa utilizando una instrucción de procesamiento de Microsoft InfoPath en la ubicación \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions.  
  
## <a name="installation"></a>Installation  
 Todos los ejemplos de administración de excepciones utilizan el mismo conjunto de servicios principales y artefactos de la aplicación de BizTalk. Por lo tanto, tendrá que instalar los artefactos de ejemplo de administración de excepción sólo una vez para poder ejecutar la excepción de todos los ejemplos de administración. Para obtener información acerca de cómo instalar los ejemplos de administración de excepciones, vea [instalar los ejemplos de administración de excepción](../esb-toolkit/installing-the-exception-management-samples.md).  
  
## <a name="running-the-sample-application"></a>Ejecutar la aplicación de ejemplo  
 **Para ejecutar el ejemplo del controlador de excepciones de personalizada de conservación de mensaje**  
  
1.  Antes de ejecutar este ejemplo por primera vez, asegúrese de que la recepción dirección URL de puerto de envío y de ubicación apuntan a los directorios adecuados en la carpeta \Source\Samples\Exception Handling\Test\Filedrop. La ubicación de recepción debe especificar la carpeta EAIProcess.RequestPort y la dirección URL de puerto de envío debe especificar la carpeta EAIGenericHandler.PostTmpMsg.  
  
2.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
3.  Iniciar el ejemplo copiando el archivo de ejemplo denominado Request_EAIGenericHandler.xml, ubicado en la carpeta \Source\Samples\Exception Handling\Test\Data, en la carpeta especificada para la ubicación de recepción de la EAIProcess.RequestPort_FILE: \Source\Samples\ Excepción Handling\Test\Filedrop\EAIProcess.RequestPort.  
  
4.  Abra la carpeta denominada EAIGenericHandler.PostTmpMsg (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop\). Verá el mensaje original.  
  
## <a name="how-the-sample-works"></a>Cómo funciona el ejemplo  
 El mensaje que se envía, activa la orquestación EAIProcess. Cuando la orquestación EAIProcess procesa el mensaje, intenta dividir 1 por el precio unitario. Dado que el precio unitario es cero, se produce una excepción de división por cero. Código del controlador de eventos de la orquestación detecta esta excepción y crea un mensaje de error. La cantidad del pedido en el mensaje es menor que 10, por lo que la lógica de negocios indica que esta excepción tiene un **FaultCode** campo de valor de **2000**.  
  
 La orquestación de EAIProcess, a continuación, publica el mensaje de error en el cuadro de mensaje de BizTalk a través de un puerto de enlace directo y finaliza la orquestación.  
  
 Una orquestación de controlador de error personalizado denominada EAIGenericHandler, que se suscribe a mensajes con un **FaultCode** campo de valor de **2000**, recoge el mensaje de error de nuevo. El código en la orquestación extrae el mensaje de excepción (error) en todos los mensajes y los escribe en archivos de disco.