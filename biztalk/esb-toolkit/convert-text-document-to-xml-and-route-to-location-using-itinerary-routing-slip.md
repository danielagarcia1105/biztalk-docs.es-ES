---
title: 'Cómo: convertir un documento de texto en XML y enrutarlo a una ubicación de archivo con una lista de distribución de itinerarios | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e6690af0cd326853fc0f96254aaaf7083ccd15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982573"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="61dfd-102">Cómo: convertir un documento de texto en XML y enrutarlo a una ubicación de archivo con una lista de distribución de itinerarios</span><span class="sxs-lookup"><span data-stu-id="61dfd-102">How to: Convert a Text Document to XML and Route to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="61dfd-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="61dfd-103">Goal</span></span>  
 <span data-ttu-id="61dfd-104">La sección muestra cómo crear una canalización que convertir un documento de texto en XML y, a continuación, seleccione el itinerario adecuado y enrutar el mensaje a una ubicación de archivo.</span><span class="sxs-lookup"><span data-stu-id="61dfd-104">The section demonstrates how to create a pipeline that will convert a text document to XML and then select the appropriate itinerary and route the message to a FILE location.</span></span>  
  
 <span data-ttu-id="61dfd-105">En este tema de procedimientos, se completará los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="61dfd-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="61dfd-106">Use una canalización para recibir un documento de archivo sin formato y convertirlo a XML.</span><span class="sxs-lookup"><span data-stu-id="61dfd-106">Use a pipeline to receive a flat file document and convert it to XML.</span></span>  
  
-   <span data-ttu-id="61dfd-107">Configurar el componente de canalización de Selector de itinerarios para resolver la lista de distribución adecuada.</span><span class="sxs-lookup"><span data-stu-id="61dfd-107">Configure the Itinerary Selector pipeline component to resolve the appropriate routing slip.</span></span>  
  
-   <span data-ttu-id="61dfd-108">Cree una vía rápida que utiliza la canalización personalizada.</span><span class="sxs-lookup"><span data-stu-id="61dfd-108">Create an on-ramp that uses the custom pipeline.</span></span>  
  
-   <span data-ttu-id="61dfd-109">Probar el enrutamiento basado en itinerarios de un mensaje de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="61dfd-109">Test itinerary-based routing of a flat file message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61dfd-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="61dfd-110">Prerequisites</span></span>  
 <span data-ttu-id="61dfd-111">Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="61dfd-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="61dfd-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="61dfd-112">Before You Begin</span></span>  
 <span data-ttu-id="61dfd-113">Complete las tareas siguientes antes de realizar los pasos más adelante en este tema de procedimientos:</span><span class="sxs-lookup"><span data-stu-id="61dfd-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="61dfd-114">Implementar el **DataFormatTransformation** itinerario.</span><span class="sxs-lookup"><span data-stu-id="61dfd-114">Deploy the **DataFormatTransformation** itinerary.</span></span>  
  
- <span data-ttu-id="61dfd-115">Crear el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="61dfd-115">Create the test message.</span></span>  
  
  <span data-ttu-id="61dfd-116">Los procedimientos siguientes describen cómo realizar cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="61dfd-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a><span data-ttu-id="61dfd-117">Para implementar el itinerario DataFormatTransformation</span><span class="sxs-lookup"><span data-stu-id="61dfd-117">To deploy the DataFormatTransformation itinerary</span></span>  
  
1.  <span data-ttu-id="61dfd-118">En Visual Studio, abra C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span><span class="sxs-lookup"><span data-stu-id="61dfd-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span></span>  
  
2.  <span data-ttu-id="61dfd-119">En el Explorador de soluciones, en el **Itinerary.Library** del proyecto, haga doble clic en **DataFormatTransformation.itinerary** para abrirlo en el Diseñador de itinerario.</span><span class="sxs-lookup"><span data-stu-id="61dfd-119">In Solution Explorer, in the **Itinerary.Library** project, double-click **DataFormatTransformation.itinerary** to open it in the Itinerary Designer.</span></span>  
  
