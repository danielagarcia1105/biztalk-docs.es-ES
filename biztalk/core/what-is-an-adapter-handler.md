---
title: ¿Qué es un controlador de adaptador? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- handlers [adapters]
- adapters, handlers
- handlers [adapters], about handlers
ms.assetid: 4d1afa39-6320-467f-a7e8-f5f18236648e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8a1b60661427776dd4e35ffce27bf120bf94a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289308"
---
# <a name="what-is-an-adapter-handler"></a><span data-ttu-id="22e48-103">¿Qué es un controlador de adaptador?</span><span class="sxs-lookup"><span data-stu-id="22e48-103">What Is an Adapter Handler?</span></span>
<span data-ttu-id="22e48-104">Un controlador de adaptador es una instancia de un host de BizTalk en la que se ejecuta el código de adaptador.</span><span class="sxs-lookup"><span data-stu-id="22e48-104">An adapter handler is an instance of a BizTalk host in which the adapter code runs.</span></span> <span data-ttu-id="22e48-105">Al especificar un controlador de envío o de recepción para un adaptador, está especificando la instancia de host en la que se ejecutará el código de adaptador.</span><span class="sxs-lookup"><span data-stu-id="22e48-105">When you specify a send or receive handler for an adapter you are specifying which host instance the adapter code will run in the context of.</span></span> <span data-ttu-id="22e48-106">Un controlador de adaptador se encarga de la ejecución del adaptador, y contiene las propiedades de una instancia de adaptador específica.</span><span class="sxs-lookup"><span data-stu-id="22e48-106">An adapter handler is responsible for executing the adapter and contains properties for a specific instance of an adapter.</span></span> <span data-ttu-id="22e48-107">La configuración predeterminada de BizTalk Server creará controladores de adaptador para todos los adaptadores instalados, aunque puede que desee crear adaptadores adicionales para equilibrar la carga, o bien para aislar los procesos de un determinado controlador de adaptador.</span><span class="sxs-lookup"><span data-stu-id="22e48-107">A default BizTalk Server configuration will create adapter handlers for all of the installed adapters, but you may want to create additional adapter handlers for purposes of load balancing or to provide process isolation for a particular adapter handler.</span></span>  
  
 <span data-ttu-id="22e48-108">Los controladores de adaptador están asociados a una instancia de host de BizTalk, y las instancias de host de BizTalk están, a su vez, asociadas a un servidor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="22e48-108">Adapter handlers are bound to a BizTalk Host instance, and BizTalk Host instances are bound to a BizTalk server.</span></span> <span data-ttu-id="22e48-109">Por tanto, deberá agregar servidores BizTalk adicionales al grupo de BizTalk si desea equilibrar la carga de procesamiento de los adaptadores en todos los servidores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="22e48-109">Therefore, you must add additional BizTalk servers to your BizTalk group if you want to load balance adapter processing across BizTalk servers.</span></span> <span data-ttu-id="22e48-110">No es necesario que agregue servidores de BizTalk adicionales al grupo de BizTalk si está creando controladores de adaptador adicionales con fines de aislamiento de procesos.</span><span class="sxs-lookup"><span data-stu-id="22e48-110">You do not need to add additional BizTalk servers to your BizTalk group if you are creating additional adapter handlers for the purpose of process isolation.</span></span>  
  
 <span data-ttu-id="22e48-111">Si necesita crear una instancia de host nueva para ejecutar un controlador de adaptador, primero deberá crear un host y, a continuación, crear una instancia de ese host para que se ejecute en uno de los servidores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="22e48-111">If you need to create a new host instance to run an adapter handler in, you must first create a host and then create an instance of that host to run on one of your BizTalk servers.</span></span> <span data-ttu-id="22e48-112">Para obtener más información, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md) y [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).</span><span class="sxs-lookup"><span data-stu-id="22e48-112">For more information, see [How to Create a New Host](../core/how-to-create-a-new-host.md) and [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="22e48-113">Todos los controladores de adaptador, a excepción de los controladores de recepción de adaptadores de HTTP y SOAP, deben configurarse de tal forma que se ejecuten en un host en curso.</span><span class="sxs-lookup"><span data-stu-id="22e48-113">All adapter handlers except for HTTP and SOAP adapter receive handlers must be configured to run in an in-process host.</span></span> <span data-ttu-id="22e48-114">Los controladores de adaptador de HTTP y de SOAP sólo pueden ejecutarse en hosts aislados.</span><span class="sxs-lookup"><span data-stu-id="22e48-114">HTTP and SOAP adapter receive handlers can only be run in an isolated host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e48-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e48-115">See Also</span></span>  
 [<span data-ttu-id="22e48-116">Crear y eliminar controladores de adaptador</span><span class="sxs-lookup"><span data-stu-id="22e48-116">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)