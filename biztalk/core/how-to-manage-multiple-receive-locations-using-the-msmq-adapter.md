---
title: "Cómo administrar varias ubicaciones de recepción mediante el adaptador de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a><span data-ttu-id="9bbf7-102">Cómo administrar varias ubicaciones de recepción mediante el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="9bbf7-102">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>
<span data-ttu-id="9bbf7-103">Para aumentar su rendimiento, el adaptador de MSMQ es multiproceso.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-103">To increase performance, the MSMQ adapter is multithreaded.</span></span> <span data-ttu-id="9bbf7-104">Cuando se han definido muchas ubicaciones de recepción, puede que no haya suficientes subprocesos disponibles para todas estas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-104">If you have many receive locations, there may not be enough threads available for all the receive locations.</span></span> <span data-ttu-id="9bbf7-105">Esto impide que algunas de las ubicaciones de recepción recojan mensajes.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-105">This prevents some of the receive locations from picking up messages.</span></span> <span data-ttu-id="9bbf7-106">Existen tres formas de solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="9bbf7-106">There are three ways to solve this problem:</span></span>  
  
-   <span data-ttu-id="9bbf7-107">Agregar hosts de BizTalk a su equipo y distribuir las ubicaciones de recepción entre los hosts.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-107">Add BizTalk Hosts to your computer and divide the receive locations among the hosts.</span></span> <span data-ttu-id="9bbf7-108">La adición de hosts resulta en más subprocesos disponibles para las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-108">Adding hosts makes more threads available for the receive locations.</span></span>  
  
-   <span data-ttu-id="9bbf7-109">Establecer el **procesamiento en serie** propiedad `True` en cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-109">Set the **Serial Processing** property to `True` on each receive location.</span></span> <span data-ttu-id="9bbf7-110">Cuando esta propiedad se define como `True`, se asigna un solo subproceso a cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-110">Setting the property to `True` assigns a single thread to each receive location.</span></span> <span data-ttu-id="9bbf7-111">Esto deja más subprocesos disponibles en el grupo.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-111">This leaves more threads available in the pool.</span></span> <span data-ttu-id="9bbf7-112">No obstante, también esto puede provocar una disminución del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-112">However, this may also cause a decrease in performance.</span></span>  
  
-   <span data-ttu-id="9bbf7-113">Modificar el Registro para aumentar el número de subprocesos disponibles para el host del controlador de recepción del adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9bbf7-113">Modify the registry to increase the number of threads that are available to the host for the MSMQ adapter receive handler.</span></span> <span data-ttu-id="9bbf7-114">Para obtener más información, consulte el **modificar los valores de subprocesos que alojan CLR para el host** sección de [parámetros de configuración que afectan al rendimiento del adaptador](../core/configuration-parameters-that-affect-adapter-performance.md).</span><span class="sxs-lookup"><span data-stu-id="9bbf7-114">For more information see the **Modify the CLR Hosting thread values for the host** section of [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbf7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bbf7-115">See Also</span></span>  
 [<span data-ttu-id="9bbf7-116">Configurar el adaptador MSMQ</span><span class="sxs-lookup"><span data-stu-id="9bbf7-116">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)