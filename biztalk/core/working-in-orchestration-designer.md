---
title: Trabajar en el Diseñador de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, saving
- deleting, orchestrations
- projects, orchestrations
- orchestrations, properties
- orchestrations, creating
- creating, orchestrations
- naming conventions, orchestrations
- orchestrations, naming conventions
- orchestrations, deleting
ms.assetid: 13e72b41-d9b6-4508-9a44-b3c7c1804f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52eb574f9f6b55b784357ff03c05ccb23774fecb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975482"
---
# <a name="working-in-orchestration-designer"></a><span data-ttu-id="07001-102">Trabajar en el Diseñador de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="07001-102">Working in Orchestration Designer</span></span>
<span data-ttu-id="07001-103">Después de iniciar un proyecto de BizTalk, puede crear nuevas orquestaciones y agregar otras existentes al proyecto.</span><span class="sxs-lookup"><span data-stu-id="07001-103">After you have started a BizTalk project, you can create new orchestrations and add existing orchestrations to the project.</span></span> <span data-ttu-id="07001-104">En los procedimientos siguientes se explica cómo crear y guardar una orquestación, agregar una orquestación existente a un proyecto o quitarla de él, cambiar el nombre de una orquestación y establecer las propiedades de orquestación.</span><span class="sxs-lookup"><span data-stu-id="07001-104">See the following procedures to create and save an orchestration, to add an existing orchestration to a project or remove one from it, to change the name of an orchestration, and to set orchestration properties.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="07001-105">Para crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-105">To create an orchestration</span></span>  
  
1.  <span data-ttu-id="07001-106">En el Explorador de soluciones, haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="07001-106">In Solution Explorer, right-click the project name, select **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="07001-107">En el **Agregar nuevo elemento** cuadro de diálogo, en la **categorías** panel, haga clic en **elementos de proyecto de BizTalk**y, a continuación, en la **plantillas** panel, haga clic en **Orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="07001-107">In the **Add New Item** dialog box, in the **Categories** pane, click **BizTalk Project Items**, and then in the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
3.  <span data-ttu-id="07001-108">En el **nombre** cuadro en la parte inferior del cuadro de diálogo, proporcione un nombre para la orquestación y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="07001-108">In the **Name** box at the bottom of the dialog box, supply a name for the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="07001-109">Se crea la nueva orquestación y se muestra en el Diseñador de orquestaciones; además, el archivo .odx correspondiente se crea y muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="07001-109">The new orchestration is created and displayed in Orchestration Designer, and a corresponding .odx file is created and displayed in Solution Explorer.</span></span>  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a><span data-ttu-id="07001-110">Para agregar una orquestación existente a un proyecto</span><span class="sxs-lookup"><span data-stu-id="07001-110">To add an existing orchestration to a project</span></span>  
  
1.  <span data-ttu-id="07001-111">En el Explorador de soluciones, haga clic en el nombre del proyecto, haga clic en **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="07001-111">In Solution Explorer, right-click the project name, click **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="07001-112">En el **Agregar elemento existente** cuadro de diálogo, desplácese al directorio que contiene la orquestación, seleccione la orquestación y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="07001-112">In the **Add Existing Item** dialog box, navigate to the directory containing the orchestration, select the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="07001-113">Se agregará la orquestación al proyecto.</span><span class="sxs-lookup"><span data-stu-id="07001-113">The orchestration is added to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07001-114">Si agrega un archivo existente, éste se copia en el proyecto</span><span class="sxs-lookup"><span data-stu-id="07001-114">When you add an existing file, the file is copied to your project.</span></span> <span data-ttu-id="07001-115">(no solo se agrega mediante referencia). Si cambia el archivo en el proyecto, el archivo original permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="07001-115">(The file is not simply added by reference.) If you change the file in your project, the original file is left unchanged.</span></span>  
  
### <a name="to-change-the-name-of-an-orchestration"></a><span data-ttu-id="07001-116">Para cambiar el nombre de una orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-116">To change the name of an orchestration</span></span>  
  