3.  <span data-ttu-id="61dfd-120">En Visual Studio, haga clic en la superficie de diseño de **DataFormatTransformation.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-120">In Visual Studio, click the design surface of **DataFormatTransformation.itinerary**.</span></span> <span data-ttu-id="61dfd-121">En el **DataFormatTransformation.itinerary** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="61dfd-121">In the **DataFormatTransformation.itinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="61dfd-122">En el **estado itinerario** la lista desplegable, haga clic en **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-122">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    2.  <span data-ttu-id="61dfd-123">En el **modelo exportador** la lista desplegable, haga clic en **exportador de base de datos de itinerario**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-123">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="61dfd-124">Haga clic en el botón de puntos suspensivos (...) junto a la **Itinerary Database** propiedad.</span><span class="sxs-lookup"><span data-stu-id="61dfd-124">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    4.  <span data-ttu-id="61dfd-125">En el **las propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de itinerario del repositorio y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).</span><span class="sxs-lookup"><span data-stu-id="61dfd-125">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
4.  <span data-ttu-id="61dfd-126">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="61dfd-126">Save all project artifacts.</span></span>  
  
5.  <span data-ttu-id="61dfd-127">En Visual Studio, haga clic en la superficie de diseño de la **DataModelTransformation** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-127">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-create-the-receive-pipeline"></a><span data-ttu-id="61dfd-128">Para crear la canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="61dfd-128">To create the receive pipeline</span></span>  
  
1.  <span data-ttu-id="61dfd-129">En Visual Studio, haga clic en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-129">In Visual Studio, right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="61dfd-130">Haga clic en **aplicación**y, a continuación, escriba **GlobalBank.ESB.DataFormatTransformation.Schemas** en el **nombre del ensamblado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="61dfd-130">Click **Application**, and then type **GlobalBank.ESB.DataFormatTransformation.Schemas** in the **Assembly name** box.</span></span>  
  
2.  <span data-ttu-id="61dfd-131">Haga clic en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-131">Right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="61dfd-132">Haga clic en **firma**y, a continuación, compruebe que la **firmar el ensamblado** casilla está activada y que señala la ubicación del ensamblado **.\\... \\.. \\.. \\.. \\.. \keys\Microsoft.Practices.ESB.snk**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-132">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **.\\..\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
3.  <span data-ttu-id="61dfd-133">Haga clic en **DataFormatTransformation.Pipelines**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-133">Right-click **DataFormatTransformation.Pipelines**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="61dfd-134">Haga clic en **DataFormatTransformation**, apunte a **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-134">Right-click **DataFormatTransformation**, point to **Add**, and then click **New Project**.</span></span> <span data-ttu-id="61dfd-135">Haga clic en **proyectos de Biztalk**y, a continuación, haga clic en **proyecto vacío de servidor Biztalk**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-135">Click **Biztalk Projects**, and then click **Empty Biztalk Server Project**.</span></span> <span data-ttu-id="61dfd-136">En el **nombre** , escriba **DataFormatTransformationReceive.Pipeline**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-136">In the **Name** box, type **DataFormatTransformationReceive.Pipeline**.</span></span>  
  
5.  <span data-ttu-id="61dfd-137">Haga clic en **DataFormatTransformationReceive.Pipeline**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-137">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="61dfd-138">Haga clic en **firma**y, a continuación, compruebe que la **firmar el ensamblado** casilla está activada y que señala la ubicación del ensamblado **C:\projects\Microsoft.Practices.ESB\keys\ Microsoft.Practices.ESB.snk**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-138">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
6.  <span data-ttu-id="61dfd-139">Haga clic en **DataFormatTransformationReceive.Pipeline**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-139">Right-click **DataFormatTransformationReceive.Pipeline**, point to **Add**, and then click **New Item**.</span></span>  
  
