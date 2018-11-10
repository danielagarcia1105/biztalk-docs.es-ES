---
title: Mediante la característica con canalizaciones de pruebas unitarias | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d58bfa4-322b-455f-a062-5bd44d368f57
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e437df707ace58eef6de9dc9f7eb65d888309a9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752644"
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a><span data-ttu-id="44ef6-102">Uso de la característica de pruebas de unidades con canalizaciones</span><span class="sxs-lookup"><span data-stu-id="44ef6-102">Using the Unit Testing Feature with Pipelines</span></span>
<span data-ttu-id="44ef6-103">En este tema se muestra el modo de usar la función de pruebas de unidad para agregar una prueba de unidad para la canalización al ejemplo de canalización FlatFileReceive.</span><span class="sxs-lookup"><span data-stu-id="44ef6-103">This topic demonstrates how to use the unit testing feature to add a unit test for the pipeline in the FlatFileReceive pipeline example.</span></span> <span data-ttu-id="44ef6-104">Las pruebas unitarias de canalización es similar a la herramienta Pipeline.exe que se documenta aquí: [herramientas de canalización](../core/pipeline-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44ef6-104">Pipeline unit testing is similar to the Pipeline.exe tool that is documented here: [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="44ef6-105">Al habilitar pruebas unitarias en el **implementación** se deriva de ficha de propiedades del proyecto, la clase de canalización en el proyecto **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-105">When you enable unit testing on the **Deployment** tab of the project properties, the pipeline class in your project is derived from **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.</span></span>  <span data-ttu-id="44ef6-106">Esta clase modela parte de la misma funcionalidad expuesta por la herramienta Pipeline.exe.</span><span class="sxs-lookup"><span data-stu-id="44ef6-106">This class models some of the same functionality exposed by the Pipeline.exe tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="44ef6-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44ef6-107">Prerequisites</span></span>  
 <span data-ttu-id="44ef6-108">Primero debe seguir los pasos para generar la muestra FlatFileReceive y familiarizarse con dicha muestra.</span><span class="sxs-lookup"><span data-stu-id="44ef6-108">You must first follow the steps for building the FlatFileReceive sample and become familiar with that sample.</span></span> <span data-ttu-id="44ef6-109">La documentación que incluye los pasos para generar la muestra FlatFileReceive puede encontrarse aquí: [FlatFileReceive (ejemplo de BizTalk Server)](../core/flatfilereceive-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="44ef6-109">The documentation that includes the steps for building the FlatFileReceive sample can be found here: [FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span>  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="44ef6-110">Adición de un proyecto de prueba de unidad al ejemplo FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="44ef6-110">Adding a Unit Test Project to the FlatFileReceive Sample</span></span>  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="44ef6-111">Procedimiento para agregar un proyecto de prueba de unidad al ejemplo FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="44ef6-111">To add a unit test project to the FlatFileReceive sample</span></span>  
  
1.  <span data-ttu-id="44ef6-112">En Visual Studio, abra el archivo de solución FlatFileReceive.sln.</span><span class="sxs-lookup"><span data-stu-id="44ef6-112">In Visual Studio, open the FlatFileReceive.sln solution file.</span></span>  
  
2.  <span data-ttu-id="44ef6-113">En el Explorador de soluciones, haga clic en el **FlatFileReceive** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-113">In Solution Explorer, right-click the **FlatFileReceive** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="44ef6-114">En el Diseñador de proyectos, haga clic en el **implementación** ficha de página de propiedades y establezca **habilitar pruebas de unidades** a `True`.</span><span class="sxs-lookup"><span data-stu-id="44ef6-114">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="44ef6-115">Cierre la página de propiedades del proyecto guardando los cambios.</span><span class="sxs-lookup"><span data-stu-id="44ef6-115">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="44ef6-116">En el menú principal, haga clic en **compilar**y, a continuación, haga clic en **recompilar solución**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-116">On the main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="44ef6-117">En el menú principal, haga clic en **prueba**y, a continuación, haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-117">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="44ef6-118">En el **agregar nueva prueba** cuadro de diálogo, seleccione **crear un nuevo objeto Visual C# proyecto de prueba** para el **agregar a proyecto de prueba** campo.</span><span class="sxs-lookup"><span data-stu-id="44ef6-118">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for the **Add to Test Project** field.</span></span> <span data-ttu-id="44ef6-119">Seleccione **Asistente para pruebas unitarias** en el **plantillas** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-119">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="44ef6-120">En el **nuevo proyecto de prueba** diálogo cuadro, deje el nombre del proyecto como **TestProject1** y haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-120">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="44ef6-121">En el **crear pruebas unitarias** cuadro de diálogo, expanda los tipos y seleccione el **FFReceivePipeline()** constructor bajo el **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline**  nodo.</span><span class="sxs-lookup"><span data-stu-id="44ef6-121">In the **Create Unit Tests** dialog box, expand the types and select the **FFReceivePipeline()** constructor under the **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline** node.</span></span> <span data-ttu-id="44ef6-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-122">Click **OK**.</span></span>  
  
## <a name="adding-test-code-to-test-the-pipeline"></a><span data-ttu-id="44ef6-123">Agregar código de prueba para probar la canalización</span><span class="sxs-lookup"><span data-stu-id="44ef6-123">Adding Test Code to Test the Pipeline</span></span>  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a><span data-ttu-id="44ef6-124">Procedimiento para agregar código de prueba para probar la canalización</span><span class="sxs-lookup"><span data-stu-id="44ef6-124">To add test code to test the pipeline</span></span>  
  
1.  <span data-ttu-id="44ef6-125">Agregue las siguientes referencias a la **TestProject1** proyecto:</span><span class="sxs-lookup"><span data-stu-id="44ef6-125">Add the following references to the **TestProject1** project:</span></span>  
  
    -   <span data-ttu-id="44ef6-126">Interoperabilidad de canalizaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="44ef6-126">BizTalk Pipeline Interop</span></span>  
  
    -   <span data-ttu-id="44ef6-127">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="44ef6-127">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="44ef6-128">Tipos de base de Microsoft XLANG/s</span><span class="sxs-lookup"><span data-stu-id="44ef6-128">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="44ef6-129">En el Explorador de soluciones, abra FFReceivePipelineTest.cs y agregue las siguientes directivas a la parte superior de dicho archivo:</span><span class="sxs-lookup"><span data-stu-id="44ef6-129">In Solution Explorer, open FFReceivePipelineTest.cs and add the following directives to the top of that file:</span></span>  
  
    ```  
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="44ef6-130">Desplácese hasta la parte inferior del archivo y reemplace el **FFReceivePipelineConstructorTest** método con el código siguiente, que comprueba que existen las entradas de la canalización antes de probar la canalización.</span><span class="sxs-lookup"><span data-stu-id="44ef6-130">Scroll to the bottom of the file and replace the **FFReceivePipelineConstructorTest** method with the following code, which verifies that the pipeline inputs exist before testing the pipeline.</span></span> <span data-ttu-id="44ef6-131">Este código también comprueba que se genera un mensaje conforme con el esquema de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="44ef6-131">This code also verifies that a message conforming to the flat file schema is generated.</span></span>  
  
    ```  
    [TestMethod()]  
    public void FFReceivePipelineUnitTest()  
    {  
        //=== Pipeline class derived from TestableReceivePipeline ===//  
        FFReceivePipeline target = new FFReceivePipeline();  
  
        //=== Collection of messages to test the flat file pipeline ===//  
        StringCollection documents = new StringCollection();  
        string strSourcePO_XML = @".\..\..\..\FlatFileReceive_in.txt";  
        Assert.IsTrue(File.Exists(strSourcePO_XML));  
        documents.Add(strSourcePO_XML);  
  
        //=== Only a body part for this test message so an empty ===//  
        //=== collection will be passed.                         ===//  
        StringCollection parts = new StringCollection();  
  
        //=== Dictionary mapping the schema to the namespace and type ===//  
        //=== as displayed in the properties window for the *.xsd     ===//  
        Dictionary<string, string> schemas = new Dictionary<string, string>();  
        string SchemaFile = @".\..\..\..\PO.xsd";  
        Assert.IsTrue(File.Exists(SchemaFile));  
        schemas.Add("Microsoft.Samples.BizTalk.FlatFileReceive.PO", SchemaFile);  
  
        //=== Test the execution of the pipeline using the inputs ===//  
        target.TestPipeline(documents, parts, schemas);  
  
        //=== Validate that the pipeline test produced the message ===//  
        //=== which conforms to the schema.                        ===//  
        string[] strMessages = Directory.GetFiles(testContextInstance.TestDir + "\\out","Message*.out");              
        Assert.IsTrue(strMessages.Length > 0);                          
        PO PO_target = new PO();  
        foreach(string outFile in strMessages)  
        {  
          Assert.IsTrue(PO_target.ValidateInstance(outFile,Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
        }                       
    }  
    ```  
  
## <a name="building-and-running-the-unit-test"></a><span data-ttu-id="44ef6-132">Generar y ejecutar la prueba de la unidad</span><span class="sxs-lookup"><span data-stu-id="44ef6-132">Building and Running the Unit Test</span></span>  
  
#### <a name="to-build-and-run-the-unit-test"></a><span data-ttu-id="44ef6-133">Procedimiento para generar y ejecutar la prueba de unidad</span><span class="sxs-lookup"><span data-stu-id="44ef6-133">To build and run the unit test</span></span>  
  
1.  <span data-ttu-id="44ef6-134">En el Explorador de soluciones, haga clic en **TestProject1**y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-134">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="44ef6-135">En el menú principal, haga clic en **prueba**y, a continuación, en el **Windows** lista, haga clic en **vista de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-135">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="44ef6-136">En la ventana Vista de pruebas, haga clic en **FFReceivePipelineUnitTest**y, a continuación, haga clic en **Ejecutar selección**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-136">In the Test View window, right-click **FFReceivePipelineUnitTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="44ef6-137">Compruebe que ve **superada** en la ventana Resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="44ef6-137">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="44ef6-138">En el directorio TestResults, examine el \*archivo .out.</span><span class="sxs-lookup"><span data-stu-id="44ef6-138">In the TestResults directory examine the \*.out file.</span></span> <span data-ttu-id="44ef6-139">Este archivo debe contener el nuevo mensaje procesado por la canalización.</span><span class="sxs-lookup"><span data-stu-id="44ef6-139">This file should contain the new message processed by the pipeline.</span></span>  <span data-ttu-id="44ef6-140">Debe estar ubicado en un directorio similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ef6-140">It should be located in a directory similar to the following:</span></span>  
  
     <span data-ttu-id="44ef6-141">C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span><span class="sxs-lookup"><span data-stu-id="44ef6-141">C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span></span>  
  
     <span data-ttu-id="44ef6-142">El mensaje procesado debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ef6-142">The processed message should look similar to the following:</span></span>  
  
    ```  
    <purchaseOrder orderDate="1999-10-20" xmlns="http://FlatFileRecieve.PO">  
  
      <shipTo country="US" xmlns="">  
        <name>Alice Smith</name>  
        <street>123 Maple Street</street>  
        <city>Mill Valley</city>  
        <state>CA</state>  
        <zip>90952</zip>  
      </shipTo>  
  
      <billTo country="US" xmlns="">  
        <name>Robert Smith</name>  
        <street>8 Oak Avenue</street>  
        <city>Old Town</city>  
        <state>PA</state>  
        <zip>95819</zip>  
      </billTo>  
  
      <comment>Hurry, my lawn is going wild!</comment>  
  
      <items xmlns="">  
  
        <item partNum="872-AA">  
          <productName>Lawnmower</productName>  
          <quantity>1</quantity>  
          <USPrice>148.95</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
        </item>  
  
        <item partNum="926-AA">  
          <productName>Baby Monitor</productName>  
          <quantity>1</quantity>  
          <USPrice>39.98</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
          <shipDate>1999-05-21</shipDate>  
        </item>  
  
      </items>  
  
    </purchaseOrder>  
    ```  
  
5.  <span data-ttu-id="44ef6-143">Si alguna prueba falla, puede hacer doble clic en ella en la ventana Resultados de la prueba para ver la aserción o excepción que ha provocado el fallo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="44ef6-143">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="44ef6-144">Resumen de códigos de prueba</span><span class="sxs-lookup"><span data-stu-id="44ef6-144">Test Code Summary</span></span>  
 <span data-ttu-id="44ef6-145">Cuando las pruebas unitarias se habilitó para la **FlatFileReceive** proyecto, el **FFReceivePipeline** C# clase asociada **FFReceivePipeline.btp** se derivó de el **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** clase.</span><span class="sxs-lookup"><span data-stu-id="44ef6-145">When unit testing was enabled for the **FlatFileReceive** project, the **FFReceivePipeline** C# class associated with **FFReceivePipeline.btp** was derived from the **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** class.</span></span> <span data-ttu-id="44ef6-146">El **FFReceivePipelineUnitTest** método **TestProject1** usa el **TestPipeline** método que **FFReceivePipeline** heredado Para probar la canalización de recepción del archivo plano.</span><span class="sxs-lookup"><span data-stu-id="44ef6-146">The **FFReceivePipelineUnitTest** method in **TestProject1** used the **TestPipeline** method that **FFReceivePipeline** inherited to test the flat file receive pipeline.</span></span> <span data-ttu-id="44ef6-147">Una vez que la canalización ha procesado el mensaje, el mensaje de salida se validó contra el esquema del archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="44ef6-147">After the pipeline processed the message, the output message was validated against the flat file schema.</span></span> <span data-ttu-id="44ef6-148">Los parámetros para el **TestPipeline** método son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="44ef6-148">The parameters for the **TestPipeline** method are as follows:</span></span>  
  
|<span data-ttu-id="44ef6-149">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="44ef6-149">Parameter Name</span></span>|<span data-ttu-id="44ef6-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ef6-150">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="44ef6-151">Documentos</span><span class="sxs-lookup"><span data-stu-id="44ef6-151">Documents</span></span>|<span data-ttu-id="44ef6-152">StringCollection que contiene los mensajes que va a procesar la canalización.</span><span class="sxs-lookup"><span data-stu-id="44ef6-152">StringCollection containing messages to be processed by the pipeline.</span></span>|  
|<span data-ttu-id="44ef6-153">Partes</span><span class="sxs-lookup"><span data-stu-id="44ef6-153">Parts</span></span>|<span data-ttu-id="44ef6-154">StringCollection que contiene las partes para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="44ef6-154">StringCollection containing the parts for the messages.</span></span>|  
|<span data-ttu-id="44ef6-155">Esquemas</span><span class="sxs-lookup"><span data-stu-id="44ef6-155">Schemas</span></span>|<span data-ttu-id="44ef6-156">Asignación de diccionario que se usa para asignar cada tipo de mensaje a su correspondiente \*archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="44ef6-156">Dictionary mapping used to map each message type to its corresponding \*.xsd schema file.</span></span> <span data-ttu-id="44ef6-157">La clave debe tener el formato **Namespace.Type**.</span><span class="sxs-lookup"><span data-stu-id="44ef6-157">The key must be in the format **Namespace.Type**.</span></span> <span data-ttu-id="44ef6-158">El espacio de nombres y tipo utilizados deben anotarse desde la ventana Propiedades para el \*archivo .xsd en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="44ef6-158">The namespace and type used should be noted from the properties window for the \*.xsd file in Visual Studio.</span></span> <span data-ttu-id="44ef6-159">Consulte la captura de pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="44ef6-159">See the screenshot below.</span></span><br /><br /> <span data-ttu-id="44ef6-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span><span class="sxs-lookup"><span data-stu-id="44ef6-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span></span><br /><br /> <span data-ttu-id="44ef6-161">**Namespace y el tipo expuestos desde la ventana Propiedades de un archivo XSD.**</span><span class="sxs-lookup"><span data-stu-id="44ef6-161">**Namespace and type exposed from the properties window of an XSD file.**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44ef6-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="44ef6-162">See Also</span></span>  
 <span data-ttu-id="44ef6-163">[Uso de la característica con esquemas y asignaciones de pruebas unitarias](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span><span class="sxs-lookup"><span data-stu-id="44ef6-163">[Using the Unit Testing Feature with Schemas and Maps](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span></span>  
 [<span data-ttu-id="44ef6-164">Trabajar con pruebas unitarias (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="44ef6-164">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)