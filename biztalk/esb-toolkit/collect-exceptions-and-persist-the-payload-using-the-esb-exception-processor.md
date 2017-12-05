---
title: "Recopilar excepciones y conservar la carga con el procesador de la excepción de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dd0ec42ab60636202a8ff99fa8fab8d96a95a19
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>Recopilar excepciones y conservar la carga con el procesador de la excepción de ESB
En este caso de uso, el controlador de excepciones para una orquestación publica un mensaje de error ESB en el cuadro de mensaje de BizTalk Server o el mecanismo de enrutamiento de mensajes de error de BizTalk genera un mensaje de error. Un puerto de envío configurado previamente con el componente de canalización de codificador de excepción de ESB, se suscribe a los dos tipos de mensaje de error. Procesa los mensajes de error y, a continuación, los conserva como archivos de disco que se pueden ver con InfoPath, tal como se muestra en la figura 1.  
  
 ![Recopilar Carga de excepciones](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")  
  
 **Figura 1**  
  
 **Captura de un mensaje de error y almacenarla en un archivo de disco**  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye lo siguiente:  
  
-   **Un preconfiguradas puerto de envío que se usa la canalización de envío de procesador de error de ESB.** Puede configurar este puerto de envío según sus propios requisitos específicos.  
  
-   **El ejemplo del controlador de excepción de personalizada de conservación de mensaje.** Este ejemplo muestra cómo un controlador de excepción genérica acoplamiento flexible puede recibir mensajes de error, extraer los mensajes de BizTalk Server contienen, normalizar y enriquecer los mensajes y escribirlos como archivos de disco en el sistema de archivos.  
  
-   **El ejemplo de enrutamiento de mensajes de error de BizTalk.** Este ejemplo muestra cómo el marco de trabajo de administración de excepciones de ESB puede normalizar y enriquecer los mensajes de error de forma nativa generados por el mecanismo de enrutamiento de mensajes de error en BizTalk Server.  
  
 Para obtener más información, consulte [ejecuta el mensaje de persistencia personalizado excepción ejemplo del controlador](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) y [ejecutando el error mensaje enrutamiento ESB procesamiento de ejemplo de BizTalk](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).