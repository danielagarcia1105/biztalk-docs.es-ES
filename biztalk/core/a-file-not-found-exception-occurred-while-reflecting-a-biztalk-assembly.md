---
title: "Un archivo de excepción no encontrado al reflejar el ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00000896eb4cb97e44ed51602675fc65495552be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="3447c-102">Excepción de archivo no encontrado al reflejar el ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="3447c-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="3447c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3447c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3447c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3447c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3447c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3447c-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="3447c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3447c-106">Event ID</span></span>|<span data-ttu-id="3447c-107">0</span><span class="sxs-lookup"><span data-stu-id="3447c-107">0</span></span>|  
|<span data-ttu-id="3447c-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3447c-108">Event Source</span></span>|<span data-ttu-id="3447c-109">0</span><span class="sxs-lookup"><span data-stu-id="3447c-109">0</span></span>|  
|<span data-ttu-id="3447c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3447c-110">Component</span></span>|<span data-ttu-id="3447c-111">0</span><span class="sxs-lookup"><span data-stu-id="3447c-111">0</span></span>|  
|<span data-ttu-id="3447c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3447c-112">Symbolic Name</span></span>|<span data-ttu-id="3447c-113">0</span><span class="sxs-lookup"><span data-stu-id="3447c-113">0</span></span>|  
|<span data-ttu-id="3447c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3447c-114">Message Text</span></span>|<span data-ttu-id="3447c-115">Excepción de archivo no encontrado al reflejar el ensamblado de BizTalk "{0}".</span><span class="sxs-lookup"><span data-stu-id="3447c-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="3447c-116">El problema surge si una o más dependencias no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3447c-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="3447c-117">Para corregir este problema, pruebe una de las siguientes acciones: 1.</span><span class="sxs-lookup"><span data-stu-id="3447c-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="3447c-118">Copie las dependencias del ensamblado en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="3447c-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="3447c-119">2.</span><span class="sxs-lookup"><span data-stu-id="3447c-119">2.</span></span> <span data-ttu-id="3447c-120">Instale las dependencias que faltan en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3447c-120">Install the missing dependencies into the Global Assembly Cache.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3447c-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="3447c-121">Explanation</span></span>  
 <span data-ttu-id="3447c-122">Este error indica que el ensamblado de BizTalk que se publica hace referencia a otro ensamblado que no está en la memoria caché global de ensamblados (GAC) o en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="3447c-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3447c-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3447c-123">User Action</span></span>  
 <span data-ttu-id="3447c-124">Además de las acciones especificadas en el mensaje de error, mueva el ensamblado de referencia a la memora caché global de ensamblados o cópielo en la misma ubicación que el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3447c-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="3447c-125">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Visual Studio**y, a continuación, haga clic en **Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="3447c-125">Click **Start**, point to **All Programs**, point to **Visual Studio**, and then click **Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="3447c-126">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3447c-126">Open a command prompt.</span></span>  
  
3.  <span data-ttu-id="3447c-127">Vaya a la ubicación del ensamblado y escriba **gacutil /I /\<***nombre de ensamblado***\>.dll**</span><span class="sxs-lookup"><span data-stu-id="3447c-127">Browse to the location of the assembly, and enter **gacutil /I /\<***assembly name***\>.dll**</span></span>