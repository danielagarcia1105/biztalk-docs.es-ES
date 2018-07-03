---
title: Recopilación de excepciones y conservación de la carga mediante el procesador de excepciones de ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c43925006153ccfdcfa0c9700dd1ecf27fd3fd2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994821"
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>Recopilación de excepciones y conservación de la carga mediante el procesador de excepciones de ESB
En este caso de uso, el controlador de excepciones para una orquestación publica un mensaje de error ESB en el cuadro de mensaje de BizTalk Server o el mecanismo de enrutamiento de mensajes de error de BizTalk genera un mensaje de error. Un puerto de envío configurado previamente con el componente de canalización de codificador de excepciones de ESB, se suscribe a ambos de los tipos de mensaje de error. Procesa los mensajes de error y los conserva como archivos de disco que se pueden ver mediante InfoPath, como se muestra en la figura 1.  
  
 ![Recopilar Carga de excepciones](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")  
  
 **Figura 1**  
  
 **Captura de un mensaje de error y guardarlos en un archivo de disco**  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye lo siguiente:  
  
- **Un preconfigurada puerto de envío que usa la canalización de envío del procesador de errores de ESB.** Puede configurar este puerto de envío según sus propios requisitos específicos.  
  
- **El ejemplo de controlador de excepciones de mensaje persistencia personalizada.** Este ejemplo muestra cómo un controlador de excepciones con acoplamiento flexible puede recibir mensajes de error, extraer los mensajes de BizTalk Server contienen, normalizar y enriquecer los mensajes y escribirlos como archivos de disco en el sistema de archivos.  
  
- **El ejemplo de enrutamiento de mensajes de error de BizTalk.** En este ejemplo se muestra cómo el marco de administración de excepciones de ESB puede normalizar y enriquecer los mensajes de error generados de forma nativa mediante el mecanismo de enrutamiento de mensajes de error en BizTalk Server.  
  
  Para obtener más información, consulte [ejecutando el mensaje de persistencia personalizado excepción ejemplo del controlador](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md) y [ejecución del error mensaje enrutamiento ESB procesamiento ejemplo BizTalk](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md).