---
title: El bucle contiene un nodo de hoja. Solo puede contener otros bucles o segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8d88e0fb114255d19310eefb87e00c820b17420
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014237"
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a><span data-ttu-id="e33a4-103">El bucle contiene un nodo de hoja.</span><span class="sxs-lookup"><span data-stu-id="e33a4-103">The loop contains a leaf node.</span></span> <span data-ttu-id="e33a4-104">Sólo puede contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="e33a4-104">It can only contain other Loops or Segments</span></span>
## <a name="details"></a><span data-ttu-id="e33a4-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="e33a4-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e33a4-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e33a4-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e33a4-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e33a4-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e33a4-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e33a4-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e33a4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e33a4-109">Event Source</span></span>   | <span data-ttu-id="e33a4-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e33a4-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="e33a4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e33a4-111">Component</span></span>    |                                       <span data-ttu-id="e33a4-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e33a4-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e33a4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e33a4-113">Symbolic Name</span></span>  |                           <span data-ttu-id="e33a4-114">SchemaCode125ELoopContainsLeafNode</span><span class="sxs-lookup"><span data-stu-id="e33a4-114">SchemaCode125ELoopContainsLeafNode</span></span>                           |
|  <span data-ttu-id="e33a4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e33a4-115">Message Text</span></span>   |       <span data-ttu-id="e33a4-116">El bucle contiene un nodo de hoja.</span><span class="sxs-lookup"><span data-stu-id="e33a4-116">The loop contains a leaf node.</span></span> <span data-ttu-id="e33a4-117">Sólo puede contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="e33a4-117">It can only contain other Loops or Segments</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="e33a4-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e33a4-118">Explanation</span></span>  
 <span data-ttu-id="e33a4-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio no se ajustaba al esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="e33a4-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the interchange did not conform to the document schema.</span></span> <span data-ttu-id="e33a4-120">En este caso, un bucle contenía un nodo hoja sin hijos, mientras que el esquema especificada que el bucle solo podía contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="e33a4-120">In this case, a loop contained a childless leaf node, whereas the schema specified that the loop could only contain other loops or segments.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e33a4-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e33a4-121">User Action</span></span>  
 <span data-ttu-id="e33a4-122">Para resolver este error, pida al remitente del conjunto de transacciones que corrija el bucle de modo que no contenga nodos de hoja y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e33a4-122">To resolve this error, have the sender of the interchange fix the loop so that it does not contain leaf nodes, and then resend the interchange.</span></span>