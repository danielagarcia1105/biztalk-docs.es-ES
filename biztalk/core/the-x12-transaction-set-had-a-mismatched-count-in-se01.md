---
title: El X12 conjunto de transacciones tiene un recuento que no coincide con SE01 | Microsoft Docs
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
ms.openlocfilehash: 947a557a81c6857b5d31f447acb2ec5a46cfcef9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993357"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="93c67-102">El conjunto de transacciones X12 tiene un recuento que no coincide con SE01</span><span class="sxs-lookup"><span data-stu-id="93c67-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="93c67-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="93c67-103">Details</span></span>  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="93c67-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="93c67-104">Product Name</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| <span data-ttu-id="93c67-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="93c67-105">Product Version</span></span> |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    <span data-ttu-id="93c67-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="93c67-106">Event ID</span></span>     |                                                               -                                                               |
|  <span data-ttu-id="93c67-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="93c67-107">Event Source</span></span>   |                    <span data-ttu-id="93c67-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c67-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                     |
|    <span data-ttu-id="93c67-109">Componente</span><span class="sxs-lookup"><span data-stu-id="93c67-109">Component</span></span>    |                                                          <span data-ttu-id="93c67-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="93c67-110">EDI Engine</span></span>                                                           |
|  <span data-ttu-id="93c67-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="93c67-111">Symbolic Name</span></span>  |                                                     <span data-ttu-id="93c67-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="93c67-112">X12StSeCountMismatch</span></span>                                                      |
|  <span data-ttu-id="93c67-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="93c67-113">Message Text</span></span>   | <span data-ttu-id="93c67-114">El conjunto de transacciones X12 tiene un recuento que no coincide con SE01.</span><span class="sxs-lookup"><span data-stu-id="93c67-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="93c67-115">SE01 era {0}, mientras que debería haber sido {1}.</span><span class="sxs-lookup"><span data-stu-id="93c67-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="93c67-116">Se han realizado las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="93c67-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="93c67-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="93c67-117">Explanation</span></span>  
 <span data-ttu-id="93c67-118">Esta advertencia indica que el número que aparece en el finalizador del conjunto de transacciones (campo SE01) no coincidía con el número de segmentos del conjunto de transacciones del intercambio.</span><span class="sxs-lookup"><span data-stu-id="93c67-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="93c67-119">La canalización de envío corrige el recuento del campo SE01 y expone la advertencia.</span><span class="sxs-lookup"><span data-stu-id="93c67-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93c67-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="93c67-120">User Action</span></span>  
 <span data-ttu-id="93c67-121">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="93c67-121">No action is necessary.</span></span>