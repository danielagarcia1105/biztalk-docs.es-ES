---
title: Usar archivos de enlace para importar o exportar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ed0f50d6a6d841169b16f3f3ffd485ee345aeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990597"
---
# <a name="use-binding-files-to-import-or-export"></a><span data-ttu-id="25849-102">Usar archivos de enlace para importar o exportar</span><span class="sxs-lookup"><span data-stu-id="25849-102">Use binding files to import or export</span></span>

<span data-ttu-id="25849-103">A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede exportar e importar archivos de enlace en el **partes** y **acuerdo** niveles.</span><span class="sxs-lookup"><span data-stu-id="25849-103">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can export and import binding files at the **Parties** and **Agreement** levels.</span></span> <span data-ttu-id="25849-104">Para versiones anteriores de BizTalk, exportar en el nivel de aplicación, como se describe en:</span><span class="sxs-lookup"><span data-stu-id="25849-104">For previous BizTalk versions, you export at the application level, as described at:</span></span> 

* [<span data-ttu-id="25849-105">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="25849-105">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="25849-106">Cómo importar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="25849-106">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

<span data-ttu-id="25849-107">En este tema se muestra cómo importar y exporta las partes, sus perfiles, contratos, configuración de reserva y utilizando más [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] y BTSTask.</span><span class="sxs-lookup"><span data-stu-id="25849-107">This topic shows you how to import and exports parties, their profiles, agreements, fallback settings, and more using [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] and BTSTask.</span></span> 

## <a name="overview"></a><span data-ttu-id="25849-108">Información general</span><span class="sxs-lookup"><span data-stu-id="25849-108">Overview</span></span>

<span data-ttu-id="25849-109">Algunas de las características de importación y exportación incluyen:</span><span class="sxs-lookup"><span data-stu-id="25849-109">Some of the import and export features include:</span></span>

* <span data-ttu-id="25849-110">Importar entidades, perfiles de negocio y contratos desde un archivo de enlace XML</span><span class="sxs-lookup"><span data-stu-id="25849-110">Import parties, business profiles, and agreements from an XML binding file</span></span>
* <span data-ttu-id="25849-111">Exportar entidades, perfiles de negocio, acuerdos y configuración de reserva de EDI en un archivo de enlace XML</span><span class="sxs-lookup"><span data-stu-id="25849-111">Export parties, business profiles, agreements, and EDI fallback settings to an XML binding file</span></span>
* <span data-ttu-id="25849-112">Al importar un archivo de enlace, puede decidir no importar las partes, o la configuración de reserva</span><span class="sxs-lookup"><span data-stu-id="25849-112">When importing a binding file, you can chose to not import the parties, or the fallback settings</span></span>
* <span data-ttu-id="25849-113">Cuando se importan en el nivel de entidades, se importan solo las entidades y contratos en el archivo de enlace</span><span class="sxs-lookup"><span data-stu-id="25849-113">When importing at the Parties-level, only the parties and agreements within the binding file are imported</span></span>
* <span data-ttu-id="25849-114">Exportar entidades específicas en el mismo archivo de enlace y optar por exportar también todos los contratos asociados con dichos terceros</span><span class="sxs-lookup"><span data-stu-id="25849-114">Export specific parties to the same binding file, and choose to also export all the agreements associated with those parties</span></span>
* <span data-ttu-id="25849-115">El Asistente Importar aplicación de enlace le permite elegir importar la configuración de seguimiento o excluir las entidades.</span><span class="sxs-lookup"><span data-stu-id="25849-115">The application import binding wizard lets you choose to import the tracking settings, or exclude the parties.</span></span>
* <span data-ttu-id="25849-116">BTSTask incluye la `ImportParties` y `ExportParties` comandos</span><span class="sxs-lookup"><span data-stu-id="25849-116">BTSTask includes the `ImportParties` and `ExportParties` commands</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="25849-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="25849-117">Prerequisites</span></span>

* <span data-ttu-id="25849-118">Debe haber iniciado sesión con una cuenta que sea miembro de la ** grupo de administradores de servidor BizTalk **.</span><span class="sxs-lookup"><span data-stu-id="25849-118">You must be logged on with an account that is a member of the** BizTalk Server Administrators** group.</span></span> <span data-ttu-id="25849-119">Consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="25849-119">See [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

* <span data-ttu-id="25849-120">Debe haber agregado una referencia a la **aplicación EDI de BizTalk** desde una aplicación de BizTalk que se usará como una aplicación de EDI.</span><span class="sxs-lookup"><span data-stu-id="25849-120">You must have added a reference to the **BizTalk EDI Application** from a BizTalk application that will be used as an EDI application.</span></span> <span data-ttu-id="25849-121">Consulte [pasos posteriores a la configuración](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="25849-121">See [Post-configuration steps](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>

## <a name="import-or-export-all-the-trading-partners"></a><span data-ttu-id="25849-122">Importar o exportar a todos los socios comerciales</span><span class="sxs-lookup"><span data-stu-id="25849-122">Import or export all the trading partners</span></span>
1. <span data-ttu-id="25849-123">Abra **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** y expanda el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25849-123">Open **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, and expand the BizTalk group.</span></span>
2. <span data-ttu-id="25849-124">Haga clic en **partes**y seleccione **exportar**.</span><span class="sxs-lookup"><span data-stu-id="25849-124">Right-click **Parties**, and select **Export**.</span></span> 

    <span data-ttu-id="25849-125">Cuando se exportan en el **partes**-nivel, que va a exportar todos los socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="25849-125">When you export at the **parties**-level, you are exporting all the trading partners.</span></span> <span data-ttu-id="25849-126">Esto también exporta todos los elementos utilizados por los socios comerciales, incluidos perfiles de negocio y los contratos en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="25849-126">This also exports everything used by the trading partners, including business profiles, and agreements into an XML file.</span></span> 

3. <span data-ttu-id="25849-127">Haga clic en **partes**, seleccione **importación**y seleccione el archivo XML de enlace.</span><span class="sxs-lookup"><span data-stu-id="25849-127">Right-click **Parties**, select **Import**, and select the binding XML file.</span></span> 

      <span data-ttu-id="25849-128">Elegir **excluir partes**, o **excluir la configuración de reserva de EDI** por lo que no se importan.</span><span class="sxs-lookup"><span data-stu-id="25849-128">Choose to **Exclude Parties**, or **Exclude EDI Fallback Settings** so they are not imported.</span></span> <span data-ttu-id="25849-129">En caso contrario, todo el contenido del archivo de enlace se importa, incluidos los socios, perfiles de negocio y acuerdos comerciales.</span><span class="sxs-lookup"><span data-stu-id="25849-129">Otherwise, everything in the binding file is imported, including the trading partners, business profiles, and agreements.</span></span>     

### <a name="btstask-example"></a><span data-ttu-id="25849-130">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="25849-130">BTSTask example</span></span>

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

<span data-ttu-id="25849-131">Consulte [ImportParties (comando)](../core/importparties-command.md).</span><span class="sxs-lookup"><span data-stu-id="25849-131">See [ImportParties command](../core/importparties-command.md).</span></span>

    
## <a name="export-individual-partners"></a><span data-ttu-id="25849-132">Exportar individuales asociados</span><span class="sxs-lookup"><span data-stu-id="25849-132">Export individual partners</span></span>
1. <span data-ttu-id="25849-133">En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, seleccione **partes**.</span><span class="sxs-lookup"><span data-stu-id="25849-133">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, select **Parties**.</span></span>
2. <span data-ttu-id="25849-134">En el **entidades y perfiles empresariales** panel, haga clic en una entidad y seleccione **exportar**.</span><span class="sxs-lookup"><span data-stu-id="25849-134">In the **Parties and business profiles** pane, right-click a party, and select **Export**.</span></span>

    <span data-ttu-id="25849-135">Al exportar una entidad específica, tiene la opción para exportar todas las entidades y todos los acuerdos utilizados por esa entidad.</span><span class="sxs-lookup"><span data-stu-id="25849-135">When you export a specific party, you are given the choice to export all the parties, and all the agreements used by that party.</span></span> <span data-ttu-id="25849-136">Puede desactivar **exportar entidades seleccionadas y todos los acuerdos dentro de las partes seleccionadas** para exportar sólo la entidad que seleccione.</span><span class="sxs-lookup"><span data-stu-id="25849-136">You can uncheck **Export selected parties and all the agreements within the selected parties** to only export the party you select.</span></span>

3. <span data-ttu-id="25849-137">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25849-137">Select **OK**.</span></span> 

> [!TIP]
> <span data-ttu-id="25849-138">En el **entidades y perfiles empresariales** panel, también puede usar el **CTRL** y **MAYÚS** teclas para seleccionar varias entidades en la lista.</span><span class="sxs-lookup"><span data-stu-id="25849-138">In the **Parties and business profiles** pane, you can also use the **CTRL** and **Shift** keys to select multiple parties in the list.</span></span> <span data-ttu-id="25849-139">Todas las entidades que seleccione exportación en el mismo archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="25849-139">All of the parties you select export into the same binding file.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="25849-140">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="25849-140">BTSTask example</span></span>

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

<span data-ttu-id="25849-141">Consulte [ExportParties (comando)](../core/exportparties-command.md).</span><span class="sxs-lookup"><span data-stu-id="25849-141">See [ExportParties command](../core/exportparties-command.md).</span></span>


## <a name="import-application-binding-file"></a><span data-ttu-id="25849-142">Importar archivo de enlace de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="25849-142">Import application binding file</span></span>

<span data-ttu-id="25849-143">En el nivel de aplicación, puede importar un archivo de enlace con entidades de EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="25849-143">At the application-level, you can import a binding file with EDI and AS2 parties.</span></span> 

1. <span data-ttu-id="25849-144">En **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expanda **aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="25849-144">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expand **Applications**</span></span>
2. <span data-ttu-id="25849-145">Haga clic en la aplicación y seleccione **importación**.</span><span class="sxs-lookup"><span data-stu-id="25849-145">Right-click your application, and select **Import**.</span></span>
3. <span data-ttu-id="25849-146">**Importar la configuración de seguimiento** y **excluir partes** opciones están disponibles.</span><span class="sxs-lookup"><span data-stu-id="25849-146">**Import Tracking Settings** and **Exclude Parties** options are available.</span></span> <span data-ttu-id="25849-147">Con estas opciones, puede elegir importar ninguna configuración de seguimiento existente o excluir todas las entidades EDI y AS2 en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="25849-147">Using these options, you can choose to import any existing tracking settings, or exclude any EDI/AS2 parties within the binding file.</span></span>

    | <span data-ttu-id="25849-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="25849-148">Setting</span></span> | <span data-ttu-id="25849-149">Detalles</span><span class="sxs-lookup"><span data-stu-id="25849-149">Details</span></span> |
    |---|---|
    |<span data-ttu-id="25849-150">**Importar la configuración del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="25849-150">**Import Tracking Settings**</span></span> | <span data-ttu-id="25849-151">Importa la configuración de seguimiento habilitada en los diferentes artefactos dentro de la aplicación, como el seguimiento de partes de mensaje y seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="25849-151">Imports the tracking settings enabled on the different artifacts within the application, such as track message bodies, and track events.</span></span> <br/><br/><span data-ttu-id="25849-152">Habilitado de forma predeterminada para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="25849-152">Enabled by default to ensure backwards-compatibility.</span></span> |
    | <span data-ttu-id="25849-153">**Excluir entidades**</span><span class="sxs-lookup"><span data-stu-id="25849-153">**Exclude Parties**</span></span>|<span data-ttu-id="25849-154">Hace no importar entidades, perfiles y los acuerdos que existan dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="25849-154">Does not import parties, profiles, and agreements that existing within the file.</span></span> <br/><br/><span data-ttu-id="25849-155">Deshabilitada de forma predeterminada para garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="25849-155">Disabled by default to ensure backwards-compatibility.</span></span>|

   > [!IMPORTANT]
   > <span data-ttu-id="25849-156">Invalida la configuración de seguimiento global **importar la configuración de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="25849-156">The global tracking settings override **Import Tracking Settings**.</span></span> <span data-ttu-id="25849-157">Por lo que si ha deshabilitado el seguimiento a nivel global de nivel, cualquier configuración no se importa de seguimiento, incluso si **importar la configuración de seguimiento** está activada.</span><span class="sxs-lookup"><span data-stu-id="25849-157">So if you've disabled tracking at the global level, any tracking settings are not imported, even if **Import Tracking Settings** is checked.</span></span>
   > 
   > <span data-ttu-id="25849-158">**Panel de configuración de BizTalk, página grupo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explica la **Permitir importar configuración seguimiento** configuración global.</span><span class="sxs-lookup"><span data-stu-id="25849-158">**BizTalk Settings Dashboard, Group Page** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explains the **Allow import of tracking settings** global setting.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="25849-159">Ejemplo de BTSTask</span><span class="sxs-lookup"><span data-stu-id="25849-159">BTSTask example</span></span>

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

<span data-ttu-id="25849-160">Consulte [ImportBindings (comando)](../core/importbindings-command.md).</span><span class="sxs-lookup"><span data-stu-id="25849-160">See [ImportBindings command](../core/importbindings-command.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="25849-161">En esta sección</span><span class="sxs-lookup"><span data-stu-id="25849-161">In this section</span></span>
<span data-ttu-id="25849-162">Para importar o exportar los archivos de enlace de EDI y AS2 en versiones anteriores de BizTalk, consulte:</span><span class="sxs-lookup"><span data-stu-id="25849-162">To import or export EDI and AS2 binding files on previous BizTalk versions, see:</span></span> 

* [<span data-ttu-id="25849-163">Cómo exportar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="25849-163">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="25849-164">Cómo importar enlaces para una solución EDI y AS2</span><span class="sxs-lookup"><span data-stu-id="25849-164">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
