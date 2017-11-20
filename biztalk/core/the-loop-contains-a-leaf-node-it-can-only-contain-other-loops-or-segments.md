---
title: El bucle contiene un nodo de hoja. Solo puede contener otros bucles o segmentos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a><span data-ttu-id="b883c-103">El bucle contiene un nodo de hoja.</span><span class="sxs-lookup"><span data-stu-id="b883c-103">The loop contains a leaf node.</span></span> <span data-ttu-id="b883c-104">Sólo puede contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="b883c-104">It can only contain other Loops or Segments</span></span>
## <a name="details"></a><span data-ttu-id="b883c-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="b883c-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b883c-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b883c-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b883c-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b883c-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b883c-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b883c-108">Event ID</span></span>|-|  
|<span data-ttu-id="b883c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b883c-109">Event Source</span></span>|<span data-ttu-id="b883c-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b883c-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b883c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b883c-111">Component</span></span>|<span data-ttu-id="b883c-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b883c-112">EDI Engine</span></span>|  
|<span data-ttu-id="b883c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b883c-113">Symbolic Name</span></span>|<span data-ttu-id="b883c-114">SchemaCode125ELoopContainsLeafNode</span><span class="sxs-lookup"><span data-stu-id="b883c-114">SchemaCode125ELoopContainsLeafNode</span></span>|  
|<span data-ttu-id="b883c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b883c-115">Message Text</span></span>|<span data-ttu-id="b883c-116">El bucle contiene un nodo de hoja.</span><span class="sxs-lookup"><span data-stu-id="b883c-116">The loop contains a leaf node.</span></span> <span data-ttu-id="b883c-117">Sólo puede contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="b883c-117">It can only contain other Loops or Segments</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b883c-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="b883c-118">Explanation</span></span>  
 <span data-ttu-id="b883c-119">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante debido a que el intercambio no se ajustaba al esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="b883c-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the interchange did not conform to the document schema.</span></span> <span data-ttu-id="b883c-120">En este caso, un bucle contenía un nodo hoja sin hijos, mientras que el esquema especificada que el bucle solo podía contener otros bucles o segmentos.</span><span class="sxs-lookup"><span data-stu-id="b883c-120">In this case, a loop contained a childless leaf node, whereas the schema specified that the loop could only contain other loops or segments.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b883c-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b883c-121">User Action</span></span>  
 <span data-ttu-id="b883c-122">Para resolver este error, pida al remitente del conjunto de transacciones que corrija el bucle de modo que no contenga nodos de hoja y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="b883c-122">To resolve this error, have the sender of the interchange fix the loop so that it does not contain leaf nodes, and then resend the interchange.</span></span>