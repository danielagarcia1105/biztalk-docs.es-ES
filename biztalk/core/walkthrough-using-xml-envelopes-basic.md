---
title: 'Tutorial: Utilizar sobres XML (básicos) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9090c4ee7d576bb7ab610cd81637680d837b2cae
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975762"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a><span data-ttu-id="fa620-102">Tutorial: Utilizar sobres XML (básicos)</span><span class="sxs-lookup"><span data-stu-id="fa620-102">Walkthrough: Using XML Envelopes (Basic)</span></span>
<span data-ttu-id="fa620-103">En este ejemplo se demuestra un desensamblado de sobre XML básico implementando parte de un sistema de seguimiento de errores ficticio.</span><span class="sxs-lookup"><span data-stu-id="fa620-103">This example demonstrates basic XML envelope disassembly by implementing part of a fictitious error-tracking system.</span></span> <span data-ttu-id="fa620-104">El ejemplo cumple los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa620-104">The example meets the following requirements:</span></span>  
  
1.  <span data-ttu-id="fa620-105">Los mensajes de error se registran en varias ubicaciones físicas de la compañía y se envían a una ubicación central para su procesamiento en varios sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="fa620-105">Error messages are logged at various physical sites within the company and sent to a central location for processing into various back-end systems.</span></span>  
  
2.  <span data-ttu-id="fa620-106">Los mensajes de error escriben en formato XML.</span><span class="sxs-lookup"><span data-stu-id="fa620-106">Error messages are written in XML format.</span></span>  
  
