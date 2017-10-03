---
title: "No se pudo encontrar ningún acuerdo correspondiente al lote | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce17af0e382a137dc8d55d30705da58dd52301c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a><span data-ttu-id="76218-102">No se encuentra ningún acuerdo correspondiente al lote</span><span class="sxs-lookup"><span data-stu-id="76218-102">Could not find an Agreement corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="76218-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="76218-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76218-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="76218-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="76218-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="76218-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="76218-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="76218-106">Event ID</span></span>|-|  
|<span data-ttu-id="76218-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="76218-107">Event Source</span></span>|<span data-ttu-id="76218-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76218-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="76218-109">Componente</span><span class="sxs-lookup"><span data-stu-id="76218-109">Component</span></span>|<span data-ttu-id="76218-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="76218-110">EDI Engine</span></span>|  
|<span data-ttu-id="76218-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="76218-111">Symbolic Name</span></span>|<span data-ttu-id="76218-112">AgreementNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="76218-112">AgreementNotFoundForBatch</span></span>|  
|<span data-ttu-id="76218-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="76218-113">Message Text</span></span>|<span data-ttu-id="76218-114">No se encuentra ningún acuerdo correspondiente al lote {0}.</span><span class="sxs-lookup"><span data-stu-id="76218-114">Could not find an Agreement corresponding to batch {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76218-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="76218-115">Explanation</span></span>  
 <span data-ttu-id="76218-116">Este evento de error indica que BizTalk Server no pudo encontrar un lote correspondiente a este identificador al tratar de iniciar o detener un lote o procesar un mensaje por lotes.</span><span class="sxs-lookup"><span data-stu-id="76218-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a Batch corresponding to this Id while trying to start/stop a batch or process a batch message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76218-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="76218-117">User Action</span></span>  
 <span data-ttu-id="76218-118">Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor.</span><span class="sxs-lookup"><span data-stu-id="76218-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement.</span></span>