---
title: No en transacción definida por el conjunto de segmento | Documentos de Microsoft
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
ms.openlocfilehash: a2f0b330110ef08196681e54e543173c3f2bd0f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269524"
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="5465c-102">Segmento no definido en el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="5465c-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="5465c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5465c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5465c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5465c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5465c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5465c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5465c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5465c-106">Event ID</span></span>|-|  
|<span data-ttu-id="5465c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5465c-107">Event Source</span></span>|<span data-ttu-id="5465c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5465c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="5465c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5465c-109">Component</span></span>|<span data-ttu-id="5465c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="5465c-110">EDI Engine</span></span>|  
|<span data-ttu-id="5465c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5465c-111">Symbolic Name</span></span>|<span data-ttu-id="5465c-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="5465c-112">X12SegmentNotInDefinedTSDescription</span></span>|  
|<span data-ttu-id="5465c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5465c-113">Message Text</span></span>|<span data-ttu-id="5465c-114">Segmento no definido en el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="5465c-114">Segment Not In Defined Transaction set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5465c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="5465c-115">Explanation</span></span>  
 <span data-ttu-id="5465c-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque un conjunto de transacciones de dicho intercambio no contiene un segmento que requiere el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="5465c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5465c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5465c-117">User Action</span></span>  
 <span data-ttu-id="5465c-118">Para resolver este error, pida al remitente del intercambio que agregue el segmento requerido al conjunto de transacciones del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="5465c-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>