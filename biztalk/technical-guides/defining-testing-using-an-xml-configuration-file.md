---
title: Definir pruebas mediante un archivo de configuración XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18d6ed5e237a9ee5e9dbe36c58c10ec6f22907d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976338"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a><span data-ttu-id="9d971-102">Definir pruebas mediante un archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="9d971-102">Defining Testing Using an XML Configuration File</span></span>
<span data-ttu-id="9d971-103">BizUnit ofrece dos métodos para definir las pruebas: a través de un archivo de configuración XML y a través de una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="9d971-103">BizUnit offers two ways to define tests: via an XML configuration file and via an Excel worksheet.</span></span> <span data-ttu-id="9d971-104">En este tema se centra sobre el uso de un archivo de configuración XML para definir pruebas; Sin embargo, también debe buscar en el SDK de BizUnit, puesto que ofrece un ejemplo de cómo definir los casos de prueba de BizUnit usando Excel interesante.</span><span class="sxs-lookup"><span data-stu-id="9d971-104">This topic focuses on using an XML configuration file to define tests; however, you should also look at the BizUnit SDK, since it provides an interesting example of how to define BizUnit test cases using Excel.</span></span> <span data-ttu-id="9d971-105">Además, puede que desee investigar la herramienta Diseñador de BizUnit, que proporciona una interfaz gráfica de usuario que permite la rápida creación de casos de prueba de BizUnit.</span><span class="sxs-lookup"><span data-stu-id="9d971-105">In addition, you may wish to investigate the BizUnit Designer tool, which provides a GUI that allows for rapid creation of BizUnit test cases.</span></span> <span data-ttu-id="9d971-106">Este tema proporciona información general sobre cómo definir los casos de prueba con la configuración de XML con un escenario muy simplificado.</span><span class="sxs-lookup"><span data-stu-id="9d971-106">This topic provides an overview of how to define test cases using XML configuration using a very simplified scenario.</span></span>  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a><span data-ttu-id="9d971-107">Información general de la definición de un caso de prueba de BizUnit mediante la configuración de XML</span><span class="sxs-lookup"><span data-stu-id="9d971-107">Overview of defining a BizUnit test case using XML configuration</span></span>  
 <span data-ttu-id="9d971-108">Como solo se ha indicado, este escenario se simplifica con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="9d971-108">As just stated, this scenario is simplified for purposes of illustration.</span></span> <span data-ttu-id="9d971-109">Considere la posibilidad de obtener un ejemplo de aplicación, como se ilustra a continuación de mensajería.</span><span class="sxs-lookup"><span data-stu-id="9d971-109">Consider a sample messaging application such as the one illustrated below.</span></span> <span data-ttu-id="9d971-110">Supongamos que el comportamiento normal de funcional para esta aplicación es que BizTalk recibe un archivo XML a través de un archivo de ubicación de recepción,, a continuación, lo envía a un suscriptor adecuado en función de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="9d971-110">Let’s assume that normal functional behavior for this application is that BizTalk receives an XML file via a file receive location, it then sends it to an appropriate subscriber based on a subscription.</span></span> <span data-ttu-id="9d971-111">Para validar este escenario eficazmente es importante que llevamos a cabo los siguientes pasos de la prueba:</span><span class="sxs-lookup"><span data-stu-id="9d971-111">To validate this scenario effectively it is important that we perform the following steps in the test:</span></span>  
  
1.  <span data-ttu-id="9d971-112">Configurar el entorno para asegurarse de que se encuentra en un estado coherente y listo para la prueba se ejecute:</span><span class="sxs-lookup"><span data-stu-id="9d971-112">Set up the environment to ensure that it is in a consistent state and ready for the test to be run:</span></span>  
  
    -   <span data-ttu-id="9d971-113">Para ello, elimine los archivos que se encuentran en las ubicaciones de archivo de dos.</span><span class="sxs-lookup"><span data-stu-id="9d971-113">This is done by deleting any files that are present in the two file locations used.</span></span>  
  
