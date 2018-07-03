---
title: No se puede serializar el mensaje de lote porque no hay ninguna entidad asociada al puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84915c3544ed6e4222dd7fb035808617b51e5280
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969565"
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a><span data-ttu-id="57a34-102">El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío</span><span class="sxs-lookup"><span data-stu-id="57a34-102">Batch message cannot be serialized as there is no party associated with send port</span></span>
## <a name="details"></a><span data-ttu-id="57a34-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="57a34-103">Details</span></span>  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="57a34-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="57a34-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="57a34-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="57a34-105">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    <span data-ttu-id="57a34-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="57a34-106">Event ID</span></span>     |                                                                     -                                                                      |
|  <span data-ttu-id="57a34-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="57a34-107">Event Source</span></span>   |                           <span data-ttu-id="57a34-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a34-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                           |
|    <span data-ttu-id="57a34-109">Componente</span><span class="sxs-lookup"><span data-stu-id="57a34-109">Component</span></span>    |                                                              <span data-ttu-id="57a34-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="57a34-110">Batching Engine</span></span>                                                               |
|  <span data-ttu-id="57a34-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="57a34-111">Symbolic Name</span></span>  |                                             <span data-ttu-id="57a34-112">BatchMessageSerializationFailureDueToMissingParty</span><span class="sxs-lookup"><span data-stu-id="57a34-112">BatchMessageSerializationFailureDueToMissingParty</span></span>                                              |
|  <span data-ttu-id="57a34-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="57a34-113">Message Text</span></span>   | <span data-ttu-id="57a34-114">El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="57a34-114">Batch message can not be serialized as there is no party associated with send port {0}.</span></span> <span data-ttu-id="57a34-115">Asegúrese de que hay una entidad asociada al puerto.</span><span class="sxs-lookup"><span data-stu-id="57a34-115">Make sure that a party is associated with the port</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="57a34-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="57a34-116">Explanation</span></span>  
 <span data-ttu-id="57a34-117">Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio conservado porque no pudo determinar la entidad a la que debe enviarse el mensaje.</span><span class="sxs-lookup"><span data-stu-id="57a34-117">This Error/Warning/Information event indicates that the send pipeline could not process a preserved interchange because it could not determine the party that the message should be sent to.</span></span> <span data-ttu-id="57a34-118">No pudo determinar la entidad porque no se configuró la propiedad de contexto de DestinationPartyName.</span><span class="sxs-lookup"><span data-stu-id="57a34-118">It could not determine the party because the DestinationPartyName context property was not set.</span></span> <span data-ttu-id="57a34-119">Como resultado, la canalización de envío no pudo determinar la configuración de sobre.</span><span class="sxs-lookup"><span data-stu-id="57a34-119">As a result, the send pipeline could not determine the envelope settings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57a34-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="57a34-120">User Action</span></span>  
 <span data-ttu-id="57a34-121">Para resolver este error, pase el mensaje por una canalización de envío de atravesar y, a continuación, determine la propiedad de contexto DestinationPartyName para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="57a34-121">To resolve this error, pass the message through a passthrough send pipeline, and then determine the DestinationPartyName context property for the message.</span></span> <span data-ttu-id="57a34-122">Compruebe que existe la entidad.</span><span class="sxs-lookup"><span data-stu-id="57a34-122">Verify that the party exists.</span></span> <span data-ttu-id="57a34-123">Si no existe, créela y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="57a34-123">If not, create the party, and then resend the message.</span></span>