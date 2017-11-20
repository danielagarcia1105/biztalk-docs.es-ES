---
title: Usar archivos de enlace para importar o exportar | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="use-binding-files-to-import-or-export"></a><span data-ttu-id="0743e-102">Usar archivos de enlace para importar o exportar</span><span class="sxs-lookup"><span data-stu-id="0743e-102">Use binding files to import or export</span></span>

<span data-ttu-id="0743e-103">A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede exportar e importar archivos de enlace en el **partes** y **acuerdo** niveles.</span><span class="sxs-lookup"><span data-stu-id="0743e-103">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can export and import binding files at the **Parties** and **Agreement** levels.</span></span> <span data-ttu-id="0743e-104">Para las versiones anteriores de BizTalk, exportar en el nivel de aplicación, como se describe en:</span><span class="sxs-lookup"><span data-stu-id="0743e-104">For previous BizTalk versions, you export at the application level, as described at:</span></span> 

* [<span data-ttu-id="0743e-105">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="0743e-105">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="0743e-106">Cómo importar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="0743e-106">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

<span data-ttu-id="0743e-107">En este tema muestra cómo importar y exporta entidades, sus perfiles, acuerdos, configuración de reserva y usar más [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] y BTSTask.</span><span class="sxs-lookup"><span data-stu-id="0743e-107">This topic shows you how to import and exports parties, their profiles, agreements, fallback settings, and more using [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] and BTSTask.</span></span> 

## <a name="overview"></a><span data-ttu-id="0743e-108">Información general</span><span class="sxs-lookup"><span data-stu-id="0743e-108">Overview</span></span>

<span data-ttu-id="0743e-109">Algunas de las características de importación y exportación son:</span><span class="sxs-lookup"><span data-stu-id="0743e-109">Some of the import and export features include:</span></span>

* <span data-ttu-id="0743e-110">Importar entidades y perfiles de negocio, acuerdos desde un archivo de enlace XML</span><span class="sxs-lookup"><span data-stu-id="0743e-110">Import parties, business profiles, and agreements from an XML binding file</span></span>
* <span data-ttu-id="0743e-111">Exportar entidades, perfiles de negocio, acuerdos y configuración de reserva de EDI en un archivo de enlace XML</span><span class="sxs-lookup"><span data-stu-id="0743e-111">Export parties, business profiles, agreements, and EDI fallback settings to an XML binding file</span></span>
* <span data-ttu-id="0743e-112">Al importar un archivo de enlace, puede decidir no importar las entidades o la configuración de reserva</span><span class="sxs-lookup"><span data-stu-id="0743e-112">When importing a binding file, you can chose to not import the parties, or the fallback settings</span></span>
* <span data-ttu-id="0743e-113">Cuando se importan en el nivel de entidades, solo las entidades y acuerdos en el archivo de enlace se importan</span><span class="sxs-lookup"><span data-stu-id="0743e-113">When importing at the Parties-level, only the parties and agreements within the binding file are imported</span></span>
* <span data-ttu-id="0743e-114">Exportar entidades específicas en el mismo archivo de enlace y optar por exportar todos los acuerdos asociados con esas entidades</span><span class="sxs-lookup"><span data-stu-id="0743e-114">Export specific parties to the same binding file, and choose to also export all the agreements associated with those parties</span></span>
* <span data-ttu-id="0743e-115">El Asistente para enlace de importación de aplicaciones le permite elegir importar la configuración de seguimiento o excluir las entidades.</span><span class="sxs-lookup"><span data-stu-id="0743e-115">The application import binding wizard lets you choose to import the tracking settings, or exclude the parties.</span></span>
* <span data-ttu-id="0743e-116">BTSTask incluye la `ImportParties` y `ExportParties` comandos</span><span class="sxs-lookup"><span data-stu-id="0743e-116">BTSTask includes the `ImportParties` and `ExportParties` commands</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0743e-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0743e-117">Prerequisites</span></span>

* <span data-ttu-id="0743e-118">Debe haber iniciado sesión con una cuenta que sea miembro de la ** grupo de administradores de servidor BizTalk **.</span><span class="sxs-lookup"><span data-stu-id="0743e-118">You must be logged on with an account that is a member of the** BizTalk Server Administrators** group.</span></span> <span data-ttu-id="0743e-119">Vea [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0743e-119">See [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

* <span data-ttu-id="0743e-120">Debe haber agregado una referencia a la **aplicación EDI de BizTalk** desde una aplicación de BizTalk que se usará como una aplicación de EDI.</span><span class="sxs-lookup"><span data-stu-id="0743e-120">You must have added a reference to the **BizTalk EDI Application** from a BizTalk application that will be used as an EDI application.</span></span> <span data-ttu-id="0743e-121">Vea [pasos posteriores a la configuración](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0743e-121">See [Post-configuration steps](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>

## <a name="import-or-export-all-the-trading-partners"></a><span data-ttu-id="0743e-122">Importar o exportar a todos los socios comerciales</span><span class="sxs-lookup"><span data-stu-id="0743e-122">Import or export all the trading partners</span></span>
1. <span data-ttu-id="0743e-123">Abra  **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** y expanda el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0743e-123">Open **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, and expand the BizTalk group.</span></span>
2. <span data-ttu-id="0743e-124">Haga clic en **partes**y seleccione **exportar**.</span><span class="sxs-lookup"><span data-stu-id="0743e-124">Right-click **Parties**, and select **Export**.</span></span> 

    <span data-ttu-id="0743e-125">Cuando se exportan en el **partes**-nivel, que va a exportar todos los socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="0743e-125">When you export at the **parties**-level, you are exporting all the trading partners.</span></span> <span data-ttu-id="0743e-126">También exporta todos los elementos utilizados por los socios comerciales, incluidos los perfiles de negocio y los contratos en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="0743e-126">This also exports everything used by the trading partners, including business profiles, and agreements into an XML file.</span></span> 

3. <span data-ttu-id="0743e-127">Haga clic en **partes**, seleccione **importación**y seleccione el archivo de enlace XML.</span><span class="sxs-lookup"><span data-stu-id="0743e-127">Right-click **Parties**, select **Import**, and select the binding XML file.</span></span> 

      <span data-ttu-id="0743e-128">Elegir **excluir entidades**, o **excluir la configuración de reserva de EDI** por lo que no se importan.</span><span class="sxs-lookup"><span data-stu-id="0743e-128">Choose to **Exclude Parties**, or **Exclude EDI Fallback Settings** so they are not imported.</span></span> <span data-ttu-id="0743e-129">En caso contrario, todo el contenido del archivo de enlace se importa, incluidos el comercial socios, perfiles de negocio y acuerdos.</span><span class="sxs-lookup"><span data-stu-id="0743e-129">Otherwise, everything in the binding file is imported, including the trading partners, business profiles, and agreements.</span></span>     

### <a name="btstask-example"></a><span data-ttu-id="0743e-130">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="0743e-130">BTSTask example</span></span>

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

<span data-ttu-id="0743e-131">Vea [ImportParties comando](../core/importparties-command.md).</span><span class="sxs-lookup"><span data-stu-id="0743e-131">See [ImportParties command](../core/importparties-command.md).</span></span>

    
## <a name="export-individual-partners"></a><span data-ttu-id="0743e-132">Asociados de negocios individuales de exportación</span><span class="sxs-lookup"><span data-stu-id="0743e-132">Export individual partners</span></span>
1. <span data-ttu-id="0743e-133">En  **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** , seleccione **partes**.</span><span class="sxs-lookup"><span data-stu-id="0743e-133">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, select **Parties**.</span></span>
2. <span data-ttu-id="0743e-134">En el **entidades y perfiles empresariales** panel, haga clic en una entidad y seleccione **exportar**.</span><span class="sxs-lookup"><span data-stu-id="0743e-134">In the **Parties and business profiles** pane, right-click a party, and select **Export**.</span></span>

    <span data-ttu-id="0743e-135">Cuando se exporta una entidad específica, se tiene la opción para exportar todas las entidades y todos los acuerdos utilizados por esa entidad.</span><span class="sxs-lookup"><span data-stu-id="0743e-135">When you export a specific party, you are given the choice to export all the parties, and all the agreements used by that party.</span></span> <span data-ttu-id="0743e-136">Puede desactivar **exportar entidades seleccionados y todos los acuerdos dentro de las entidades seleccionadas** para exportar solo la entidad que seleccione.</span><span class="sxs-lookup"><span data-stu-id="0743e-136">You can uncheck **Export selected parties and all the agreements within the selected parties** to only export the party you select.</span></span>

3. <span data-ttu-id="0743e-137">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0743e-137">Select **OK**.</span></span> 

> [!TIP]
> <span data-ttu-id="0743e-138">En el **entidades y perfiles empresariales** panel, también puede usar el **CTRL** y **MAYÚS** teclas para seleccionar varias entidades en la lista.</span><span class="sxs-lookup"><span data-stu-id="0743e-138">In the **Parties and business profiles** pane, you can also use the **CTRL** and **Shift** keys to select multiple parties in the list.</span></span> <span data-ttu-id="0743e-139">Todas las entidades que seleccione exportación al mismo archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="0743e-139">All of the parties you select export into the same binding file.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="0743e-140">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="0743e-140">BTSTask example</span></span>

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

<span data-ttu-id="0743e-141">Vea [ExportParties comando](../core/exportparties-command.md).</span><span class="sxs-lookup"><span data-stu-id="0743e-141">See [ExportParties command](../core/exportparties-command.md).</span></span>


## <a name="import-application-binding-file"></a><span data-ttu-id="0743e-142">Importar archivo de enlace de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0743e-142">Import application binding file</span></span>

<span data-ttu-id="0743e-143">En el nivel de aplicación, puede importar un archivo de enlace con entidades EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="0743e-143">At the application-level, you can import a binding file with EDI and AS2 parties.</span></span> 

1. <span data-ttu-id="0743e-144">En  **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** , expanda **aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="0743e-144">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expand **Applications**</span></span>
2. <span data-ttu-id="0743e-145">Haga clic en la aplicación y seleccione **importación**.</span><span class="sxs-lookup"><span data-stu-id="0743e-145">Right-click your application, and select **Import**.</span></span>
3. <span data-ttu-id="0743e-146">**Importar la configuración de seguimiento** y **excluir entidades** opciones están disponibles.</span><span class="sxs-lookup"><span data-stu-id="0743e-146">**Import Tracking Settings** and **Exclude Parties** options are available.</span></span> <span data-ttu-id="0743e-147">Usar estas opciones, puede importar cualquier configuración de seguimiento existente o excluir todas las entidades EDI/AS2 en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="0743e-147">Using these options, you can choose to import any existing tracking settings, or exclude any EDI/AS2 parties within the binding file.</span></span>

    | <span data-ttu-id="0743e-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="0743e-148">Setting</span></span> | <span data-ttu-id="0743e-149">Detalles</span><span class="sxs-lookup"><span data-stu-id="0743e-149">Details</span></span> |
    |---|---|
    |<span data-ttu-id="0743e-150">**Importar la configuración del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="0743e-150">**Import Tracking Settings**</span></span> | <span data-ttu-id="0743e-151">Importa la configuración de seguimiento habilitada en los diferentes artefactos dentro de la aplicación, como el seguimiento de partes de mensaje y seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="0743e-151">Imports the tracking settings enabled on the different artifacts within the application, such as track message bodies, and track events.</span></span> <br/><br/><span data-ttu-id="0743e-152">Habilitado de forma predeterminada para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0743e-152">Enabled by default to ensure backwards-compatibility.</span></span> |
    | <span data-ttu-id="0743e-153">**Excluir entidades**</span><span class="sxs-lookup"><span data-stu-id="0743e-153">**Exclude Parties**</span></span>|<span data-ttu-id="0743e-154">Hace no importar entidades, perfiles y acuerdos que existan dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="0743e-154">Does not import parties, profiles, and agreements that existing within the file.</span></span> <br/><br/><span data-ttu-id="0743e-155">Deshabilitada de forma predeterminada para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0743e-155">Disabled by default to ensure backwards-compatibility.</span></span>|

     > [!IMPORTANT] 
     > <span data-ttu-id="0743e-156">Invalida la configuración de seguimiento global **importar la configuración de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="0743e-156">The global tracking settings override **Import Tracking Settings**.</span></span> <span data-ttu-id="0743e-157">Por lo que si ha deshabilitado el seguimiento a nivel global de nivel, cualquier configuración no se importa de seguimiento, aunque **importar la configuración de seguimiento** está activada.</span><span class="sxs-lookup"><span data-stu-id="0743e-157">So if you've disabled tracking at the global level, any tracking settings are not imported, even if **Import Tracking Settings** is checked.</span></span>
     > 
     > <span data-ttu-id="0743e-158">**Panel de configuración de BizTalk, página grupo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explica el **permitir la importación de la configuración del seguimiento** configuración global.</span><span class="sxs-lookup"><span data-stu-id="0743e-158">**BizTalk Settings Dashboard, Group Page** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explains the **Allow import of tracking settings** global setting.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="0743e-159">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="0743e-159">BTSTask example</span></span>

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

<span data-ttu-id="0743e-160">Vea [comando ImportBindings](../core/importbindings-command.md).</span><span class="sxs-lookup"><span data-stu-id="0743e-160">See [ImportBindings command](../core/importbindings-command.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0743e-161">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0743e-161">In this section</span></span>
<span data-ttu-id="0743e-162">Para importar o exportar los archivos de enlace de EDI y AS2 en versiones anteriores de BizTalk, vea:</span><span class="sxs-lookup"><span data-stu-id="0743e-162">To import or export EDI and AS2 binding files on previous BizTalk versions, see:</span></span> 

* [<span data-ttu-id="0743e-163">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="0743e-163">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="0743e-164">Cómo importar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="0743e-164">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