1.  <span data-ttu-id="07001-117">En el Explorador de soluciones, haga clic en el archivo .odx desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="07001-117">In Solution Explorer, right-click the .odx file you want to change, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="07001-118">Escriba un nuevo nombre de archivo y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="07001-118">Type the new file name you want, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07001-119">Al cambiar el nombre de un archivo .odx, también puede cambiar el nombre del tipo de orquestación haciendo clic en la superficie de diseño para que aparezca la ventana Propiedades y cambiar el valor de la **Typename** propiedad de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07001-119">When you change the name of an .odx file, you might also want to change the name of the orchestration type by clicking on the design surface to bring up the Properties window and changing the value of the **Typename** property of the orchestration.</span></span>  
  
### <a name="to-save-an-orchestration"></a><span data-ttu-id="07001-120">Para guardar una orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-120">To save an orchestration</span></span>  
  
-   <span data-ttu-id="07001-121">En el **archivo** menú, haga clic en **guardar \<nombre de la orquestación\>**.</span><span class="sxs-lookup"><span data-stu-id="07001-121">On the **File** menu, click **Save \<orchestration name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07001-122">Archivos de orquestación se guardan como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="07001-122">Orchestration files are saved as UTF-8.</span></span>  <span data-ttu-id="07001-123">Esquemas, asignaciones y canalizaciones se guardan como UTF-16.</span><span class="sxs-lookup"><span data-stu-id="07001-123">Schemas, maps, and pipelines are saved as UTF-16.</span></span>  
  
### <a name="to-remove-an-orchestration-from-a-project"></a><span data-ttu-id="07001-124">Para quitar una orquestación de un proyecto</span><span class="sxs-lookup"><span data-stu-id="07001-124">To remove an orchestration from a project</span></span>  
  
-   <span data-ttu-id="07001-125">En el Explorador de soluciones, haga clic en el archivo que desea quitar y, a continuación, haga clic en **excluir del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="07001-125">In Solution Explorer, right-click the file you want to remove, and then click **Exclude From Project**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07001-126">Para quitar la orquestación de un proyecto y eliminar permanentemente el archivo, haga clic en **eliminar** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="07001-126">To remove the orchestration from a project and permanently delete the file, click **Delete** instead.</span></span>  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a><span data-ttu-id="07001-127">Para incluir una orquestación excluida en un proyecto</span><span class="sxs-lookup"><span data-stu-id="07001-127">To include an excluded orchestration in a project</span></span>  
  
-   <span data-ttu-id="07001-128">En el Explorador de soluciones, haga clic en el **mostrar todo** botón de barra de herramientas, menú contextual del archivo .odx deseado y seleccione **incluir en el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="07001-128">In Solution Explorer, click the **Show All** toolbar button, right-click the .odx file you want, and select **Include in Project**.</span></span>  
  
### <a name="to-set-orchestration-properties"></a><span data-ttu-id="07001-129">Para establecer las propiedades de orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-129">To set orchestration properties</span></span>  
  
1.  <span data-ttu-id="07001-130">Abra la orquestación haciendo doble clic en el archivo .odx del proyecto o seleccionando la pestaña que contiene la orquestación en el área de proceso.</span><span class="sxs-lookup"><span data-stu-id="07001-130">Open the orchestration by double-clicking on the .odx file in the project, or by selecting the tab containing the orchestration in the Process Area.</span></span>  
  
2.  <span data-ttu-id="07001-131">En la ventana Vista orquestación, seleccione **propiedades de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="07001-131">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
     <span data-ttu-id="07001-132">: "O":</span><span class="sxs-lookup"><span data-stu-id="07001-132">—Or—</span></span>  
  
     <span data-ttu-id="07001-133">Haga clic en el **área de proceso** fondo de la superficie de diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="07001-133">Click the **Process Area** background of the Orchestration Design Surface.</span></span>  
  
