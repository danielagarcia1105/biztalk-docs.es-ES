---
title: No se pudo encontrar las identidades de negocio correspondientes al lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f1027186e5b001d21e08bbabcfc100400a02d5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237836"
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="44b0f-102">No encuentran las identidades de negocio correspondientes al lote</span><span class="sxs-lookup"><span data-stu-id="44b0f-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="44b0f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="44b0f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44b0f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="44b0f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="44b0f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="44b0f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="44b0f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="44b0f-106">Event ID</span></span>|-|  
|<span data-ttu-id="44b0f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="44b0f-107">Event Source</span></span>|<span data-ttu-id="44b0f-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44b0f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="44b0f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="44b0f-109">Component</span></span>|<span data-ttu-id="44b0f-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="44b0f-110">EDI Engine</span></span>|  
|<span data-ttu-id="44b0f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="44b0f-111">Symbolic Name</span></span>|<span data-ttu-id="44b0f-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="44b0f-112">IdentitiesNotFoundForBatch</span></span>|  
|<span data-ttu-id="44b0f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="44b0f-113">Message Text</span></span>|<span data-ttu-id="44b0f-114">No encuentran las identidades de negocio correspondientes al lote {0}.</span><span class="sxs-lookup"><span data-stu-id="44b0f-114">Could not find Business Identities corresponding to batch {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44b0f-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="44b0f-115">Explanation</span></span>  
 <span data-ttu-id="44b0f-116">Este evento de error,  indica que el servidor BizTalk no pudo procesar un mensaje por lotes por no tener datos suficientes.</span><span class="sxs-lookup"><span data-stu-id="44b0f-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44b0f-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="44b0f-117">User Action</span></span>  
 <span data-ttu-id="44b0f-118">Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y que estén especificadas las identidades empresariales adecuadas para el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="44b0f-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>