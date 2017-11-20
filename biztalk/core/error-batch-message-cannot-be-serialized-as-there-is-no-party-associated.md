---
title: "No se puede serializar el mensaje por lotes porque no hay ninguna entidad asociada con el puerto de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b20d10a2c7b584eccc7d1fb57e5132a4ac0d608
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a><span data-ttu-id="cc601-102">El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío</span><span class="sxs-lookup"><span data-stu-id="cc601-102">Batch message cannot be serialized as there is no party associated with send port</span></span>
## <a name="details"></a><span data-ttu-id="cc601-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cc601-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc601-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cc601-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cc601-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cc601-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cc601-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cc601-106">Event ID</span></span>|-|  
|<span data-ttu-id="cc601-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cc601-107">Event Source</span></span>|<span data-ttu-id="cc601-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc601-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="cc601-109">Componente</span><span class="sxs-lookup"><span data-stu-id="cc601-109">Component</span></span>|<span data-ttu-id="cc601-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="cc601-110">Batching Engine</span></span>|  
|<span data-ttu-id="cc601-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cc601-111">Symbolic Name</span></span>|<span data-ttu-id="cc601-112">BatchMessageSerializationFailureDueToMissingParty</span><span class="sxs-lookup"><span data-stu-id="cc601-112">BatchMessageSerializationFailureDueToMissingParty</span></span>|  
|<span data-ttu-id="cc601-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cc601-113">Message Text</span></span>|<span data-ttu-id="cc601-114">El mensaje de procesamiento por lotes no puede serializarse puesto que no existe ninguna entidad asociada al puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="cc601-114">Batch message can not be serialized as there is no party associated with send port {0}.</span></span> <span data-ttu-id="cc601-115">Asegúrese de que hay una entidad asociada al puerto.</span><span class="sxs-lookup"><span data-stu-id="cc601-115">Make sure that a party is associated with the port</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cc601-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="cc601-116">Explanation</span></span>  
 <span data-ttu-id="cc601-117">Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio conservado porque no pudo determinar la entidad a la que debe enviarse el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cc601-117">This Error/Warning/Information event indicates that the send pipeline could not process a preserved interchange because it could not determine the party that the message should be sent to.</span></span> <span data-ttu-id="cc601-118">No pudo determinar la entidad porque no se configuró la propiedad de contexto de DestinationPartyName.</span><span class="sxs-lookup"><span data-stu-id="cc601-118">It could not determine the party because the DestinationPartyName context property was not set.</span></span> <span data-ttu-id="cc601-119">Como resultado, la canalización de envío no pudo determinar la configuración de sobre.</span><span class="sxs-lookup"><span data-stu-id="cc601-119">As a result, the send pipeline could not determine the envelope settings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc601-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cc601-120">User Action</span></span>  
 <span data-ttu-id="cc601-121">Para resolver este error, pase el mensaje por una canalización de envío de atravesar y, a continuación, determine la propiedad de contexto DestinationPartyName para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cc601-121">To resolve this error, pass the message through a passthrough send pipeline, and then determine the DestinationPartyName context property for the message.</span></span> <span data-ttu-id="cc601-122">Compruebe que existe la entidad.</span><span class="sxs-lookup"><span data-stu-id="cc601-122">Verify that the party exists.</span></span> <span data-ttu-id="cc601-123">Si no existe, créela y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cc601-123">If not, create the party, and then resend the message.</span></span>