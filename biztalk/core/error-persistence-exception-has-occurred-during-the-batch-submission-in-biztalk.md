---
title: "Se produjo una excepción de persistencia durante el envío del lote en la orquestación por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eae4f48209dc4f5afefbc69c40706a31f2b00b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="07aed-102">Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="07aed-102">A persistence exception has occurred during the batch submission in the batching Orchestration</span></span>
## <a name="details"></a><span data-ttu-id="07aed-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="07aed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07aed-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="07aed-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="07aed-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="07aed-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="07aed-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="07aed-106">Event ID</span></span>|-|  
|<span data-ttu-id="07aed-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="07aed-107">Event Source</span></span>|<span data-ttu-id="07aed-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07aed-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="07aed-109">Componente</span><span class="sxs-lookup"><span data-stu-id="07aed-109">Component</span></span>|<span data-ttu-id="07aed-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="07aed-110">Batching Engine</span></span>|  
|<span data-ttu-id="07aed-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="07aed-111">Symbolic Name</span></span>|<span data-ttu-id="07aed-112">PersistenceExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="07aed-112">PersistenceExceptionOccured</span></span>|  
|<span data-ttu-id="07aed-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="07aed-113">Message Text</span></span>|<span data-ttu-id="07aed-114">Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="07aed-114">A persistence exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="07aed-115">Identificador de lote = {0}, ErrorMessage = {1}.</span><span class="sxs-lookup"><span data-stu-id="07aed-115">Batch Id = {0}, ErrorMessage = {1}.</span></span> <span data-ttu-id="07aed-116">Compruebe las suscripciones de puerto de envío y corríjalas.</span><span class="sxs-lookup"><span data-stu-id="07aed-116">Please check your send port subscriptions and fix them.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07aed-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="07aed-117">Explanation</span></span>  
 <span data-ttu-id="07aed-118">Este evento de error,  indica que BizTalk Server no pudo enviar un intercambio por lotes por no estar ningún puerto de envío suscrito al intercambio.</span><span class="sxs-lookup"><span data-stu-id="07aed-118">This Error/Warning/Information event indicates that BizTalk Server could not send a batched interchange because no send port subscribed to the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07aed-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="07aed-119">User Action</span></span>  
 <span data-ttu-id="07aed-120">Para resolver este error, asegúrese de que un puerto de envío se suscribe al lote estableciendo las siguientes propiedades de filtro para el puerto de envío: EDI. DestinationPartyName = \<PartyName >, EDI. BatchEncodingType = EDIFACT o X12 y EDI. ToBeBatched = False.</span><span class="sxs-lookup"><span data-stu-id="07aed-120">To resolve this error, ensure that a send port subscribes to the batch by setting the following filter properties for the send port: EDI.DestinationPartyName = \<PartyName>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>