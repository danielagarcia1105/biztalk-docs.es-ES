---
title: Durante la serialización nodo raíz no se coloca en el elemento de inicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dced7e36802dd9d9ec9620272fc8a96bd6b590
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240052"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a><span data-ttu-id="749a6-102">Durante la serialización, el nodo raíz no se coloca en el elemento de inicio.</span><span class="sxs-lookup"><span data-stu-id="749a6-102">During serialization root node is not placed at start element</span></span>
## <a name="details"></a><span data-ttu-id="749a6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="749a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="749a6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="749a6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="749a6-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="749a6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="749a6-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="749a6-106">Event ID</span></span>|-|  
|<span data-ttu-id="749a6-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="749a6-107">Event Source</span></span>|<span data-ttu-id="749a6-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749a6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="749a6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="749a6-109">Component</span></span>|<span data-ttu-id="749a6-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="749a6-110">EDI Engine</span></span>|  
|<span data-ttu-id="749a6-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="749a6-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="749a6-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="749a6-112">Message Text</span></span>|<span data-ttu-id="749a6-113">Durante la serialización, el nodo raíz no se coloca en el elemento de inicio.</span><span class="sxs-lookup"><span data-stu-id="749a6-113">During serialization root node is not placed at start element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="749a6-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="749a6-114">Explanation</span></span>  
 <span data-ttu-id="749a6-115">Este evento de error,  indica que la canalización de recepción no pudo procesar un intercambio entrante porque el conjunto de transacciones no comienza con un encabezado ST o UNH.</span><span class="sxs-lookup"><span data-stu-id="749a6-115">This Error/Warning/Information event indicates that the receive pipeline could not process an incoming interchange because the transaction set does not start with an ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="749a6-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="749a6-116">User Action</span></span>  
 <span data-ttu-id="749a6-117">Para resolver este error, asegúrese de que cada uno de los conjuntos de transacciones de un intercambio comienza por un segmento ST (para intercambios X12) o por un segmento UNH (para intercambios EDIFACT) y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="749a6-117">To resolve this error, ensure that each of the transaction sets in an interchange starts with an ST segment (for X12 interchanges) or an UNH segment (for EDIFACT interchanges), and then resubmit the interchange.</span></span>