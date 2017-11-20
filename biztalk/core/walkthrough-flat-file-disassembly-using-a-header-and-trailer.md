---
title: 'Tutorial: Desensamblador de archivos sin formato con un encabezado y finalizador | Documentos de Microsoft'
description: "Use el Asistente para esquemas de archivo sin formato para crear un esquema de encabezado, el esquema de finalizador y el esquema de cuerpo y, a continuación, desensamblar un archivo sin formato de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715af9cc-d718-483d-b593-64462aa5a58b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e49014ac4c15f1fd303b2646c74f11b5242aed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-flat-file-disassembly-using-a-header-and-trailer"></a><span data-ttu-id="7f059-103">Tutorial: Desensamblador de archivos sin formato con un encabezado y finalizador</span><span class="sxs-lookup"><span data-stu-id="7f059-103">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>

## <a name="overview"></a><span data-ttu-id="7f059-104">Información general</span><span class="sxs-lookup"><span data-stu-id="7f059-104">Overview</span></span>
<span data-ttu-id="7f059-105">En este tutorial se muestra el uso de esquemas creados por el Asistente para esquema de archivo sin formato a fin de llevar a cabo el desensamblado de un archivo con un encabezado, un finalizador y un cuerpo de mensaje repetido.</span><span class="sxs-lookup"><span data-stu-id="7f059-105">This walkthrough demonstrates the use of schemas created by the Flat File Schema Wizard to perform flat file disassembly of a file containing a header, a trailer, and a repeating message body.</span></span> <span data-ttu-id="7f059-106">En este tutorial se desarrollará parte de un sistema de seguimiento de errores ficticio que cumple con los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="7f059-106">In this walkthrough, you develop part of a fictitious error-tracking system that meets the following requirements:</span></span>  
  
-   <span data-ttu-id="7f059-107">Los mensajes de error se registran en varias ubicaciones físicas de la compañía y se envían a una ubicación central para su procesamiento en varios sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="7f059-107">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
-   <span data-ttu-id="7f059-108">Los mensajes de error se escriben en el formato de archivo sin formato que contiene un encabezado que indica la ubicación, un cuerpo que contiene uno o varios mensajes y un finalizador que indica el número de lote.</span><span class="sxs-lookup"><span data-stu-id="7f059-108">Error messages are written into a flat file format that contains a header indicating location, a body containing one or more error messages, and a trailer indicating the batch number.</span></span>  
  
