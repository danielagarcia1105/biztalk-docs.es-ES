---
title: "Cómo agregar asignaciones existentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a61fb0faf5f4eed614257361b00cea781db2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-existing-maps"></a><span data-ttu-id="58da0-102">Cómo agregar asignaciones existentes</span><span class="sxs-lookup"><span data-stu-id="58da0-102">How to Add Existing Maps</span></span>
<span data-ttu-id="58da0-103">Habrá ocasiones en las que desee agregar una asignación existente a un proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="58da0-103">There may be times when you want to add an existing map to a BizTalk project.</span></span> <span data-ttu-id="58da0-104">Antes de hacerlo, debe asegurarse de que los esquemas de origen y de destino de la asignación están incluidos en el proyecto de BizTalk al que va a agregar la asignación o al menos deben tener una referencia en el ensamblado .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="58da0-104">Before doing so, you must ensure that the source and destination schemas of the map are included in the BizTalk project to which you are adding the map; or, referenced by the corresponding .NET assembly.</span></span>  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a><span data-ttu-id="58da0-105">Para agregar un asignación ya existente a un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="58da0-105">To add an existing map to a BizTalk project</span></span>  
  
1.  <span data-ttu-id="58da0-106">Haga clic en un proyecto de BizTalk en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="58da0-106">Right-click a BizTalk project in Solution Explorer, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="58da0-107">En el **Agregar elemento existente** cuadro de diálogo, busque la carpeta que contiene el mapa para agregar, selecciónelo y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="58da0-107">In the **Add Existing Item** dialog box, browse to the folder containing the map to be added, select it, and then click **Add**.</span></span>  
  
     <span data-ttu-id="58da0-108">Se abre la asignación en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="58da0-108">The map opens in BizTalk Mapper.</span></span> <span data-ttu-id="58da0-109">La asignación que acaba de agregar también aparece como un elemento secundario del proyecto actual de BizTalk en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="58da0-109">The newly added map also appears as a child of the current BizTalk project in Solution Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58da0-110">Si abrió otra carpeta distinta de la del proyecto de BizTalk, en la carpeta del proyecto se creó una copia de la asignación que agregó, y esta es la copia que se agregó al proyecto.</span><span class="sxs-lookup"><span data-stu-id="58da0-110">If you browsed to a folder other than the BizTalk project folder, a copy of the map you added was created in the project folder, and it was this copy of the map that was added to the project.</span></span> <span data-ttu-id="58da0-111">Los cambios posteriores a esta asignación se realizan en esta copia, no en la asignación original en la otra carpeta.</span><span class="sxs-lookup"><span data-stu-id="58da0-111">Subsequent changes to the map are made to this copy, not to the original map in the other folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="58da0-112">Las asignaciones de BizTalk solo se pueden abrir con el Asignador de BizTalk, el cual se hospeda dentro del shell de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58da0-112">BizTalk maps can only be opened by BizTalk Mapper, which is hosted within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="58da0-113">Si hace doble clic en una asignación en el Explorador de Windows, se abre una nueva instancia de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y el Asignador de BizTalk abrirá la asignación, siempre y cuando los esquemas correspondientes se carguen correctamente.</span><span class="sxs-lookup"><span data-stu-id="58da0-113">If you double-click a map in Windows Explorer, a new instance of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will be opened, and then the map will be opened by BizTalk Mapper, provided the corresponding schemas are loaded properly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58da0-114">Si el mapa existente contiene functoids personalizados, los DLL correspondientes deberán copiarse a la carpeta "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions".</span><span class="sxs-lookup"><span data-stu-id="58da0-114">If the existing map contains custom functoids, then the corresponding DLLs must be copied to the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span> <span data-ttu-id="58da0-115">En caso contrario, la asignación no se cargará y lanzará un error debido a no poder cargar functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="58da0-115">Else, the map will not load and throws an error because of failure to load custom functoids.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58da0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="58da0-116">See Also</span></span>  
 <span data-ttu-id="58da0-117">[Administrar asignaciones en proyectos](../core/managing-maps-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="58da0-117">[Managing Maps Within Projects](../core/managing-maps-within-projects.md) </span></span>  
 [<span data-ttu-id="58da0-118">Desarrollar Functoids personalizados</span><span class="sxs-lookup"><span data-stu-id="58da0-118">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)