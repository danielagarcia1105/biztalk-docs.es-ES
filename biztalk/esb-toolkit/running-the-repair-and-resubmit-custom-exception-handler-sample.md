---
title: Ejecución del ejemplo de controlador de excepciones personalizadas de reparación y reenvío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7363c440-44aa-4d08-8290-72787d17ac60
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34bb03565f7b044f9c6c2f29332862ae8aafef7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004485"
---
# <a name="running-the-repair-and-resubmit-custom-exception-handler-sample"></a>Ejecución del ejemplo de controlador de excepciones personalizadas de reparación y reenvío
El ejemplo de reparación y volver a enviar controlador de excepciones personalizado, muestra una técnica muy eficaz para integrar la intervención humana en ESB y aplicación de BizTalk procesa e implementa un patrón de diseño útiles de Microsoft. El código de ejemplo se integra perfectamente en el sistema de administración de excepciones de ESB.  
  
 El ejemplo muestra cómo puede usar un controlador de excepciones personalizado en una orquestación. Cuando un proceso en la orquestación (EAIProcess.odx) encuentra un error, el controlador de excepción se genera y publica un mensaje de error ESB. Este mensaje de error que incluye en su carga de los mensajes (incluidos sus propiedades de contexto relacionadas con BizTalk) que estaban "en proceso" cuando se produjo la excepción y la instancia actual de System.Exception detectada por el motor de orquestaciones de BizTalk. Cuando esto ocurre, se conservan un mensaje "Denegado" y un mensaje de "Aprobado" con el mensaje de error.  
  
 Una segunda orquestación denominada EAIProcessHandler.odx, que se implementa en una forma desacoplada y actúa como un controlador de excepciones personalizado, se suscribe al código de error específico generado en la orquestación EAIProcess.odx y consume el mensaje de error. Este controlador de excepciones extrae los mensajes originales (como documentos con tipo) y las instancias de System.Exception originalmente se conservan en el mensaje de error.  
  
 Los mensajes originales están ahora disponibles para su procesamiento con todas sus propiedades de contexto original. El controlador de excepciones personalizado (EAIProcessHandler.odx), a continuación, escribe el "Denied" y los mensajes de "Aprobado" en el sistema de archivos en las siguientes ubicaciones:  
  
- Mensaje aprobado:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.PostApproval  
  
- Mensaje denegado para la reparación y reenvío:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.RepairSubmit  
  
- Mensaje de denegación:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.PostDecline  
  
  El controlador de excepciones serializa el mensaje de "Denegado" para la reparación y reenvío al sistema de archivos mediante una instrucción de procesamiento de Microsoft InfoPath. Una plantilla de InfoPath permite al usuario editar el formulario y volver a enviar el resultado (consulte la figura 1), que inicia la orquestación EAIProcess.odx que valida el mensaje.  
  
  ![Reenvío de reparación](../esb-toolkit/media/ch6-repairresubmit.gif "Ch6-RepairResubmit")  
  
  **Figura 1**  
  
  **Un mensaje de prueba generado por la plantilla de reenvío y reparación de InfoPath**  
  
  Además, hay un puerto de envío genérico denominado todos. Exceptions_FILE que está configurado para usar la canalización GlobalFaultProcessor. Este puerto se suscribe a todas las excepciones en el sistema, ambos BizTalk error mensaje enrutamiento de mensajes y mensajes de error ESB. El marco de administración de excepciones normaliza ellos todo en un único formato y se serializa utilizando una instrucción de procesamiento de InfoPath en la carpeta de \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions.  
  
## <a name="installation"></a>Installation  
 Los ejemplos de administración de excepciones usan el mismo conjunto de servicios principales y los artefactos de la aplicación de BizTalk. Por lo tanto, tendrá que instalar los artefactos de ejemplo de administración de excepciones sólo una vez para poder ejecutar ejemplos de administración de toda la excepción. Para obtener información sobre cómo instalar los ejemplos de administración de excepciones, vea [instalar los ejemplos de administración de excepciones](../esb-toolkit/installing-the-exception-management-samples.md).  
  
## <a name="running-the-sample-application"></a>Ejecutar la aplicación de ejemplo  
 **Para ejecutar el ejemplo de reparación y volver a enviar controlador de excepciones personalizado**  
  
1.  Antes de ejecutar este ejemplo por primera vez, asegúrese de que la ubicación de recepción y direcciones URL de puerto de envío señalan a los directorios adecuados en la carpeta \Source\Samples\Exception Handling\Test\Filedrop. La ubicación de recepción debe especificar la carpeta EAIProcess.RequestPort y las direcciones URL de puerto de envío deben especificar las carpetas EAIProcess.PostApproval y EAIProcessHandler.PostDecline.  
  
2.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de BizTalk para iniciarlo.  
  
3.  Iniciar el ejemplo copiando el archivo de ejemplo denominado Request_EAIProcessHandler.xml, ubicado en la carpeta \Source\Samples\Exception Handling\Test\Data, en la carpeta especificada para el EAIProcess.RequestPort_FILE la ubicación de recepción: \Source\Samples\ Excepción Handling\Test\Filedrop\EAIProcess.RequestPort.  
  
4.  Abra la carpeta denominada EAIProcessHandler.PostDecline (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop). Verá el mensaje de "Rechazada *" generado por la orquestación de control de excepciones.  
  
5.  Abra la carpeta denominada EAIProcessHandler.RepairSubmit (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop). Verá un mensaje de "RepairSubmit" generado por la orquestación de control de excepciones.  
  
6.  Haga doble clic en el archivo RepairSubmit para abrirlo en la plantilla adecuada de InfoPath. Verá el mensaje listo para su edición y reenvío.  
  
7.  Cambie el valor de la **precio unitario** arrastrándolo desde **0** a **2**y, a continuación, haga clic en el **enviar** situado en la barra de herramientas de InfoPath formulario para enviar el documento modificado a BizTalk para su procesamiento. Ubicación de recepción de los usos de proceso de enviar un HTTP de BizTalk configurado.  
  
8.  Navegue hasta la carpeta EAIProcess.PostApproval (en la carpeta \Source\Samples\Exception Handling\Test\Filedrop). Ahora verá el documento "Aprobación *", que contiene el valor actualizado para el precio unitario.  
  
## <a name="how-the-sample-works"></a>Cómo funciona el ejemplo  
 El mensaje que se envía, activa la orquestación EAIProcess. Cuando la orquestación EAIProcess procesa el mensaje, intenta dividir 1 por el precio unitario. Dado que el precio unitario es cero, se produce una excepción de división por cero. Código del controlador de eventos de la orquestación detecta esta excepción y crea un mensaje de error. La cantidad del pedido en el mensaje es mayor que 10, por lo que la lógica de negocios dicta que esta excepción tiene un **FaultCode** campo valor de **1000**.  
  
 La orquestación EAIProcess, a continuación, publica el mensaje de error en el cuadro de mensaje de BizTalk a través de un puerto de enlace directo y finaliza la orquestación.  
  
 Una orquestación de controlador de error personalizado denominada EAIProcessHandler, que se suscribe a mensajes con un **FaultCode** campo valor de **1000**, recoge el nuevo mensaje de error. El código de la orquestación crea el mensaje "Denied" y el archivo de InfoPath y, a continuación, coloca esto en las carpetas EAIProcessHandler.PostDecline y EAIProcessHandler.RepairSubmit listo intervención humana.