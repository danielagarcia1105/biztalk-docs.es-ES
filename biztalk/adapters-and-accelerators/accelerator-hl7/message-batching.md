---
title: Mensaje de procesamiento por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc1157dc270fceae7b092a252f75e2c0de658eb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004973"
---
# <a name="message-batching"></a>Mensaje de procesamiento por lotes
Estándares de protocolo, problemas de programación o las limitaciones de tamaño de mensaje pueden motivar la necesidad de mensajes por lotes. Un lote de siete de nivel de mantenimiento (HL7) se compone de mensajes está incluidos en un encabezado de lote de HL7 y finalizador de batch. Separadores de mensaje separan los mensajes individuales dentro del lote.  
  
 Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] mensaje admite los siguientes tres escenarios de procesamiento por lotes:  
  
-   **Lote de entrada fragmentado**. En este escenario, BTAHL7 recibe un lote de mensajes de HL7 y, a continuación, enruta los mensajes individuales para el sistema de destino.  
  
-   **Procesar por lotes en o salida**. En este escenario, BTAHL7 recibe un lote de mensajes HL7, comprueba los mensajes individuales dentro del lote y, a continuación, enruta el lote de mensajes en el sistema de destino.  
  
-   **Creación de lote o el procesamiento por lotes saliente**. En este escenario, BTAHL7 recibe los mensajes individuales y crea los lotes antes de enrutarlos al sistema de destino.  
  
    > [!NOTE]
    >  BTAHL7 no habilita el procesamiento por lotes de mensajes por lotes saliente de forma predeterminada. Debe usar el Explorador de BizTalk en primer lugar dar de alta la orquestación del lote BTAHL7 y, a continuación, iniciar la orquestación del lote. Para obtener más información acerca de cómo habilitar el procesamiento por lotes de mensajes, vea [configuración de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [Configuración del procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [Programación del procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [Configuración de confirmaciones de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)