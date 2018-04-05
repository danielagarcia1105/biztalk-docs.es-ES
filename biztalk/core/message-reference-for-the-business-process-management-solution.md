---
title: Referencia de mensajes para la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, message reference
ms.assetid: 0595817e-da5d-426a-9ee1-0c5d04334de6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f22551bb22af20566fd6bff412dd8cf42f2a5911
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-reference-for-the-business-process-management-solution"></a>Referencia de mensajes para la solución de administración de procesos empresariales
En esta sección se muestran los mensajes y tipos de mensajes utilizados por cada orquestación de la solución.  
  
 En la tabla, \< *Prefijosolución* \> sustituye a Microsoft.Samples.BizTalk.SouthridgeVideo para facilitar la lectura de la tabla.  
  
> [!NOTE]
>  Un tipo de mensaje de **System.Xml.XmlDocument** indica un tipo de mensaje definido por una clase .NET en lugar de un esquema.  
  
 Las orquestaciones, los mensajes y los tipos son los siguientes.  
  
|Orquestación|de mensaje|Tipo de mensaje|  
|-------------------|-------------|------------------|  
|Activate.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Activate.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|Analyze.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|Analyze.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|TerminatedMsg|\<Prefijosolución\>. SchemaClasses.Terminated|  
|CableOrder1.odx|OrderMgrMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|CompletionMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|CableOrder1.odx|AckMsg|\<Prefijosolución\>. SchemaClasses.OrderAck|  
|CableOrder1.odx|InterruptMsg|\<Prefijosolución\>. SchemaClasses.Interrupt|  
|CableOrder2.odx|OrderMgrMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|CableOrder2.odx|TerminatedMsg|\<Prefijosolución\>. SchemaClasses.Terminated|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|CableOrder2.odx|CompleteOrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|CableOrder2.odx|AckMsg|\<Prefijosolución\>. SchemaClasses.OrderAck|  
|CableOrder2.odx|CompletionMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Cancel.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Change.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|CheckInterrupt.odx|InterruptMsg|\<Prefijosolución\>. SchemaClasses.Interrupt|  
|Complete.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|Complete.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|InterruptMsg|\<Prefijosolución\>. SchemaClasses.Interrupt|  
|ErrorHandler.odx|OrderStatusMsg|\<Prefijosolución\>. SchemaClasses.OrderStatus|  
|ErrorHandler.odx|ResponseMsg|\<Prefijosolución\>. SchemaClasses.OrderStatus|  
|ErrorHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|ReturnedMsg|System.Xml.XmlDocument|  
|ExceptionHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|Interrupter.odx|InterruptMsg|\<Prefijosolución\>. SchemaClasses.Interrupt|  
|OrderBroker.odx|CSRConfMsg|\<Prefijosolución\>. OrderBrokerSchemas.CSR_OrderRequestSchema|  
|OrderBroker.odx|CSROrderMsg|\<Prefijosolución\>. OrderBrokerSchemas.CSR_OrderRequestSchema|  
|OrderBroker.odx|HistoryInsertMsg|\<Prefijosolución\>. OrderBrokerSchemas.SQLHistoryInsertSchema.HistoryInsert|  
|OrderBroker.odx|ServicingMsg|\<Prefijosolución\>. OrderBrokerSchemas.Servicing_OrderRequestSchema|  
|OrderBroker.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
|OrderBroker.odx|OrderMgrMsg|\<Prefijosolución\>. OrderBroker.OrderMgrMPMsg|  
|OrderManager.odx|CompletionMsg|\<Prefijosolución\>. SchemaClasses.OrderStatus|  
|OrderManager.odx|NewOrderMgrMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderMgrMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderAck|\<Prefijosolución\>. SchemaClasses.OrderAck|  
|OrderManager.odx|TerminatedMsg|\<Prefijosolución\>. SchemaClasses.Terminated|  
|OrderManager.odx|ErrorMsg|\<Prefijosolución\>. OrderManager.OrderMgrMsgType|  
|Validate.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|OrderMsg|\<Prefijosolución\>. Schemas.OrderSchema|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de solución de administración de proceso empresarial](../core/business-process-management-solution-reference.md)   
 [Campos y los mensajes de teclado](../core/key-messages-and-fields.md)   
 [Flujo de pedidos mediante el administrador de procesos](../core/order-flow-through-the-process-manager.md)