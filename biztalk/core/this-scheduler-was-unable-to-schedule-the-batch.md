---
title: Este programador no pudo programar el lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4146124c-1eb0-4c1e-843b-b19c687a56b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7be725a96f00c3d27db71db7748aff512ad960
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974365"
---
# <a name="this-scheduler-was-unable-to-schedule-the-batch"></a><span data-ttu-id="9b132-102">Este programador no pudo programar el lote</span><span class="sxs-lookup"><span data-stu-id="9b132-102">This scheduler was unable to schedule the batch</span></span>
## <a name="details"></a><span data-ttu-id="9b132-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9b132-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9b132-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9b132-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9b132-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9b132-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9b132-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9b132-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9b132-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9b132-107">Event Source</span></span>   | <span data-ttu-id="9b132-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b132-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="9b132-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9b132-109">Component</span></span>    |                                    <span data-ttu-id="9b132-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="9b132-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="9b132-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9b132-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="9b132-112">UnableToScheduleBatch</span><span class="sxs-lookup"><span data-stu-id="9b132-112">UnableToScheduleBatch</span></span>                                  |
|  <span data-ttu-id="9b132-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9b132-113">Message Text</span></span>   |                    <span data-ttu-id="9b132-114">Este programador no pudo programar el lote</span><span class="sxs-lookup"><span data-stu-id="9b132-114">This scheduler was unable to schedule the batch</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="9b132-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="9b132-115">Explanation</span></span>  
 <span data-ttu-id="9b132-116">Este error indica que el programador no pudo determinar la siguiente repetición de una liberación por lotes.</span><span class="sxs-lookup"><span data-stu-id="9b132-116">This error indicates the scheduler could not determine the next occurrence of a batch release.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b132-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9b132-117">User Action</span></span>  
 <span data-ttu-id="9b132-118">Para resolver este error, asegúrese de que el programa de liberación por lotes es válido.</span><span class="sxs-lookup"><span data-stu-id="9b132-118">To resolve this error, make sure the batch release schedule is valid.</span></span>