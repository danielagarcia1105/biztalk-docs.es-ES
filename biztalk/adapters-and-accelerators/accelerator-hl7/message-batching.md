---
title: Procesamiento por lotes de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849f14113d5a5e4776c303ef7a5ea4e1e50a552b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-batching"></a>Procesamiento por lotes de mensajes
Estándares de protocolo, problemas de programación o limitaciones de tamaño de mensaje pueden motivar a la necesidad de mensajes por lotes. Un lote de siete de nivel de mantenimiento (HL7) se compone de delimitadas por un encabezado de lote de HL7 y finalizador de lote de mensajes. Separadores de mensaje separan los mensajes individuales dentro del lote.  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] mensaje admite los siguientes tres escenarios de procesamiento por lotes:  
  
-   **Fragmentados por lotes entrantes**. En este escenario, BTAHL7 recibe un lote de mensajes HL7 y, a continuación, enruta los mensajes individuales en el sistema de destino.  
  
-   **Procesar por lotes en / lote**. En este escenario, BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
-   **Crear el lote o el procesamiento por lotes saliente**. En este escenario, BTAHL7 recibe los mensajes individuales y los lotes antes de enrutarlos al sistema de destino.  
  
    > [!NOTE]
    >  BTAHL7 no habilita el procesamiento por lotes de mensajes para procesar por lotes salientes de forma predeterminada. Debe usar el Explorador de BizTalk para primero dar de alta la orquestación de lotes de BTAHL7 y, a continuación, iniciar la orquestación del lote. Para obtener más información acerca de cómo habilitar el procesamiento por lotes de mensajes, vea [configurar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [Configurar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [Programar el procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [Configurar confirmaciones de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)