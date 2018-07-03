---
title: Volver a generar el libro de datos en directo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c62686c15c2e0b04576ca3175fb22d52a71922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987413"
---
# <a name="regenerate-the-live-data-workbook"></a><span data-ttu-id="ddbf7-102">Volver a generar el libro de datos en directo</span><span class="sxs-lookup"><span data-stu-id="ddbf7-102">Regenerate the Live Data Workbook</span></span>
<span data-ttu-id="ddbf7-103">En caso de pérdida o daño del libro de trabajo de datos activos de BAM, es posible regenerar el libro de trabajo mediante la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-103">In cases where the BAM live data workbook has been lost or corrupted, you can regenerate the workbook using the BAM Management utiprolity.</span></span> <span data-ttu-id="ddbf7-104">Este proceso también es útil cuando está actualizando desde desde versiones anteriores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-104">This process is also useful when you are upgrading from from previous BizTalk Server versions.</span></span>
  
 <span data-ttu-id="ddbf7-105">Los pasos generales son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ddbf7-105">The general steps are as follows:</span></span>  
  
-   <span data-ttu-id="ddbf7-106">Recuperar la definición de BAM de la base de datos de BAM mediante la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-106">Retrieve the BAM definition from the BAM database using the BAM Management utility.</span></span>  
  
-   <span data-ttu-id="ddbf7-107">Volver a crear informes de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-107">Re-create the PivotTable reports.</span></span> <span data-ttu-id="ddbf7-108">Puesto que la recuperación de XML mediante el comando get-defxml contiene, únicamente, las actividades y las vistas, es preciso volver a crear los informes de tabla dinámica mediante el complemento de BAM para Excel.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-108">Since the XML retrieval by the get-defxml command contains only the activities and views, you must re-create the PivotTable reports using the BAM Add-in for Excel.</span></span>  
  
-   <span data-ttu-id="ddbf7-109">Cambiar el nombre de los informes de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-109">Rename the PivotTable reports.</span></span> <span data-ttu-id="ddbf7-110">Este paso puede ser necesario si va a actualizar desde una versión anterior de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-110">This step may be necessary if you are upgrading from a previous BizTalk Server version.</span></span> <span data-ttu-id="ddbf7-111">Con algunas versiones, BAM almacena dos conjuntos de nombres para los libros BAM: un nombre para mostrar y un nombre interno.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-111">With some versions, BAM stores two sets of names for BAM workbooks: a display name and an internal name.</span></span> <span data-ttu-id="ddbf7-112">Al recuperar la definición de BAM, el XML contiene el nombre interno del libro de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-112">When you retrieve the BAM definition, the XML contains the internal name for the workbook.</span></span> <span data-ttu-id="ddbf7-113">Es preciso cambiar el nombre de los informes de tabla dinámica para garantizar que el libro de trabajo de datos activos tenga la conexión adecuada con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-113">You must rename the PivotTable reports to ensure that the live data workbook has the correct connection to the database.</span></span>  
  
-   <span data-ttu-id="ddbf7-114">Regenerar el libro de trabajo de datos activos mediante la utilidad de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-114">Regenerate the live data workbook using the BAM Management utility.</span></span>  
  
## <a name="retrieve-the-bam-definition"></a><span data-ttu-id="ddbf7-115">Recuperar la definición de BAM</span><span class="sxs-lookup"><span data-stu-id="ddbf7-115">Retrieve the BAM definition</span></span>  
  
1. <span data-ttu-id="ddbf7-116">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-116">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ddbf7-117">En el símbolo del sistema, navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-117">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="ddbf7-118">Tipo: **bm.exe get-defxml-FileName:abc.xml**</span><span class="sxs-lookup"><span data-stu-id="ddbf7-118">Type: **bm.exe get-defxml -FileName:abc.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ddbf7-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="recreate-the-pivottable-reports"></a><span data-ttu-id="ddbf7-120">Volver a crear los informes de tabla dinámica</span><span class="sxs-lookup"><span data-stu-id="ddbf7-120">Recreate the PivotTable reports</span></span>  
  
1. <span data-ttu-id="ddbf7-121">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-121">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2. <span data-ttu-id="ddbf7-122">Haga clic en el **Add-Ins** pestaña y, a continuación, seleccione **importar XML** desde el **BAM** lista desplegable en el **comandos de menú** grupo.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-122">Click the **Add-Ins** tab, and then select **Import XML** from the **BAM** drop-down list in the **Menu Commands** group.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ddbf7-123">Si el **Add-Ins** ficha no está presente, siga las instrucciones de [paso 1: agregar el complemento BAM para Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) para agregar el complemento de BAM.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-123">If the **Add-Ins** tab is not present, follow the instructions in [Step 1: Add the BAM Add-In to Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) to add the BAM add-in.</span></span>  
  
