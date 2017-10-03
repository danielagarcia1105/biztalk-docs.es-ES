---
title: Propiedades de contexto en el servidor BizTalk Server del mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, accessing
- message context properties, BizTalk Server
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e92e458ec6927ab8e1bc6082cd9a71ee3e4387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-in-biztalk-server"></a>Propiedades de contexto de mensaje de BizTalk Server
Para obtener acceso a campos de descriptor de mensajes de TIBCO Enterprise Message System desde una orquestación de BizTalk Server, debe agregar una referencia a **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** al proyecto. Este ensamblado se encuentra en  **\<EMS_Adapter_installation_directory TIBCO > \bin**. Tras hacer referencia a este esquema de propiedad de TIBCO EMS, se puede obtener acceso a propiedades de contexto adicionales mediante varias herramientas de desarrollo de BizTalk Server (por ejemplo, la forma Asignación de mensaje en el Diseñador de orquestaciones).  
  
## <a name="accessing-context-properties"></a>Obtener acceso a propiedades de contexto  
 Para obtener acceso a la propiedad de contexto, especifique una de las disponibles en el espacio de nombres de TIBCO EMS. Para leer la propiedad de contexto de un mensaje recibido de un puerto enlazado con el adaptador de BizTalk para TIBCO EMNS, use la siguiente sintaxis en una expresión:  
  
```  
Message(TibcoEMS.Property)  
```  
  
 Para obtener más información, consulte [propiedades de Descriptor de mensajes de TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-message-descriptor-properties.md).  
  
 En BizTalk Server, los mensajes son inmutables. Por lo tanto, para asignar un valor de propiedad de contexto de mensaje, cree un nuevo mensaje, configure el contenido de mensaje (puede hacerlo mediante la asignación de un mensaje existente) y, a continuación, configure las propiedades que necesite.  
  
 Para asignar propiedades de contexto de TIBCO EMS a un mensaje destinado a un puerto de envío enlazado con el adaptador de BizTalk para TIBCO EMS, utilice el operador de asignación de mensajes y especifique una de las propiedades de contexto disponibles en el espacio de nombres de TIBCO EMS. La sintaxis es la siguiente:  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de contexto de mensaje](../core/message-context-properties2.md)