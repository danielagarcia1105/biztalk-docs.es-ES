---
title: No se encontró el lote | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c3e65a806f02faeb81baa6a5263019079b0c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279484"
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="6e0ef-102">No se encontró el lote</span><span class="sxs-lookup"><span data-stu-id="6e0ef-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="6e0ef-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e0ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e0ef-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6e0ef-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6e0ef-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6e0ef-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6e0ef-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6e0ef-106">Event ID</span></span>|-|  
|<span data-ttu-id="6e0ef-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6e0ef-107">Event Source</span></span>|<span data-ttu-id="6e0ef-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e0ef-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="6e0ef-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6e0ef-109">Component</span></span>|<span data-ttu-id="6e0ef-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="6e0ef-110">EDI Engine</span></span>|  
|<span data-ttu-id="6e0ef-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6e0ef-111">Symbolic Name</span></span>|<span data-ttu-id="6e0ef-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="6e0ef-112">Err_BatchNotFound</span></span>|  
|<span data-ttu-id="6e0ef-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6e0ef-113">Message Text</span></span>|<span data-ttu-id="6e0ef-114">No se encontró el lote.</span><span class="sxs-lookup"><span data-stu-id="6e0ef-114">The batch was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6e0ef-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="6e0ef-115">Explanation</span></span>  
 <span data-ttu-id="6e0ef-116">Este evento de error, indica que BizTalk Server no encontró un lote durante el inicio o detención de un lote mientras la orquestación por lotes intentaba procesar un mensaje por lotes.</span><span class="sxs-lookup"><span data-stu-id="6e0ef-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e0ef-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6e0ef-117">User Action</span></span>  
 <span data-ttu-id="6e0ef-118">Para resolver este error, asegúrese de el lote correspondiente esté presente en las propiedades del acuerdo contenedor.</span><span class="sxs-lookup"><span data-stu-id="6e0ef-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>