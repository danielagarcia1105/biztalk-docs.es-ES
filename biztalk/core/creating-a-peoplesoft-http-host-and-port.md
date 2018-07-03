---
title: Creación de puertos y hosts HTTP de PeopleSoft | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d991642b45a636c50ea12148d07efd8b93917754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997165"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a><span data-ttu-id="eb867-102">Creación de puertos y hosts HTTP de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="eb867-102">Creating a PeopleSoft HTTP Host and Port</span></span>
<span data-ttu-id="eb867-103">La arquitectura de publicación de mensajes en PeopleSoft se conoce como Integration Broker.</span><span class="sxs-lookup"><span data-stu-id="eb867-103">The Message publication architecture in PeopleSoft is known as Integration Broker.</span></span> <span data-ttu-id="eb867-104">Los componentes principales de Integration Broker son:</span><span class="sxs-lookup"><span data-stu-id="eb867-104">The main components of Integration Broker are as follows:</span></span>  
  
- <span data-ttu-id="eb867-105">Puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="eb867-105">Gateway</span></span>  
  
- <span data-ttu-id="eb867-106">Nodo de publicación</span><span class="sxs-lookup"><span data-stu-id="eb867-106">Publishing node</span></span>  
  
- <span data-ttu-id="eb867-107">Nodo de suscriptor</span><span class="sxs-lookup"><span data-stu-id="eb867-107">Subscriber node</span></span>  
  
  <span data-ttu-id="eb867-108">Los tres funcionan conjuntamente para publicar un mensaje en una dirección URL para una escucha HTTP.</span><span class="sxs-lookup"><span data-stu-id="eb867-108">All three work together to publish a message to a URL for an HTTP listener.</span></span> <span data-ttu-id="eb867-109">Debe configurar el nodo de publicación.</span><span class="sxs-lookup"><span data-stu-id="eb867-109">You must set the Publishing node.</span></span> <span data-ttu-id="eb867-110">PeopleSoft tiene un nodo de publicación predeterminad, conocido también como nodo de mensaje local.</span><span class="sxs-lookup"><span data-stu-id="eb867-110">PeopleSoft has a default publishing node, also known as local message node.</span></span> <span data-ttu-id="eb867-111">Debe activar el nodo y las transacciones para el nodo de publicación.</span><span class="sxs-lookup"><span data-stu-id="eb867-111">You must activate the node and the transactions for the publishing node.</span></span> <span data-ttu-id="eb867-112">Debe configurar el nodo de suscripción con el tipo como nodo externo y, a continuación, activar el nodo y las transacciones.</span><span class="sxs-lookup"><span data-stu-id="eb867-112">You must set the Subscription node with the type as external node, and then activate the node and the transactions.</span></span> <span data-ttu-id="eb867-113">Para este nodo, también configura el tipo para que sea HTTP, y configura la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="eb867-113">For this node, you also set the type to be HTTP and set the connection information.</span></span>  
  
  <span data-ttu-id="eb867-114">Para crear un host y un puerto HTTP de PeopleSoft donde PeopleSoft envíe los eventos, se usa PeopleSoft Integration Broker.</span><span class="sxs-lookup"><span data-stu-id="eb867-114">You use PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="eb867-115">Asegúrese de que el mensaje esté activo y enrutado mediante el procedimiento descrito en [cómo comprobar el estado de actividad de un mensaje](../core/how-to-verify-activity-status-of-a-message.md).</span><span class="sxs-lookup"><span data-stu-id="eb867-115">You make sure that the message is active and routed by using the procedure in [How to Verify Activity Status of a Message](../core/how-to-verify-activity-status-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb867-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eb867-116">In This Section</span></span>  
  
-   [<span data-ttu-id="eb867-117">Cómo comprobar el estado de actividad de un mensaje</span><span class="sxs-lookup"><span data-stu-id="eb867-117">How to Verify Activity Status of a Message</span></span>](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [<span data-ttu-id="eb867-118">Cómo configurar la puerta de enlace de integración y el conector de salida HTTP</span><span class="sxs-lookup"><span data-stu-id="eb867-118">How to Configure the Integration Gateway and HTTP Output Connector</span></span>](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [<span data-ttu-id="eb867-119">Cómo crear un nuevo nodo de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="eb867-119">How to Create a New Gateway Node</span></span>](../core/how-to-create-a-new-gateway-node.md)  
  
-   [<span data-ttu-id="eb867-120">Cómo agregar una transacción</span><span class="sxs-lookup"><span data-stu-id="eb867-120">How to Add a Transaction</span></span>](../core/how-to-add-a-transaction.md)  
  
-   [<span data-ttu-id="eb867-121">Cómo probar el nodo HTTP</span><span class="sxs-lookup"><span data-stu-id="eb867-121">How to Test the HTTP Node</span></span>](../core/how-to-test-the-http-node.md)