---
title: El X12 conjunto de transacciones tiene un recuento que no coincide con SE01 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41539f0492f90d3f7276b0d80af28c568593ef4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278708"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="a218d-102">El conjunto de transacciones X12 tiene un recuento que no coincide con SE01</span><span class="sxs-lookup"><span data-stu-id="a218d-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="a218d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a218d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a218d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a218d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a218d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a218d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a218d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a218d-106">Event ID</span></span>|-|  
|<span data-ttu-id="a218d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a218d-107">Event Source</span></span>|<span data-ttu-id="a218d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a218d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="a218d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a218d-109">Component</span></span>|<span data-ttu-id="a218d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="a218d-110">EDI Engine</span></span>|  
|<span data-ttu-id="a218d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a218d-111">Symbolic Name</span></span>|<span data-ttu-id="a218d-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="a218d-112">X12StSeCountMismatch</span></span>|  
|<span data-ttu-id="a218d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a218d-113">Message Text</span></span>|<span data-ttu-id="a218d-114">El conjunto de transacciones X12 tiene un recuento que no coincide con SE01.</span><span class="sxs-lookup"><span data-stu-id="a218d-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="a218d-115">SE01 era {0}, mientras que debería haber sido {1}.</span><span class="sxs-lookup"><span data-stu-id="a218d-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="a218d-116">Se han realizado las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="a218d-116">It has been corrected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a218d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a218d-117">Explanation</span></span>  
 <span data-ttu-id="a218d-118">Esta advertencia indica que el número que aparece en el finalizador del conjunto de transacciones (campo SE01) no coincidía con el número de segmentos del conjunto de transacciones del intercambio.</span><span class="sxs-lookup"><span data-stu-id="a218d-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="a218d-119">La canalización de envío corrige el recuento del campo SE01 y expone la advertencia.</span><span class="sxs-lookup"><span data-stu-id="a218d-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a218d-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a218d-120">User Action</span></span>  
 <span data-ttu-id="a218d-121">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a218d-121">No action is necessary.</span></span>