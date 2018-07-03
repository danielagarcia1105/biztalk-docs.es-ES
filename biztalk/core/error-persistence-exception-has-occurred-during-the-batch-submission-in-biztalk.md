---
title: Se ha producido una excepción de persistencia durante el envío del lote en la orquestación por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8a1277dd26fcb2036e3378f7fa6d22067a1f7e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020922"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="755e7-102">Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="755e7-102">A persistence exception has occurred during the batch submission in the batching Orchestration</span></span>
## <a name="details"></a><span data-ttu-id="755e7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="755e7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="755e7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="755e7-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="755e7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="755e7-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="755e7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="755e7-106">Event ID</span></span>     |                                                                                             -                                                                                              |
|  <span data-ttu-id="755e7-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="755e7-107">Event Source</span></span>   |                                                   <span data-ttu-id="755e7-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="755e7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                   |
|    <span data-ttu-id="755e7-109">Componente</span><span class="sxs-lookup"><span data-stu-id="755e7-109">Component</span></span>    |                                                                                      <span data-ttu-id="755e7-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="755e7-110">Batching Engine</span></span>                                                                                       |
|  <span data-ttu-id="755e7-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="755e7-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="755e7-112">PersistenceExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="755e7-112">PersistenceExceptionOccured</span></span>                                                                                 |
|  <span data-ttu-id="755e7-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="755e7-113">Message Text</span></span>   | <span data-ttu-id="755e7-114">Se produjo una excepción de persistencia durante el envío del lote en la orquestación de procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="755e7-114">A persistence exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="755e7-115">Identificador de lote = {0}; Mensaje de error = {1}.</span><span class="sxs-lookup"><span data-stu-id="755e7-115">Batch Id = {0}, ErrorMessage = {1}.</span></span> <span data-ttu-id="755e7-116">Compruebe las suscripciones de puerto de envío y corríjalas.</span><span class="sxs-lookup"><span data-stu-id="755e7-116">Please check your send port subscriptions and fix them.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="755e7-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="755e7-117">Explanation</span></span>  
 <span data-ttu-id="755e7-118">Este evento de error,  indica que BizTalk Server no pudo enviar un intercambio por lotes por no estar ningún puerto de envío suscrito al intercambio.</span><span class="sxs-lookup"><span data-stu-id="755e7-118">This Error/Warning/Information event indicates that BizTalk Server could not send a batched interchange because no send port subscribed to the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="755e7-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="755e7-119">User Action</span></span>  
 <span data-ttu-id="755e7-120">Para resolver este error, asegúrese de que un puerto de envío se suscribe al lote estableciendo las siguientes propiedades de filtro para el puerto de envío: EDI. DestinationPartyName = \<PartyName\>, EDI. BatchEncodingType = EDIFACT o X12 y EDI. ToBeBatched = False.</span><span class="sxs-lookup"><span data-stu-id="755e7-120">To resolve this error, ensure that a send port subscribes to the batch by setting the following filter properties for the send port: EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>