2.  <span data-ttu-id="9d971-114">Ejecute la prueba para comprobar la funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="9d971-114">Run the test to verify functionality:</span></span>  
  
    -   <span data-ttu-id="9d971-115">Crear un mensaje XML válido en la carpeta que el archivo de sondeos de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9d971-115">Create a valid XML message in the folder that the file receive location polls.</span></span>  
  
    -   <span data-ttu-id="9d971-116">Validar que el mensaje XML correcto se encuentra ubicado en la ubicación de carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="9d971-116">Validate that the correct XML message is placed in the outbound folder location.</span></span>  
  
    -   <span data-ttu-id="9d971-117">La validación debe cubrir el esquema y la información de carga para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="9d971-117">The validation should cover both the schema and the payload information for the message.</span></span> <span data-ttu-id="9d971-118">(Normalmente un par de los campos de clave debe examinarse.)</span><span class="sxs-lookup"><span data-stu-id="9d971-118">(Typically a couple of the key fields should be examined.)</span></span>  
  
3.  <span data-ttu-id="9d971-119">Limpiar el entorno para asegurarse de que el entorno está en el mismo estado que antes de la prueba que se ejecuta:</span><span class="sxs-lookup"><span data-stu-id="9d971-119">Clean up the environment to ensure that the environment is in the same state as before the test executed:</span></span>  
  
    -   <span data-ttu-id="9d971-120">Elimine los archivos que se encuentran en las ubicaciones de archivo de dos.</span><span class="sxs-lookup"><span data-stu-id="9d971-120">Delete any files that are present in the two file locations used.</span></span>  
  
 <span data-ttu-id="9d971-121">![Aplicación de mensajería de BizTalk de ejemplo](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span><span class="sxs-lookup"><span data-stu-id="9d971-121">![Sample BizTalk Messaging Application](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span></span>  
<span data-ttu-id="9d971-122">Aplicación de mensajería de BizTalk de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d971-122">Sample BizTalk Messaging application</span></span>  
  
 <span data-ttu-id="9d971-123">Cada caso de prueba empieza y termina con la etiqueta TestCase XML; el parámetro nombreDePrueba se pasó a esto como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9d971-123">Each test case begins and ends with the TestCase XML tag; the testName parameter is passed into this as indicated here.</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 <span data-ttu-id="9d971-124">A continuación, escribimos la fase de TestSetup, en el que es asegurarse de que el entorno está en un estado coherente para ejecutar la prueba.</span><span class="sxs-lookup"><span data-stu-id="9d971-124">Then we enter the TestSetup phase, in which we ensure that the environment is in a consistent state to run the test.</span></span> <span data-ttu-id="9d971-125">En este ejemplo, se elimina los mensajes XML que se encuentran en el directorio TestData.</span><span class="sxs-lookup"><span data-stu-id="9d971-125">In this example, we delete any XML messages that are contained in our TestData directory.</span></span> <span data-ttu-id="9d971-126">Esto se realiza mediante la **FileDeleteMultipleStep**.</span><span class="sxs-lookup"><span data-stu-id="9d971-126">This is done using the **FileDeleteMultipleStep**.</span></span>  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="9d971-127">A continuación, escribimos ¿qué es la sección más importante de la prueba, la fase de ejecución de prueba.</span><span class="sxs-lookup"><span data-stu-id="9d971-127">We then enter what is the most critical section of the test, the test execution stage.</span></span> <span data-ttu-id="9d971-128">Esta fase puede contener varios pasos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9d971-128">This stage can contain multiple test steps.</span></span> <span data-ttu-id="9d971-129">En este ejemplo se usa el FileCreateStep para copiar un documento (InDoc1.xml que puede verse en la \<SourcePath\> etiqueta) a una caída del archivo que se usa por nuestro ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="9d971-129">In this example we use the FileCreateStep to copy a document (InDoc1.xml which can be seen in the \<SourcePath\> tag) to a file drop which is used by our receive location.</span></span> <span data-ttu-id="9d971-130">Es importante tener en cuenta que BizUnit admite el uso de identificadores únicos para los nombres de archivo en este paso; Esto puede verse con el Guid % referencia en la etiqueta de CreationPath %.</span><span class="sxs-lookup"><span data-stu-id="9d971-130">It’s important to note that BizUnit supports using unique identifiers for filenames in this step; this can be seen with the %Guid% reference in the CreationPath tag.</span></span>  
  
 <span data-ttu-id="9d971-131">Una vez finalizado este procedimiento, es necesario usar el **FileValidateStep** validar el mensaje saliente se ha creado.</span><span class="sxs-lookup"><span data-stu-id="9d971-131">After this has been completed, we need to use the **FileValidateStep** to validate the outbound message has been created.</span></span> <span data-ttu-id="9d971-132">Puede observar que este paso le permite especificar un valor de tiempo de espera (Esto está en milisegundos), el directorio y el patrón de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9d971-132">You will notice this step allows you to specify a timeout value (this is in milliseconds), the directory and the search pattern.</span></span> <span data-ttu-id="9d971-133">Además, el **DeleteFile** etiqueta le permite especificar si desea que el archivo que debe quitarse después de que se ha validado.</span><span class="sxs-lookup"><span data-stu-id="9d971-133">In addition to this, the **DeleteFile** tag enables you to specify whether you want the file to be removed after it has been validated.</span></span> <span data-ttu-id="9d971-134">Por último, también tenga en cuenta que la validación incluye una consulta XPath, que valida el nodo PONumber dentro del mensaje XML (comprueba que el valor es PONumber_0). Examen y validación de la carga de todos los mensajes salientes es otro ejemplo de una directriz principal que debe seguir al utilizar BizUnit.</span><span class="sxs-lookup"><span data-stu-id="9d971-134">Finally, you should also note the validation includes an XPath query, which validates the PONumber node within the XML message (it checks that the value is PONumber_0.) Examination and validation of the payload of any outbound messages is another example of a guiding principle that you should follow when using BizUnit.</span></span>  
  
```  
<TestExecution>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
      <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
      <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
      <Timeout>3000</Timeout>  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>TransactionId_*.xml</SearchPattern>  
      <DeleteFile>true</DeleteFile>  
      <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
         <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
         <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
         <XPathList>  
            <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
         </XPathList>  
      </ValidationStep>  
   </TestStep>  
</TestExecution>  
```  
  
 <span data-ttu-id="9d971-135">La fase final del caso de prueba es la limpieza de nuevo.</span><span class="sxs-lookup"><span data-stu-id="9d971-135">The final stage of the test case is the cleanup.</span></span> <span data-ttu-id="9d971-136">Como puede ver en este caso, el **FileDelete** paso de prueba se utiliza para limpiar los directorios utilizados por la prueba.</span><span class="sxs-lookup"><span data-stu-id="9d971-136">As can be seen here, the **FileDelete** test step is used to clean up the directories used by the test.</span></span>  
  
```  
<TestCleanup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
</TestCleanup>  
```  
  
 <span data-ttu-id="9d971-137">Espero que este ejemplo se muestra que la definición de pruebas en BizUnit es relativamente sencilla y que mediante el uso de este marco de pruebas, podrá para desarrollar con rapidez los casos de prueba para proporcionar las pruebas funcionales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d971-137">Hopefully this example illustrates that defining tests in BizUnit is relatively straightforward and that by using this test framework, you will be able to rapidly develop test cases to provide functional testing of your application.</span></span>  
  
### <a name="full-test-case-example"></a><span data-ttu-id="9d971-138">Ejemplo de caso de prueba completa</span><span class="sxs-lookup"><span data-stu-id="9d971-138">Full test case example</span></span>  
 <span data-ttu-id="9d971-139">El contenido del archivo de configuración completa de los casos de prueba se incluyen aquí para su referencia:</span><span class="sxs-lookup"><span data-stu-id="9d971-139">The full test case configuration file contents are included here for your reference:</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
   <TestSetup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
            <SearchPattern>*.xml</SearchPattern>   
         </TestStep>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
         <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
         <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
         <Timeout>3000</Timeout>  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>TransactionId_*.xml</SearchPattern>  
         <DeleteFile>true</DeleteFile>  
         <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
            <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
            <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
            <XPathList>  
               <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
            </XPathList>  
         </ValidationStep>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d971-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d971-140">See Also</span></span>  
 [<span data-ttu-id="9d971-141">Uso de BizUnit para facilitar las pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="9d971-141">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)