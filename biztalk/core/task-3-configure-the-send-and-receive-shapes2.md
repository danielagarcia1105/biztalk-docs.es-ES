---
title: 'Tarea 3: Configurar el envío y recepción formas2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279028"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a>Tarea 3: Configurar el envío y recepción formas
Utilice este procedimiento para configurar las formas de envío y recepción.  
  
### <a name="to-configure-the-send-and-receive-shapes"></a>Para configurar las formas de envío y recepción  
  
1.  Arrastre las formas de envío y recepción del cuadro de herramientas al centro de la orquestación en el siguiente orden.  
  
2.  Establezca los parámetros siguientes:  
  
    |Forma|Nombre|Configuración|  
    |-----------|----------|-------------|  
    |Receive1|Activate|True|  
    ||de mensaje|BeginDocMsg|  
    ||Nombre|ReceiveBeginDoc|  
    ||Operación|BeginDoc.Operation_1.Request|  
    |Send1|de mensaje|BeginDocSessionMsg|  
    ||Nombre|SendBeginDoc|  
    ||Operación|JDEPort.Operation_1.Request|  
    |Receive2|Activate|False|  
    ||de mensaje|BeginDocResponseMsg|  
    ||Nombre|ReceiveBeginDocResponse|  
    ||Operación|JDEPort.Operation_1.Response|  
    |Send2|de mensaje|EditLineSessionMsg|  
    ||Nombre|SendEditLine|  
    ||Operación|JDEPort.Operation_2.Request|  
    |Receive3|Activate|False|  
    ||de mensaje|EditLineResponseMsg|  
    ||Nombre|ReceiveEditLine|  
    ||Operación|JDEPort.Operation_2.Response|  
    |Send3|de mensaje|EndDocSessionMsg|  
    ||Nombre|SendEndDoc|  
    ||Operación|JDEPort.Operation_3.Request|  
    |Receive4|Activate|False|  
    ||de mensaje|EndDocResponseMsg|  
    ||Nombre|ReceiveEndDocResponse|  
    ||Operación|JDEPort.Operation_3.Response|  
    |Send4|de mensaje|EndDocResponseMsg|  
    ||Nombre|SendEndDocResponse|  
    ||Operación|EndDocOut.Operation_1.Request|  
  
## <a name="see-also"></a>Vea también  
 [Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md)   
 [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md)   
 [Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md)   
 [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape2.md)