-   <span data-ttu-id="7f059-109">Los mensajes se consideran no válidos si no tienen un encabezado, un cuerpo y un finalizador.</span><span class="sxs-lookup"><span data-stu-id="7f059-109">Messages are considered invalid if they do not have a header, body, and trailer.</span></span>  
  
 <span data-ttu-id="7f059-110">Cuando se completa un tutorial, es preciso disponer de una aplicación de BizTalk Server que procese archivos sin formatos y los escriba como XML para que lo procese un sistema de servidor.</span><span class="sxs-lookup"><span data-stu-id="7f059-110">When the walkthrough is completed you will have a BizTalk Server application that processes flat files and writes them out as XML for processing by a back-end system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7f059-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7f059-111">Prerequisites</span></span>  
 <span data-ttu-id="7f059-112">Para este ejemplo, es preciso saber desenvolverse con la creación de proyectos de BizTalk Server, la firma de un ensamblado y el uso de la consola de administración de BizTalk Server para ver aplicaciones y puertos.</span><span class="sxs-lookup"><span data-stu-id="7f059-112">For this example you need to be comfortable with creating BizTalk Server projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="7f059-113">También debe estar familiarizado con las ideas presentadas en [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="7f059-113">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span> <span data-ttu-id="7f059-114">También resultará de utilidad cierta familiaridad de nivel básico con el Asistente para esquemas de archivo sin formato, aunque no constituye un requisito necesario.</span><span class="sxs-lookup"><span data-stu-id="7f059-114">Basic familiarity with the Flat File Schema Wizard is also helpful but not required.</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="7f059-115">Qué se hace en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f059-115">What This Example Does</span></span>  
 <span data-ttu-id="7f059-116">En este ejemplo, se procesan mensajes de archivo sin formato de entrada mediante una canalización personalizada y el componente Desensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="7f059-116">This example processes inbound flat file messages using a custom pipeline and the Flat File Disassembler component.</span></span> <span data-ttu-id="7f059-117">Los mensajes se analizan mediante esquemas de cuerpo, finalizador y encabezado y, seguidamente, se escriben en una ubicación de envío para el procesamiento de servidor.</span><span class="sxs-lookup"><span data-stu-id="7f059-117">Messages are parsed using header, trailer, and body schemas and then written out to a send location for back-end processing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f059-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f059-118">Example</span></span>  
 <span data-ttu-id="7f059-119">Para crear el ejemplo, siga los pasos que se especifican en las secciones que se presentan a continuación.</span><span class="sxs-lookup"><span data-stu-id="7f059-119">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="7f059-120">Cree un nuevo proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7f059-120">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="7f059-121">Antes de generar una solución, es preciso crear un proyecto de BizTalk, asegurarse de que se le ha asignado un nombre seguro y un nombre de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f059-121">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="7f059-122">La asignación de un nombre de aplicación evita que BizTalk Server implemente la solución en la aplicación de BizTalk predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f059-122">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
1.  <span data-ttu-id="7f059-123">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7f059-123">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="7f059-124">Asigne al proyecto el **FFDisassemblerWalkthrough**.</span><span class="sxs-lookup"><span data-stu-id="7f059-124">Call the project **FFDisassemblerWalkthrough**.</span></span>  
  
2.  <span data-ttu-id="7f059-125">Genere un archivo de clave y asígnelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-125">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="7f059-126">Para obtener más información acerca de esta tarea, vea [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).</span><span class="sxs-lookup"><span data-stu-id="7f059-126">For more information about this task, see [Signing Page, Project Designer](http://go.microsoft.com/fwlink/?LinkId=125876).</span></span>  
  
3.  <span data-ttu-id="7f059-127">En las propiedades de implementación para el proyecto, establezca **nombre de la aplicación** en "FlatFileExample" y establezca **reiniciar instancias de Host** a `True`.</span><span class="sxs-lookup"><span data-stu-id="7f059-127">In the deployment properties for the project, set **Application Name** to “FlatFileExample” and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="7f059-128">Al definir esta marca, se ordena al host que borre todas las instancias del ensamblado almacenadas en caché.</span><span class="sxs-lookup"><span data-stu-id="7f059-128">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-sample-data-file"></a><span data-ttu-id="7f059-129">Crear el archivo de datos del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f059-129">Create the Sample Data File</span></span>  
<span data-ttu-id="7f059-130">Antes de generar esquemas, es necesario crear un archivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="7f059-130">Before generating schemas, you need to create a test file.</span></span>   
  
1.  <span data-ttu-id="7f059-131">Inicie Bloc de notas u otro procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="7f059-131">Start Notepad or another text editor.</span></span>  
  
2.  <span data-ttu-id="7f059-132">Crear un archivo de prueba de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f059-132">Create a sample test file.</span></span> <span data-ttu-id="7f059-133">El archivo consta de un encabezado que indica la ubicación que informa de los errores, un finalizador con un Id. para este lote y un cuerpo compuesto de uno o varios registros de errores.</span><span class="sxs-lookup"><span data-stu-id="7f059-133">The file consists of a header indicating the location reporting the error(s), a trailer with a batch ID for this batch, and a body consisting of one or more error records.</span></span> <span data-ttu-id="7f059-134">El formato del archivo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f059-134">The format of the file is as follows:</span></span>  
  
    ```  
    Location  
    ERRORid|type|priority|description|errorDateTime  
    …additional error records   
    BatchID  
    ```  
  
    <span data-ttu-id="7f059-135">El registro de ERROR está etiquetado con el texto "ERROR" y delimitado por el "&#124;" carácter (frente al caso posicional).</span><span class="sxs-lookup"><span data-stu-id="7f059-135">The ERROR record is tagged with the text “ERROR” and delimited with the “&#124;” character (versus positional).</span></span> <span data-ttu-id="7f059-136">Los elementos de datos del registro ERROR se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="7f059-136">The data elements of the ERROR record are described in the following table.</span></span>  
  
    |<span data-ttu-id="7f059-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f059-137">Element</span></span>|<span data-ttu-id="7f059-138">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7f059-138">Data type</span></span>|<span data-ttu-id="7f059-139">Description</span><span class="sxs-lookup"><span data-stu-id="7f059-139">Description</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="7f059-140">ID</span><span class="sxs-lookup"><span data-stu-id="7f059-140">ID</span></span>|<span data-ttu-id="7f059-141">integer</span><span class="sxs-lookup"><span data-stu-id="7f059-141">integer</span></span>|<span data-ttu-id="7f059-142">ID de este error.</span><span class="sxs-lookup"><span data-stu-id="7f059-142">ID for this error.</span></span>|  
    |<span data-ttu-id="7f059-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="7f059-143">Type</span></span>|<span data-ttu-id="7f059-144">integer</span><span class="sxs-lookup"><span data-stu-id="7f059-144">integer</span></span>|<span data-ttu-id="7f059-145">Tipo de error.</span><span class="sxs-lookup"><span data-stu-id="7f059-145">Type of error.</span></span>|  
    |<span data-ttu-id="7f059-146">Prioridad</span><span class="sxs-lookup"><span data-stu-id="7f059-146">Priority</span></span>|<span data-ttu-id="7f059-147">string</span><span class="sxs-lookup"><span data-stu-id="7f059-147">string</span></span>|<span data-ttu-id="7f059-148">Indicador de prioridad: alta, Media o baja.</span><span class="sxs-lookup"><span data-stu-id="7f059-148">Priority indicator: Low, Medium, or High.</span></span>|  
    |<span data-ttu-id="7f059-149">Description</span><span class="sxs-lookup"><span data-stu-id="7f059-149">Description</span></span>|<span data-ttu-id="7f059-150">string</span><span class="sxs-lookup"><span data-stu-id="7f059-150">string</span></span>|<span data-ttu-id="7f059-151">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="7f059-151">Description of the error.</span></span>|  
    |<span data-ttu-id="7f059-152">ErrorDateTime</span><span class="sxs-lookup"><span data-stu-id="7f059-152">ErrorDateTime</span></span>|<span data-ttu-id="7f059-153">DateTime</span><span class="sxs-lookup"><span data-stu-id="7f059-153">DateTime</span></span>|<span data-ttu-id="7f059-154">Fecha y hora del error.</span><span class="sxs-lookup"><span data-stu-id="7f059-154">Date and time that the error occurred.</span></span>|  
  
    <span data-ttu-id="7f059-155">El archivo puede tener uno o varios registros ERROR.</span><span class="sxs-lookup"><span data-stu-id="7f059-155">The file can have one or more ERROR records.</span></span>  
  
     <span data-ttu-id="7f059-156">**--O BIEN--**</span><span class="sxs-lookup"><span data-stu-id="7f059-156">**-- OR --  **</span></span>
  
     <span data-ttu-id="7f059-157">Copie los datos de ejemplo siguiente en el nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="7f059-157">Copy the following sample data into the new file.</span></span> <span data-ttu-id="7f059-158">La última línea contiene un avance de línea al final:</span><span class="sxs-lookup"><span data-stu-id="7f059-158">The last line contains a trailing linefeed:</span></span>
  
    ```  
    East Coast Facility  
    ERROR102|0|High|Sprocket query fails.|1999-05-31T13:20:00.000-05:00  
    ERROR16502|2|Low|Time threshold exceeded.|1999-05-31T13:20:00.000-05:00  
    8675309  
  
    ```  
  
3.  <span data-ttu-id="7f059-159">Guarde el nuevo archivo de ejemplo en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-159">Save the new sample file in the project directory.</span></span> <span data-ttu-id="7f059-160">Use un nombre descriptivo como "ArchivoErrores.txt" para localizarlo fácilmente.</span><span class="sxs-lookup"><span data-stu-id="7f059-160">Use a descriptive name like "ErrorFile.txt" so it can be located easily.</span></span>  
  
### <a name="create-and-test-the-header-trailer-and-body-schemas"></a><span data-ttu-id="7f059-161">Crear y probar los esquemas de cuerpo, finalizador y encabezado</span><span class="sxs-lookup"><span data-stu-id="7f059-161">Create and Test the Header, Trailer, and Body Schemas</span></span>  
 <span data-ttu-id="7f059-162">Una vez creado el archivo de datos del ejemplo, el paso siguiente es crear los esquemas de cuerpo, finalizador y encabezado.</span><span class="sxs-lookup"><span data-stu-id="7f059-162">After the sample data file is created, the next step is to create the header, trailer, and body schemas.</span></span> <span data-ttu-id="7f059-163">Estos esquemas se utilizan con el componente de canalización de recepción Desensamblador de archivos sin formato para procesar mensajes recibidos.</span><span class="sxs-lookup"><span data-stu-id="7f059-163">These schemas are used with the Flat File Disassembler receive pipeline component to process received messages.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-header-schema"></a><span data-ttu-id="7f059-164">Usar al Asistente para esquemas de archivo sin formato para crear el esquema de encabezado</span><span class="sxs-lookup"><span data-stu-id="7f059-164">Use the Flat File Schema Wizard to create the header schema</span></span>  
  
1.  <span data-ttu-id="7f059-165">Agregue un nuevo esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-165">Add a new schema to the project.</span></span> <span data-ttu-id="7f059-166">En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7f059-166">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="7f059-167">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="7f059-167">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="7f059-168">Asígnele al nuevo esquema "el nombre Header.xsd" y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-168">Name the new schema "Header.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="7f059-169">En el **Bienvenido al Asistente de esquema de archivo sin formato de BizTalk** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-169">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="7f059-170">En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f059-170">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="7f059-171">Cambiar el **nombre de registro** a "Encabezado", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-171">Change the **Record Name** to "Header", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f059-172">Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200).</span><span class="sxs-lookup"><span data-stu-id="7f059-172">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="7f059-173">Esto no tendrá ninguna repercusión negativa en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f059-173">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="7f059-174">A continuación, seleccione los datos de documento.</span><span class="sxs-lookup"><span data-stu-id="7f059-174">Next select the document data.</span></span> <span data-ttu-id="7f059-175">En el **seleccionar datos del documento** página, resalte la primera línea de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="7f059-175">On the **Select Document Data** page, highlight the first line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="7f059-176">![Datos seleccionados para el esquema de encabezado](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="7f059-176">![Data selected for header schema](../core/media/ffwiz-header-select-document-data.gif "ffwiz_header_select_document_data")</span></span>  
  
     <span data-ttu-id="7f059-177">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-177">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7f059-178">En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f059-178">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="7f059-179">Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.</span><span class="sxs-lookup"><span data-stu-id="7f059-179">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="7f059-180">En el **registro delimitado** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-180">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="7f059-181">Ahora, podrá especificar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f059-181">Now you specify child elements.</span></span> <span data-ttu-id="7f059-182">El encabezado contiene un elemento denominado “Location”.</span><span class="sxs-lookup"><span data-stu-id="7f059-182">The header contains one element named "Location":</span></span>  
  
     <span data-ttu-id="7f059-183">![Nodo ubicación definido para el encabezado](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span><span class="sxs-lookup"><span data-stu-id="7f059-183">![Location node defined for header](../core/media/ffwiz-header-child-elements.gif "ffwiz_header_child_elements")</span></span>  
  
     <span data-ttu-id="7f059-184">Para continuar, haga clic en **Siguiente** .</span><span class="sxs-lookup"><span data-stu-id="7f059-184">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="7f059-185">En el **vista esquema** , comprueba el esquema.</span><span class="sxs-lookup"><span data-stu-id="7f059-185">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="7f059-186">![Esquema de encabezado que muestra la vista de esquema completado](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span><span class="sxs-lookup"><span data-stu-id="7f059-186">![Schema view showing completed Header schema](../core/media/ffwiz-header-schema-view.gif "ffwiz_header_schema_view")</span></span>  
  
     <span data-ttu-id="7f059-187">Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7f059-187">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="7f059-188">Haga clic en el  **\<esquema >** nodo en el panel de esquema de encabezado.</span><span class="sxs-lookup"><span data-stu-id="7f059-188">Click the **\<Schema>** node in the Header schema pane.</span></span> <span data-ttu-id="7f059-189">En el panel Propiedades, cambie **Element FormDefault** a **Qualified**.</span><span class="sxs-lookup"><span data-stu-id="7f059-189">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="7f059-190">Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.</span><span class="sxs-lookup"><span data-stu-id="7f059-190">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-trailer-schema"></a><span data-ttu-id="7f059-191">Usar al Asistente para esquemas de archivo sin formato para crear el esquema de finalizador</span><span class="sxs-lookup"><span data-stu-id="7f059-191">Use the Flat File Schema Wizard to create the trailer schema</span></span>  
  
1.  <span data-ttu-id="7f059-192">Agregue un nuevo esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-192">Add a new schema to the project.</span></span> <span data-ttu-id="7f059-193">En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, seleccione **agregar** y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7f059-193">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add** , and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="7f059-194">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="7f059-194">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="7f059-195">Asígnele al nuevo esquema "el nombre Trailer.xsd" y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-195">Name the new schema "Trailer.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="7f059-196">En el **Bienvenido al Asistente de esquema de archivo sin formato de BizTalk** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-196">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="7f059-197">En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f059-197">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="7f059-198">Cambiar el **nombre de registro** a "Finalizador", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-198">Change the **Record Name** to "Trailer", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f059-199">Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200).</span><span class="sxs-lookup"><span data-stu-id="7f059-199">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="7f059-200">Esto no tendrá ninguna repercusión negativa en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f059-200">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="7f059-201">A continuación, seleccione los datos de documento.</span><span class="sxs-lookup"><span data-stu-id="7f059-201">Next select the document data.</span></span> <span data-ttu-id="7f059-202">En el **seleccionar datos del documento** página, resalte la última línea de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="7f059-202">On the **Select Document Data** page, highlight the last line of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="7f059-203">![Datos seleccionados para el esquema de finalizador](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="7f059-203">![Data selected for trailer schema](../core/media/ffwiz-trailer-select-document-data.gif "ffwiz_trailer_select_document_data")</span></span>  
  
     <span data-ttu-id="7f059-204">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-204">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7f059-205">En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f059-205">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="7f059-206">Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.</span><span class="sxs-lookup"><span data-stu-id="7f059-206">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="7f059-207">En el **registro delimitado** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-207">On the **Delimited Record** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="7f059-208">Ahora, podrá especificar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f059-208">Now you specify child elements.</span></span> <span data-ttu-id="7f059-209">El encabezado contiene un elemento denominado “BatchID”.</span><span class="sxs-lookup"><span data-stu-id="7f059-209">The header contains one element named "BatchID":</span></span>  
  
     <span data-ttu-id="7f059-210">![Nodo ubicación definido para el finalizador](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span><span class="sxs-lookup"><span data-stu-id="7f059-210">![Location node defined for trailer](../core/media/ffwiz-trailer-child-elements.gif "ffwiz_trailer_child_elements")</span></span>  
  
     <span data-ttu-id="7f059-211">Para continuar, haga clic en **Siguiente** .</span><span class="sxs-lookup"><span data-stu-id="7f059-211">Click **Next** to continue.</span></span>  
  
9. <span data-ttu-id="7f059-212">En el **vista esquema** , comprueba el esquema.</span><span class="sxs-lookup"><span data-stu-id="7f059-212">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="7f059-213">![Esquema de finalizador de vista que muestra completado](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span><span class="sxs-lookup"><span data-stu-id="7f059-213">![Schema view showing completed Trailer schema](../core/media/ffwiz-trailer-schema-view.gif "ffwiz_trailer_schema_view")</span></span>  
  
     <span data-ttu-id="7f059-214">Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7f059-214">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
10. <span data-ttu-id="7f059-215">Haga clic en el  **\<esquema >** nodo en el panel de esquema de finalizador.</span><span class="sxs-lookup"><span data-stu-id="7f059-215">Click the **\<Schema>** node in the Trailer schema pane.</span></span> <span data-ttu-id="7f059-216">En el panel Propiedades, cambie **elementFormDefault** a **Qualified**.</span><span class="sxs-lookup"><span data-stu-id="7f059-216">In the Properties pane, change **elementFormDefault** to **Qualified**.</span></span> <span data-ttu-id="7f059-217">Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.</span><span class="sxs-lookup"><span data-stu-id="7f059-217">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
##### <a name="use-the-flat-file-schema-wizard-to-create-the-body-schema"></a><span data-ttu-id="7f059-218">Usar al Asistente para esquemas de archivo sin formato para crear el esquema de cuerpo</span><span class="sxs-lookup"><span data-stu-id="7f059-218">Use the Flat File Schema Wizard to create the body schema</span></span>  
  
1.  <span data-ttu-id="7f059-219">Agregue un nuevo esquema al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-219">Add a new schema to the project.</span></span> <span data-ttu-id="7f059-220">En el Explorador de soluciones, haga clic en **FFDisassemblerWalkthrough**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7f059-220">In Solution Explorer, right-click **FFDisassemblerWalkthrough**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="7f059-221">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **archivos de esquema** y seleccione **Asistente para esquemas de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="7f059-221">In the **Add New Item** dialog box, click **Schema Files** and select **Flat File Schema Wizard**.</span></span> <span data-ttu-id="7f059-222">Asígnele al nuevo esquema "el nombre Body.xsd" y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-222">Name the new schema "Body.xsd" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="7f059-223">En el **Bienvenido al Asistente de esquema de archivo sin formato de BizTalk** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-223">On the **Welcome to the BizTalk Flat File Schema Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="7f059-224">En el **información de esquema de archivo sin formato** página, haga clic en **examinar** y busque el archivo de datos de ejemplo creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f059-224">On the **Flat File Schema Information** page, click **Browse** and locate the sample data file created earlier.</span></span> <span data-ttu-id="7f059-225">Cambiar el **nombre de registro** como "Cuerpo", compruebe la página de códigos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-225">Change the **Record Name** to "Body", verify the code page, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f059-226">Si se ha guardado el archivo de ejemplo en formato Unicode, la página de código será Little-Endian-UTF16 (1200).</span><span class="sxs-lookup"><span data-stu-id="7f059-226">If you saved the sample file in Unicode format the code page will be Little-Endian-UTF16 (1200).</span></span> <span data-ttu-id="7f059-227">Esto no tendrá ninguna repercusión negativa en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f059-227">This will not adversely affect the example.</span></span>  
  
5.  <span data-ttu-id="7f059-228">A continuación, seleccione los datos de documento.</span><span class="sxs-lookup"><span data-stu-id="7f059-228">Next select the document data.</span></span> <span data-ttu-id="7f059-229">En el **seleccionar datos del documento** página, resalte dos y tres líneas de datos, incluidos los caracteres de nueva línea {CR} y {LF}, tal como se muestra:</span><span class="sxs-lookup"><span data-stu-id="7f059-229">On the **Select Document Data** page, highlight lines two and three of data including the new-line characters {CR} and {LF} as shown:</span></span>  
  
     <span data-ttu-id="7f059-230">![Datos seleccionados para el esquema de cuerpo](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span><span class="sxs-lookup"><span data-stu-id="7f059-230">![Data selected for body schema](../core/media/ffwiz-body-select-document-data.gif "ffwiz_body_select_document_data")</span></span>  
  
     <span data-ttu-id="7f059-231">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-231">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7f059-232">En el **Seleccionar formato de registro** página, haga clic en **siguiente** para aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f059-232">On the **Select Record Format** page, click **Next** to accept the default.</span></span> <span data-ttu-id="7f059-233">Se puede aceptar el valor predeterminado "por símbolo delimitador" porque el archivo de datos no utiliza posición relativa.</span><span class="sxs-lookup"><span data-stu-id="7f059-233">You can accept the default "by delimiter symbol" because the data file does not use relative position.</span></span>  
  
7.  <span data-ttu-id="7f059-234">En el **registro delimitado** página, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-234">On the **Delimited Record** page, select **Next**.</span></span>  
  
8.  <span data-ttu-id="7f059-235">A continuación, defina los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f059-235">Next define the child elements.</span></span> <span data-ttu-id="7f059-236">Cambio **Body_Child1** a **Error**y establezca su tipo de elemento en **repitiendo registro**.</span><span class="sxs-lookup"><span data-stu-id="7f059-236">Change **Body_Child1** to **Error**and set its element type to **Repeating record**.</span></span> <span data-ttu-id="7f059-237">Establecer el **Body_Child2** tipo de registro de elemento para **omitir**.</span><span class="sxs-lookup"><span data-stu-id="7f059-237">Set the **Body_Child2** element record type to **Ignore**.</span></span>  
  
9. <span data-ttu-id="7f059-238">En el **vista esquema** página, haga clic en **siguiente** para definir los elementos secundarios del registro de Error.</span><span class="sxs-lookup"><span data-stu-id="7f059-238">On the **Schema View** page, click **Next** to define the child elements of the Error record.</span></span>  
  
10. <span data-ttu-id="7f059-239">En el **seleccionar datos del documento** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-239">On the **Select Document Data** page, click **Next**.</span></span> <span data-ttu-id="7f059-240">El Asistente selecciona los datos de definición del registro correctamente.</span><span class="sxs-lookup"><span data-stu-id="7f059-240">The wizard chooses the record-defining data correctly.</span></span>  
  
11. <span data-ttu-id="7f059-241">En el **Seleccionar formato de registro** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-241">On the **Select Record Format** page, click **Next**.</span></span> <span data-ttu-id="7f059-242">El símbolo delimitador da formato a los datos.</span><span class="sxs-lookup"><span data-stu-id="7f059-242">The data is formatted by delimiter symbol.</span></span>  
  
12. <span data-ttu-id="7f059-243">En el **registro delimitado** página, seleccione **&#124;** para el **delimitador secundario**.</span><span class="sxs-lookup"><span data-stu-id="7f059-243">On the **Delimited Record** page, select **&#124;** for the **Child delimiter**.</span></span> <span data-ttu-id="7f059-244">A continuación, seleccione la **registro tiene un identificador de etiquetas** casilla de verificación y tipo **ERROR** para el valor de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7f059-244">Next, select the **Record has a tag identifier** check box and type **ERROR** for the tag value.</span></span>  
  
     <span data-ttu-id="7f059-245">![Configurar registro delimitado con identificador de etiquetas](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span><span class="sxs-lookup"><span data-stu-id="7f059-245">![Configuring delimited record with tag identifier](../core/media/ffwiz-bodyerror-delimited-record.gif "ffwiz_bodyerror_delimited_record")</span></span>  
  
     <span data-ttu-id="7f059-246">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-246">Click **Next**.</span></span>  
  
13. <span data-ttu-id="7f059-247">Ahora, defina los elementos secundarios del registro de errores.</span><span class="sxs-lookup"><span data-stu-id="7f059-247">Now define the child elements of the Error record.</span></span>  
  
     <span data-ttu-id="7f059-248">![Registro de errores definidos con cinco elementos](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span><span class="sxs-lookup"><span data-stu-id="7f059-248">![Error record defined with five elements](../core/media/ffwiz-bodyerror-child-elements.gif "ffwiz_bodyerror_child_elements")</span></span>  
  
     <span data-ttu-id="7f059-249">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f059-249">Click **Next**.</span></span>  
  
14. <span data-ttu-id="7f059-250">En el **vista esquema** , comprueba el esquema.</span><span class="sxs-lookup"><span data-stu-id="7f059-250">On the **Schema View** page, verify the schema.</span></span>  
  
     <span data-ttu-id="7f059-251">![Esquema de cuerpo de la vista que muestra completado](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span><span class="sxs-lookup"><span data-stu-id="7f059-251">![Schema view showing completed Body schema](../core/media/ffwiz-bodyerror-schema-view.gif "ffwiz_bodyerror_schema_view")</span></span>  
  
     <span data-ttu-id="7f059-252">Si se ha cometido algún, haga clic en **volver** y realice las correcciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="7f059-252">If you have made any mistakes, click **Back** and make the necessary corrections.</span></span> <span data-ttu-id="7f059-253">Cuando esté satisfecho, haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="7f059-253">When you are satisfied, click **Finish** to complete the wizard.</span></span>  
  
15. <span data-ttu-id="7f059-254">Haga clic en el  **\<esquema >** nodo en el panel de esquema de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="7f059-254">Click the **\<Schema>** node in the Body schema pane.</span></span> <span data-ttu-id="7f059-255">En el panel Propiedades, cambie **Element FormDefault** a **Qualified**.</span><span class="sxs-lookup"><span data-stu-id="7f059-255">In the Properties pane, change **Element FormDefault** to **Qualified**.</span></span> <span data-ttu-id="7f059-256">Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.</span><span class="sxs-lookup"><span data-stu-id="7f059-256">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
16. <span data-ttu-id="7f059-257">Haga clic en el  **\<Error >** nodo en el panel de esquema de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="7f059-257">Click the **\<Error>** node on the Body schema pane.</span></span> <span data-ttu-id="7f059-258">En el panel Propiedades, cambie **Max Occurs** a **1**.</span><span class="sxs-lookup"><span data-stu-id="7f059-258">In the Properties pane, change **Max Occurs** to **1**.</span></span> <span data-ttu-id="7f059-259">Con ello, el Desensamblador de archivos sin formato divide cada uno de los errores en su propio mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f059-259">This causes the Flat File Disassembler to split each error into its own message.</span></span>  
  
##### <a name="test-the-schemas-using-ffdasm"></a><span data-ttu-id="7f059-260">Probar los esquemas mediante FFDasm</span><span class="sxs-lookup"><span data-stu-id="7f059-260">Test the schemas using FFDasm</span></span>  
  
1.  <span data-ttu-id="7f059-261">Abra un símbolo del sistema y cambie el directorio al que le corresponde al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-261">Open a command prompt and change the directory to your project directory.</span></span>  
  
2.  <span data-ttu-id="7f059-262">En el símbolo del sistema, ejecute FFDasm.exe, tal como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7f059-262">From the command prompt, run FFDasm.exe as shown below.</span></span>  
  
    ```  
    <Samples Path>\SDK\Utilities\PipelineTools\FFDasm ErrorFile.txt  -hs header.xsd -bs body.xsd -ts Trailer.xsd  
    ```  
  
     <span data-ttu-id="7f059-263">Para obtener información acerca de la ubicación de esta y otras herramientas de canalización, consulte [herramientas de canalización](../core/pipeline-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f059-263">For information about the location of this and other pipeline tools, see [Pipeline Tools](../core/pipeline-tools.md).</span></span>  
  
3.  <span data-ttu-id="7f059-264">FFDasm.exe debe producir dos archivos de salida denominados {GUID}.xml, uno para cada registro ERROR en el archivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="7f059-264">FFDasm.exe should produce two output files named {GUID}.xml, one for each ERROR record in the test file.</span></span> <span data-ttu-id="7f059-265">El registro ERROR de alta prioridad tiene el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f059-265">The high-priority error record looks like the following:</span></span>  
  
    ```  
    <Body xmlns="http://FFDisassemblerWalkthrough.Body">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <DateTime>1999-05-31T13:20:00.000-05:00</DateTime>  
      </Error>  
    </Body>  
    ```  
  
### <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="7f059-266">Crear una canalización de recepción personalizada</span><span class="sxs-lookup"><span data-stu-id="7f059-266">Create a Custom Receive Pipeline</span></span>  
 <span data-ttu-id="7f059-267">Ahora que están definidos los esquemas de archivo sin formato, será necesario crear una canalización personalizada que utilice el componente Desensamblador de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="7f059-267">Now that the flat file schemas are defined, you need to create a custom pipeline that uses the Flat File Disassembler component.</span></span> <span data-ttu-id="7f059-268">Seguidamente, el Desensamblador de archivos sin formato puede configurarse para utilizar los esquemas de finalizador, cuerpo y encabezado para fragmentar mensajes.</span><span class="sxs-lookup"><span data-stu-id="7f059-268">The Flat File Disassembler component can then be configured to use the header, body, and trailer schemas to break up messages.</span></span>    
 
1.  <span data-ttu-id="7f059-269">Agregue una nueva canalización de recepción al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-269">Add a new receive pipeline to the project.</span></span> <span data-ttu-id="7f059-270">En el Explorador de soluciones, haga clic en el **FFDisassemblerWalkthrough** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7f059-270">In Solution Explorer, right-click the **FFDisassemblerWalkthrough** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="7f059-271">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivos de canalización** y, a continuación, haga clic en **canalización de recepción**.</span><span class="sxs-lookup"><span data-stu-id="7f059-271">In the **Add New Item** dialog box, point to **Pipeline Files** and then click **Receive Pipeline**.</span></span> <span data-ttu-id="7f059-272">Nombre de la nueva canalización "FFReceivePipeline" y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-272">Name the new pipeline "FFReceivePipeline" and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="7f059-273">Para configurar la nueva canalización, arrastre el componente Desensamblador de archivos sin formato desde el panel Cuadro de herramientas hasta el paso de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f059-273">Configure the new pipeline by dragging the Flat File Disassembler component from the Toolbox pane to the Disassemble step.</span></span>  
  
4.  <span data-ttu-id="7f059-274">En el panel Propiedades, establezca la **esquema de documento** a **como FFDisassemblerWalkthrough.Body**, **esquema de encabezado** a  **Como FFDisassemblerWalkthrough.Header** y **esquema de finalizador** a **como FFDisassemblerWalkthrough.Trailer**.</span><span class="sxs-lookup"><span data-stu-id="7f059-274">In the Properties pane, set the **Document schema** to **FFDisassemblerWalkthrough.Body**, the **Header schema** to **FFDisassemblerWalkthrough.Header** and the **Trailer schema** to **FFDisassemblerWalkthrough.Trailer**.</span></span>  
  
### <a name="deploy-the-application-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="7f059-275">Implementar la aplicación y configurar los puertos de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="7f059-275">Deploy the Application and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="7f059-276">Con los esquemas y la canalización de recepción personalizada creados, será necesario compilar el proyecto e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="7f059-276">With the schemas and custom receive pipeline created, you need to compile and deploy the project.</span></span> <span data-ttu-id="7f059-277">Una vez implementado, se podrá utilizar la consola de administración de BizTalk Server para configurar los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="7f059-277">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  

##### <a name="deploy"></a><span data-ttu-id="7f059-278">Implementar</span><span class="sxs-lookup"><span data-stu-id="7f059-278">Deploy</span></span>  
1.  <span data-ttu-id="7f059-279">Desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], implementar la solución con el botón secundario en el proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-279">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by right-clicking on the project and then clicking **Deploy**.</span></span>  
  
2.  <span data-ttu-id="7f059-280">Mediante la consola de administración de BizTalk Server, expanda el **aplicaciones** grupo para comprobar que **FlatFileExample** está presente como una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="7f059-280">Using the BizTalk Server Administration console, expand the **Applications** group to verify that **FlatFileExample** is present as a custom application.</span></span>  
  
##### <a name="configure-the-receive-port"></a><span data-ttu-id="7f059-281">Configurar el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="7f059-281">Configure the receive port</span></span>  
  
1.  <span data-ttu-id="7f059-282">Utilice el Explorador de Windows para crear un directorio denominado "Receive" en la **FFDisassemblerWalkthrough** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-282">Use Windows Explorer to create a directory named "Receive" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="7f059-283">En la consola de administración de BizTalk Server, expanda el **FlatFileExample** aplicación, haga clic en **puertos de recepción**, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="7f059-283">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="7f059-284">En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto "ReceiveError".</span><span class="sxs-lookup"><span data-stu-id="7f059-284">In the **Receive Port Properties** dialog box, set the name of the port to "ReceiveError".</span></span>  
  
4.  <span data-ttu-id="7f059-285">Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New** para agregar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="7f059-285">Click **Receive Locations**, and then click **New** to add a receive location.</span></span> <span data-ttu-id="7f059-286">Nombre la nueva ubicación de recepción "ReceiveErrorLocation".</span><span class="sxs-lookup"><span data-stu-id="7f059-286">Name the new receive location "ReceiveErrorLocation".</span></span> <span data-ttu-id="7f059-287">Establecer el **canalización de recepción** a **FFReceivePipeline**.</span><span class="sxs-lookup"><span data-stu-id="7f059-287">Set the **Receive Pipeline** to **FFReceivePipeline**.</span></span> <span data-ttu-id="7f059-288">Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-288">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="7f059-289">Seleccione el directorio de recepción creado y, a continuación, establezca el **máscara de archivo** como *.txt.</span><span class="sxs-lookup"><span data-stu-id="7f059-289">Select the receive directory you created, and then set the **File mask** to *.txt.</span></span>  
  
5.  <span data-ttu-id="7f059-290">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-290">Click **OK**.</span></span> <span data-ttu-id="7f059-291">Con ello, el puerto de recepción debería estar configurado.</span><span class="sxs-lookup"><span data-stu-id="7f059-291">Your receive port should now be configured.</span></span> <span data-ttu-id="7f059-292">Haga clic en **Aceptar** para cerrar.</span><span class="sxs-lookup"><span data-stu-id="7f059-292">Click **OK** to close.</span></span>  
  
##### <a name="configure-the-send-port"></a><span data-ttu-id="7f059-293">Configurar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7f059-293">Configure the send port</span></span>  
  
1.  <span data-ttu-id="7f059-294">Utilice el Explorador de Windows para crear un directorio denominado "Send" en la **FFDisassemblerWalkthrough** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f059-294">Use Windows Explorer to create a directory named "Send" under the **FFDisassemblerWalkthrough** project directory.</span></span>  
  
2.  <span data-ttu-id="7f059-295">En la consola de administración de BizTalk Server, expanda el **FlatFileExample** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Puerto de envío unidireccional estático...** .</span><span class="sxs-lookup"><span data-stu-id="7f059-295">In the BizTalk Server Administration console, expand the **FlatFileExample** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way  Send Port…**.</span></span>  
  
3.  <span data-ttu-id="7f059-296">En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto de "Envío".</span><span class="sxs-lookup"><span data-stu-id="7f059-296">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="7f059-297">Para el tipo de transporte, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-297">For transport type, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="7f059-298">Defina el directorio de envío creado anteriormente como la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="7f059-298">Set the destination folder to the send directory you created earlier.</span></span>  
  
5.  <span data-ttu-id="7f059-299">Ahora, configure el filtro.</span><span class="sxs-lookup"><span data-stu-id="7f059-299">Now configure the filter.</span></span> <span data-ttu-id="7f059-300">Haga clic en **filtros** y agregue una expresión:</span><span class="sxs-lookup"><span data-stu-id="7f059-300">Click **Filters** and add one expression:</span></span>  
  
    -   <span data-ttu-id="7f059-301">BTS. MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span><span class="sxs-lookup"><span data-stu-id="7f059-301">BTS.MessageType == **http://FFDisassemblerWalkthrough.Body#Body**</span></span>  
  
6.  <span data-ttu-id="7f059-302">Haga clic en **Aceptar** para completar la configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7f059-302">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="7f059-303">Con ello, el puerto de envío debería estar configurado.</span><span class="sxs-lookup"><span data-stu-id="7f059-303">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="7f059-304">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f059-304">Run the Example</span></span>  
 <span data-ttu-id="7f059-305">Ha llegado el momento de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7f059-305">It is now time to run the example.</span></span> <span data-ttu-id="7f059-306">Después de usar la consola de administración de BizTalk Server para iniciar la aplicación, copie los archivos de prueba en la ubicación de recepción y observará lo que se produce en la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="7f059-306">After using the BizTalk Server Management console to start the application, copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
1.  <span data-ttu-id="7f059-307">En la consola de administración de BizTalk Server, haga clic en el **FlatFileExample** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7f059-307">In the BizTalk Server Administration console, right-click the **FlatFileExample** application, and then click **Start**.</span></span> <span data-ttu-id="7f059-308">Esto se da de alta e inicia el envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="7f059-308">This enlists and starts the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="7f059-309">Suelte la copia del archivo Errorfile.txt de ejemplo en el directorio de recepción.</span><span class="sxs-lookup"><span data-stu-id="7f059-309">Drop the copy of the sample Errorfile.txt into the receive directory.</span></span> <span data-ttu-id="7f059-310">Se deberían escribir dos archivos de salida en el directorio de envío.</span><span class="sxs-lookup"><span data-stu-id="7f059-310">Two output files should be written to the send directory.</span></span>  
  
