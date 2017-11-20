---
title: "La ubicación del proyecto no está vacía | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-project-location-is-not-empty"></a><span data-ttu-id="72fd7-102">La ubicación del proyecto no está vacía</span><span class="sxs-lookup"><span data-stu-id="72fd7-102">The project location is not empty</span></span>
## <a name="details"></a><span data-ttu-id="72fd7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="72fd7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72fd7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="72fd7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="72fd7-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="72fd7-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="72fd7-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="72fd7-106">Event ID</span></span>|<span data-ttu-id="72fd7-107">0</span><span class="sxs-lookup"><span data-stu-id="72fd7-107">0</span></span>|  
|<span data-ttu-id="72fd7-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="72fd7-108">Event Source</span></span>|<span data-ttu-id="72fd7-109">0</span><span class="sxs-lookup"><span data-stu-id="72fd7-109">0</span></span>|  
|<span data-ttu-id="72fd7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="72fd7-110">Component</span></span>|<span data-ttu-id="72fd7-111">0</span><span class="sxs-lookup"><span data-stu-id="72fd7-111">0</span></span>|  
|<span data-ttu-id="72fd7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="72fd7-112">Symbolic Name</span></span>|<span data-ttu-id="72fd7-113">0</span><span class="sxs-lookup"><span data-stu-id="72fd7-113">0</span></span>|  
|<span data-ttu-id="72fd7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="72fd7-114">Message Text</span></span>|<span data-ttu-id="72fd7-115">La ubicación del proyecto "{0}" no está vacía.</span><span class="sxs-lookup"><span data-stu-id="72fd7-115">The project location "{0}" is not empty.</span></span> <span data-ttu-id="72fd7-116">Debe llevar a cabo una de las siguientes acciones: 1.</span><span class="sxs-lookup"><span data-stu-id="72fd7-116">You need to do one of the following: 1.</span></span> <span data-ttu-id="72fd7-117">Elija una ubicación diferente para el nuevo proyecto, 2.</span><span class="sxs-lookup"><span data-stu-id="72fd7-117">Choose a different location for the new project, 2.</span></span> <span data-ttu-id="72fd7-118">Especificar sobrescribir para volver a usar la ubicación existente, o 3.</span><span class="sxs-lookup"><span data-stu-id="72fd7-118">Specify overwrite to reuse the existing location, or 3.</span></span> <span data-ttu-id="72fd7-119">Elimine manualmente el contenido de la ubicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="72fd7-119">Manually delete the contents of the project location.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72fd7-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="72fd7-120">Explanation</span></span>  
 <span data-ttu-id="72fd7-121">Este error indica que el directorio virtual donde se intenta publicar el servicio no está vacío.</span><span class="sxs-lookup"><span data-stu-id="72fd7-121">This error indicates the virtual directory where the service is trying to be published is not empty.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="72fd7-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="72fd7-122">User Action</span></span>  
 <span data-ttu-id="72fd7-123">Seleccione la ubicación de sobrescritura para volver a usar la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="72fd7-123">Select the overwrite location to reuse the same location.</span></span> <span data-ttu-id="72fd7-124">O bien especifique una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="72fd7-124">Or specify a new location.</span></span>  <span data-ttu-id="72fd7-125">En el Asistente de publicación de servicio de WCF, seleccione **sobrescribir la ubicación existente** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="72fd7-125">In the WCF Service Publishing Wizard, select **Overwrite Existing Location** and click **Next**.</span></span> <span data-ttu-id="72fd7-126">Este paso sobrescribe la ubicación.</span><span class="sxs-lookup"><span data-stu-id="72fd7-126">This step overwrites the location.</span></span>