---
title: El conjunto de transacciones de Edifact tiene un recuento no coincidente UNT01 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717260f8e45298c19756707ed042b97ab6e207fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016051"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="e8451-102">El recuento de UNT01 del conjunto de transacciones Edifact no coincide</span><span class="sxs-lookup"><span data-stu-id="e8451-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="e8451-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8451-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e8451-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e8451-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="e8451-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e8451-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="e8451-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e8451-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="e8451-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e8451-107">Event Source</span></span>   |                       <span data-ttu-id="e8451-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8451-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                        |
|    <span data-ttu-id="e8451-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e8451-109">Component</span></span>    |                                                             <span data-ttu-id="e8451-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e8451-110">EDI Engine</span></span>                                                              |
|  <span data-ttu-id="e8451-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e8451-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="e8451-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="e8451-112">EfactUnhUntCountMismatch</span></span>                                                       |
|  <span data-ttu-id="e8451-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8451-113">Message Text</span></span>   | <span data-ttu-id="e8451-114">El recuento de UNT01 del conjunto de transacciones Edifact no coincide.</span><span class="sxs-lookup"><span data-stu-id="e8451-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="e8451-115">UNT01 era {0}, mientras que debería haber sido {1}.</span><span class="sxs-lookup"><span data-stu-id="e8451-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="e8451-116">Se han realizado las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="e8451-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e8451-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e8451-117">Explanation</span></span>  
 <span data-ttu-id="e8451-118">Esta advertencia indica que el campo UNT01, que es el recuento de segmentos, no coincidía con el número de segmentos del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e8451-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="e8451-119">O bien el valor de UNT01 ha cambiado o está dañado o se han agregado o eliminado segmentos una vez determinado el recuento.</span><span class="sxs-lookup"><span data-stu-id="e8451-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="e8451-120">La canalización de envío restableció el campo UNT01 al número de segmentos correcto y, a continuación, envió el intercambio.</span><span class="sxs-lookup"><span data-stu-id="e8451-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8451-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e8451-121">User Action</span></span>  
 <span data-ttu-id="e8451-122">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e8451-122">No user action is necessary.</span></span>