7.  <span data-ttu-id="61dfd-140">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **canalización de recepción** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="61dfd-140">In the **Add New Item** dialog box, click **Receive Pipeline** in the Templates pane.</span></span> <span data-ttu-id="61dfd-141">En el **nombre** , escriba **ItinerarySelectReceiveFF**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-141">In the **Name** box, type **ItinerarySelectReceiveFF**, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="61dfd-142">Haga clic en **referencias** para el proyecto DataFormatTransformationReceive.Pipeline y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-142">Right-click **References** for the DataFormatTransformationReceive.Pipeline project, and then click **Add Reference**.</span></span> <span data-ttu-id="61dfd-143">Haga clic en el **proyectos** pestaña y, a continuación, haga clic en **DataFormatTransformation.Schemas**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-143">Click the **Projects** tab, and then click **DataFormatTransformation.Schemas**.</span></span> <span data-ttu-id="61dfd-144">Haga clic en **Aceptar** para agregar la referencia.</span><span class="sxs-lookup"><span data-stu-id="61dfd-144">Click **OK** to add the reference.</span></span>  
  
9. <span data-ttu-id="61dfd-145">En el cuadro de herramientas, arrastre un **Desensamblador de archivos** componente de canalización para la **desensamblar** fase de la canalización.</span><span class="sxs-lookup"><span data-stu-id="61dfd-145">From the Toolbox, drag a **Flat file disassembler** pipeline component to the **Disassemble** stage of the pipeline.</span></span>  
  
10. <span data-ttu-id="61dfd-146">En la ventana de propiedades del archivo plano de desensamblado, haga clic en **DataModelTransformation.Schemas.NAOrderDocFF** en el **esquema de documento** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="61dfd-146">In the Properties window for the flat file disassemble, click **DataModelTransformation.Schemas.NAOrderDocFF** in the **Document schema** drop-down list.</span></span>  
  
11. <span data-ttu-id="61dfd-147">En el cuadro de herramientas, arrastre un **Selector de itinerarios de ESB** componente de canalización para la **resolver entidad** fase de la canalización.</span><span class="sxs-lookup"><span data-stu-id="61dfd-147">From the Toolbox, drag an **ESB Itinerary Selector** pipeline component to the **Resolve Party** stage of the pipeline.</span></span>  
  
12. <span data-ttu-id="61dfd-148">En el cuadro de herramientas, arrastre un **distribuidor de ESB** componente de canalización para la **resolver entidad** fase de la canalización y, a continuación, colóquelo bajo el **Selector de itinerarios de ESB** canalización componente.</span><span class="sxs-lookup"><span data-stu-id="61dfd-148">From the Toolbox, drag an **ESB Dispatcher** pipeline component to the **Resolve Party** stage of the pipeline, and then place it under the **ESB Itinerary Selector** pipeline component.</span></span>  
  
13. <span data-ttu-id="61dfd-149">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="61dfd-149">Save all project artifacts.</span></span>  
  
## <a name="to-create-the-test-message"></a><span data-ttu-id="61dfd-150">Para crear el mensaje de prueba</span><span class="sxs-lookup"><span data-stu-id="61dfd-150">To create the test message</span></span>  
  
