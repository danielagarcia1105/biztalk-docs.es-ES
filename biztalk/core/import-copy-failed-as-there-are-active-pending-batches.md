---
title: Error al importar-copiar porque hay lotes activos pendientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74bfdccbd12db00cd0f325aedee2e42cc76729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970541"
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a><span data-ttu-id="ba7fd-102">Error al importar-copiar porque hay lotes activos pendientes</span><span class="sxs-lookup"><span data-stu-id="ba7fd-102">Import-Copy failed as there are active-pending batches</span></span>
## <a name="details"></a><span data-ttu-id="ba7fd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba7fd-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ba7fd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ba7fd-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="ba7fd-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ba7fd-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="ba7fd-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ba7fd-106">Event ID</span></span>     |                                                       -                                                        |
|  <span data-ttu-id="ba7fd-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ba7fd-107">Event Source</span></span>   |             <span data-ttu-id="ba7fd-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba7fd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>             |
|    <span data-ttu-id="ba7fd-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ba7fd-109">Component</span></span>    |                                                   <span data-ttu-id="ba7fd-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ba7fd-110">EDI Engine</span></span>                                                   |
|  <span data-ttu-id="ba7fd-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ba7fd-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="ba7fd-112">Err_ActiveBatchFound</span><span class="sxs-lookup"><span data-stu-id="ba7fd-112">Err_ActiveBatchFound</span></span>                                              |
|  <span data-ttu-id="ba7fd-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ba7fd-113">Message Text</span></span>   | <span data-ttu-id="ba7fd-114">Error al importar o copiar porque hay lotes activos o pendientes.</span><span class="sxs-lookup"><span data-stu-id="ba7fd-114">Import/Copy failed as there are active/pending batches.</span></span> <span data-ttu-id="ba7fd-115">Detenga los lotes activos o pendientes e intente realizar de nuevo la importación o copia.</span><span class="sxs-lookup"><span data-stu-id="ba7fd-115">Stop active/pending batches and try importing/copying.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ba7fd-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ba7fd-116">Explanation</span></span>  
 <span data-ttu-id="ba7fd-117">Este evento de error,  indica que BizTalk Server no pudo importar un archivo de enlace o copiar la configuración, porque los acuerdos afectados tienen uno o varios lotes activos o pendientes.</span><span class="sxs-lookup"><span data-stu-id="ba7fd-117">This Error/Warning/Information event indicates BizTalk Server was unable to Import a binding file or copy the settings as the affected Agreement(s) have one or more active or pending batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba7fd-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ba7fd-118">User Action</span></span>  
 <span data-ttu-id="ba7fd-119">Para resolver este error, asegúrese de que todos los lotes de los acuerdos afectados se muestran como detenidos en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="ba7fd-119">To resolve this error, ensure that all the batches in affected agreements are showing as stopped in the Agreement properties.</span></span>