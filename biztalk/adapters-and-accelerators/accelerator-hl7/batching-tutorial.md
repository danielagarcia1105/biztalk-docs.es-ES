---
title: Tutorial de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790303ac2026cbbce2fdb1c436e3dc8c7e9ff7f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980093"
---
# <a name="batching-tutorial"></a>Tutorial de procesamiento por lotes
Este tutorial proporciona procedimientos paso a paso para usar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para recibir y enviar los mensajes procesados por lotes. Procesamiento por lotes implica la recepción o el envío de un grupo de mensajes individuales (o las confirmaciones) como un solo mensaje compuesto.  
  
 BTAHL7 admite los siguientes tres escenarios de procesamiento por lotes de mensajes:  
  
- **Lote de entrada fragmentado**. En este escenario, BTAHL7 recibe un lote de mensajes de HL7 y, a continuación, enruta los mensajes individuales para el sistema de destino.  
  
- **Procesar por lotes en o salida**. BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
- **Creación de lote (o el procesamiento por lotes saliente)**. BTAHL7 recibe los mensajes individuales y crea los lotes antes de enrutarlos al sistema de destino.  
  
  Este tutorial incluye elementos para cada uno de los tres escenarios de procesamiento por lotes. Use las tres partes del tutorial en el orden indicado; parte 1 contiene pasos de requisitos previos para la parte 2 y 3.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparación para usar el tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [Parte 1: Escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [Parte 2: Escenario de lote de entrada o salida](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)