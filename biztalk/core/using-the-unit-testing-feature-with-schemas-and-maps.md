---
title: Uso de la característica con esquemas y asignaciones de pruebas de unidades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc14621a1830f15da02336b7b82e9df475cfe9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288996"
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a><span data-ttu-id="94f4b-102">Uso de la característica de pruebas de unidades con esquemas y asignaciones</span><span class="sxs-lookup"><span data-stu-id="94f4b-102">Using the Unit Testing Feature with Schemas and Maps</span></span>
<span data-ttu-id="94f4b-103">En este tema se muestra el modo de usar la función de pruebas de unidad para agregar una prueba de unidad para los esquemas y la asignación al ejemplo de orquestación HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="94f4b-103">This topic demonstrates how to use the unit testing feature to add a unit test for the schemas and map in the HelloWorld orchestration example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94f4b-104">La característica de pruebas de unidad para asignaciones actualmente no es compatible con varias asignaciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="94f4b-104">The unit testing feature for maps currently does not support multiple input maps.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94f4b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="94f4b-105">Prerequisites</span></span>  
 <span data-ttu-id="94f4b-106">En primer lugar, debe seguir los pasos para generar el ejemplo HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="94f4b-106">You must first follow the steps for building the HelloWorld sample.</span></span> <span data-ttu-id="94f4b-107">Estos pasos se pueden encontrar aquí: [HelloWorld (ejemplo de BizTalk Server)](../core/helloworld-biztalk-server-sample.md)</span><span class="sxs-lookup"><span data-stu-id="94f4b-107">Those steps can be found here: [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md)</span></span>  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a><span data-ttu-id="94f4b-108">Adición de un proyecto de prueba de unidad al ejemplo HelloWorld</span><span class="sxs-lookup"><span data-stu-id="94f4b-108">Adding a Unit Test Project to the HelloWorld Sample</span></span>  
  
1.  <span data-ttu-id="94f4b-109">En Visual Studio, abra el archivo de soluciones HelloWorld.sln.</span><span class="sxs-lookup"><span data-stu-id="94f4b-109">In Visual Studio, open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="94f4b-110">En el Explorador de soluciones, haga clic en el **HelloWorld** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-110">In Solution Explorer, right-click the **HelloWorld** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="94f4b-111">En el Diseñador de proyectos, haga clic en el **implementación** ficha de página de propiedades y establezca **habilitar pruebas de unidades** a `True`.</span><span class="sxs-lookup"><span data-stu-id="94f4b-111">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="94f4b-112">Cierre la página de propiedades del proyecto guardando los cambios.</span><span class="sxs-lookup"><span data-stu-id="94f4b-112">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="94f4b-113">En el menú principal, haga clic en **generar**y, a continuación, haga clic en **volver a generar solución**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-113">In main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="94f4b-114">En el menú principal, haga clic en **prueba**y, a continuación, haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-114">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="94f4b-115">En el **agregar nueva prueba** cuadro de diálogo, seleccione **crear un nuevo proyecto de prueba de Visual C#** para **agregar a proyecto de prueba** campo.</span><span class="sxs-lookup"><span data-stu-id="94f4b-115">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for **Add to Test Project** field.</span></span> <span data-ttu-id="94f4b-116">Seleccione **Asistente para pruebas unitarias** en el **plantillas** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-116">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="94f4b-117">En el **nuevo proyecto de prueba** diálogo cuadro, deje el nombre del proyecto como **TestProject1** y haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-117">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="94f4b-118">En el **crear pruebas unitarias** diálogo cuadro, expanda los tipos y seleccione el **Ffreceivepipeline()** constructor en el **Microsoft.Samples.BizTalk.HelloWorld.POSchema** nodo.</span><span class="sxs-lookup"><span data-stu-id="94f4b-118">In the **Create Unit Tests** dialog box, expand the types and select the **POSchema()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POSchema** node.</span></span> <span data-ttu-id="94f4b-119">Seleccionar **POToInvoice()** constructor en el **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** nodo.</span><span class="sxs-lookup"><span data-stu-id="94f4b-119">Also select **POToInvoice()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** node.</span></span> <span data-ttu-id="94f4b-120">La siguiente ilustración muestra las selecciones que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="94f4b-120">The figure below shows the selections that should be made.</span></span> <span data-ttu-id="94f4b-121">Después de realizar las selecciones que se muestra a continuación, presione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-121">After making the selections shown below, press **OK**.</span></span>  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a><span data-ttu-id="94f4b-122">Agregar código de prueba para probar los esquemas y la asignación</span><span class="sxs-lookup"><span data-stu-id="94f4b-122">Adding Test Code to Test the Schemas and Map</span></span>  
  