3.  <span data-ttu-id="fa620-107">Un mensaje de error se puede enviar por sí solo, sin sobre, o como un lote contenido en un sobre.</span><span class="sxs-lookup"><span data-stu-id="fa620-107">An error message can be sent singly without an envelope or as a batch contained within an envelope.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa620-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fa620-108">Prerequisites</span></span>  
 <span data-ttu-id="fa620-109">En este ejemplo que debe estar familiarizado con la creación de proyectos de BizTalk, al firmar un ensamblado y, mediante la consola de administración de BizTalk Server para ver las aplicaciones y los puertos.</span><span class="sxs-lookup"><span data-stu-id="fa620-109">For this example you need to be comfortable with creating BizTalk projects, signing an assembly, and using the BizTalk Server Administration console to view applications and ports.</span></span> <span data-ttu-id="fa620-110">También debe estar familiarizado con las ideas presentadas en [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fa620-110">You should also be comfortable with the ideas presented in [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="what-this-example-does"></a><span data-ttu-id="fa620-111">Qué se hace en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa620-111">What This Example Does</span></span>  
 <span data-ttu-id="fa620-112">En el ejemplo se procesan los mensajes de entrada que contienen un solo mensaje de error o un lote de éstos. Para ello, se define un esquema de sobres y se usa la canalización XmlDisassembler.</span><span class="sxs-lookup"><span data-stu-id="fa620-112">The example processes inbound messages containing either a single error message or a batch of error messages by defining an envelope schema and using the XmlDisassembler pipeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa620-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa620-113">Example</span></span>  
 <span data-ttu-id="fa620-114">Para crear el ejemplo, siga los pasos que se especifican en las secciones que se presentan a continuación.</span><span class="sxs-lookup"><span data-stu-id="fa620-114">To create the example, follow the steps outlined in the following sections.</span></span>  
  
### <a name="create-a-new-biztalk-project"></a><span data-ttu-id="fa620-115">Cree un nuevo proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fa620-115">Create a New BizTalk Project</span></span>  
 <span data-ttu-id="fa620-116">Antes de generar una solución, es preciso crear un proyecto de BizTalk, asegurarse de que se le ha asignado un nombre seguro y un nombre de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa620-116">Before building a solution you need to create a BizTalk project, ensure that it is strongly named, and assign it an application name.</span></span> <span data-ttu-id="fa620-117">La asignación de un nombre de aplicación evita que BizTalk Server implemente la solución en la aplicación de BizTalk predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa620-117">Assigning an application name prevents BizTalk Server from deploying the solution into the default BizTalk application.</span></span>  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a><span data-ttu-id="fa620-118">Para crear y configurar un nuevo proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fa620-118">To create and configure a new BizTalk project</span></span>  
  
1.  <span data-ttu-id="fa620-119">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="fa620-119">Use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project.</span></span> <span data-ttu-id="fa620-120">Asigne al proyecto el **BasicXMLEnvelope**.</span><span class="sxs-lookup"><span data-stu-id="fa620-120">Call the project **BasicXMLEnvelope**.</span></span>  
  
2.  <span data-ttu-id="fa620-121">Genere un archivo de clave y asígnelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-121">Generate a key file and assign it to the project.</span></span> <span data-ttu-id="fa620-122">Para obtener más información acerca de esta tarea, vea [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span><span class="sxs-lookup"><span data-stu-id="fa620-122">For more information about this task, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
3.  <span data-ttu-id="fa620-123">En las propiedades de configuración de implementación para el proyecto, asigne un **nombre de la aplicación** y establecer **reiniciar instancias de Host** a `True`.</span><span class="sxs-lookup"><span data-stu-id="fa620-123">In the deployment configuration properties for the project, assign an **Application Name** and set **Restart Host Instances** to `True`.</span></span> <span data-ttu-id="fa620-124">Al definir esta marca, se ordena al host que borre todas las instancias del ensamblado almacenadas en caché.</span><span class="sxs-lookup"><span data-stu-id="fa620-124">Setting this flag tells the host to clear any cached instances of the assembly.</span></span>  
  
### <a name="create-the-error-schema"></a><span data-ttu-id="fa620-125">Crear el esquema de error</span><span class="sxs-lookup"><span data-stu-id="fa620-125">Create the Error Schema</span></span>  
 <span data-ttu-id="fa620-126">En este paso, se creará el esquema de error.</span><span class="sxs-lookup"><span data-stu-id="fa620-126">In this step you create the Error schema.</span></span> <span data-ttu-id="fa620-127">Define el mensaje clave para el sistema.</span><span class="sxs-lookup"><span data-stu-id="fa620-127">It defines the key message for the system.</span></span>  
  
##### <a name="to-create-the-error-schema"></a><span data-ttu-id="fa620-128">Para crear el esquema de error</span><span class="sxs-lookup"><span data-stu-id="fa620-128">To create the Error schema</span></span>  
  
1.  <span data-ttu-id="fa620-129">Agregue un nuevo esquema denominado "Error" al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-129">Add a new schema named "Error" to the project.</span></span>  
  
2.  <span data-ttu-id="fa620-130">Cambiar el espacio de nombres de destino para el esquema como **http://BasicXMLEnvelope**.</span><span class="sxs-lookup"><span data-stu-id="fa620-130">Change the target namespace for the schema to **http://BasicXMLEnvelope**.</span></span>  
  
3.  <span data-ttu-id="fa620-131">Cambiar la propiedad de esquema **Element FormDefault** en el **avanzadas** categoría a **Qualified**.</span><span class="sxs-lookup"><span data-stu-id="fa620-131">Change the schema property **Element FormDefault** under the **Advanced** category to **Qualified**.</span></span> <span data-ttu-id="fa620-132">Con ello, se indica que el espacio de nombres de destino debe calificar los elementos declarados localmente en un documento de instancia.</span><span class="sxs-lookup"><span data-stu-id="fa620-132">This indicates that locally declared elements must be qualified by the target namespace in an instance document.</span></span>  
  
4.  <span data-ttu-id="fa620-133">Cambie el nombre del nodo raíz "Error" y cree cinco elementos secundarios con los tipos que se indican:</span><span class="sxs-lookup"><span data-stu-id="fa620-133">Rename the root node "Error" and create five child elements with the types indicated:</span></span>  
  
    -   <span data-ttu-id="fa620-134">ID, xs:int</span><span class="sxs-lookup"><span data-stu-id="fa620-134">ID, xs:int</span></span>  
  
    -   <span data-ttu-id="fa620-135">Type, xs:int</span><span class="sxs-lookup"><span data-stu-id="fa620-135">Type, xs:int</span></span>  
  
    -   <span data-ttu-id="fa620-136">Priority, xs:string</span><span class="sxs-lookup"><span data-stu-id="fa620-136">Priority, xs:string</span></span>  
  
    -   <span data-ttu-id="fa620-137">Description, xs:string</span><span class="sxs-lookup"><span data-stu-id="fa620-137">Description, xs:string</span></span>  
  
    -   <span data-ttu-id="fa620-138">ErrorDateTime, xs:string</span><span class="sxs-lookup"><span data-stu-id="fa620-138">ErrorDateTime, xs:string</span></span>  
  
     <span data-ttu-id="fa620-139">El esquema tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="fa620-139">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="fa620-140">![Esquema de Error completado](../core/media/error-schema.gif "error_schema")</span><span class="sxs-lookup"><span data-stu-id="fa620-140">![Completed Error schema](../core/media/error-schema.gif "error_schema")</span></span>  
  
5.  <span data-ttu-id="fa620-141">Cree un mensaje de ejemplo para este esquema</span><span class="sxs-lookup"><span data-stu-id="fa620-141">Create a sample message for this schema.</span></span> <span data-ttu-id="fa620-142">Este mensaje se usa para comprobar que los mensajes sencillos, no contenidos en un sobre, se procesan correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa620-142">This is used to verify that single messages outside of an envelope are processed properly.</span></span> <span data-ttu-id="fa620-143">Un mensaje de ejemplo es:</span><span class="sxs-lookup"><span data-stu-id="fa620-143">An example sample message is:</span></span>  
  
    ```  
    <Error xmlns="http://BasicXMLEnvelope">  
      <ID>1</ID>  
      <Type>5</Type>  
      <Priority>Low</Priority>  
      <Description>Sprocket widget prints reports slowly.</Description>  
      <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
    </Error>  
    ```  
  
     <span data-ttu-id="fa620-144">Guarde este mensaje en un archivo en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-144">Save this message in a file in the project directory.</span></span>  
  
### <a name="create-the-envelope-schema"></a><span data-ttu-id="fa620-145">Crear el esquema de sobres</span><span class="sxs-lookup"><span data-stu-id="fa620-145">Create the Envelope Schema</span></span>  
 <span data-ttu-id="fa620-146">El sobre contiene uno o más mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="fa620-146">The envelope contains one or more error messages.</span></span> <span data-ttu-id="fa620-147">En este ejemplo básico, el sobre no tiene propiedades ni elementos propios.</span><span class="sxs-lookup"><span data-stu-id="fa620-147">In this basic example, the envelope does not have properties and elements of its own.</span></span>  
  
##### <a name="to-create-the-envelope-schema"></a><span data-ttu-id="fa620-148">Para crear el esquema de sobres</span><span class="sxs-lookup"><span data-stu-id="fa620-148">To create the envelope schema</span></span>  
  
1.  <span data-ttu-id="fa620-149">Agregue un nuevo esquema denominado "Envelope" al proyecto BasicXMLEnvelope.</span><span class="sxs-lookup"><span data-stu-id="fa620-149">Add a new schema named "Envelope" to the BasicXMLEnvelope project.</span></span>  
  
2.  <span data-ttu-id="fa620-150">Cambiar el espacio de nombres de destino para **http://BasicXMLEnvelope**.</span><span class="sxs-lookup"><span data-stu-id="fa620-150">Change the target namespace to **http://BasicXMLEnvelope**.</span></span>  
  
3.  <span data-ttu-id="fa620-151">Cambie el nombre del nodo raíz de "Root" a "Envelope".</span><span class="sxs-lookup"><span data-stu-id="fa620-151">Change the name of the root node from "Root" to "Envelope".</span></span>  
  
4.  <span data-ttu-id="fa620-152">Ahora, marque el esquema como esquema de sobres.</span><span class="sxs-lookup"><span data-stu-id="fa620-152">Now mark the schema as an envelope schema.</span></span> <span data-ttu-id="fa620-153">Haga clic en el  **\<esquema\>**  nodo.</span><span class="sxs-lookup"><span data-stu-id="fa620-153">Click the **\<Schema\>** node.</span></span> <span data-ttu-id="fa620-154">En el panel Propiedades, establezca la propiedad de referencia de esquema **sobres** a `OK`.</span><span class="sxs-lookup"><span data-stu-id="fa620-154">In the Properties pane, set the schema reference property **Envelope** to `OK`.</span></span>  
  
5.  <span data-ttu-id="fa620-155">Establecer el **XPath de cuerpo** propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa620-155">Set the **Body XPath** property.</span></span> <span data-ttu-id="fa620-156">Para ello, haga clic en el **sobres** nodo.</span><span class="sxs-lookup"><span data-stu-id="fa620-156">To do this, click the **Envelope** node.</span></span> <span data-ttu-id="fa620-157">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón en el **XPath de cuerpo** propiedad, seleccione **sobres**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-157">In the Properties window, click the ellipsis (**...**) button in the **Body XPath** property, select **Envelope**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="fa620-158">Agregue un elemento secundario Cualquier elemento al nodo Envelope.</span><span class="sxs-lookup"><span data-stu-id="fa620-158">Add an Any element child to the Envelope node.</span></span> <span data-ttu-id="fa620-159">El mensaje de error estará contenido en este elemento.</span><span class="sxs-lookup"><span data-stu-id="fa620-159">The error message will be contained in this element.</span></span> <span data-ttu-id="fa620-160">El esquema tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="fa620-160">Your schema should look like the following:</span></span>  
  
     <span data-ttu-id="fa620-161">![Esquema de sobre completado](../core/media/envelope-schema.gif "envelope_schema")</span><span class="sxs-lookup"><span data-stu-id="fa620-161">![Completed envelope schema](../core/media/envelope-schema.gif "envelope_schema")</span></span>  
  
7.  <span data-ttu-id="fa620-162">Cree un mensaje de ejemplo que contenga un sobre y uno o varios ejemplos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa620-162">Create a sample message containing an envelope and one or more sample messages.</span></span> <span data-ttu-id="fa620-163">Es un mensaje de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa620-163">An example message is:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     <span data-ttu-id="fa620-164">Guarde este mensaje en un archivo en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-164">Save this message in a file in the project directory.</span></span>  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a><span data-ttu-id="fa620-165">Implementar y configurar los puertos de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="fa620-165">Deploy and Configure the Send and Receive Ports</span></span>  
 <span data-ttu-id="fa620-166">Con los esquemas creados, será necesario compilar el proyecto e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="fa620-166">With the schemas created, you need to compile and deploy the project.</span></span> <span data-ttu-id="fa620-167">Una vez implementado, se podrá utilizar la consola de administración de BizTalk Server para configurar los puertos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-167">After it is deployed, you can use the BizTalk Server Administration console to configure the send and receive ports.</span></span>  
  
##### <a name="to-deploy-basicxmlenvelope"></a><span data-ttu-id="fa620-168">Para implementar BasicXMLEnvelope</span><span class="sxs-lookup"><span data-stu-id="fa620-168">To deploy BasicXMLEnvelope</span></span>  
  
1.  <span data-ttu-id="fa620-169">De [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], elija **implementar BasicXMLEnvelope** en el menú Generar.</span><span class="sxs-lookup"><span data-stu-id="fa620-169">From [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], choose **Deploy BasicXMLEnvelope** from the Build menu.</span></span> <span data-ttu-id="fa620-170">Se generará e implementará en BizTalk Server como la aplicación "BasicXMLEnvelope".</span><span class="sxs-lookup"><span data-stu-id="fa620-170">This will build and deploy it to BizTalk Server as the application "BasicXMLEnvelope".</span></span>  
  
2.  <span data-ttu-id="fa620-171">En la consola de administración de BizTalk Server, expanda el **aplicaciones** grupo para comprobar que **BasicXMLEnvelope** está presente como una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="fa620-171">In the BizTalk Server Administration console, expand the **Applications** group to verify that **BasicXMLEnvelope** is present as a custom application.</span></span>  
  
##### <a name="to-configure-the-receive-port"></a><span data-ttu-id="fa620-172">Para configurar el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="fa620-172">To configure the receive port</span></span>  
  
1.  <span data-ttu-id="fa620-173">Utilice el Explorador de Windows para crear un directorio denominado "Receive" en la **BasicXMLEnvelope** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-173">Use Windows Explorer to create a directory named "Receive" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="fa620-174">En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de recepción**, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="fa620-174">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="fa620-175">En el **propiedades de puerto de recepción** diálogo cuadro, establezca el nombre del puerto de "Recepción".</span><span class="sxs-lookup"><span data-stu-id="fa620-175">In the **Receive Port Properties** dialog box, set the name of the port to "Receive".</span></span>  
  
4.  <span data-ttu-id="fa620-176">Haga clic en ubicaciones de recepción y, a continuación, haga clic en **New** para agregar un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-176">Right-click Receive Locations, and then click **New** to add a receive port.</span></span> <span data-ttu-id="fa620-177">Defina "ReceiveError" como nombre del nuevo puerto.</span><span class="sxs-lookup"><span data-stu-id="fa620-177">Name the new port "ReceiveError".</span></span> <span data-ttu-id="fa620-178">Establecer el **canalización de recepción** a **XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="fa620-178">Set the **Receive Pipeline** to **XMLReceive**.</span></span> <span data-ttu-id="fa620-179">Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-179">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="fa620-180">Seleccione el directorio de recepción creado anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-180">Select the receive directory created above and click **OK**.</span></span> <span data-ttu-id="fa620-181">Con ello, el puerto de recepción debería estar configurado.</span><span class="sxs-lookup"><span data-stu-id="fa620-181">Your receive port should now be configured.</span></span> <span data-ttu-id="fa620-182">Haga clic en **Aceptar** para cerrar.</span><span class="sxs-lookup"><span data-stu-id="fa620-182">Click **OK** to close.</span></span>  
  
##### <a name="to-configure-the-send-port"></a><span data-ttu-id="fa620-183">Para configurar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="fa620-183">To configure the send port</span></span>  
  
1.  <span data-ttu-id="fa620-184">Utilice el Explorador de Windows para crear un directorio denominado "Send" en la **BasicXMLEnvelope** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-184">Use Windows Explorer to create a directory named "Send" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="fa620-185">En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="fa620-185">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="fa620-186">En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto de "Envío".</span><span class="sxs-lookup"><span data-stu-id="fa620-186">In the **Send Port Properties** dialog box, set the name of the port to "Send".</span></span>  
  
4.  <span data-ttu-id="fa620-187">Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-187">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="fa620-188">Establece la carpeta de destino en el directorio de envío que creó anteriormente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-188">Set the destination folder to the send directory you created earlier and click **OK**.</span></span>  
  
5.  <span data-ttu-id="fa620-189">Haga clic en **filtros** y agregue un filtro único:</span><span class="sxs-lookup"><span data-stu-id="fa620-189">Click **Filters** and add a single filter:</span></span>  
  
    -   <span data-ttu-id="fa620-190">BTS. MessageType == **http://BasicXMLEnvelope#Error**</span><span class="sxs-lookup"><span data-stu-id="fa620-190">BTS.MessageType == **http://BasicXMLEnvelope#Error**</span></span>  
  
6.  <span data-ttu-id="fa620-191">Haga clic en **Aceptar** para completar la configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="fa620-191">Click **OK** to complete the send port configuration.</span></span> <span data-ttu-id="fa620-192">Con ello, el puerto de envío debería estar configurado.</span><span class="sxs-lookup"><span data-stu-id="fa620-192">Your send port should be configured.</span></span>  
  
### <a name="run-the-example"></a><span data-ttu-id="fa620-193">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa620-193">Run the Example</span></span>  
 <span data-ttu-id="fa620-194">Ha llegado el momento de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa620-194">It is now time to run the example.</span></span> <span data-ttu-id="fa620-195">Tras utilizar la consola de administración de BizTalk Server para iniciar la aplicación BasicXMLEnvelope, se copiarán los archivos de prueba en la ubicación de recepción y se observará lo que se produce en la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="fa620-195">After using the BizTalk Server Management console to start the BasicXMLEnvelope application, you will copy the test files to the receive location and observe what is produced in the send location.</span></span>  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a><span data-ttu-id="fa620-196">Para ejecutar el ejemplo BasicXMLEnvelope</span><span class="sxs-lookup"><span data-stu-id="fa620-196">To run the BasicXMLEnvelope example</span></span>  
  
1.  <span data-ttu-id="fa620-197">En la consola de administración de BizTalk Server, haga clic en el **BasicXMLEnvelope** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-197">In the BizTalk Server Administration console, right-click the **BasicXMLEnvelope** application and then click **Start**.</span></span> <span data-ttu-id="fa620-198">Con ello, se darán de alta los puertos de recepción y envío y se iniciarán.</span><span class="sxs-lookup"><span data-stu-id="fa620-198">This will enlist and start the send and receive ports.</span></span>  
  
2.  <span data-ttu-id="fa620-199">Coloque cada uno de archivos de ejemplo en el directorio de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-199">Drop each of the sample files into the receive directory.</span></span> <span data-ttu-id="fa620-200">Si usa los ejemplos facilitados anteriormente, encontrará tres mensajes de error individuales en la ubicación de envío cuando se complete el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fa620-200">If you use the samples given earlier, you should find three individual error messages in the send location when processing is completed.</span></span>  
  
## <a name="extending-the-example"></a><span data-ttu-id="fa620-201">Ampliar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa620-201">Extending the Example</span></span>  
 <span data-ttu-id="fa620-202">Puede ampliar el ejemplo para adaptarlo a otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="fa620-202">You can extend the example to accommodate other requirements.</span></span> <span data-ttu-id="fa620-203">En esta sección se tratan dos escenarios comunes.</span><span class="sxs-lookup"><span data-stu-id="fa620-203">This section addresses two common scenarios:</span></span>  
  
-   <span data-ttu-id="fa620-204">Si se envía un lote de errores dentro de un sobre, los errores en mensajes individuales del desensamblado no deberían prohibir el procesamiento ulterior de los demás mensajes sin errores.</span><span class="sxs-lookup"><span data-stu-id="fa620-204">If a batch of errors is submitted within an envelope, individual message failures in disassembly should not prohibit other nonfailing messages from being further processed.</span></span>  
  
-   <span data-ttu-id="fa620-205">Los errores deberán enviarse a distintas ubicaciones según la prioridad del error.</span><span class="sxs-lookup"><span data-stu-id="fa620-205">Errors should be delivered to different locations based on error priority.</span></span> <span data-ttu-id="fa620-206">Los mensajes de alta prioridad se envían antes, mientras que los demás niveles de prioridad se administran por los canales normales.</span><span class="sxs-lookup"><span data-stu-id="fa620-206">High-priority messages are expedited while other priorities are handled through normal channels.</span></span>  
  
 <span data-ttu-id="fa620-207">En las siguientes secciones se amplía el ejemplo de modo que incluya estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="fa620-207">The following sections extend the example to handle these requirements.</span></span>  
  
### <a name="recoverable-interchange-processing"></a><span data-ttu-id="fa620-208">Procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="fa620-208">Recoverable Interchange Processing</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fa620-209">admite el procesamiento de intercambio recuperable.</span><span class="sxs-lookup"><span data-stu-id="fa620-209"> supports recoverable interchange processing.</span></span> <span data-ttu-id="fa620-210">Esta característica permite garantizar que los lotes de mensajes con errores se traten individualmente en el desensamblado, y no como un lote.</span><span class="sxs-lookup"><span data-stu-id="fa620-210">By using this feature, you can ensure that batches of messages fail individually in disassembly and not as a batch.</span></span>  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a><span data-ttu-id="fa620-211">Para configurar el ejemplo para el procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="fa620-211">To configure the example for recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="fa620-212">En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de recepción**y, a continuación, haga doble clic en el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-212">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, click **Receive Ports**, and then double-click the Receive port.</span></span> <span data-ttu-id="fa620-213">Éste es el puerto creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fa620-213">This is the port you created previously.</span></span>  
  
2.  <span data-ttu-id="fa620-214">En el **propiedades de puerto de recepción** cuadro de diálogo, haga clic en **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="fa620-214">In the **Receive Port Properties** dialog box, click **Receive Locations**.</span></span> <span data-ttu-id="fa620-215">Haga clic en **propiedades** para que aparezca el **propiedades de ubicación de recepción ReceiveError** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa620-215">Click **Properties** to bring up the **ReceiveError Receive Location Properties** dialog box.</span></span> <span data-ttu-id="fa620-216">Haga clic en el botón de puntos suspensivos (**...** ) botón la **canalización de recepción**.</span><span class="sxs-lookup"><span data-stu-id="fa620-216">Click the ellipsis (**...**) button for the **Receive Pipeline**.</span></span>  
  
3.  <span data-ttu-id="fa620-217">En el **configurar canalización: XMLReceive** cuadro de diálogo, establezca la **procesamiento de intercambio recuperable** propiedad `True`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-217">In the **Configure Pipeline - XMLReceive** dialog box, set the **Recoverable Interchange Processing** property to `True`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fa620-218">Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo y, a continuación, haga clic en **Aceptar** para cerrar el **propiedades de puerto de recepción** cuadro de diálogo cuadro.</span><span class="sxs-lookup"><span data-stu-id="fa620-218">Click **OK** to close the **Receive Location Properties** dialog box, and then click **OK** to close the **Receive Port Properties** dialog box.</span></span>  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a><span data-ttu-id="fa620-219">Para crear un archivo de ejemplo y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa620-219">To create a sample file and run the example</span></span>  
  
1.  <span data-ttu-id="fa620-220">Para crear un archivo de ejemplo, realice una copia del archivo de ejemplo de sobre creado en el ejemplo, agregue un espacio de nombres inexistente a una de las instancias de error y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="fa620-220">To create a sample file, make a copy of the envelope sample file created in the example, add a nonexistent namespace to one of the Error instances, and then save the file:</span></span>  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  <span data-ttu-id="fa620-221">En la consola de administración de BizTalk Server, haga clic en **aplicaciones** y compruebe que la **BasicXMLEnvelope** aplicación se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="fa620-221">In the BizTalk Server Administration console, click **Applications** and verify that the **BasicXMLEnvelope** application is running.</span></span>  
  
3.  <span data-ttu-id="fa620-222">Coloque el mensaje en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-222">Drop the message in the receive location.</span></span> <span data-ttu-id="fa620-223">Después del procesamiento, deberá encontrar el primer mensaje en la ubicación de envío y el segundo, de baja prioridad, en la cola de suspensión.</span><span class="sxs-lookup"><span data-stu-id="fa620-223">After processing, you should find the first message in the send location and the second, low-priority, message in the Suspended queue.</span></span>  
  
### <a name="content-based-routing-cbr"></a><span data-ttu-id="fa620-224">Enrutamiento por contenidos (CBR)</span><span class="sxs-lookup"><span data-stu-id="fa620-224">Content-Based Routing (CBR)</span></span>  
 <span data-ttu-id="fa620-225">También puede utilizar el enrutamiento por contenidos para enrutar mensajes según su contenido.</span><span class="sxs-lookup"><span data-stu-id="fa620-225">You can use content-based routing to route messages based on their content.</span></span> <span data-ttu-id="fa620-226">En este escenario, en enrutamiento se basa en la prioridad. Los mensajes con prioridad alta van a una ubicación de envío y los mensajes con prioridad media o baja van a otra.</span><span class="sxs-lookup"><span data-stu-id="fa620-226">In this scenario, routing is based on priority, with High messages going to one send location and Low and Medium messages going to a different send location.</span></span>  
  
 <span data-ttu-id="fa620-227">Para ampliar el ejemplo, debe completar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa620-227">To extend the sample, you must complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="fa620-228">Promover la **prioridad** campo del esquema de Error en el proyecto BasicXMLEnvelope.</span><span class="sxs-lookup"><span data-stu-id="fa620-228">Promote the **Priority** field in the Error schema in the BasicXMLEnvelope project.</span></span> <span data-ttu-id="fa620-229">El enrutamiento por contenidos se basa en propiedades promocionadas para enrutar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa620-229">Content-based routing relies on promoted properties to route messages.</span></span> <span data-ttu-id="fa620-230">Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fa620-230">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
2.  <span data-ttu-id="fa620-231">Cree y configure dos puertos adicionales.</span><span class="sxs-lookup"><span data-stu-id="fa620-231">Create and configure two additional send ports.</span></span> <span data-ttu-id="fa620-232">Los puertos usan un filtro para garantizar que reciben los mensajes apropiados.</span><span class="sxs-lookup"><span data-stu-id="fa620-232">The ports use a filter to ensure they receive appropriate messages.</span></span>  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a><span data-ttu-id="fa620-233">Para promocionar el campo Priority del esquema de error</span><span class="sxs-lookup"><span data-stu-id="fa620-233">To promote the Priority field in the Error schema</span></span>  
  
1.  <span data-ttu-id="fa620-234">Con el **BasicXMLEnvelope** proyecto abierto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **Error** esquema y expanda el **Error** nodo.</span><span class="sxs-lookup"><span data-stu-id="fa620-234">With the **BasicXMLEnvelope** project open in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Error** schema and expand the **Error** node.</span></span>  
  
2.  <span data-ttu-id="fa620-235">Haga clic en el **prioridad** elemento, seleccione **promover**y, a continuación, haga clic en **promoción rápida**.</span><span class="sxs-lookup"><span data-stu-id="fa620-235">Right-click the **Priority** element, point to **Promote**, and then click **Quick Promote**.</span></span>  
  
3.  <span data-ttu-id="fa620-236">Haga clic en **Aceptar** para confirmar la adición de un nuevo esquema de propiedad para las propiedades promocionadas.</span><span class="sxs-lookup"><span data-stu-id="fa620-236">Click **OK** to confirm the addition of a new property schema for the promoted properties.</span></span>  
  
4.  <span data-ttu-id="fa620-237">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, abra el nuevo esquema de propiedades PropertySchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="fa620-237">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, open the new property schema PropertySchema.xsd.</span></span> <span data-ttu-id="fa620-238">Quite "Field1" del esquema.</span><span class="sxs-lookup"><span data-stu-id="fa620-238">Remove "Field1" from the schema.</span></span>  
  
5.  <span data-ttu-id="fa620-239">Vuelva a compilar e implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="fa620-239">Now recompile and redeploy the solution.</span></span> <span data-ttu-id="fa620-240">En el menú Generar, elija Implementar BasicXMLEnvelope.</span><span class="sxs-lookup"><span data-stu-id="fa620-240">On the Build menu, choose Deploy BasicXMLEnvelope.</span></span>  
  
6.  <span data-ttu-id="fa620-241">El proyecto se configuró para restablecer la instancia de host cuando se vuelve a implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="fa620-241">The project was configured to reset the host instance when the solution is redeployed.</span></span> <span data-ttu-id="fa620-242">Si lo ha modificado, deberá detener e iniciar el host.</span><span class="sxs-lookup"><span data-stu-id="fa620-242">If you have changed this, you need to stop and start the host.</span></span>  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a><span data-ttu-id="fa620-243">Para configurar el puerto de envío de prioridad media y baja</span><span class="sxs-lookup"><span data-stu-id="fa620-243">To configure the low and medium-priority send port</span></span>  
  
1.  <span data-ttu-id="fa620-244">Utilice el Explorador de Windows para crear un directorio denominado "SendLowMediumPriority" en la **BasicXMLEnvelope** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-244">Use Windows Explorer to create a directory named "SendLowMediumPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="fa620-245">En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="fa620-245">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="fa620-246">En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto "SendLowMediumPriority".</span><span class="sxs-lookup"><span data-stu-id="fa620-246">In the **Send Port Properties** dialog box, set the name of the port to "SendLowMediumPriority".</span></span>  
  
4.  <span data-ttu-id="fa620-247">Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-247">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="fa620-248">Defina el directorio creado anteriormente como la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="fa620-248">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="fa620-249">Haga clic en **Aceptar** para cerrar.</span><span class="sxs-lookup"><span data-stu-id="fa620-249">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="fa620-250">Haga clic en **filtros** y agregue tres expresiones de filtro:</span><span class="sxs-lookup"><span data-stu-id="fa620-250">Click **Filters** and add three filter expressions:</span></span>  
  
    -   <span data-ttu-id="fa620-251">BTS.MessageType == http://BasicXMLEnvelope#Error And</span><span class="sxs-lookup"><span data-stu-id="fa620-251">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="fa620-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span><span class="sxs-lookup"><span data-stu-id="fa620-252">BasicXMLEnvelope.PropertySchema.Priority == Low Or</span></span>  
  
    -   <span data-ttu-id="fa620-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span><span class="sxs-lookup"><span data-stu-id="fa620-253">BasicXMLEnvelope.PropertySchema.Priority == Medium</span></span>  
  
6.  <span data-ttu-id="fa620-254">Haga clic en **Aceptar** para completar la configuración de puerto de envío de prioridad Media y baja.</span><span class="sxs-lookup"><span data-stu-id="fa620-254">Click **OK** to complete the low and medium-priority send port configuration.</span></span>  
  
##### <a name="to-configure-the-high-priority-send-port"></a><span data-ttu-id="fa620-255">Para configurar el puerto de envío de prioridad alta</span><span class="sxs-lookup"><span data-stu-id="fa620-255">To configure the high-priority send port</span></span>  
  
1.  <span data-ttu-id="fa620-256">Utilice el Explorador de Windows para crear un directorio denominado "SendHighPriority" en la **BasicXMLEnvelope** directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa620-256">Use Windows Explorer to create a directory named "SendHighPriority" under the **BasicXMLEnvelope** project directory.</span></span>  
  
2.  <span data-ttu-id="fa620-257">En la consola de administración de BizTalk Server, expanda el **BasicXMLEnvelope** aplicación, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en  **Unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="fa620-257">In the BizTalk Server Administration console, expand the **BasicXMLEnvelope** application, right-click **Send Ports**, point to **New**, and then click **Static One-Way**.</span></span>  
  
3.  <span data-ttu-id="fa620-258">En el **propiedades de puerto de envío** diálogo cuadro, establezca el nombre del puerto "SendHighPriority".</span><span class="sxs-lookup"><span data-stu-id="fa620-258">In the **Send Port Properties** dialog box, set the name of the port to "SendHighPriority".</span></span>  
  
4.  <span data-ttu-id="fa620-259">Para **tipo de transporte**, seleccione **archivo**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-259">For **Transport Type**, select **FILE**, and then click **Configure**.</span></span> <span data-ttu-id="fa620-260">Defina el directorio creado anteriormente como la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="fa620-260">Set the destination folder to the directory you created earlier.</span></span> <span data-ttu-id="fa620-261">Haga clic en **Aceptar** para cerrar.</span><span class="sxs-lookup"><span data-stu-id="fa620-261">Click **OK** to close.</span></span>  
  
5.  <span data-ttu-id="fa620-262">Haga clic en **filtros** y agregue dos expresiones de filtro:</span><span class="sxs-lookup"><span data-stu-id="fa620-262">Click **Filters** and add two filter expressions:</span></span>  
  
    -   <span data-ttu-id="fa620-263">BTS.MessageType == http://BasicXMLEnvelope#Error And</span><span class="sxs-lookup"><span data-stu-id="fa620-263">BTS.MessageType == http://BasicXMLEnvelope#Error And</span></span>  
  
    -   <span data-ttu-id="fa620-264">BasicXMLEnvelope.PropertySchema.Priority == High</span><span class="sxs-lookup"><span data-stu-id="fa620-264">BasicXMLEnvelope.PropertySchema.Priority == High</span></span>  
  
6.  <span data-ttu-id="fa620-265">Haga clic en **Aceptar** para completar la configuración de puerto de envío de prioridad alta.</span><span class="sxs-lookup"><span data-stu-id="fa620-265">Click **OK** to complete the high-priority send port configuration.</span></span>  
  
##### <a name="to-test-the-routing-solution"></a><span data-ttu-id="fa620-266">Para probar la solución de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fa620-266">To test the routing solution</span></span>  
  
1.  <span data-ttu-id="fa620-267">En la consola de administración de BizTalk Server, expanda el **aplicaciones** de grupo, haga clic en el **BasicXMLEnvelope** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-267">In the BizTalk Server Administration console, expand the **Applications** group, right-click the **BasicXMLEnvelope** application, and then click **Start**.</span></span> <span data-ttu-id="fa620-268">Cuando se le pida que confirme, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fa620-268">When prompted to confirm, click **Start**.</span></span> <span data-ttu-id="fa620-269">Se darán de alta los nuevos puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="fa620-269">This enlists the new send ports.</span></span>  
  
2.  <span data-ttu-id="fa620-270">Coloque el mensaje de prueba en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa620-270">Drop the test message into the receive location.</span></span> <span data-ttu-id="fa620-271">Observe cómo se enrutan los mensajes de error a las distintas ubicaciones de envío:</span><span class="sxs-lookup"><span data-stu-id="fa620-271">Notice how error messages are routed to the different send locations:</span></span>  
  
    -   <span data-ttu-id="fa620-272">Los mensajes de error con prioridad baja, media o alta que no tengan errores al procesarse se enrutan a la ubicación de envío original (configurada en el ejemplo principal) y a las ubicaciones de envío por prioridad.</span><span class="sxs-lookup"><span data-stu-id="fa620-272">Error messages that have a Low, Medium, or High priority and do not fail message processing are routed both to the original send location (configured in the core example) and the send location by priority.</span></span> <span data-ttu-id="fa620-273">Para los mensajes con prioridad media o baja, aparece una copia en la ubicación de envío original y en la ubicación de envío de prioridad media o baja.</span><span class="sxs-lookup"><span data-stu-id="fa620-273">For messages with a Low or Medium priority, a copy appears in both the original send location and the Low/Medium send location.</span></span>  
  
    -   <span data-ttu-id="fa620-274">Si el procesamiento de intercambio recuperable está habilitado, los mensajes de error con errores no se enrutan, y los mensajes sin errores se enrutan correctamente según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="fa620-274">If recoverable interchange processing is enabled, the failed error message is not routed and the nonfailed message is properly routed as expected.</span></span> <span data-ttu-id="fa620-275">Los mensajes con errores no se enrutan porque este tipo de mensaje no coincide con el tipo usado en los filtros configurados.</span><span class="sxs-lookup"><span data-stu-id="fa620-275">The failed message is not routed because its message type does not match the type used in the configured filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa620-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa620-276">See Also</span></span>  
 <span data-ttu-id="fa620-277">[Procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md) </span><span class="sxs-lookup"><span data-stu-id="fa620-277">[Recoverable Interchange Processing](../core/recoverable-interchange-processing.md) </span></span>  
 <span data-ttu-id="fa620-278">[Promoción de propiedades](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fa620-278">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 [<span data-ttu-id="fa620-279">CBRSample (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="fa620-279">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)