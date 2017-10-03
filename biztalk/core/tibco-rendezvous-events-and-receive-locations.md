---
title: "TIBCO Rendezvous eventos y ubicaciones de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="e89c7-102">TIBCO Rendezvous eventos y ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="e89c7-102">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="e89c7-103">Cualquier sistema TIBCO Rendezvous puede enviar mensajes a su nombre de asunto de elección.</span><span class="sxs-lookup"><span data-stu-id="e89c7-103">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="e89c7-104">El concepto de *eventos* es la generación de mensajes de otros programas de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="e89c7-104">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="e89c7-105">En los pasos siguientes se describe el ciclo de vida de una ubicación de recepción:</span><span class="sxs-lookup"><span data-stu-id="e89c7-105">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="e89c7-106">Se crea la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e89c7-106">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="e89c7-107">La ubicación de recepción se asocia con un host.</span><span class="sxs-lookup"><span data-stu-id="e89c7-107">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="e89c7-108">La ubicación de recepción se enlaza con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e89c7-108">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="e89c7-109">La ubicación de recepción se habilita.</span><span class="sxs-lookup"><span data-stu-id="e89c7-109">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="e89c7-110">La ubicación de recepción recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="e89c7-110">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e89c7-111">Cada ubicación de recepción debe tener un nombre único.</span><span class="sxs-lookup"><span data-stu-id="e89c7-111">Each receive location must have a unique name.</span></span> <span data-ttu-id="e89c7-112">Dos ubicaciones de recepción no pueden tener el mismo nombre en la misma implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e89c7-112">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e89c7-113">Asimismo, conviene establecer listas de control de acceso (ACL) seguras en las ubicaciones de destino de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e89c7-113">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="e89c7-114">Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="e89c7-114">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89c7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e89c7-115">See Also</span></span>  
 [<span data-ttu-id="e89c7-116">Controladores de recepción de creación TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="e89c7-116">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)