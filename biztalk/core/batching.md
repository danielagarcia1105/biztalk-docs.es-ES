---
title: Procesamiento por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching"></a>Procesar por lotes
*Procesamiento por lotes* es un procesamiento serializado de un conjunto de mensajes que permite optimizaciones con respecto a la base de datos de ida y vuelta. Un lote constituye una unidad de trabajo atómica, es decir, el resultado correcto o incorrecto se produce en todo el conjunto. Si una operación en lote se realiza correctamente pero se producen errores en otra operación, todas las operaciones que componen el lote quedan invalidadas y deben repetirse.  
  
 BizTalk Server utiliza el procesamiento por lotes con los siguientes objetivos:  
  
-   Amortizar el costo de las transacciones entre varios mensajes.  
  
-   Aumentar la velocidad mediante la reducción del número interno de ciclos de ida y vuelta de base de datos.  
  
-   Optimizar el empleo del grupo de subprocesos de BizTalk Server mediante la API asíncrona de BizTalk Server.  
  
## <a name="applying-batching"></a>Aplicar el procesamiento por lotes  
 El procesamiento por lotes se configura en las propiedades avanzadas de una ubicación de recepción y se activa de forma automática en el puerto de envío.  
  
## <a name="lowering-the-batch-size"></a>Reducir el tamaño del lote  
 Debe reducir el tamaño de lote en las instancias siguientes:  
  
-   Al procesar mensajes de gran tamaño.  
  
-   Cuando los ciclos de ida y vuelta de base de datos no forman el cuello de botella.  
  
> [!NOTE]
>  Tenga cuidado al cambiar la **LargeMessageThreshold** configuración. El tamaño de lote multiplicado por el tamaño promedio del mensaje debe ser menor que el **LargeMessageThreshold** configuración a menos que el tamaño del lote es 1.  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería](../core/the-messaging-engine.md)   
 [Mensajes por lotes para el proceso de recepción](../core/batching-messages-for-receive-processing.md)   
 [Procesamiento por lotes de mensajes para el procesamiento de envío](../core/batching-messages-for-send-processing.md)