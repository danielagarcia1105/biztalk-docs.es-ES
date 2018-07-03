---
title: Servicio World Wide Web del host no está disponible | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b14eaae-2158-4aef-9561-610d033998be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c3623a7f39f773f720fa33cd64a7e93c3668d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991109"
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="33ae2-102">El Servicio World Wide Web del host no está disponible</span><span class="sxs-lookup"><span data-stu-id="33ae2-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="33ae2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="33ae2-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="33ae2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="33ae2-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="33ae2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="33ae2-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="33ae2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="33ae2-106">Event ID</span></span>     |                                         <span data-ttu-id="33ae2-107">0</span><span class="sxs-lookup"><span data-stu-id="33ae2-107">0</span></span>                                          |
|  <span data-ttu-id="33ae2-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="33ae2-108">Event Source</span></span>   |                                         <span data-ttu-id="33ae2-109">0</span><span class="sxs-lookup"><span data-stu-id="33ae2-109">0</span></span>                                          |
|    <span data-ttu-id="33ae2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="33ae2-110">Component</span></span>    |                                         <span data-ttu-id="33ae2-111">0</span><span class="sxs-lookup"><span data-stu-id="33ae2-111">0</span></span>                                          |
|  <span data-ttu-id="33ae2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="33ae2-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="33ae2-113">0</span><span class="sxs-lookup"><span data-stu-id="33ae2-113">0</span></span>                                          |
|  <span data-ttu-id="33ae2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="33ae2-114">Message Text</span></span>   |             <span data-ttu-id="33ae2-115">El servicio World Wide Web (W3SVC) en el host "{0}" no está disponible</span><span class="sxs-lookup"><span data-stu-id="33ae2-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="33ae2-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="33ae2-116">Explanation</span></span>  
 <span data-ttu-id="33ae2-117">Este error indica que el servicio World Wide Web no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="33ae2-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33ae2-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="33ae2-118">User Action</span></span>  
 <span data-ttu-id="33ae2-119">Use el procedimiento siguiente para iniciar el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="33ae2-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="33ae2-120">Para iniciar el servicio World Wide Web</span><span class="sxs-lookup"><span data-stu-id="33ae2-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="33ae2-121">Haga clic en **iniciar**, haga clic en **Panel de Control**, haga doble clic en **herramientas administrativas**y haga doble clic en **servicios**.</span><span class="sxs-lookup"><span data-stu-id="33ae2-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="33ae2-122">En la columna nombre, busque **publicación World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="33ae2-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="33ae2-123">Asegúrese de que el estado es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="33ae2-123">Ensure that the status is **Started**.</span></span>