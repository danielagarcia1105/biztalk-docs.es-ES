---
title: Error al cargar el ensamblado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13be3acf6974565c86cc87b14ed58929553d5220
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-loading-assembly"></a><span data-ttu-id="b091e-102">Error al cargar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="b091e-102">Error loading assembly</span></span>
## <a name="details"></a><span data-ttu-id="b091e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b091e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b091e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b091e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b091e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b091e-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b091e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b091e-106">Event ID</span></span>|<span data-ttu-id="b091e-107">0</span><span class="sxs-lookup"><span data-stu-id="b091e-107">0</span></span>|  
|<span data-ttu-id="b091e-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b091e-108">Event Source</span></span>|<span data-ttu-id="b091e-109">0</span><span class="sxs-lookup"><span data-stu-id="b091e-109">0</span></span>|  
|<span data-ttu-id="b091e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b091e-110">Component</span></span>|<span data-ttu-id="b091e-111">0</span><span class="sxs-lookup"><span data-stu-id="b091e-111">0</span></span>|  
|<span data-ttu-id="b091e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b091e-112">Symbolic Name</span></span>|<span data-ttu-id="b091e-113">0</span><span class="sxs-lookup"><span data-stu-id="b091e-113">0</span></span>|  
|<span data-ttu-id="b091e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b091e-114">Message Text</span></span>|<span data-ttu-id="b091e-115">Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b091e-115">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="b091e-116">Compruebe la directiva de seguridad de acceso a código de la zona.</span><span class="sxs-lookup"><span data-stu-id="b091e-116">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="b091e-117">O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk.</span><span class="sxs-lookup"><span data-stu-id="b091e-117">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="b091e-118">Compruebe el ensamblado para el [ensamblado: ensamblado de BizTalk] atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b091e-118">Check the assembly for the [assembly: BizTalkAssembly] custom attribute.</span></span> <span data-ttu-id="b091e-119">O bien, es posible que el archivo no sea un ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="b091e-119">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="b091e-120">Si se trata de un archivo .dll o .exe, puede haber código no controlado.</span><span class="sxs-lookup"><span data-stu-id="b091e-120">If the file is a .dll or  exe, it may be unmanaged code</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b091e-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="b091e-121">Explanation</span></span>  
 <span data-ttu-id="b091e-122">Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b091e-122">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="b091e-123">Compruebe la directiva de seguridad de acceso a código de la zona.</span><span class="sxs-lookup"><span data-stu-id="b091e-123">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="b091e-124">O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk.</span><span class="sxs-lookup"><span data-stu-id="b091e-124">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="b091e-125">Compruebe el ensamblado para el [*ensamblado: ensamblado de BizTalk*] atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b091e-125">Check the assembly for the [*assembly: BizTalkAssembly*] custom attribute.</span></span> <span data-ttu-id="b091e-126">O bien, es posible que el archivo no sea un ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="b091e-126">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="b091e-127">Si el archivo es una DLL o exe, puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b091e-127">If the file is a .dll or  exe, it may be unmanaged code.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b091e-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b091e-128">User Action</span></span>  
 <span data-ttu-id="b091e-129">Conceda el nivel de total confianza a la ubicación si es de un origen confiable.</span><span class="sxs-lookup"><span data-stu-id="b091e-129">Grant Full trust level to the location if it’s from a reliable source.</span></span>  <span data-ttu-id="b091e-130">Asegúrese de que el dll es un ensamblado .net de BizTalk válido.</span><span class="sxs-lookup"><span data-stu-id="b091e-130">Ensure the dll is a valid BizTalk .net assembly.</span></span>