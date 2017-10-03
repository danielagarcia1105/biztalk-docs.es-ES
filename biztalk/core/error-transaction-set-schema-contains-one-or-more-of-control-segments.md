---
title: Esquema del conjunto de transacciones contiene uno o varios de control segmentos ISA, IEA, GS, GE | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7589d8f0-c727-47df-afbc-77b0f190f3e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff90a7ea80208f0a69ee8aca5c7593c7b6253c53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-schema-contains-one-or-more-of-control-segments-isa-iea-gs-ge"></a><span data-ttu-id="e1da1-102">El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.</span><span class="sxs-lookup"><span data-stu-id="e1da1-102">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>
## <a name="details"></a><span data-ttu-id="e1da1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1da1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1da1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e1da1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e1da1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e1da1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e1da1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e1da1-106">Event ID</span></span>|-|  
|<span data-ttu-id="e1da1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e1da1-107">Event Source</span></span>|<span data-ttu-id="e1da1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1da1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="e1da1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e1da1-109">Component</span></span>|<span data-ttu-id="e1da1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e1da1-110">EDI Engine</span></span>|  
|<span data-ttu-id="e1da1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e1da1-111">Symbolic Name</span></span>|<span data-ttu-id="e1da1-112">SchemaCode114EOtherControlSegmentsPresent</span><span class="sxs-lookup"><span data-stu-id="e1da1-112">SchemaCode114EOtherControlSegmentsPresent</span></span>|  
|<span data-ttu-id="e1da1-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e1da1-113">Message Text</span></span>|<span data-ttu-id="e1da1-114">El esquema de conjunto de transacciones contiene uno o más segmentos de control ISA, IEA, GS, GE.</span><span class="sxs-lookup"><span data-stu-id="e1da1-114">Transaction set schema contains one or more of control segments ISA, IEA, GS, GE</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e1da1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e1da1-115">Explanation</span></span>  
 <span data-ttu-id="e1da1-116">Este evento de error, advertencia, información indica que la canalización de recepción no pudo procesar el conjunto de transacciones entrantes o que la canalización de envío no pudo procesar el conjunto de transacciones salientes porque el esquema del documento para el conjunto de transacciones definió al menos un segmento ISA, IEA, GS o GE.</span><span class="sxs-lookup"><span data-stu-id="e1da1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the document schema for the transaction set defined at least one ISA, IEA, GS, or GE segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1da1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e1da1-117">User Action</span></span>  
 <span data-ttu-id="e1da1-118">Para resolver este error, anule la implementación del esquema del documento, quite el segmento ISA, IEA, GS o GE del esquema y vuelva a implementar el esquema.</span><span class="sxs-lookup"><span data-stu-id="e1da1-118">To resolve this error, undeploy the document schema, remove the ISA, IEA, GS, or GE segment from the schema, and then redeploy the schema.</span></span>