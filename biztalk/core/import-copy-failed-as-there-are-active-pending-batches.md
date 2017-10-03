---
title: "Error al copiar de la importación ya que hay lotes activos pendientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3055f3e95ef3d0fb8bf5a36dae5957e318f6e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a><span data-ttu-id="b78ba-102">Error al copiar de la importación ya que hay lotes activos pendientes</span><span class="sxs-lookup"><span data-stu-id="b78ba-102">Import-Copy failed as there are active-pending batches</span></span>
## <a name="details"></a><span data-ttu-id="b78ba-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b78ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b78ba-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b78ba-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b78ba-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b78ba-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b78ba-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b78ba-106">Event ID</span></span>|-|  
|<span data-ttu-id="b78ba-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b78ba-107">Event Source</span></span>|<span data-ttu-id="b78ba-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b78ba-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="b78ba-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b78ba-109">Component</span></span>|<span data-ttu-id="b78ba-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="b78ba-110">EDI Engine</span></span>|  
|<span data-ttu-id="b78ba-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b78ba-111">Symbolic Name</span></span>|<span data-ttu-id="b78ba-112">Err_ActiveBatchFound</span><span class="sxs-lookup"><span data-stu-id="b78ba-112">Err_ActiveBatchFound</span></span>|  
|<span data-ttu-id="b78ba-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b78ba-113">Message Text</span></span>|<span data-ttu-id="b78ba-114">Error al importar o copiar porque hay lotes activos o pendientes.</span><span class="sxs-lookup"><span data-stu-id="b78ba-114">Import/Copy failed as there are active/pending batches.</span></span> <span data-ttu-id="b78ba-115">Detenga los lotes activos o pendientes e intente realizar de nuevo la importación o copia.</span><span class="sxs-lookup"><span data-stu-id="b78ba-115">Stop active/pending batches and try importing/copying.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b78ba-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b78ba-116">Explanation</span></span>  
 <span data-ttu-id="b78ba-117">Este evento de error,  indica que BizTalk Server no pudo importar un archivo de enlace o copiar la configuración, porque los acuerdos afectados tienen uno o varios lotes activos o pendientes.</span><span class="sxs-lookup"><span data-stu-id="b78ba-117">This Error/Warning/Information event indicates BizTalk Server was unable to Import a binding file or copy the settings as the affected Agreement(s) have one or more active or pending batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b78ba-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b78ba-118">User Action</span></span>  
 <span data-ttu-id="b78ba-119">Para resolver este error, asegúrese de que todos los lotes de los acuerdos afectados se muestran como detenidos en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="b78ba-119">To resolve this error, ensure that all the batches in affected agreements are showing as stopped in the Agreement properties.</span></span>