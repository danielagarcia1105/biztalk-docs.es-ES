---
title: Número de conjuntos de transacciones incluidos no coincide. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d2f51abc20f9cb790d2e6df62443f428c03dc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970109"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a><span data-ttu-id="2548d-102">El número de conjuntos de transacciones incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="2548d-102">Number of included transaction sets do not match</span></span>
## <a name="details"></a><span data-ttu-id="2548d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2548d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2548d-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2548d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2548d-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2548d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2548d-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2548d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2548d-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2548d-107">Event Source</span></span>   | <span data-ttu-id="2548d-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2548d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="2548d-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2548d-109">Component</span></span>    |                                       <span data-ttu-id="2548d-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2548d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="2548d-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2548d-111">Symbolic Name</span></span>  |                           <span data-ttu-id="2548d-112">X12FaNumberOfTsMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="2548d-112">X12FaNumberOfTsMismatchDescription</span></span>                           |
|  <span data-ttu-id="2548d-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2548d-113">Message Text</span></span>   |                    <span data-ttu-id="2548d-114">El número de conjuntos de transacciones incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="2548d-114">Number of included transaction sets do not match</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="2548d-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2548d-115">Explanation</span></span>  
 <span data-ttu-id="2548d-116">Este evento de error, advertencia o información indica que el número de conjuntos de transacciones del grupo del intercambio X12 no es igual al número del finalizador de grupo (campo GE01).</span><span class="sxs-lookup"><span data-stu-id="2548d-116">This Error/Warning/Information event indicates that the number of transaction sets in the group of the X12 interchange does not equal the number in the group trailer (GE01 field).</span></span> <span data-ttu-id="2548d-117">Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.</span><span class="sxs-lookup"><span data-stu-id="2548d-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="2548d-118">(El mensaje de error no se envía si el intercambio se conserva y los conjuntos de transacciones se suspenden al producirse un error o bien si el intercambio se divide.)</span><span class="sxs-lookup"><span data-stu-id="2548d-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2548d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2548d-119">User Action</span></span>  
 <span data-ttu-id="2548d-120">Para resolver este error, asegúrese de que el número que aparece en el campo GE01 del finalizador de grupo es el mismo que el número de conjuntos de transacciones del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="2548d-120">To resolve this error, make sure that the number in the GE01 field of the group trailer is the same as the number of transaction sets in the group of the interchange, and then resend the interchange.</span></span>