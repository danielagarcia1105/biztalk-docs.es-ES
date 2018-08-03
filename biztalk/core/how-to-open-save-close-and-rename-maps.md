---
title: Cómo abrir, guardar, cerrar y cambiar el nombre de asignaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a95ba8e22baa10a0b47721b8a8b3eb3554e2b8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968765"
---
# <a name="how-to-open-save-close-and-rename-maps"></a><span data-ttu-id="3964d-102">Cómo abrir, guardar, cerrar y cambiar el nombre de asignaciones</span><span class="sxs-lookup"><span data-stu-id="3964d-102">How to Open, Save, Close, and Rename Maps</span></span>
<span data-ttu-id="3964d-103">En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las asignaciones existen como archivos en el sistema de archivos con la extensión .btm.</span><span class="sxs-lookup"><span data-stu-id="3964d-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], maps exist as files in the file system with .btm extensions.</span></span> <span data-ttu-id="3964d-104">No obstante, es mucho más habitual trabajar con asignaciones como elementos de un proyecto de BizTalk, desde el que lleva a cabo operaciones como abrir, guardar y cerrar asignaciones.</span><span class="sxs-lookup"><span data-stu-id="3964d-104">Nevertheless, it is much more common to work with maps as items in a BizTalk project, from which you perform operations such as opening, saving, and closing maps.</span></span>  
  
### <a name="to-open-a-map"></a><span data-ttu-id="3964d-105">Para abrir una asignación</span><span class="sxs-lookup"><span data-stu-id="3964d-105">To open a map</span></span>  
  
1.  <span data-ttu-id="3964d-106">En el Explorador de soluciones, seleccione la asignación que desea abrir.</span><span class="sxs-lookup"><span data-stu-id="3964d-106">In Solution Explorer, select the map you want to open.</span></span>  
  
2.  <span data-ttu-id="3964d-107">En el **vista** menú, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="3964d-107">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="3964d-108">Se abre la asignación en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3964d-108">The map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3964d-109">Puede también haga clic en el mapa en el Explorador de soluciones y, a continuación, haga clic en **abierto**, o simplemente haga doble clic en el mapa en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="3964d-109">You can also right-click the map in Solution Explorer, and then click **Open**, or simply double-click the map in Solution Explorer.</span></span>  
  
### <a name="to-save-a-map"></a><span data-ttu-id="3964d-110">Para guardar una asignación</span><span class="sxs-lookup"><span data-stu-id="3964d-110">To save a map</span></span>  
  
1. <span data-ttu-id="3964d-111">En el Explorador de soluciones, seleccione la asignación que desea guardar.</span><span class="sxs-lookup"><span data-stu-id="3964d-111">In Solution Explorer, select the map you want to save.</span></span>  
  
2. <span data-ttu-id="3964d-112">En el **archivo** menú, haga clic en ** Guardar *\<de asignación de nombre\>***.</span><span class="sxs-lookup"><span data-stu-id="3964d-112">On the **File** menu, click **Save *\<Name of Map\>***.</span></span>  
  
### <a name="to-save-a-map-to-a-new-location"></a><span data-ttu-id="3964d-113">Para guardar una asignación en una nueva ubicación</span><span class="sxs-lookup"><span data-stu-id="3964d-113">To save a map to a new location</span></span>  
  
1.  <span data-ttu-id="3964d-114">En el Explorador de soluciones, seleccione la asignación que desea guardar en una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="3964d-114">In Solution Explorer, select the map you want to save to a new location.</span></span>  
  
2.  <span data-ttu-id="3964d-115">En el **archivo** menú, haga clic en **guardar *\<de asignación de nombre de\>* como**.</span><span class="sxs-lookup"><span data-stu-id="3964d-115">On the **File** menu, click **Save *\<Name of Map\>* As**.</span></span>  
  
3.  <span data-ttu-id="3964d-116">En el **Guardar archivo como** cuadro de diálogo, vaya a la ubicación de la carpeta donde desea guardar el mapa.</span><span class="sxs-lookup"><span data-stu-id="3964d-116">In the **Save File As** dialog box, browse to the folder location where you want to save the map.</span></span>  
  
4.  <span data-ttu-id="3964d-117">En el **nombre de archivo** , escriba un nombre para el archivo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="3964d-117">In the **File name** box, type a name for the file, and then click **Save**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3964d-118">No use los siguientes nombres para los mapas: "XmlContent", "SourceSchemas", "TargetSchemas" o "XsltArgumentListContent"; hacerlo provocará problemas de compilación en el código C# generado en el ensamblado .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3964d-118">Do not use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent"; doing so will cause compilation problems in the generated C# code in the corresponding .NET assembly.</span></span> <span data-ttu-id="3964d-119">Para obtener información acerca de problemas y su resolución, consulte [solución de problemas de mapas](../core/troubleshooting-maps.md).</span><span class="sxs-lookup"><span data-stu-id="3964d-119">For information about issues and their resolution, see [Troubleshooting Maps](../core/troubleshooting-maps.md).</span></span>  
  
### <a name="to-rename-a-map"></a><span data-ttu-id="3964d-120">Para cambiar el nombre de una asignación</span><span class="sxs-lookup"><span data-stu-id="3964d-120">To rename a map</span></span>  
  
1.  <span data-ttu-id="3964d-121">En el Explorador de soluciones, haga clic en el mapa que desea cambiar y, a continuación, haga clic en **cambiar el nombre**.</span><span class="sxs-lookup"><span data-stu-id="3964d-121">In Solution Explorer, right-click the map that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="3964d-122">En el cuadro de edición que aparece en la ubicación de la asignación en el Explorador de soluciones, escriba el nuevo nombre de la asignación o modifique el existente y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3964d-122">In the editing box that appears in the location of the map in Solution Explorer, type the new name for the map, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3964d-123">También puede cambiar el **nombre de tipo** del mapa cuando se cambia el nombre.</span><span class="sxs-lookup"><span data-stu-id="3964d-123">You may also want to change the **Type Name** of the map when you rename it.</span></span> <span data-ttu-id="3964d-124">Cambia el **nombre de tipo** seleccionando el **mapa** en el Explorador de soluciones y escribiendo el nuevo nombre en el **nombre de tipo** en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="3964d-124">You change the **Type Name** by selecting the **map** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
#### <a name="to-close-a-map"></a><span data-ttu-id="3964d-125">Para cerrar una asignación</span><span class="sxs-lookup"><span data-stu-id="3964d-125">To close a map</span></span>  
  
1. <span data-ttu-id="3964d-126">En el Explorador de soluciones, seleccione la asignación que desea cerrar.</span><span class="sxs-lookup"><span data-stu-id="3964d-126">In Solution Explorer, select the map you want to close.</span></span>  
  
2. <span data-ttu-id="3964d-127">En el menú **Archivo** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3964d-127">On the **File** menu, click **Close**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3964d-128">También puede hacer clic en el icono Cerrar ([**x**]) en la esquina superior derecha de la Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de edición.</span><span class="sxs-lookup"><span data-stu-id="3964d-128">You can also click the close icon ([**x**]) in the upper-right corner of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3964d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3964d-129">See Also</span></span>  
 [<span data-ttu-id="3964d-130">Administración de asignaciones en proyectos</span><span class="sxs-lookup"><span data-stu-id="3964d-130">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)