3.  <span data-ttu-id="07001-134">En la ventana Propiedades, especifique las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="07001-134">In the Properties window, specify the following properties.</span></span> <span data-ttu-id="07001-135">Tenga en cuenta que algunas propiedades solo aparecen en determinadas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="07001-135">Note that some properties appear only under certain circumstances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07001-136">Los nombres de las orquestaciones, los tipos de puerto y los tipos de mensaje de varias partes deben ser únicos en el ámbito de un módulo.</span><span class="sxs-lookup"><span data-stu-id="07001-136">The names of orchestrations, port types and multi-part message types must be unique within the scope of a module.</span></span>  
  
    |<span data-ttu-id="07001-137">Propiedad</span><span class="sxs-lookup"><span data-stu-id="07001-137">Property</span></span>|<span data-ttu-id="07001-138">Description</span><span class="sxs-lookup"><span data-stu-id="07001-138">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="07001-139">Lote</span><span class="sxs-lookup"><span data-stu-id="07001-139">Batch</span></span>|<span data-ttu-id="07001-140">Determina si una orquestación que es una transacción atómica se puede procesar por lotes con otras instancias.</span><span class="sxs-lookup"><span data-stu-id="07001-140">Determines whether an orchestration that is an atomic transaction can be batched with other instances.</span></span>|  
    |<span data-ttu-id="07001-141">Compensación</span><span class="sxs-lookup"><span data-stu-id="07001-141">Compensation</span></span>|<span data-ttu-id="07001-142">Especifica qué tipo de compensación debe realizarse en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07001-142">Specifies what type of compensation to perform on the orchestration.</span></span>|  
    |<span data-ttu-id="07001-143">Nivel de aislamiento</span><span class="sxs-lookup"><span data-stu-id="07001-143">Isolation Level</span></span>|<span data-ttu-id="07001-144">Para las orquestaciones transaccionales, determina el nivel de acceso a los datos para las transacciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="07001-144">For transactional orchestrations, determines the degree to which data is accessible among concurrent transactions.</span></span>|  
    |<span data-ttu-id="07001-145">Exportable a módulo</span><span class="sxs-lookup"><span data-stu-id="07001-145">Module Exportable</span></span>|<span data-ttu-id="07001-146">Determina si el módulo se puede exportar BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="07001-146">Determines whether or not the module can be exported to BPEL4WS.</span></span>|  
    |<span data-ttu-id="07001-147">Target Namespace XML de módulo</span><span class="sxs-lookup"><span data-stu-id="07001-147">Module XML Target Namespace</span></span>|<span data-ttu-id="07001-148">Espacio de nombres de destino XML que se usa al exportar tipos a BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="07001-148">The XML target namespace used when exporting types to BPEL4WS.</span></span>|  
    |<span data-ttu-id="07001-149">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="07001-149">Namespace</span></span>|<span data-ttu-id="07001-150">Determina el nombre del módulo contenedor que incluye la orquestación y los tipos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="07001-150">Determines the name of the containing module that includes the orchestration and the orchestration types.</span></span>|  
    |<span data-ttu-id="07001-151">Exportable a orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-151">Orchestration Exportable</span></span>|<span data-ttu-id="07001-152">Indica si esta orquestación se podrá exportar a BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="07001-152">Indicates whether this orchestration is intended to be exportable to BPEL4WS.</span></span>|  
    |<span data-ttu-id="07001-153">Target Namespace XML de orquestación</span><span class="sxs-lookup"><span data-stu-id="07001-153">Orchestration XML Target Namespace</span></span>|<span data-ttu-id="07001-154">Espacio de nombres de destino XML que se usa al exportar esta orquestación a BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="07001-154">The XML target namespace used when exporting this orchestration to BPEL4WS.</span></span>|  
    |<span data-ttu-id="07001-155">Reintentar</span><span class="sxs-lookup"><span data-stu-id="07001-155">Retry</span></span>|<span data-ttu-id="07001-156">Especifica si se reintentará una orquestación transaccional en caso de error.</span><span class="sxs-lookup"><span data-stu-id="07001-156">Specify whether to retry a transactional orchestration if it fails.</span></span>|  
    |<span data-ttu-id="07001-157">Timeout</span><span class="sxs-lookup"><span data-stu-id="07001-157">Timeout</span></span>|<span data-ttu-id="07001-158">Tiempo en segundos transcurrido hasta que se produzca un error en la orquestación transaccional por inactividad.</span><span class="sxs-lookup"><span data-stu-id="07001-158">The time in seconds until a transactional orchestration fails due to inactivity.</span></span>|  
    |<span data-ttu-id="07001-159">Identificador de transacción</span><span class="sxs-lookup"><span data-stu-id="07001-159">Transaction Identifier</span></span>|<span data-ttu-id="07001-160">Identificador único de una orquestación transaccional.</span><span class="sxs-lookup"><span data-stu-id="07001-160">Unique identifier for a transactional orchestration.</span></span>|  
    |<span data-ttu-id="07001-161">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="07001-161">Transaction Type</span></span>|<span data-ttu-id="07001-162">Determina si la orquestación es una transacción atómica, una transacción de larga ejecución o no tiene transacciones.</span><span class="sxs-lookup"><span data-stu-id="07001-162">Determines whether the orchestration is an atomic transaction, a long-running transaction, or is not transacted.</span></span>|  
    |<span data-ttu-id="07001-163">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="07001-163">Type Modifier</span></span>|<span data-ttu-id="07001-164">Determina el ámbito de las variables de la orquestación:</span><span class="sxs-lookup"><span data-stu-id="07001-164">Determines the scope of orchestration-level variables:</span></span><br /><br /> <span data-ttu-id="07001-165">Privado: acceso a esta orquestación está limitado al módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="07001-165">Private—Access to this orchestration is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="07001-166">Público: acceso a esta orquestación no está limitado.</span><span class="sxs-lookup"><span data-stu-id="07001-166">Public—Access to this orchestration is not limited.</span></span><br /><br /> <span data-ttu-id="07001-167">Interno: acceso a esta orquestación está limitado a los módulos dentro del mismo proyecto.</span><span class="sxs-lookup"><span data-stu-id="07001-167">Internal—Access to this orchestration is limited to modules within the same project.</span></span>|  
    |<span data-ttu-id="07001-168">Nombre de tipo</span><span class="sxs-lookup"><span data-stu-id="07001-168">Typename</span></span>|<span data-ttu-id="07001-169">Determina el nombre de esta orquestación en el módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="07001-169">Determines the name of this orchestration within the containing module.</span></span> <span data-ttu-id="07001-170">**Nota:** si usar un nombre de tipo que es el mismo que un espacio de nombres de nivel de raíz, puede recibir un error del Diseñador de orquestaciones al definir mensajes y variables basadas en el nombre de tipo e intentar realizar operaciones de asignación con ellos.</span><span class="sxs-lookup"><span data-stu-id="07001-170">**Note:**  If you to use a Typename that is the same as a root-level namespace, you may receive an error from Orchestration Designer when you define messages and variables based on the Typename and attempt to perform assign operations on them.</span></span> <span data-ttu-id="07001-171">Por ejemplo, si especifica el nombre de tipo System, y define mensajes y variables cuyo nombre sea, por ejemplo, System.String, podría recibir un error.</span><span class="sxs-lookup"><span data-stu-id="07001-171">For example, if you specify a Typename of System, and then define messages and variables like System.String, you may receive an error.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07001-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="07001-172">See Also</span></span>  
 <span data-ttu-id="07001-173">[Formas de orquestación](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="07001-173">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="07001-174">[Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="07001-174">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 <span data-ttu-id="07001-175">[Cómo agregar parámetros a orquestaciones](../core/how-to-add-parameters-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="07001-175">[How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="07001-176">Cómo usar el cuadro de diálogo de tipo de artefacto Select</span><span class="sxs-lookup"><span data-stu-id="07001-176">How to Use the Select Artifact Type Dialog Box</span></span>](../core/how-to-use-the-select-artifact-type-dialog-box.md)