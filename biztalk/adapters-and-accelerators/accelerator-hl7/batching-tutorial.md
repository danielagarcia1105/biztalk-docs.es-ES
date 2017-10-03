---
title: Tutorial de procesamiento por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e2aff66468c697c92adb4c452250b70dae2e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batching-tutorial"></a>Tutorial de procesamiento por lotes
Este tutorial proporciona procedimientos paso a paso para usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para enviar y recibir mensajes por lotes. Procesamiento por lotes implica la recepción y/o el envío de un grupo de mensajes individuales (o confirmaciones) como un solo mensaje compuesto.  
  
 BTAHL7 admite los siguientes tres escenarios de procesamiento por lotes de mensajes:  
  
-   **Fragmentados por lotes entrantes**. En este escenario, BTAHL7 recibe un lote de mensajes HL7 y, a continuación, enruta los mensajes individuales en el sistema de destino.  
  
-   **Procesar por lotes en / lote**. BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
-   **Crear lote (o procesamiento por lotes saliente)**. BTAHL7 recibe los mensajes individuales y los lotes antes de enrutarlos al sistema de destino.  
  
 Este tutorial incluye elementos para cada uno de los tres escenarios de procesamiento por lotes. Utilice las tres partes del tutorial en el orden proporcionado; parte 1 contiene los pasos necesarios para la parte 2 y 3 de la parte.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparando para utilizar el Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [Parte 1: Escenario de fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [Parte 2: Lote / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [Parte 3: Escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)