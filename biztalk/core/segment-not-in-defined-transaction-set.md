---
title: No en transacción definida por el conjunto de segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914e333f-96e4-4094-880d-51a5f25915c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3db84f1ae6fda183799b0344d95da7b395aaee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991701"
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="822fd-102">Segmento no definido en el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="822fd-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="822fd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="822fd-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="822fd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="822fd-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="822fd-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="822fd-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="822fd-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="822fd-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="822fd-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="822fd-107">Event Source</span></span>   | <span data-ttu-id="822fd-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="822fd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="822fd-109">Componente</span><span class="sxs-lookup"><span data-stu-id="822fd-109">Component</span></span>    |                                       <span data-ttu-id="822fd-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="822fd-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="822fd-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="822fd-111">Symbolic Name</span></span>  |                          <span data-ttu-id="822fd-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="822fd-112">X12SegmentNotInDefinedTSDescription</span></span>                           |
|  <span data-ttu-id="822fd-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="822fd-113">Message Text</span></span>   |                         <span data-ttu-id="822fd-114">Segmento no definido en el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="822fd-114">Segment Not In Defined Transaction set</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="822fd-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="822fd-115">Explanation</span></span>  
 <span data-ttu-id="822fd-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque un conjunto de transacciones de dicho intercambio no contiene un segmento que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="822fd-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="822fd-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="822fd-117">User Action</span></span>  
 <span data-ttu-id="822fd-118">Para resolver este error, pida al remitente del intercambio que agregue el segmento requerido al conjunto de transacciones del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="822fd-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>