1.  <span data-ttu-id="61dfd-151">Haga clic una vez en el archivo de esquema NAOrderDocFF.xsd del proyecto DataFormatTransformation.Schemas.</span><span class="sxs-lookup"><span data-stu-id="61dfd-151">Click once in the NAOrderDocFF.xsd schema file of the DataFormatTransformation.Schemas project.</span></span> <span data-ttu-id="61dfd-152">En el panel de propiedades de Visual Studio, cambie las dos propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="61dfd-152">In the Properties pane of Visual Studio, change the following two properties:</span></span>  
  
    -   <span data-ttu-id="61dfd-153">**Genere el tipo de salida de instancia**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-153">**Generate Instance Output Type**.</span></span> <span data-ttu-id="61dfd-154">Haga clic en la lista desplegable Cambiar a esta propiedad **nativo**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-154">Click the drop-down list for this property to change it to **Native**.</span></span>  
  
    -   <span data-ttu-id="61dfd-155">**Nombre de archivo de instancia de salida**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-155">**Output Instance Filename**.</span></span> <span data-ttu-id="61dfd-156">Haga clic en el botón de puntos suspensivos (...) para esta propiedad y acepte la ruta de acceso predeterminada de C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span><span class="sxs-lookup"><span data-stu-id="61dfd-156">Click the ellipsis button (…) for this property and accept the default path of C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span></span> <span data-ttu-id="61dfd-157">En el **nombre de archivo** , escriba **NAOrderDocFF**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-157">In the **File name** box, type **NAOrderDocFF**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="61dfd-158">Haga clic en **NAOrderDocFF.xsd** en **DataFormatTransformation.Schemas**y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-158">Right-click **NAOrderDocFF.xsd** under **DataFormatTransformation.Schemas**, and then click **Generate Instance**.</span></span> <span data-ttu-id="61dfd-159">En este momento, debe tener un nuevo archivo que se genera en el directorio C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span><span class="sxs-lookup"><span data-stu-id="61dfd-159">At this point, you should have a new file generated in the C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation directory.</span></span>  
  
3.  <span data-ttu-id="61dfd-160">Copia (sin mover) el archivo NAOrderDocFF.txt desde C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="61dfd-160">Copy (do not move) the file NAOrderDocFF.txt from C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation to C:\HowTos.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61dfd-161">Este es el mensaje que recibirá y la convierte a XML.</span><span class="sxs-lookup"><span data-stu-id="61dfd-161">This is the message you will receive and convert to XML.</span></span> <span data-ttu-id="61dfd-162">En este documento representa una versión de archivo sin formato de documento de pedido de América del Norte.</span><span class="sxs-lookup"><span data-stu-id="61dfd-162">This document represents a flat file version of North American Order document.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="61dfd-163">Pasos</span><span class="sxs-lookup"><span data-stu-id="61dfd-163">Steps</span></span>  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a><span data-ttu-id="61dfd-164">Para implementar la canalización de recepción y el esquema</span><span class="sxs-lookup"><span data-stu-id="61dfd-164">To deploy the receive pipeline and the schema</span></span>  
  
1.  <span data-ttu-id="61dfd-165">Haga clic en **DataFormatTransformationReceive.Pipeline**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-165">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="61dfd-166">Haga clic en **implementación**y, a continuación, escriba **Microsoft.Practices.ESB** en el **nombre de la aplicación** cuadro.</span><span class="sxs-lookup"><span data-stu-id="61dfd-166">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
2.  <span data-ttu-id="61dfd-167">Haga clic en el **DataFormatTransformation.Schemas** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-167">Right-click the **DataFormatTransformation.Schemas** project, and then click **Properties**.</span></span> <span data-ttu-id="61dfd-168">Haga clic en **implementación**y, a continuación, escriba **Microsoft.Practices.ESB** en el **nombre de la aplicación** cuadro.</span><span class="sxs-lookup"><span data-stu-id="61dfd-168">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
3.  <span data-ttu-id="61dfd-169">Cerrar los paneles de propiedades para ambos **DataFormatTransformationReceive.Pipeline** y **DataFormatTransformation.Schemas**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-169">Close the Properties panes for both **DataFormatTransformationReceive.Pipeline** and **DataFormatTransformation.Schemas**.</span></span>  
  
