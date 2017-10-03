---
title: "Uso de la característica con esquemas y asignaciones de pruebas de unidades | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc14621a1830f15da02336b7b82e9df475cfe9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a>Uso de la característica de pruebas de unidades con esquemas y asignaciones
En este tema se muestra el modo de usar la función de pruebas de unidad para agregar una prueba de unidad para los esquemas y la asignación al ejemplo de orquestación HelloWorld.  
  
> [!NOTE]
>  La característica de pruebas de unidad para asignaciones actualmente no es compatible con varias asignaciones de entrada.  
  
## <a name="prerequisites"></a>Requisitos previos  
 En primer lugar, debe seguir los pasos para generar el ejemplo HelloWorld. Estos pasos se pueden encontrar aquí: [HelloWorld (ejemplo de BizTalk Server)](../core/helloworld-biztalk-server-sample.md)  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a>Adición de un proyecto de prueba de unidad al ejemplo HelloWorld  
  
1.  En Visual Studio, abra el archivo de soluciones HelloWorld.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **HelloWorld** del proyecto y, a continuación, haga clic en **propiedades**.  
  
3.  En el Diseñador de proyectos, haga clic en el **implementación** ficha de página de propiedades y establezca **habilitar pruebas de unidades** a `True`.  
  
4.  Cierre la página de propiedades del proyecto guardando los cambios.  
  
5.  En el menú principal, haga clic en **generar**y, a continuación, haga clic en **volver a generar solución**.  
  
6.  En el menú principal, haga clic en **prueba**y, a continuación, haga clic en **nueva prueba**.  
  
7.  En el **agregar nueva prueba** cuadro de diálogo, seleccione **crear un nuevo proyecto de prueba de Visual C#** para **agregar a proyecto de prueba** campo. Seleccione **Asistente para pruebas unitarias** en el **plantillas** lista y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **nuevo proyecto de prueba** diálogo cuadro, deje el nombre del proyecto como **TestProject1** y haga clic en **crear**.  
  
9. En el **crear pruebas unitarias** diálogo cuadro, expanda los tipos y seleccione el **Ffreceivepipeline()** constructor en el **Microsoft.Samples.BizTalk.HelloWorld.POSchema** nodo. Seleccionar **POToInvoice()** constructor en el **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** nodo. La siguiente ilustración muestra las selecciones que se deben realizar. Después de realizar las selecciones que se muestra a continuación, presione **Aceptar**.  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a>Agregar código de prueba para probar los esquemas y la asignación  
  
1.  Agregue las siguientes referencias a la **TestProject1** proyecto desde el **.NET** ficha en el cuadro de diálogo Agregar referencia:  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Tipos de base de Microsoft XLANG/s  
  
2.  En el Explorador de soluciones, abra POSchemaTest.cs  
  
3.  Desplácese hasta el final del archivo y reemplazar el **Microsoft.Samples.BizTalk.HelloWorld.poschema** mensaje de entrada de método con el siguiente código que valida el pedido de compra de ejemplo:  
  
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
  
4.  En el Explorador de soluciones, abra POToInvoiceTest.cs y agregue la siguiente directiva a la parte superior de dicho archivo:  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  Desplácese hasta el final del archivo y reemplazar el **POToInvoiceConstructorTest** mensaje de entrada de método con el siguiente código que comprueba la asignación mediante el pedido de compra de ejemplo:  
  
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
  
### <a name="building-and-running-the-unit-test"></a>Generar y ejecutar la prueba de la unidad  
  
1.  En el Explorador de soluciones, haga clic en **TestProject1**y, a continuación, haga clic en **generar**.  
  
2.  En el menú principal, haga clic en **prueba**y, a continuación, en la **Windows** lista, haga clic en **vista de pruebas**.  
  
3.  En la ventana Vista de pruebas, haga clic en **POSchemaInstanceValidationTest**y, a continuación, haga clic en **Ejecutar selección**. Compruebe que ve **superada** en la ventana Resultados de pruebas.  
  
4.  En la ventana Vista de pruebas, haga clic en **POToInvoiceMapTest**y, a continuación, haga clic en **Ejecutar selección**. Compruebe que ve **superada** en la ventana Resultados de pruebas.  
  
5.  Si alguna prueba falla, puede hacer doble clic en ella en la ventana Resultados de la prueba para ver la aserción o excepción que ha provocado el fallo de la prueba.  
  
## <a name="test-code-summary"></a>Resumen de códigos de prueba  
 Cuando se habilitó las pruebas unitarias para el **HelloWorld** del proyecto, la clase de C# asociada **POSchema.xsd** se derivó de la **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**  clase. El **POSchemaInstanceValidationTest** método **TestProject1** utiliza la **ValidateInstance** método de la **POSchema** clase a validar SamplePOInput.xml contra el esquema de pedido de compra.  
  
 De forma similar, cuando se habilitó pruebas unitarias para el **HelloWorld** del proyecto, la clase de C# asociada con el **POToInvoice.btm** derivó de la  **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** clase. El **POToInvoiceMaptest** método usa la **comprobar asignación** método de la **POToInvoice** clase para probar la asignación con el mismo mensaje SamplePOInput.xml. Esto provocó la creación de SampleInvoiceOutput.xml en el directorio HelloWorld.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la característica con canalizaciones de pruebas de unidades](../core/using-the-unit-testing-feature-with-pipelines.md)   
 [Trabajar con pruebas unitarias (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)