1.  <span data-ttu-id="94f4b-123">Agregue las siguientes referencias a la **TestProject1** proyecto desde el **.NET** ficha en el cuadro de diálogo Agregar referencia:</span><span class="sxs-lookup"><span data-stu-id="94f4b-123">Add the following references to the **TestProject1** project from the **.NET** tab in the Add Reference dialog:</span></span>  
  
    -   <span data-ttu-id="94f4b-124">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="94f4b-124">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="94f4b-125">Tipos de base de Microsoft XLANG/s</span><span class="sxs-lookup"><span data-stu-id="94f4b-125">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="94f4b-126">En el Explorador de soluciones, abra POSchemaTest.cs</span><span class="sxs-lookup"><span data-stu-id="94f4b-126">In Solution Explorer, open POSchemaTest.cs</span></span>  
  
3.  <span data-ttu-id="94f4b-127">Desplácese hasta el final del archivo y reemplazar el **Microsoft.Samples.BizTalk.HelloWorld.poschema** mensaje de entrada de método con el siguiente código que valida el pedido de compra de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94f4b-127">Scroll to the bottom of the file and replace the **POSchemaConstructorTest** method with the following code which validates the sample PO input message:</span></span>  
  
    ```  
    [TestMethod()]  
    public void POSchemaInstanceValidationTest()  
    {  
        POSchema target = new POSchema();  
  
        //=== The SamplePOInput.xml file from <Samples Path>\Orchestrations\HelloWorld ===//  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
  
        //=== Validate the SamplePOInput message against the schema ===//  
        Assert.IsTrue(target.ValidateInstance(strSourcePO_XML, Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
    }  
    ```  
  
4.  <span data-ttu-id="94f4b-128">En el Explorador de soluciones, abra POToInvoiceTest.cs y agregue la siguiente directiva a la parte superior de dicho archivo:</span><span class="sxs-lookup"><span data-stu-id="94f4b-128">In Solution Explorer open POToInvoiceTest.cs and add the following directive to the top of that file:</span></span>  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  <span data-ttu-id="94f4b-129">Desplácese hasta el final del archivo y reemplazar el **POToInvoiceConstructorTest** mensaje de entrada de método con el siguiente código que comprueba la asignación mediante el pedido de compra de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94f4b-129">Scroll to the bottom of the file and replace the **POToInvoiceConstructorTest** method with the following code which tests the map using the sample PO input message:</span></span>  
  
    ```  
  
    [TestMethod()]  
    public void POToInvoiceMapTest()  
    {  
        POToInvoice target = new POToInvoice();  
  
        //=== Use the HelloWorld sample directory path for the message files ===//  
  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
        string strDestInvoice_XML = testContextInstance.TestDir + "..\\..\\..\\SampleInvoiceOutput.xml";  
  
        //=== Test the map by using the TestMap method of the TestableMapBase class ===//  
  
        target.ValidateOutput = true;  
        target.TestMap(strSourcePO_XML,  
                       Microsoft.BizTalk.TestTools.Schema.InputInstanceType.Xml,  
                       strDestInvoice_XML,  
                       Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML);  
  
        //=== Output file should be created as a result of testing the map ===//  
  
        Assert.IsTrue(File.Exists(strDestInvoice_XML));   
    }  
    ```  
  
