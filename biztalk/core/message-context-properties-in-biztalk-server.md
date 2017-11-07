---
title: Usar propiedades de contexto del mensaje de TIBCO EMS | Documentos de Microsoft
description: "Utilice los campos de descriptor de mensajes de TIBCO Enterprise Message System en una orquestación de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4f0d8c606724cec9c85551251cb003aa8a7e34
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="message-context-properties-in-tibco-ems"></a><span data-ttu-id="25f7a-103">Propiedades de contexto de mensaje de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="25f7a-103">Message Context Properties in TIBCO EMS</span></span>

## <a name="tibcoemspropertiesdll"></a><span data-ttu-id="25f7a-104">TibcoEMSProperties.dll</span><span class="sxs-lookup"><span data-stu-id="25f7a-104">TibcoEMSProperties.dll</span></span>
<span data-ttu-id="25f7a-105">Para obtener acceso a campos de descriptor de mensajes de TIBCO Enterprise Message System desde una orquestación de BizTalk Server, debe agregar una referencia a **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** al proyecto.</span><span class="sxs-lookup"><span data-stu-id="25f7a-105">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="25f7a-106">Este ensamblado se encuentra en  **\<EMS_Adapter_installation_directory TIBCO > \bin**.</span><span class="sxs-lookup"><span data-stu-id="25f7a-106">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory>\bin**.</span></span> <span data-ttu-id="25f7a-107">Tras hacer referencia a este esquema de propiedad de TIBCO EMS, se puede obtener acceso a propiedades de contexto adicionales mediante varias herramientas de desarrollo de BizTalk Server (por ejemplo, la forma Asignación de mensaje en el Diseñador de orquestaciones).</span><span class="sxs-lookup"><span data-stu-id="25f7a-107">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="access-context-properties"></a><span data-ttu-id="25f7a-108">Obtener acceso a propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="25f7a-108">Access context Properties</span></span>  
 <span data-ttu-id="25f7a-109">Para obtener acceso a la propiedad de contexto, especifique una de las disponibles en el espacio de nombres de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="25f7a-109">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="25f7a-110">Para leer la propiedad de contexto de un mensaje recibido de un puerto enlazado con el adaptador de BizTalk para TIBCO EMNS, use la siguiente sintaxis en una expresión:</span><span class="sxs-lookup"><span data-stu-id="25f7a-110">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="25f7a-111">Para obtener más información, consulte [propiedades de Descriptor de mensajes de TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span><span class="sxs-lookup"><span data-stu-id="25f7a-111">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="25f7a-112">En BizTalk Server, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="25f7a-112">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="25f7a-113">Por lo tanto, para asignar un valor de propiedad de contexto de mensaje, cree un nuevo mensaje, configure el contenido de mensaje (puede hacerlo mediante la asignación de un mensaje existente) y, a continuación, configure las propiedades que necesite.</span><span class="sxs-lookup"><span data-stu-id="25f7a-113">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="25f7a-114">Para asignar propiedades de contexto de TIBCO EMS a un mensaje destinado a un puerto de envío enlazado con el adaptador de BizTalk para TIBCO EMS, utilice el operador de asignación de mensajes y especifique una de las propiedades de contexto disponibles en el espacio de nombres de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="25f7a-114">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="25f7a-115">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="25f7a-115">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a><span data-ttu-id="25f7a-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="25f7a-116">Next steps</span></span>
-   [<span data-ttu-id="25f7a-117">Valores & Propiedades de Descriptor de mensajes de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="25f7a-117">TIBCO EMS Message Descriptor properties & values</span></span>](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [<span data-ttu-id="25f7a-118">Tutorial: Uso de las propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="25f7a-118">Tutorial: Use Message Context Properties</span></span>](../core/tutorial-using-message-context-properties.md)