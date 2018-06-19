---
title: No se puede enrutar el mensaje a la orquestación por lotes no se pudo determinar el tipo de codificación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe5054f53f779274c9b25f2751fdcb9d85545560
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241948"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a><span data-ttu-id="81ffa-102">El mensaje no puede enrutarse a la orquestación de procesamiento por lotes. No se pudo determinar el tipo de codificación</span><span class="sxs-lookup"><span data-stu-id="81ffa-102">The message cannot be routed to the batching orchestration as the Encoding type could not be determined</span></span>
## <a name="details"></a><span data-ttu-id="81ffa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="81ffa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81ffa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="81ffa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="81ffa-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="81ffa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="81ffa-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="81ffa-106">Event ID</span></span>|-|  
|<span data-ttu-id="81ffa-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="81ffa-107">Event Source</span></span>|<span data-ttu-id="81ffa-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ffa-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="81ffa-109">Componente</span><span class="sxs-lookup"><span data-stu-id="81ffa-109">Component</span></span>|<span data-ttu-id="81ffa-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="81ffa-110">Batching Engine</span></span>|  
|<span data-ttu-id="81ffa-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="81ffa-111">Symbolic Name</span></span>|<span data-ttu-id="81ffa-112">UnknownEncodingType</span><span class="sxs-lookup"><span data-stu-id="81ffa-112">UnknownEncodingType</span></span>|  
|<span data-ttu-id="81ffa-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="81ffa-113">Message Text</span></span>|<span data-ttu-id="81ffa-114">El mensaje no puede enrutarse a la orquestación de procesamiento por lotes. No se pudo determinar el tipo de codificación.</span><span class="sxs-lookup"><span data-stu-id="81ffa-114">The message cannot be routed to the batching orchestration as the Encoding type could not be determined.</span></span> <span data-ttu-id="81ffa-115">El tipo de codificación debe ser X12 o EDIFACT para que el mensaje pueda procesarse por lotes.</span><span class="sxs-lookup"><span data-stu-id="81ffa-115">The encoding type needs to be either X12 or EDIFACT for the message to be batched.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81ffa-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="81ffa-116">Explanation</span></span>  
 <span data-ttu-id="81ffa-117">Este evento de error,  indica que un elemento de lote no EDI no se enrutó a la instancia de la orquestación por lotes, incluso aunque el conjunto de transacciones cumpla los criterios de filtro para su procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="81ffa-117">This Error/Warning/Information event indicates that a non-EDI batch element was not routed to the batching orchestration instance, even though the transaction set meets the filter criteria for batching.</span></span> <span data-ttu-id="81ffa-118">El conjunto de transacciones no se pudo enrutar a la instancia de la orquestación por lotes porque la propiedad de contexto EDI.EncodingType no se promocionó con el valor 0 para X12 o 1 para EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="81ffa-118">The transaction set could not be routed to the batching orchestration instance because the EDI.EncodingType context property was not promoted with a value of 0 for X12 or 1 for EDIFACT.</span></span> <span data-ttu-id="81ffa-119">Este error tuvo lugar cuando el componente de canalización BatchMarker enrutó el elemento de lote a la orquestación de enrutamiento, pero una asignación no convirtió el elemento de lote no EDI en un mensaje EDI.</span><span class="sxs-lookup"><span data-stu-id="81ffa-119">This error occurred when the batch element was routed by the BatchMarker pipeline component to the routing orchestration, but the non-EDI batch element was not converted by a map into an EDI message.</span></span> <span data-ttu-id="81ffa-120">Como resultado, la orquestación de enrutamiento no pudo determinar el tipo de codificación a partir de los encabezados EDI.</span><span class="sxs-lookup"><span data-stu-id="81ffa-120">As a result, the routing orchestration could not determine the encoding type from the EDI headers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81ffa-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="81ffa-121">User Action</span></span>  
 <span data-ttu-id="81ffa-122">Para resolver este error, asegúrese de que una asignación convierta el mensaje no EDI en un mensaje EDI antes de que se enrute a la orquestación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="81ffa-122">To resolve this error, make sure that the non-EDI message is converted by a map into an EDI message before it is routed to the routing orchestration.</span></span> <span data-ttu-id="81ffa-123">También debe incluir un componente de canalización personalizado (con el componente BathMarker) o una orquestación personalizada para procesar el elemento de lote no EDI.</span><span class="sxs-lookup"><span data-stu-id="81ffa-123">You must also include a custom pipeline component (with the BatchMarker component) or custom orchestration to process the non-EDI batch element.</span></span> <span data-ttu-id="81ffa-124">Para obtener más información, consulte "Ensamblar un intercambio EDI por lotes" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81ffa-124">For more information, see "Assembling a Batched EDI Interchange" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>