### <a name="building-and-running-the-unit-test"></a><span data-ttu-id="94f4b-130">Generar y ejecutar la prueba de la unidad</span><span class="sxs-lookup"><span data-stu-id="94f4b-130">Building and Running the Unit Test</span></span>  
  
1.  <span data-ttu-id="94f4b-131">En el Explorador de soluciones, haga clic en **TestProject1**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-131">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="94f4b-132">En el menú principal, haga clic en **prueba**y, a continuación, en la **Windows** lista, haga clic en **vista de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-132">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="94f4b-133">En la ventana Vista de pruebas, haga clic en **POSchemaInstanceValidationTest**y, a continuación, haga clic en **Ejecutar selección**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-133">In the Test View window, right-click **POSchemaInstanceValidationTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="94f4b-134">Compruebe que ve **superada** en la ventana Resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="94f4b-134">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="94f4b-135">En la ventana Vista de pruebas, haga clic en **POToInvoiceMapTest**y, a continuación, haga clic en **Ejecutar selección**.</span><span class="sxs-lookup"><span data-stu-id="94f4b-135">In the Test View window, right-click **POToInvoiceMapTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="94f4b-136">Compruebe que ve **superada** en la ventana Resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="94f4b-136">Verify that you see **Passed** in the Test Results window.</span></span>  
  
5.  <span data-ttu-id="94f4b-137">Si alguna prueba falla, puede hacer doble clic en ella en la ventana Resultados de la prueba para ver la aserción o excepción que ha provocado el fallo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="94f4b-137">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="94f4b-138">Resumen de códigos de prueba</span><span class="sxs-lookup"><span data-stu-id="94f4b-138">Test Code Summary</span></span>  
 <span data-ttu-id="94f4b-139">Cuando se habilitó las pruebas unitarias para el **HelloWorld** del proyecto, la clase de C# asociada **POSchema.xsd** se derivó de la **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**  clase.</span><span class="sxs-lookup"><span data-stu-id="94f4b-139">When unit testing was enabled for the **HelloWorld** project, the C# class associated with **POSchema.xsd** was derived from the **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase** class.</span></span> <span data-ttu-id="94f4b-140">El **POSchemaInstanceValidationTest** método **TestProject1** utiliza la **ValidateInstance** método de la **POSchema** clase a validar SamplePOInput.xml contra el esquema de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="94f4b-140">The **POSchemaInstanceValidationTest** method in **TestProject1** used the **ValidateInstance** method of the **POSchema** class to validate SamplePOInput.xml against the PO schema.</span></span>  
  
 <span data-ttu-id="94f4b-141">De forma similar, cuando se habilitó pruebas unitarias para el **HelloWorld** del proyecto, la clase de C# asociada con el **POToInvoice.btm** derivó de la  **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** clase.</span><span class="sxs-lookup"><span data-stu-id="94f4b-141">Similarly, when unit testing was enabled for the **HelloWorld** project, the C# class associated with the **POToInvoice.btm** map was derived from the **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** class.</span></span> <span data-ttu-id="94f4b-142">El **POToInvoiceMaptest** método usa la **comprobar asignación** método de la **POToInvoice** clase para probar la asignación con el mismo mensaje SamplePOInput.xml.</span><span class="sxs-lookup"><span data-stu-id="94f4b-142">The **POToInvoiceMaptest** method used the **TestMap** method of the **POToInvoice** class to test the map using the same SamplePOInput.xml message.</span></span> <span data-ttu-id="94f4b-143">Esto provocó la creación de SampleInvoiceOutput.xml en el directorio HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="94f4b-143">This resulted in SampleInvoiceOutput.xml being created in the HelloWorld directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f4b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="94f4b-144">See Also</span></span>  
 <span data-ttu-id="94f4b-145">[Uso de la característica con canalizaciones de pruebas de unidades](../core/using-the-unit-testing-feature-with-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="94f4b-145">[Using the Unit Testing Feature with Pipelines](../core/using-the-unit-testing-feature-with-pipelines.md) </span></span>  
 [<span data-ttu-id="94f4b-146">Trabajar con pruebas unitarias (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="94f4b-146">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)