3. <span data-ttu-id="ddbf7-124">Desplácese hasta la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking y seleccione el archivo abc.xml.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-124">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking folder and select the abc.xml file.</span></span>  
  
4. <span data-ttu-id="ddbf7-125">Vuelva a crear los informes de tabla dinámica basándose en la definición.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-125">Re-create your PivotTable reports based on your definition.</span></span>  
  
5. <span data-ttu-id="ddbf7-126">Guarde el libro de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-126">Save the workbook.</span></span> <span data-ttu-id="ddbf7-127">Para ello, haga clic en el **archivo** menú y, a continuación, haga clic en **Guardar como** y escriba mynewbook.xls cuando se le pida un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-127">To do this, click the **File** menu, and then click **Save As** and type mynewbook.xls when prompted for a file name.</span></span>  
  
## <a name="rename-the-pivottable-reports-optional"></a><span data-ttu-id="ddbf7-128">Cambiar el nombre de los informes de tabla dinámica (opcionales)</span><span class="sxs-lookup"><span data-stu-id="ddbf7-128">Rename the PivotTable reports (optional)</span></span>  

> [!NOTE]
> <span data-ttu-id="ddbf7-129">Este paso sólo puede ser necesario si va a actualizar desde una versión anterior de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-129">This step may only be required if you are upgrading from an older version of BizTalk Server.</span></span> 

1. <span data-ttu-id="ddbf7-130">Abra el archivo abc.xml creado al recuperar las definiciones de BAM mediante el Bloc de notas haciendo **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-130">Open the abc.xml file that you created when you retrieved the BAM definitions using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="ddbf7-131">Busque el \<título\> etiqueta bajo \<BAMDefinition\>\\< extensión\>\\< OWC\>\\< PivotTableView\> \\< tabla dinámica\>\\< PivotView\>\\< etiqueta\>.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-131">Locate the \<Caption\> tag under \<BAMDefinition\>\\<Extension\>\\<OWC\>\\<PivotTableView\>\\<PivotTable\>\\<PivotView\>\\<Label\>.</span></span> <span data-ttu-id="ddbf7-132">El contenido de esta etiqueta es el nombre interno de uno de los informes de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-132">The content of this tag is the internal name for one of your PivotTable reports.</span></span> <span data-ttu-id="ddbf7-133">Puede encontrar el nombre interno para los otros informes de tabla dinámica localizando la próxima \<título\> etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-133">You can find the internal name for the other PivotTable reports by locating the next \<Caption\> tag.</span></span> <span data-ttu-id="ddbf7-134">Abra **mynewbook.xls** y usar los nombres encontrados para cambiar el nombre de los informes de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-134">Open **mynewbook.xls** and use the names you located to rename your PivotTable reports.</span></span>  
  
3. <span data-ttu-id="ddbf7-135">Guarde el libro de trabajo actualizado.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-135">Save the updated workbook.</span></span>    
 
  
## <a name="regenerate-the-bam-live-data-workbook"></a><span data-ttu-id="ddbf7-136">Volver a generar el libro de datos activos de BAM</span><span class="sxs-lookup"><span data-stu-id="ddbf7-136">Regenerate the BAM live data workbook</span></span>  

> [!NOTE]
>  <span data-ttu-id="ddbf7-137">Ejecute esta herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-137">Run this tool with Administrative privileges.</span></span>  


1. <span data-ttu-id="ddbf7-138">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-138">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ddbf7-139">En el símbolo del sistema, navegue hasta el siguiente directorio: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span><span class="sxs-lookup"><span data-stu-id="ddbf7-139">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking.</span></span>  
  
3. <span data-ttu-id="ddbf7-140">Tipo: **bm.exe regenerate-livedataworkbook-WorkbookName:mynewbook.xls**</span><span class="sxs-lookup"><span data-stu-id="ddbf7-140">Type: **bm.exe regenerate-livedataworkbook -WorkbookName:mynewbook.xls**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbf7-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddbf7-141">See Also</span></span>  
 <span data-ttu-id="ddbf7-142">[Administración de BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="ddbf7-142">[Managing BAM](../core/managing-bam.md) </span></span>  
 <span data-ttu-id="ddbf7-143">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ddbf7-143">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 <span data-ttu-id="ddbf7-144">[Requisitos para usar el complemento BAM para Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="ddbf7-144">[Requirements for Using the BAM Add-In for Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="ddbf7-145">Paso 1: Agregar el complemento de BAM a Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="ddbf7-145">Step 1: Add the BAM Add-In to Microsoft Office Excel</span></span>](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)