---
title: Crear controladores de excepciones personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f725084c838d026f9028f0ac2e684ec2d727c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290636"
---
# <a name="creating-custom-exception-handlers"></a>Crear controladores de excepción personalizada
Para que una aplicación detectar y reaccionar ante excepciones, los programadores deben proporcionar un controlador de excepciones. Este controlador de excepciones puede suscribirse a un único tipo de mensaje de excepción o a mensajes de excepción generados a partir de algunas o todas las partes de un sistema o una aplicación. Por ejemplo, puede requerir solo un único controlador para todos los mensajes de un sistema determinado (por ejemplo, las excepciones que se producen en el sistema de nóminas), o en su lugar, puede requerir controladores de destino para los errores específicos (por ejemplo, para detectar si la comprobación del proceso de impresión se produce un error).  
  
 Para suscribirse a un tipo de excepción específico, utilice una orquestación que tenga un filtro en la forma de recepción de activación, tal como se muestra en el ejemplo siguiente.  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 También puede tener una condición de filtro en un puerto de envío que envía un mensaje al sistema de archivos o a través de correo electrónico si el mensaje cumple una condición de filtro específico.  
  
## <a name="sample-exception-handling-projects"></a>Proyectos de ejemplo de control de excepciones  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varias aplicaciones de BizTalk de ejemplo que muestran el control de excepciones. Estos ejemplos se pueden encontrar en la carpeta de control de \Source\Samples\Exception.  
  
 También hay cuatro proyectos de BizTalk, ubicados en la solución GlobalBank.ESB.Samples.ExceptionHandling, que muestran cómo usar el mecanismo de excepción enrutamiento de orquestación de error de ESB. Estos proyectos están preconfigurados para implementar en la aplicación de GlobalBank.ESB BizTalk. Los proyectos son los siguientes:  
  
-   **ESB. ExceptionHandling.Schemas.** Este proyecto contiene los esquemas utilizados para las orquestaciones de ejemplo.  
  
-   **ESB. ExceptionHandling.Pipelines.** Este proyecto contiene la canalización de envío configurada con el procesador de excepción, utilizado en un puerto de envío que se suscribe a todas las excepciones. Esto incluye las excepciones generadas por BizTalk y las excepciones generadas por el marco de trabajo de administración de excepciones.  
  
-   **ESB. ExceptionHandling.Processes.** Este proyecto contiene la orquestación EAIProcess.odx, que simula una excepción al intentar dividir por cero y llama el **CreateFaultMessage** y **AddMessage** métodos para generar un adecuado mensaje de error, tal como se muestra en la figura 1.  
  
     ![Orquestación procesa ejemplo](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")  
  
     **Figura 1**  
  
 **La orquestación EAIProcess.odx en el proyecto de ejemplo de procesos**  
  
-   **ESB. ExceptionHandling.Handlers.** Este proyecto contiene la orquestación EAIGenericHandler.odx, que llama el **GetMessages** método y recorre en iteración la **MessageCollection** mediante el **MoveNext**(método), tal como se muestra en la figura 2.  
  
 ![Ejemplo genérico de controladores de orquestación](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")  
  
 **Figura 2**  
  
 **La orquestación EAIGenericHandler.odx en el proyecto de ejemplo de controladores**  
  
 ESB. ExceptionHandling.Handlers proyecto también contiene la orquestación EAIProcessHandler.odx, que llama el **GetMessage** y **GetException** métodos, como se muestra en la figura 3.  
  
 ![Proceso de ejemplo de controladores de orquestación](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")  
  
 **Figura 3**  
  
 **La orquestación EAIProcessHandler.odx en el proyecto de ejemplo de controladores**