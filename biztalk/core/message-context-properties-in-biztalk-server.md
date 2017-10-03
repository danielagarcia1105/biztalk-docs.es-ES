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
# <a name="message-context-properties-in-biztalk-server"></a><span data-ttu-id="144e5-102">Propiedades de contexto de mensaje de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="144e5-102">Message Context Properties in BizTalk Server</span></span>
<span data-ttu-id="144e5-103">Para obtener acceso a campos de descriptor de mensajes de TIBCO Enterprise Message System desde una orquestación de BizTalk Server, debe agregar una referencia a **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** al proyecto.</span><span class="sxs-lookup"><span data-stu-id="144e5-103">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="144e5-104">Este ensamblado se encuentra en  **\<EMS_Adapter_installation_directory TIBCO > \bin**.</span><span class="sxs-lookup"><span data-stu-id="144e5-104">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory>\bin**.</span></span> <span data-ttu-id="144e5-105">Tras hacer referencia a este esquema de propiedad de TIBCO EMS, se puede obtener acceso a propiedades de contexto adicionales mediante varias herramientas de desarrollo de BizTalk Server (por ejemplo, la forma Asignación de mensaje en el Diseñador de orquestaciones).</span><span class="sxs-lookup"><span data-stu-id="144e5-105">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="accessing-context-properties"></a><span data-ttu-id="144e5-106">Obtener acceso a propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="144e5-106">Accessing Context Properties</span></span>  
 <span data-ttu-id="144e5-107">Para obtener acceso a la propiedad de contexto, especifique una de las disponibles en el espacio de nombres de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="144e5-107">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="144e5-108">Para leer la propiedad de contexto de un mensaje recibido de un puerto enlazado con el adaptador de BizTalk para TIBCO EMNS, use la siguiente sintaxis en una expresión:</span><span class="sxs-lookup"><span data-stu-id="144e5-108">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="144e5-109">Para obtener más información, consulte [propiedades de Descriptor de mensajes de TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span><span class="sxs-lookup"><span data-stu-id="144e5-109">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="144e5-110">En BizTalk Server, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="144e5-110">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="144e5-111">Por lo tanto, para asignar un valor de propiedad de contexto de mensaje, cree un nuevo mensaje, configure el contenido de mensaje (puede hacerlo mediante la asignación de un mensaje existente) y, a continuación, configure las propiedades que necesite.</span><span class="sxs-lookup"><span data-stu-id="144e5-111">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="144e5-112">Para asignar propiedades de contexto de TIBCO EMS a un mensaje destinado a un puerto de envío enlazado con el adaptador de BizTalk para TIBCO EMS, utilice el operador de asignación de mensajes y especifique una de las propiedades de contexto disponibles en el espacio de nombres de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="144e5-112">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="144e5-113">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="144e5-113">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="144e5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="144e5-114">See Also</span></span>  
 [<span data-ttu-id="144e5-115">Propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="144e5-115">Message Context Properties</span></span>](../core/message-context-properties2.md)