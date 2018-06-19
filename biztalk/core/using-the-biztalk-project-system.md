---
title: Utilizar el sistema del proyecto de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b8c3a83d75219b9e52fd2ab13124480d772832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008197"
---
# <a name="using-the-biztalk-project-system"></a><span data-ttu-id="9ba19-102">Utilizar el sistema del proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9ba19-102">Using the BizTalk Project System</span></span>
<span data-ttu-id="9ba19-103">Puede usar el sistema del proyectos de BizTalk para crear, organizar y configurar soluciones de BizTalk en el entorno de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ba19-103">You can use the BizTalk project system to create, organize, and configure BizTalk solutions in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="9ba19-104">Los temas y procedimientos de esta sección describen como realizar varias tareas mediante el sistema del proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9ba19-104">The topics and procedures in this section describe how to perform various tasks by using the BizTalk project system.</span></span>  
  
 <span data-ttu-id="9ba19-105">El sistema de proyectos de BizTalk Server utiliza los mismos principios de administración de proyectos y los procedimientos que se utilizan con otros proyectos de Microsoft Build Engine (MSBuild) en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ba19-105">The BizTalk Server project system uses the same project management principles and procedures that you use with other Microsoft Build Engine (MSBuild) projects in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="9ba19-106">Esta sección detalla procedimientos comunes que puede usar al crear una aplicación que ejecuta Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ba19-106">This section details common procedures that you might use when creating an application that runs on Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9ba19-107">Para obtener más información acerca de MSBuild, vea la sección de referencia de MSBuild en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection en [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span><span class="sxs-lookup"><span data-stu-id="9ba19-107">For more information about MSBuild, see the MSBuild reference section in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
 <span data-ttu-id="9ba19-108">Para obtener más información sobre el uso de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] entorno, vea "Administrar soluciones, proyectos y archivos" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection en [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ba19-108">For more information about using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment, see "Managing Solutions, Projects, and Files" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx).</span></span>  
  
 <span data-ttu-id="9ba19-109">La siguiente ilustración muestra el entorno de diseño del sistema de proyecto de BizTalk con el **nuevo proyecto** cuadro de diálogo abierto.</span><span class="sxs-lookup"><span data-stu-id="9ba19-109">The following figure shows the BizTalk project system design environment with the **New Project** dialog box open.</span></span>  
  
 <span data-ttu-id="9ba19-110">![Sistemas del proyecto](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span><span class="sxs-lookup"><span data-stu-id="9ba19-110">![Project Systems](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")</span></span>  
<span data-ttu-id="9ba19-111">Representación del entorno de diseño del sistema del proyecto</span><span class="sxs-lookup"><span data-stu-id="9ba19-111">Depicts the Project System Design Environment</span></span>  
  
### <a name="to-open-biztalk-editor"></a><span data-ttu-id="9ba19-112">Para abrir el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9ba19-112">To open BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="9ba19-113">En el Explorador de soluciones, haga clic en un esquema.</span><span class="sxs-lookup"><span data-stu-id="9ba19-113">In Solution Explorer, click a schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-114">Para abrir el Editor de BizTalk, en primer lugar debe crear un esquema o abrir uno previamente creado.</span><span class="sxs-lookup"><span data-stu-id="9ba19-114">To open BizTalk Editor, you must first create a schema or open a previously created schema.</span></span> <span data-ttu-id="9ba19-115">Para obtener información acerca de cómo crear un esquema, vea [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-115">For information about creating a schema, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="9ba19-116">Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-116">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="9ba19-117">En el **vista** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-117">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-118">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-118">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-119">Haga clic en el esquema y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-119">Right-click the schema, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-120">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-120">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-121">Haga doble clic en el esquema.</span><span class="sxs-lookup"><span data-stu-id="9ba19-121">Double-click the schema.</span></span>  
  
     <span data-ttu-id="9ba19-122">El esquema seleccionado se abre en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9ba19-122">The selected schema opens in BizTalk Editor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-123">Para crear un esquema, debe tener abierto un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ba19-123">To create a schema, you must have a project open.</span></span> <span data-ttu-id="9ba19-124">Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-124">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="9ba19-125">Para obtener información sobre cómo agregar elementos a un proyecto, vea [cómo crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-125">For information about adding items to a project, see [How to Create Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md).</span></span> <span data-ttu-id="9ba19-126">Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-126">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
### <a name="to-open-biztalk-mapper"></a><span data-ttu-id="9ba19-127">Para abrir el Asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9ba19-127">To open BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="9ba19-128">En el Explorador de soluciones, haga clic en una asignación.</span><span class="sxs-lookup"><span data-stu-id="9ba19-128">In Solution Explorer, click a map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-129">Para abrir el Asignador de BizTalk, en primer lugar debe crear una asignación o abrir una previamente creada.</span><span class="sxs-lookup"><span data-stu-id="9ba19-129">To open BizTalk Mapper, you must first create a map or open a previously created map.</span></span> <span data-ttu-id="9ba19-130">Para obtener información acerca de cómo crear un mapa, consulte [cómo crear nuevas asignaciones](../core/how-to-create-new-maps.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-130">For information about creating a map, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span> <span data-ttu-id="9ba19-131">Consulte también [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-131">Also see [Adding Project Items](../core/adding-project-items.md).</span></span>  
  
2.  <span data-ttu-id="9ba19-132">En el **vista** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-132">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-133">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-133">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-134">Haga clic en el mapa y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-134">Right-click the map, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-135">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-135">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-136">Haga doble clic en la asignación.</span><span class="sxs-lookup"><span data-stu-id="9ba19-136">Double-click a map.</span></span>  
  
     <span data-ttu-id="9ba19-137">Se abre la asignación seleccionada en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9ba19-137">The selected map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-138">Para crear una asignación, debe tener abierto un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ba19-138">To create a map, you must have a project open.</span></span> <span data-ttu-id="9ba19-139">Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-139">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="9ba19-140">Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-140">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="9ba19-141">Consulte también [cómo crear nuevas asignaciones](../core/how-to-create-new-maps.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-141">Also see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
### <a name="to-open-orchestration-designer"></a><span data-ttu-id="9ba19-142">Para abrir el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="9ba19-142">To open Orchestration Designer</span></span>  
  
1.  <span data-ttu-id="9ba19-143">En el Explorador de soluciones, haga clic en una orquestación (.odx).</span><span class="sxs-lookup"><span data-stu-id="9ba19-143">In Solution Explorer, click an orchestration (.odx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-144">Para abrir el Diseñador de orquestaciones, en primer lugar debe crear una orquestación o abrir una previamente creada.</span><span class="sxs-lookup"><span data-stu-id="9ba19-144">To open Orchestration Designer, you must first create an orchestration or open a previously created orchestration.</span></span> <span data-ttu-id="9ba19-145">Para obtener información sobre cómo crear una orquestación, consulte [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-145">For information about how to create an orchestration, see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
2.  <span data-ttu-id="9ba19-146">En el **vista** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-146">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-147">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-147">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-148">Haga clic en la orquestación y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-148">Right-click the orchestration, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-149">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-149">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-150">Haga doble clic en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9ba19-150">Double-click the orchestration.</span></span>  
  
     <span data-ttu-id="9ba19-151">Se abre el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="9ba19-151">Orchestration Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-152">Para crear una orquestación, debe tener abierto un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ba19-152">To create an orchestration, you must have a project open.</span></span> <span data-ttu-id="9ba19-153">Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-153">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="9ba19-154">Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-154">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="9ba19-155">Consulte también [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-155">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
### <a name="to-open-pipeline-designer"></a><span data-ttu-id="9ba19-156">Para abrir el Diseñador de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="9ba19-156">To open Pipeline Designer</span></span>  
  
1.  <span data-ttu-id="9ba19-157">En el Explorador de soluciones, haga clic en una canalización.</span><span class="sxs-lookup"><span data-stu-id="9ba19-157">In Solution Explorer, click a pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-158">Para abrir el Diseñador de canalizaciones, en primer lugar debe crear una canalización o abrir una previamente creada.</span><span class="sxs-lookup"><span data-stu-id="9ba19-158">To open Pipeline Designer, you must first create a pipeline or open a previously created pipeline.</span></span> <span data-ttu-id="9ba19-159">Para obtener información sobre cómo crear una canalización, consulte [cómo crear una nueva canalización](../core/how-to-create-a-new-pipeline.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-159">For information about how to create a pipeline, see [How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md).</span></span>  
  
2.  <span data-ttu-id="9ba19-160">En el **vista** menú, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-160">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-161">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-161">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-162">Haga clic en la canalización y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9ba19-162">Right-click the pipeline, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9ba19-163">: "O":</span><span class="sxs-lookup"><span data-stu-id="9ba19-163">—Or—</span></span>  
  
     <span data-ttu-id="9ba19-164">Haga doble clic en la canalización.</span><span class="sxs-lookup"><span data-stu-id="9ba19-164">Double-click the pipeline.</span></span>  
  
     <span data-ttu-id="9ba19-165">Se abre el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="9ba19-165">Pipeline Designer opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ba19-166">Para crear una canalización, debe tener abierto un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ba19-166">To create a pipeline, you must have a project open.</span></span> <span data-ttu-id="9ba19-167">Para obtener información sobre cómo crear un proyecto, vea [cómo crear proyectos de BizTalk](../core/how-to-create-biztalk-projects.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-167">For information about how to create a project, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span> <span data-ttu-id="9ba19-168">Para obtener información sobre cómo agregar elementos a un proyecto, vea [agregar elementos de proyecto](../core/adding-project-items.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-168">For information about adding items to a project, see [Adding Project Items](../core/adding-project-items.md).</span></span> <span data-ttu-id="9ba19-169">Consulte también [trabaja en el Diseñador de orquestaciones](../core/working-in-orchestration-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9ba19-169">Also see [Working in Orchestration Designer](../core/working-in-orchestration-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba19-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba19-170">See Also</span></span>  
 <span data-ttu-id="9ba19-171">[Crear orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-171">[Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md) </span></span>  
 <span data-ttu-id="9ba19-172">[Utilizando el Diseñador de canalizaciones](../core/using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-172">[Using Pipeline Designer](../core/using-pipeline-designer.md) </span></span>  
 <span data-ttu-id="9ba19-173">[Ventanas del compositor de reglas de negocios](../core/windows-of-the-business-rule-composer.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-173">[Windows of the Business Rule Composer](../core/windows-of-the-business-rule-composer.md) </span></span>  
 <span data-ttu-id="9ba19-174">[Usar el Editor de BizTalk](../core/using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-174">[Using BizTalk Editor](../core/using-biztalk-editor.md) </span></span>  
 <span data-ttu-id="9ba19-175">[Con el asignador de BizTalk](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="9ba19-175">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="9ba19-176">Herramientas de desarrollo</span><span class="sxs-lookup"><span data-stu-id="9ba19-176">Developer Tools</span></span>](../core/developer-tools.md)