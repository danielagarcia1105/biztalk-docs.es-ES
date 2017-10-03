---
title: "Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a><span data-ttu-id="e57dc-102">Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e57dc-102">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>
<span data-ttu-id="e57dc-103">Un puerto de transmisión puede enviar cualquier tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e57dc-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="e57dc-104">Cuando BizTalk Server envía un mensaje a través del Adaptador de Microsoft BizTalk para TIBCO Rendezvous, el adaptador genera el mensaje basándose en los valores de las propiedades de contexto del mensaje o bien usa el valor predeterminado y lo envía al destinatario especificado.</span><span class="sxs-lookup"><span data-stu-id="e57dc-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e57dc-105">Según la documentación de TIBCO Rendezvous, no se admiten caracteres comodín en nombres de destinatarios de transmisión.</span><span class="sxs-lookup"><span data-stu-id="e57dc-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="e57dc-106">Tratamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="e57dc-106">Message Handling</span></span>  
 <span data-ttu-id="e57dc-107">El adaptador mantiene un estado y trata los mensajes entrantes de BizTalk Server en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="e57dc-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="e57dc-108">Si no se puede enviar un mensaje debido a un fallo de transporte, se indica a BizTalk Server que vuelva a enviar más tarde.</span><span class="sxs-lookup"><span data-stu-id="e57dc-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="e57dc-109">Si no se puede enviar un mensaje porque el adaptador esté aún inicializándose, el mensaje de BizTalk Server se pondrá en cola.</span><span class="sxs-lookup"><span data-stu-id="e57dc-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="e57dc-110">Si se produce un error de inicialización, BizTalk Server tiene instrucciones de volver a enviarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="e57dc-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="e57dc-111">Generación de mensajes</span><span class="sxs-lookup"><span data-stu-id="e57dc-111">Message Generation</span></span>  
 <span data-ttu-id="e57dc-112">Con el adaptador de transmisión, el Adaptador de BizTalk para TIBCO Rendezvous ignora el espacio de nombres de destino del mensaje y el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="e57dc-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="e57dc-113">Si el adaptador envía mensajes, envía la carga como está.</span><span class="sxs-lookup"><span data-stu-id="e57dc-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="e57dc-114">Si el adaptador genera un mensaje TIBCO Rendezvous estructurado, el nombre del elemento raíz se ignora (el mensaje no tiene nombre).</span><span class="sxs-lookup"><span data-stu-id="e57dc-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="e57dc-115">En cada caso, el adaptador usa una propiedad de contexto para encontrar el asunto que debe usar al publicar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e57dc-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="e57dc-116">Para obtener más información, consulte [propiedades de contexto de mensaje de BizTalk Server (controladores de envío)](../core/biztalk-server-message-context-properties-send-handlers.md) y [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span><span class="sxs-lookup"><span data-stu-id="e57dc-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57dc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e57dc-117">See Also</span></span>  
 <span data-ttu-id="e57dc-118">[Creación de puertos de envío](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="e57dc-118">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="e57dc-119">Crear controladores de envío TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="e57dc-119">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)