4.  <span data-ttu-id="61dfd-170">En el Explorador de soluciones, haga clic en el **DataFormatTransformation** del proyecto y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-170">In Solution Explorer, right-click the **DataFormatTransformation** project, and then click **Deploy Solution**.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="61dfd-171">Para crear y configurar una rampa de ESB</span><span class="sxs-lookup"><span data-stu-id="61dfd-171">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="61dfd-172">Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-172">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="61dfd-173">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-173">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then click **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="61dfd-174">Haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-174">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="61dfd-175">En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-175">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="61dfd-176">En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba **OnRamp.Itinerary.FlatFile.FILE**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-176">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.FlatFile.FILE**.</span></span>  
  
6.  <span data-ttu-id="61dfd-177">En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-177">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="61dfd-178">En el **propiedades de transporte de archivo** cuadro de diálogo el **carpetas de recepción** , escriba **C:\HowTos\DropFolder**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-178">In the **FILE Transport Properties** dialog box, in the **Receive Folder** box, type **C:\HowTos\DropFolder**.</span></span>  
  
8.  <span data-ttu-id="61dfd-179">En el **propiedades de transporte de archivo** cuadro de diálogo el **máscara de archivo** , escriba  **\*.txt**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-179">In the **FILE Transport Properties** dialog box, in the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="61dfd-180">Para configurar el componente de canalización de Selector de itinerarios</span><span class="sxs-lookup"><span data-stu-id="61dfd-180">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="61dfd-181">En el **propiedades de ubicación de recepción** cuadro de diálogo, haga clic en **ItinerarySelectReceiveFF** en el **canalización de recepción** lista desplegable y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="61dfd-181">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveFF** in the **Receive pipeline** drop down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="61dfd-182">Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **itinerario Selector** propiedades de componente:</span><span class="sxs-lookup"><span data-stu-id="61dfd-182">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="61dfd-183">Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-183">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="61dfd-184">Haga clic en el **ResolverConnectionString** propiedad, tipo **itinerario:\\\name=DataFormatTransformation;** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-184">Click the **ResolverConnectionString** property, type **ITINERARY:\\\name=DataFormatTransformation;** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="61dfd-185">Haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61dfd-185">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="61dfd-186">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.FlatFile.FILE** ubicación de recepción y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-186">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a><span data-ttu-id="61dfd-187">Para probar el enrutamiento basado en itinerarios de un mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="61dfd-187">To test itinerary-based routing of a flat file message</span></span>  
  
1.  <span data-ttu-id="61dfd-188">En el Explorador de Windows, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="61dfd-188">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="61dfd-189">Copia (no se mueven) NAOrderDocFF.txt a C:\HowTos\DropFolder.</span><span class="sxs-lookup"><span data-stu-id="61dfd-189">Copy (do not move) NAOrderDocFF.txt to C:\HowTos\DropFolder.</span></span>  
  
3.  <span data-ttu-id="61dfd-190">Vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje DFT%MessageID%.xml en el directorio.</span><span class="sxs-lookup"><span data-stu-id="61dfd-190">Browse to C:\HowTos\Out. Verify that the DFT%MessageID%.xml message has been written to the directory.</span></span>  
  
4.  <span data-ttu-id="61dfd-191">En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.FlatFile.FILE** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-191">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="61dfd-192">Después de la **OnRamp.Itinerary.FlatFile.FILE** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-192">After the **OnRamp.Itinerary.FlatFile.FILE** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="61dfd-193">En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="61dfd-193">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="61dfd-194">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="61dfd-194">Additional Resources</span></span>  
 <span data-ttu-id="61dfd-195">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="61dfd-195">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="61dfd-196">Cómo: Transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución de itinerarios</span><span class="sxs-lookup"><span data-stu-id="61dfd-196">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="61dfd-197">Cómo: Enrutar un solo mensaje a varios destinatarios mediante una lista de distribución de itinerarios</span><span class="sxs-lookup"><span data-stu-id="61dfd-197">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [<span data-ttu-id="61dfd-198">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="61dfd-198">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="61dfd-199">Patrones de transformación de mensajes</span><span class="sxs-lookup"><span data-stu-id="61dfd-199">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)