---
title: Servidor Web en el puerto de host no encontrado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987149"
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="ba2a3-102">No se encontró el servidor web en el puerto de host</span><span class="sxs-lookup"><span data-stu-id="ba2a3-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="ba2a3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba2a3-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ba2a3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ba2a3-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ba2a3-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ba2a3-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ba2a3-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ba2a3-106">Event ID</span></span>     |                                         <span data-ttu-id="ba2a3-107">0</span><span class="sxs-lookup"><span data-stu-id="ba2a3-107">0</span></span>                                          |
|  <span data-ttu-id="ba2a3-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ba2a3-108">Event Source</span></span>   |                                         <span data-ttu-id="ba2a3-109">0</span><span class="sxs-lookup"><span data-stu-id="ba2a3-109">0</span></span>                                          |
|    <span data-ttu-id="ba2a3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ba2a3-110">Component</span></span>    |                                         <span data-ttu-id="ba2a3-111">0</span><span class="sxs-lookup"><span data-stu-id="ba2a3-111">0</span></span>                                          |
|  <span data-ttu-id="ba2a3-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ba2a3-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ba2a3-113">0</span><span class="sxs-lookup"><span data-stu-id="ba2a3-113">0</span></span>                                          |
|  <span data-ttu-id="ba2a3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ba2a3-114">Message Text</span></span>   |                    <span data-ttu-id="ba2a3-115">Servidor Web en el host "{0}" puerto {1} no encontrado</span><span class="sxs-lookup"><span data-stu-id="ba2a3-115">Web server on host "{0}" port {1} not found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="ba2a3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ba2a3-116">Explanation</span></span>  
 <span data-ttu-id="ba2a3-117">Este error indica que el servicio World Wide Web (WWW) no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba2a3-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ba2a3-118">User Action</span></span>  
 <span data-ttu-id="ba2a3-119">Use el procedimiento siguiente para iniciar el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="ba2a3-120">Para iniciar el servicio World Wide Web</span><span class="sxs-lookup"><span data-stu-id="ba2a3-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="ba2a3-121">Haga clic en **iniciar**, haga clic en **Panel de Control**, haga doble clic en **herramientas administrativas**y haga doble clic en **servicios.**</span><span class="sxs-lookup"><span data-stu-id="ba2a3-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="ba2a3-122">En la columna nombre, busque **publicación World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="ba2a3-123">Asegúrese de que el estado es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="ba2a3-124">Vuelva a la **herramientas administrativas** ventana.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="ba2a3-125">Haga doble clic en **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="ba2a3-126">Expanda el área de la carpeta y localice el sitio web.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="ba2a3-127">Asegúrese de que el estado es **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="ba2a3-127">Ensure that the status is **Started**.</span></span>