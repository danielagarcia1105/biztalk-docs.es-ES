---
title: 'Tutorial: Módulo 2: integrar Office con Windows SharePoint Services adaptador | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79297c55152688821ba5b472335eade1d31b0ffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022394"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="7474e-102">Tutorial: Módulo 2: integrar Office con el adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="7474e-102">Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="7474e-103">En este tutorial es una continuación de [Tutorial: módulo 1: enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) y le muestra cómo integrar Microsoft Office con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] basado en contenido aplicación de enrutamiento (CBR) que creó.</span><span class="sxs-lookup"><span data-stu-id="7474e-103">This walkthrough is a continuation of [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and shows you how to integrate Microsoft Office with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] content-based routing (CBR) application you created.</span></span> <span data-ttu-id="7474e-104">Para obtener una introducción al adaptador de Windows SharePoint Services, consulte [¿qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7474e-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7474e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7474e-105">Prerequisites</span></span>  
 <span data-ttu-id="7474e-106">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="7474e-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="7474e-107">Debe tener una implementación de un solo servidor con una instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7474e-107">You must have a single-server deployment with a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="7474e-108">Debe completar el tutorial siguiente: [Tutorial: módulo 1: enviar y recibir mensajes con el adaptador de Windows SharePoint Services](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="7474e-108">You must complete the following walkthrough: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span></span>  
  
  <span data-ttu-id="7474e-109">Para obtener información sobre cómo usar el adaptador de Windows SharePoint Services en una implementación multiservidor, consulte [configurar e implementar el adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="7474e-109">For information about using the Windows SharePoint Services Adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="create-a-biztalk-project"></a><span data-ttu-id="7474e-110">Crear un proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7474e-110">Create a BizTalk project</span></span>  
 <span data-ttu-id="7474e-111">En este procedimiento, creará un proyecto de BizTalk vacío y un esquema utilizando el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7474e-111">In this procedure you create an empty BizTalk project and a schema using the BizTalk Editor.</span></span> <span data-ttu-id="7474e-112">Este procedimiento se requiere para crear el esquema del formulario de InfoPath que se utilizará posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7474e-112">This procedure is required to create the schema for the InfoPath form that is used later.</span></span>  
  
#### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="7474e-113">Crear un archivo de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="7474e-113">Create a strong name key file</span></span>  
  
1.  <span data-ttu-id="7474e-114">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7474e-114">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="7474e-115">Tipo `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="7474e-115">Type `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`, and then press **Enter**.</span></span> <span data-ttu-id="7474e-116">Se escribirá el par de claves.</span><span class="sxs-lookup"><span data-stu-id="7474e-116">The key pair will be written.</span></span>  
  
3.  <span data-ttu-id="7474e-117">Cierre el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7474e-117">Close the command prompt.</span></span>  
  
#### <a name="create-an-empty-biztalk-project"></a><span data-ttu-id="7474e-118">Crear un proyecto de BizTalk vacío</span><span class="sxs-lookup"><span data-stu-id="7474e-118">Create an empty BizTalk project</span></span>  
  
1.  <span data-ttu-id="7474e-119">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7474e-119">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="7474e-120">Haga clic en **archivo**, **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7474e-120">Click **File**, **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="7474e-121">En **tipos de proyecto**, seleccione **proyectos de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="7474e-121">Under **Project types**, select **BizTalk Projects**.</span></span>  
  
4.  <span data-ttu-id="7474e-122">En **plantillas**, seleccione **proyecto vacío de servidor BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="7474e-122">Under **Templates**, select **Empty BizTalk Server Project**.</span></span>  
  
5.  <span data-ttu-id="7474e-123">Tipo `OrderProcess` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-123">Type `OrderProcess` in the **Name** field.</span></span>  
  
6.  <span data-ttu-id="7474e-124">Escriba la ruta de acceso al directorio de trabajo en el **ubicación** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-124">Type the file path to your working directory in the **Location** field.</span></span> <span data-ttu-id="7474e-125">Por ejemplo, `C:\WSSAdapterWalkthrough\`.</span><span class="sxs-lookup"><span data-stu-id="7474e-125">For example, `C:\WSSAdapterWalkthrough\`.</span></span>  
  
7.  <span data-ttu-id="7474e-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-126">Click **OK**.</span></span>  
  
#### <a name="associate-the-key-file-with-the-assembly"></a><span data-ttu-id="7474e-127">Asociar el archivo de clave al ensamblado</span><span class="sxs-lookup"><span data-stu-id="7474e-127">Associate the key file with the assembly</span></span>  
  
1.  <span data-ttu-id="7474e-128">En el Explorador de soluciones, haga clic en el `OrderProcess` del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="7474e-128">In Solution Explorer, right-click the `OrderProcess` project, and then click **Properties** to launch the Project Designer.</span></span>  
  
2.  <span data-ttu-id="7474e-129">Haga clic en la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="7474e-129">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="7474e-130">Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-130">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
4.  <span data-ttu-id="7474e-131">Tipo `C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span><span class="sxs-lookup"><span data-stu-id="7474e-131">Type `C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span></span>  
  
5.  <span data-ttu-id="7474e-132">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7474e-132">Click **Open**.</span></span>  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a><span data-ttu-id="7474e-133">Crear un esquema XSD utilizando el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7474e-133">Create an XSD schema by using the BizTalk Editor</span></span>  
  
1. <span data-ttu-id="7474e-134">En el Explorador de soluciones, haga clic en el `OrderProcess` del proyecto, haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7474e-134">In Solution Explorer, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="7474e-135">En **categorías**, haga clic en **archivos de esquema**.</span><span class="sxs-lookup"><span data-stu-id="7474e-135">Under **Categories**, click **Schema Files**.</span></span>  
  
3. <span data-ttu-id="7474e-136">En **plantillas**, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="7474e-136">Under **Templates**, click **Schema**.</span></span>  
  
4. <span data-ttu-id="7474e-137">Tipo `OrderProcessSchema` en el **nombre** campo y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-137">Type `OrderProcessSchema` in the **Name** field, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="7474e-138">En la ventana Propiedades para `OrderProcessSchema`, seleccione `Qualified` para el **Element FormDefault** propiedad.</span><span class="sxs-lookup"><span data-stu-id="7474e-138">In the Properties Window for `OrderProcessSchema`, select `Qualified` for the **Element FormDefault** property.</span></span>  
  
6. <span data-ttu-id="7474e-139">En la ventana Propiedades para `OrderProcessSchema`, tipo `http://OrderProcess.PurchaseOrder` en el **Target Namespace** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-139">In the Properties Window for `OrderProcessSchema`, type `http://OrderProcess.PurchaseOrder` in the **Target Namespace** field.</span></span>  
  
7. <span data-ttu-id="7474e-140">En el **el Editor de BizTalk**, haga clic en `Root`, haga clic en **cambiar el nombre de**y, a continuación, escriba `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="7474e-140">In the **BizTalk Editor**, right-click `Root`, click **Rename**, and then type `PurchaseOrder`.</span></span>  
  
8. <span data-ttu-id="7474e-141">Haga clic en el **PurchaseOrder** nodo, haga clic en **Insertar nodo de esquema**, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="7474e-141">Right-click the **PurchaseOrder** node, click **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
9. <span data-ttu-id="7474e-142">Asígnele el nombre `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="7474e-142">Name it `PurchaseOrderID`.</span></span>  
  
10. <span data-ttu-id="7474e-143">Cree otro elemento de campo secundario y asígnele el nombre `BillTo`.</span><span class="sxs-lookup"><span data-stu-id="7474e-143">Create another child field element and name it `BillTo`.</span></span>  
  
11. <span data-ttu-id="7474e-144">Cree otro elemento de campo secundario y asígnele el nombre `Amount`.</span><span class="sxs-lookup"><span data-stu-id="7474e-144">Create another child field element and name it `Amount`.</span></span>  
  
12. <span data-ttu-id="7474e-145">En la ventana Propiedades, establezca la **tipo de datos** propiedad `Amount` a xs: unsignedInt.</span><span class="sxs-lookup"><span data-stu-id="7474e-145">In the Properties Window, set the **Data Type** property for `Amount` to xs:unsignedInt.</span></span>  
  
13. <span data-ttu-id="7474e-146">Cree otro elemento de campo secundario y asígnele el nombre `PurchaseOrderDate`.</span><span class="sxs-lookup"><span data-stu-id="7474e-146">Create another child field element and name it `PurchaseOrderDate`.</span></span>  
  
14. <span data-ttu-id="7474e-147">En la ventana Propiedades, establezca la **tipo de datos** propiedad `PurchaseOrderDate` a xs: DateTime.</span><span class="sxs-lookup"><span data-stu-id="7474e-147">In the Properties Window, set the **Data Type** property for `PurchaseOrderDate` to xs:dateTime.</span></span>  
  
15. <span data-ttu-id="7474e-148">Haga clic en **archivo**y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="7474e-148">Click **File**, and then click **Save All**.</span></span>  
  
16. <span data-ttu-id="7474e-149">Cierre [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7474e-149">Close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="create-an-infopath-form"></a><span data-ttu-id="7474e-150">Crear un formulario de InfoPath</span><span class="sxs-lookup"><span data-stu-id="7474e-150">Create an InfoPath form</span></span>  
 <span data-ttu-id="7474e-151">En este procedimiento, creará otra biblioteca de documentos y un formulario de InfoPath basado en el esquema creado en el último procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7474e-151">In this procedure you create another document library and an InfoPath form based on the schema you created in the last procedure.</span></span> <span data-ttu-id="7474e-152">Este formulario de InfoPath se usará para enviar un documento a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7474e-152">This InfoPath form will be used to submit a document to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7474e-153">Este tutorial requiere tener instalado Microsoft Office InfoPath 2007</span><span class="sxs-lookup"><span data-stu-id="7474e-153">This walkthrough requires Microsoft Office InfoPath 2007</span></span>  
  
#### <a name="create-a-new-document-library"></a><span data-ttu-id="7474e-154">Crear una nueva biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="7474e-154">Create a new document library</span></span>  
  
1.  <span data-ttu-id="7474e-155">Abra un explorador web y vaya a la dirección URL del sitio creado.</span><span class="sxs-lookup"><span data-stu-id="7474e-155">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="7474e-156">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="7474e-156">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="7474e-157">En la barra de navegación superior, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="7474e-157">On the top navigation bar, click **Create**.</span></span>  
  
3.  <span data-ttu-id="7474e-158">En **las bibliotecas de documentos**, haga clic en **biblioteca de documentos**.</span><span class="sxs-lookup"><span data-stu-id="7474e-158">Under **Document Libraries**, click **Document Library**.</span></span>  
  
4.  <span data-ttu-id="7474e-159">En el **nombre y descripción** , escriba `InfoPathSolutions` en el **campo nombre**.</span><span class="sxs-lookup"><span data-stu-id="7474e-159">In the **Name and Description** section, type `InfoPathSolutions` in the **Name field**.</span></span>  
  
5.  <span data-ttu-id="7474e-160">En el **navegación** sección, seleccione **Sí** para mostrar esta biblioteca de formularios en la barra Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="7474e-160">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
6.  <span data-ttu-id="7474e-161">En el **plantilla de documento** sección, seleccione `None` para el **plantilla de documento**.</span><span class="sxs-lookup"><span data-stu-id="7474e-161">In the **Document Template** section, select `None` for the **Document Template**.</span></span>  
  
7.  <span data-ttu-id="7474e-162">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="7474e-162">Click **Create**.</span></span> <span data-ttu-id="7474e-163">Tendrá lugar una redirección a la biblioteca vacía recién creada.</span><span class="sxs-lookup"><span data-stu-id="7474e-163">You will be redirected to the empty library you just created.</span></span>  
  
8.  <span data-ttu-id="7474e-164">En el lado izquierdo, haga clic en **modificar la configuración y las columnas**.</span><span class="sxs-lookup"><span data-stu-id="7474e-164">On the left side, click **Modify Settings and Columns**.</span></span>  
  
9. <span data-ttu-id="7474e-165">En **columnas**, haga clic en **agregar una nueva columna**.</span><span class="sxs-lookup"><span data-stu-id="7474e-165">Under **Columns**, click **Add a New Column**.</span></span>  
  
10. <span data-ttu-id="7474e-166">En **nombre y tipo**, tipo `Namespace` en el **nombre** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-166">Under **Name and Type**, type `Namespace` in the **Name** field.</span></span>  
  
11. <span data-ttu-id="7474e-167">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-167">Click **OK**.</span></span>  
  
12. <span data-ttu-id="7474e-168">Cierre el sitio web de `WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="7474e-168">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a><span data-ttu-id="7474e-169">Crear un formulario de InfoPath basado en el archivo de esquema OrderProcessSchema</span><span class="sxs-lookup"><span data-stu-id="7474e-169">Create an InfoPath form based on the OrderProcessSchema schema file</span></span>  
  
1.  <span data-ttu-id="7474e-170">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Office**y, a continuación, haga clic en **Microsoft Office InfoPath 2007**.</span><span class="sxs-lookup"><span data-stu-id="7474e-170">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office InfoPath 2007**.</span></span>  
  
2.  <span data-ttu-id="7474e-171">En el **rellenar un formulario** cuadro de diálogo, seleccione **diseñar un formulario.**</span><span class="sxs-lookup"><span data-stu-id="7474e-171">In the **Fill Out a Form** dialog box, select **Design a Form.**</span></span>  
  
3.  <span data-ttu-id="7474e-172">En el **diseñar un formulario** panel de tareas, seleccione **nuevo a partir de documento XML o esquema**.</span><span class="sxs-lookup"><span data-stu-id="7474e-172">In the **Design a Form** task pane, select **New from XML Document or Schema**.</span></span>  
  
4.  <span data-ttu-id="7474e-173">En el **Data Source Wizard**, haga clic en **examinar** y seleccione el archivo de esquema que creó en el último procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7474e-173">In the **Data Source Wizard**, click **Browse** and select the schema file you created in the last procedure.</span></span> <span data-ttu-id="7474e-174">Por ejemplo, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.</span><span class="sxs-lookup"><span data-stu-id="7474e-174">For example, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.</span></span>  
  
5.  <span data-ttu-id="7474e-175">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-175">Click **Next**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="7474e-176">En el **origen de datos** panel de tareas, haga clic en el **PurchaseOrder** nodo y, a continuación, haga clic en **sección con controles**.</span><span class="sxs-lookup"><span data-stu-id="7474e-176">In the **Data Source** task pane, right-click the **PurchaseOrder** node, and then click **Section with Controls**.</span></span> <span data-ttu-id="7474e-177">Al hacerlo, se creará el formulario en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7474e-177">This will create the form on the template.</span></span>  
  
7.  <span data-ttu-id="7474e-178">Haga clic en **archivo**, haga clic en **guardar**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-178">Click **File**, click **Save**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="7474e-179">En el **Guardar como** cuadro de diálogo, escriba `PurchaseOrder.xsn` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-179">In the **Save As** dialog box, type `PurchaseOrder.xsn` in the **File name** field, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="7474e-180">Haga clic en **archivo**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-180">Click **File**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="7474e-181">En el **Asistente para publicación de**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7474e-181">In the **Publishing Wizard**, click **Next**.</span></span>  
  
11. <span data-ttu-id="7474e-182">Seleccione **en un servidor Web**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7474e-182">Select **To a Web Server**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="7474e-183">Escriba la ruta de acceso y nombre de archivo para su `InfoPathSolutions` biblioteca de documentos y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7474e-183">Type the path and filename to your `InfoPathSolutions` document library, and then click **Next**.</span></span> <span data-ttu-id="7474e-184">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.</span><span class="sxs-lookup"><span data-stu-id="7474e-184">For example, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.</span></span>  
  
13. <span data-ttu-id="7474e-185">Haga clic en **finalizar**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-185">Click **Finish**, and then click **Close**.</span></span>  
  
14. <span data-ttu-id="7474e-186">Cierre Microsoft InfoPath.</span><span class="sxs-lookup"><span data-stu-id="7474e-186">Close Microsoft InfoPath.</span></span>  
  
## <a name="modify-the-sharepoint-document-libraries"></a><span data-ttu-id="7474e-187">Modificar las bibliotecas de documentos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="7474e-187">Modify the SharePoint document libraries</span></span>  
 <span data-ttu-id="7474e-188">En este procedimiento, se actualizará la propiedad de espacio de nombres para el archivo PurchaseOrder.xsn y se modificará la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="7474e-188">In this procedure you will update the namespace property for the PurchaseOrder.xsn file and modify the Destination Document Library.</span></span> <span data-ttu-id="7474e-189">Este espacio de nombres se utiliza como una variable al determinar suscriptores de documentos publicados para escenarios de enrutamiento por contenidos.</span><span class="sxs-lookup"><span data-stu-id="7474e-189">This namespace is used as a variable when determining subscribers of published documents for content based routing scenarios.</span></span>  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a><span data-ttu-id="7474e-190">Actualizar el espacio de nombres para PurchaseOrder.xsn</span><span class="sxs-lookup"><span data-stu-id="7474e-190">Update the namespace for PurchaseOrder.xsn</span></span>  
  
1.  <span data-ttu-id="7474e-191">Abra un explorador web y vaya a la dirección URL del sitio creado.</span><span class="sxs-lookup"><span data-stu-id="7474e-191">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="7474e-192">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="7474e-192">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="7474e-193">En el lado izquierdo, bajo **documentos**, haga clic en `InfoPathSolutions`.</span><span class="sxs-lookup"><span data-stu-id="7474e-193">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="7474e-194">Mueva el puntero sobre `PurchaseOrder.xsn`, haga clic en él y, a continuación, haga clic en **editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7474e-194">Move the pointer over `PurchaseOrder.xsn`, right-click it, and then click **Edit Properties**.</span></span>  
  
4.  <span data-ttu-id="7474e-195">Tipo `http://OrderProcess.PurchaseOrder` en el **Namespace** campo y, a continuación, haga clic en **guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-195">Type `http://OrderProcess.PurchaseOrder` in the **Namespace** field, and then click **Save and Close**.</span></span>  
  
#### <a name="modify-the-destination-document-library"></a><span data-ttu-id="7474e-196">Modificar la biblioteca de documentos de destino</span><span class="sxs-lookup"><span data-stu-id="7474e-196">Modify the Destination document library</span></span>  
  
1.  <span data-ttu-id="7474e-197">En la barra de navegación superior, haga clic en **documentos y listas**.</span><span class="sxs-lookup"><span data-stu-id="7474e-197">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
2.  <span data-ttu-id="7474e-198">En **las bibliotecas de documentos**, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="7474e-198">Under **Document Libraries**, click **Destination**.</span></span>  
  
3.  <span data-ttu-id="7474e-199">En el lado izquierdo, haga clic en **modificar la configuración y las columnas**.</span><span class="sxs-lookup"><span data-stu-id="7474e-199">On the left side, click **Modify Settings and Columns**.</span></span>  
  
4.  <span data-ttu-id="7474e-200">En **columnas**, haga clic en **agregar nueva columna**.</span><span class="sxs-lookup"><span data-stu-id="7474e-200">Under **Columns**, click **Add New Column**.</span></span>  
  
5.  <span data-ttu-id="7474e-201">En **nombre y tipo**, tipo `Partner Name` en el **nombre de columna** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-201">Under **Name and Type**, type `Partner Name` in the **Column name** field.</span></span>  
  
6.  <span data-ttu-id="7474e-202">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-202">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="7474e-203">Cierre el sitio web de `WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="7474e-203">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a><span data-ttu-id="7474e-204">Modificar el puerto de envío del Tutorial 1</span><span class="sxs-lookup"><span data-stu-id="7474e-204">Modify the send port from walkthrough 1</span></span>  
 <span data-ttu-id="7474e-205">En este procedimiento, modificará el puerto de envío del Tutorial 1.</span><span class="sxs-lookup"><span data-stu-id="7474e-205">In this procedure you modify the send port from walkthrough 1.</span></span> <span data-ttu-id="7474e-206">Este procedimiento se requiere para garantizar que el documento procesado en este tutorial se enrute correctamente al puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7474e-206">This procedure is required to ensure that the document processed in this walkthrough is correctly routed to the send port.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="7474e-207">Modificar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7474e-207">Modify the send port</span></span>  
  
1. <span data-ttu-id="7474e-208">Abra **administración de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="7474e-208">Open **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="7474e-209">Expanda **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **BizTalk Application 1**y, a continuación, haga clic en el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="7474e-209">Expand **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Send Ports** node.</span></span>  
  
3. <span data-ttu-id="7474e-210">Haga clic en `SendToDestination`y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7474e-210">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="7474e-211">En **transporte**, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-211">Under **Transport**, click **Configure**.</span></span>  
  
5. <span data-ttu-id="7474e-212">En el **Filename** , escriba `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.</span><span class="sxs-lookup"><span data-stu-id="7474e-212">In the **Filename** field, type `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.</span></span>  
  
6. <span data-ttu-id="7474e-213">En el **Namespace alias** , escriba `pons="http://OrderProcess.PurchaseOrder"`.</span><span class="sxs-lookup"><span data-stu-id="7474e-213">In the **Namespace Aliases** field, type `pons="http://OrderProcess.PurchaseOrder"`.</span></span>  
  
7. <span data-ttu-id="7474e-214">En el **biblioteca de documentos de plantillas**, tipo `InfoPathSolutions`.</span><span class="sxs-lookup"><span data-stu-id="7474e-214">In the **Templates Document Library**, type `InfoPathSolutions`.</span></span>  
  
8. <span data-ttu-id="7474e-215">En el **plantillas Namespace columna**, tipo `Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7474e-215">In the **Templates Namespace Column**, type `Namespace`.</span></span>  
  
9. <span data-ttu-id="7474e-216">Seleccione `Yes` para el **integración con Microsoft Office** propiedad.</span><span class="sxs-lookup"><span data-stu-id="7474e-216">Select `Yes` for the **Microsoft Office Integration** property.</span></span>  
  
10. <span data-ttu-id="7474e-217">En **integración con Windows SharePoint Services**, tipo `Partner Name` en el **columna 01** campo.</span><span class="sxs-lookup"><span data-stu-id="7474e-217">Under **Windows SharePoint Services Integration**, type `Partner Name` in the **Column 01** field.</span></span>  
  
11. <span data-ttu-id="7474e-218">Tipo `%XPATH=//pons:PurchaseOrder/pons:BillTo%` en el **valor de columna 01** , a continuación, haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo para salir del **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7474e-218">Type `%XPATH=//pons:PurchaseOrder/pons:BillTo%` in the **Column 01 Value** field, click **OK**, and then click **OK** again to exit the **Send Port Properties** dialog box.</span></span>  
  
#### <a name="restart-the-send-port"></a><span data-ttu-id="7474e-219">Reiniciar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7474e-219">Restart the send port</span></span>  
  
1.  <span data-ttu-id="7474e-220">En el **consola de administración de BizTalk**, haga clic en el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="7474e-220">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="7474e-221">Haga clic en `SendToDestination`y, a continuación, haga clic en **dar de baja**.</span><span class="sxs-lookup"><span data-stu-id="7474e-221">Right-click `SendToDestination`, and then click **Unenlist**.</span></span>  
  
3.  <span data-ttu-id="7474e-222">Haga clic en `SendToDestination`y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-222">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="7474e-223">Cerrar la **consola de administración de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="7474e-223">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="7474e-224">Enviar un mensaje a través del sistema</span><span class="sxs-lookup"><span data-stu-id="7474e-224">Send a message through the system</span></span>  
 <span data-ttu-id="7474e-225">En este procedimiento, creará un formulario de InfoPath y lo cargará en el sitio web de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="7474e-225">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="7474e-226">El adaptador de Windows SharePoint Services tomará el mensaje, lo archivará en la biblioteca de documentos de archivo y, a continuación, lo enviará a la biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="7474e-226">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="7474e-227">En este procedimiento se demuestra cómo un documento se transfiere de un sitio web de Sharepoint, a través de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a un sitio web de Sharepoint Services mediante el adaptador de Windows Sharepoint Services.</span><span class="sxs-lookup"><span data-stu-id="7474e-227">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="7474e-228">Crear un formulario de InfoPath para su envío a través del sistema</span><span class="sxs-lookup"><span data-stu-id="7474e-228">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="7474e-229">Abra un explorador web y vaya a la dirección URL del sitio creado.</span><span class="sxs-lookup"><span data-stu-id="7474e-229">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="7474e-230">Por ejemplo, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span><span class="sxs-lookup"><span data-stu-id="7474e-230">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="7474e-231">En el lado izquierdo, bajo **documentos**, haga clic en `InfoPathSolutions`.</span><span class="sxs-lookup"><span data-stu-id="7474e-231">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="7474e-232">Haga clic en el `PurchaseOrder` archivo para mostrar el **de descarga del archivo** cuadro de diálogo y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="7474e-232">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="7474e-233">InfoPath cargará el formulario.</span><span class="sxs-lookup"><span data-stu-id="7474e-233">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="7474e-234">En el **Purchase Order ID** , escriba `1002`.</span><span class="sxs-lookup"><span data-stu-id="7474e-234">In the **Purchase Order ID** field, type `1002`.</span></span>  
  
5.  <span data-ttu-id="7474e-235">En el **facturar a** , escriba `John Doe`.</span><span class="sxs-lookup"><span data-stu-id="7474e-235">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="7474e-236">En el **cantidad** , escriba `750`.</span><span class="sxs-lookup"><span data-stu-id="7474e-236">In the **Amount** field, type `750`.</span></span>  
  
7.  <span data-ttu-id="7474e-237">En el **fecha del pedido de compra** , escriba `1/2/2005`.</span><span class="sxs-lookup"><span data-stu-id="7474e-237">In the **Purchase Order Date** field, type `1/2/2005`.</span></span>  
  
8.  <span data-ttu-id="7474e-238">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-238">Click **Save**.</span></span>  
  
9. <span data-ttu-id="7474e-239">En el **Guardar como** cuadro de diálogo, escriba `http://<server_name>/sites/WSSAdapterWalkthrough/Source`en el **nombre de archivo** campo y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="7474e-239">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then hit Enter.</span></span>  
  
10. <span data-ttu-id="7474e-240">Tipo `PurchaseOrder2.xml` en el **nombre de archivo** campo y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="7474e-240">Type `PurchaseOrder2.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="7474e-241">Cierre Microsoft Office InfoPath.</span><span class="sxs-lookup"><span data-stu-id="7474e-241">Close Microsoft Office InfoPath.</span></span>  
  
12. <span data-ttu-id="7474e-242">En el explorador Web, en la barra de navegación superior, haga clic en **documentos y listas**.</span><span class="sxs-lookup"><span data-stu-id="7474e-242">In the Web browser, on the top navigation bar, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="7474e-243">En **las bibliotecas de documentos**, haga clic en **destino**.</span><span class="sxs-lookup"><span data-stu-id="7474e-243">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="7474e-244">En la biblioteca de documentos de destino, verá ahora el mensaje incluido en la lista.</span><span class="sxs-lookup"><span data-stu-id="7474e-244">In the Destination document library, you will now see your message listed.</span></span> <span data-ttu-id="7474e-245">También encontrará una copia archivada en la biblioteca de documentos de archivo.</span><span class="sxs-lookup"><span data-stu-id="7474e-245">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="7474e-246">En la biblioteca de documentos de destino, haga clic en `PurchaseOrder1.xml`.</span><span class="sxs-lookup"><span data-stu-id="7474e-246">In the Destination document library, click `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="7474e-247">Tenga en cuenta que este archivo XML se abre en Microsoft Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7474e-247">Note that this XML file is opened in Microsoft Internet Explorer.</span></span>  
  
16. <span data-ttu-id="7474e-248">En la biblioteca de documentos de destino, haga clic en `PurchaseOrder2.xml`.</span><span class="sxs-lookup"><span data-stu-id="7474e-248">In the Destination document library, click `PurchaseOrder2.xml`.</span></span> <span data-ttu-id="7474e-249">Tenga en cuenta que este archivo XML se abre en Microsoft Office InfoPath.</span><span class="sxs-lookup"><span data-stu-id="7474e-249">Note that this XML file is opened in Microsoft Office InfoPath.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7474e-250">En la biblioteca de documentos de destino, la columna de nombre de archivo debe contener el valor del campo PurchaseOrderID y la columna Nombre de socio comercial debe contener el valor del campo BillTo.</span><span class="sxs-lookup"><span data-stu-id="7474e-250">In the Destination document library, the file name column should contain the value of the PurchaseOrderID field and the Partner Name column should contain the value of the BillTo field.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7474e-251">Resumen</span><span class="sxs-lookup"><span data-stu-id="7474e-251">Summary</span></span>  
 <span data-ttu-id="7474e-252">En este tutorial, ha visto cómo agregar una mayor integración con Microsoft InfoPath utilizando el adaptador de Windows SharePoint Services y el enrutamiento por contenidos (CBR).</span><span class="sxs-lookup"><span data-stu-id="7474e-252">In this walkthrough you have seen how to add tighter integration with Microsoft InfoPath using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7474e-253">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7474e-253">Next Steps</span></span>  
 <span data-ttu-id="7474e-254">Ahora que ha realizado este tutorial, realice el [Tutorial: módulo 3: obtener acceso a propiedades de SharePoint desde una orquestación](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) tutorial que se amplía el trabajo que ha realizado en este tutorial, se integra un orquestación al proyecto y se muestra cómo obtener acceso a las propiedades de SharePoint desde dentro de él.</span><span class="sxs-lookup"><span data-stu-id="7474e-254">Now that you have completed this walkthrough, perform the [Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) walkthrough which expands on the work you have done with this walkthrough, integrates an orchestration into the project, and shows you how to access SharePoint properties from within it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7474e-255">Vea también</span><span class="sxs-lookup"><span data-stu-id="7474e-255">See Also</span></span>  
 <span data-ttu-id="7474e-256">[¿Qué es el adaptador de Windows SharePoint Services?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7474e-256">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="7474e-257">Tutoriales del adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="7474e-257">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)