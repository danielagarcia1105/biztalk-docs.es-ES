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
ms.openlocfilehash: 7deaaa8d0ca60f13e5f3b835a91a31e06cdf2cbd
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826331"
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a>Uso de la característica de pruebas de unidades con canalizaciones
En este tema se muestra el modo de usar la función de pruebas de unidad para agregar una prueba de unidad para la canalización al ejemplo de canalización FlatFileReceive. Las pruebas unitarias de canalización es similar a la herramienta Pipeline.exe que se documenta aquí: [herramientas de canalización](../core/pipeline-tools.md). Al habilitar pruebas unitarias en el **implementación** se deriva de ficha de propiedades del proyecto, la clase de canalización en el proyecto **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.  Esta clase modela parte de la misma funcionalidad expuesta por la herramienta Pipeline.exe.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Primero debe seguir los pasos para generar la muestra FlatFileReceive y familiarizarse con dicha muestra. La documentación que incluye los pasos para generar la muestra FlatFileReceive puede encontrarse aquí: [FlatFileReceive (ejemplo de BizTalk Server)](../core/flatfilereceive-biztalk-server-sample.md).  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a>Adición de un proyecto de prueba de unidad al ejemplo FlatFileReceive  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a>Procedimiento para agregar un proyecto de prueba de unidad al ejemplo FlatFileReceive  
  
1.  En Visual Studio, abra el archivo de solución FlatFileReceive.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **FlatFileReceive** del proyecto y, a continuación, haga clic en **propiedades**.  
  
3.  En el Diseñador de proyectos, haga clic en el **implementación** ficha de página de propiedades y establezca **habilitar pruebas de unidades** a `True`.  
  
4.  Cierre la página de propiedades del proyecto guardando los cambios.  
  
5.  En el menú principal, haga clic en **compilar**y, a continuación, haga clic en **recompilar solución**.  
  
6.  En el menú principal, haga clic en **prueba**y, a continuación, haga clic en **nueva prueba**.  
  
7.  En el **agregar nueva prueba** cuadro de diálogo, seleccione **crear un nuevo objeto Visual C# proyecto de prueba** para el **agregar a proyecto de prueba** campo. Seleccione **Asistente para pruebas unitarias** en el **plantillas** lista y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **nuevo proyecto de prueba** diálogo cuadro, deje el nombre del proyecto como **TestProject1** y haga clic en **crear**.  
  
9. En el **crear pruebas unitarias** cuadro de diálogo, expanda los tipos y seleccione el **FFReceivePipeline()** constructor bajo el **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline**  nodo. Haga clic en **Aceptar**.  
  
## <a name="adding-test-code-to-test-the-pipeline"></a>Agregar código de prueba para probar la canalización  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a>Procedimiento para agregar código de prueba para probar la canalización  
  
1.  Agregue las siguientes referencias a la **TestProject1** proyecto:  
  
    -   Interoperabilidad de canalizaciones de BizTalk  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Tipos de base de Microsoft XLANG/s  
  
2.  En el Explorador de soluciones, abra FFReceivePipelineTest.cs y agregue las siguientes directivas a la parte superior de dicho archivo:  
  
    ```csharp
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  Desplácese hasta la parte inferior del archivo y reemplace el **FFReceivePipelineConstructorTest** método con el código siguiente, que comprueba que existen las entradas de la canalización antes de probar la canalización. Este código también comprueba que se genera un mensaje conforme con el esquema de archivo sin formato.  
  
    ```csharp
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
  
## <a name="building-and-running-the-unit-test"></a>Generar y ejecutar la prueba de la unidad  
  
#### <a name="to-build-and-run-the-unit-test"></a>Procedimiento para generar y ejecutar la prueba de unidad  
  
1.  En el Explorador de soluciones, haga clic en **TestProject1**y, a continuación, haga clic en **compilar**.  
  
2.  En el menú principal, haga clic en **prueba**y, a continuación, en el **Windows** lista, haga clic en **vista de pruebas**.  
  
3.  En la ventana Vista de pruebas, haga clic en **FFReceivePipelineUnitTest**y, a continuación, haga clic en **Ejecutar selección**. Compruebe que ve **superada** en la ventana Resultados de pruebas.  
  
4.  En el directorio TestResults, examine el \*archivo .out. Este archivo debe contener el nuevo mensaje procesado por la canalización.  Debe estar ubicado en un directorio similar al siguiente:  
  
     C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out  
  
     El mensaje procesado debe ser similar al siguiente:  
  
    ```xml
    <purchaseOrder orderDate="1999-10-20" xmlns="http://FlatFileReceive.PO">  
  
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
          <comment xmlns="http://FlatFileReceive.PO">Confirm this is electric</comment>  
        </item>  
  
        <item partNum="926-AA">  
          <productName>Baby Monitor</productName>  
          <quantity>1</quantity>  
          <USPrice>39.98</USPrice>  
          <comment xmlns="http://FlatFileReceive.PO">Confirm this is electric</comment>  
          <shipDate>1999-05-21</shipDate>  
        </item>  
  
      </items>  
  
    </purchaseOrder>  
    ```  
  
5.  Si alguna prueba falla, puede hacer doble clic en ella en la ventana Resultados de la prueba para ver la aserción o excepción que ha provocado el fallo de la prueba.  
  
## <a name="test-code-summary"></a>Resumen de códigos de prueba  
 Cuando las pruebas unitarias se habilitó para la **FlatFileReceive** proyecto, el **FFReceivePipeline** C# clase asociada **FFReceivePipeline.btp** se derivó de el **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** clase. El **FFReceivePipelineUnitTest** método **TestProject1** usa el **TestPipeline** método que **FFReceivePipeline** heredado Para probar la canalización de recepción del archivo plano. Una vez que la canalización ha procesado el mensaje, el mensaje de salida se validó contra el esquema del archivo sin formato. Los parámetros para el **TestPipeline** método son los siguientes:  
  
|Nombre de parámetro|Descripción|  
|--------------------|-----------------|  
|Documentos|StringCollection que contiene los mensajes que va a procesar la canalización.|  
|Partes|StringCollection que contiene las partes para los mensajes.|  
|Esquemas|Asignación de diccionario que se usa para asignar cada tipo de mensaje a su correspondiente \*archivo de esquema XSD. La clave debe tener el formato **Namespace.Type**. El espacio de nombres y tipo utilizados deben anotarse desde la ventana Propiedades para el \*archivo .xsd en Visual Studio. Consulte la captura de pantalla siguiente.<br /><br /> ![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")<br /><br /> **Namespace y el tipo expuestos desde la ventana Propiedades de un archivo XSD.**|  
  
## <a name="see-also"></a>Vea también  
 [Uso de la característica con esquemas y asignaciones de pruebas unitarias](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)   
 [Trabajar con pruebas unitarias (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)