---
title: "El acuerdo asociado con el identificador de lote no está habilitado o ha expirado. No se puede continuar el procesamiento por lotes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d92cb07-7646-42b3-90a8-18acbcd145cd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68e91fe1cd2d91c20c84a32afd37212769a4736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-agreement-associated-with-batchid-is-not-enabled-or-has-expired-batching-cannot-continue"></a><span data-ttu-id="e1b93-103">El acuerdo asociado con el identificador de lote no está habilitado o ha expirado.</span><span class="sxs-lookup"><span data-stu-id="e1b93-103">The agreement associated with BatchId is not enabled or has expired.</span></span> <span data-ttu-id="e1b93-104">El procesamiento por lotes no puede continuar</span><span class="sxs-lookup"><span data-stu-id="e1b93-104">Batching cannot continue</span></span>
## <a name="details"></a><span data-ttu-id="e1b93-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1b93-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1b93-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e1b93-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e1b93-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e1b93-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e1b93-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e1b93-108">Event ID</span></span>|-|  
|<span data-ttu-id="e1b93-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e1b93-109">Event Source</span></span>|<span data-ttu-id="e1b93-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1b93-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="e1b93-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e1b93-111">Component</span></span>|<span data-ttu-id="e1b93-112">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e1b93-112">EDI Engine</span></span>|  
|<span data-ttu-id="e1b93-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e1b93-113">Symbolic Name</span></span>|<span data-ttu-id="e1b93-114">ErrorBatchAgreementDisabled</span><span class="sxs-lookup"><span data-stu-id="e1b93-114">ErrorBatchAgreementDisabled</span></span>|  
|<span data-ttu-id="e1b93-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e1b93-115">Message Text</span></span>|<span data-ttu-id="e1b93-116">El acuerdo asociado con el identificador de lote {0} no está habilitado o ha expirado.</span><span class="sxs-lookup"><span data-stu-id="e1b93-116">The agreement associated with BatchId {0} is not enabled or has expired.</span></span> <span data-ttu-id="e1b93-117">El procesamiento por lotes no puede continuar.</span><span class="sxs-lookup"><span data-stu-id="e1b93-117">Batching cannot continue.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e1b93-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="e1b93-118">Explanation</span></span>  
 <span data-ttu-id="e1b93-119">Este evento de error,  indica que BizTalk Server no pudo iniciar un lote o procesar un mensaje por lotes porque el acuerdo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="e1b93-119">This Error/Warning/Information event indicates BizTalk Server was not able to start a batch or process a batch message because of Agreement getting expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1b93-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e1b93-120">User Action</span></span>  
 <span data-ttu-id="e1b93-121">Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y sus fechas de inicio y fin estén dentro de las fechas de inicio y fin del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e1b93-121">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and its start and end date fall within the start and end dates of the Agreement.</span></span> <span data-ttu-id="e1b93-122">Asegúrese también de que el acuerdo esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="e1b93-122">Also make sure that the agreement is enabled.</span></span>