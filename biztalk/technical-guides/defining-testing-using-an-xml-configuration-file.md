---
title: "Definir pruebas mediante un archivo de configuración XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 761f8c0a4480c26240926240cd890c1c68419b58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="defining-testing-using-an-xml-configuration-file"></a>Definir pruebas mediante un archivo de configuración XML
BizUnit ofrece dos métodos para definir las pruebas: a través de un archivo de configuración XML y a través de una hoja de cálculo de Excel. En este tema se centra sobre el uso de un archivo de configuración XML para definir pruebas; Sin embargo, también debe buscar en el SDK de BizUnit, puesto que ofrece un ejemplo de cómo definir los casos de prueba de BizUnit usando Excel interesante. Además, puede que desee investigar la herramienta Diseñador de BizUnit, que proporciona una interfaz gráfica de usuario que permite la rápida creación de casos de prueba de BizUnit. Este tema proporciona información general sobre cómo definir los casos de prueba con la configuración de XML con un escenario muy simplificado.  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>Información general de la definición de un caso de prueba de BizUnit mediante la configuración de XML  
 Como solo se ha indicado, este escenario se simplifica con fines ilustrativos. Considere la posibilidad de obtener un ejemplo de aplicación, como se ilustra a continuación de mensajería. Supongamos que el comportamiento normal de funcional para esta aplicación es que BizTalk recibe un archivo XML a través de un archivo de ubicación de recepción,, a continuación, lo envía a un suscriptor adecuado en función de una suscripción. Para validar este escenario eficazmente es importante que llevamos a cabo los siguientes pasos de la prueba:  
  
1.  Configurar el entorno para asegurarse de que se encuentra en un estado coherente y listo para la prueba se ejecute:  
  
    -   Para ello, elimine los archivos que se encuentran en las ubicaciones de archivo de dos.  
  
2.  Ejecute la prueba para comprobar la funcionalidad:  
  
    -   Crear un mensaje XML válido en la carpeta que el archivo de sondeos de la ubicación de recepción.  
  
    -   Validar que el mensaje XML correcto se encuentra ubicado en la ubicación de carpeta de salida.  
  
    -   La validación debe cubrir el esquema y la información de carga para el mensaje. (Normalmente un par de los campos de clave debe examinarse.)  
  
3.  Limpiar el entorno para asegurarse de que el entorno está en el mismo estado que antes de la prueba que se ejecuta:  
  
    -   Elimine los archivos que se encuentran en las ubicaciones de archivo de dos.  
  
 ![Aplicación de mensajería de BizTalk de ejemplo](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
Aplicación de mensajería de BizTalk de ejemplo  
  
 Cada caso de prueba empieza y termina con la etiqueta TestCase XML; el parámetro nombreDePrueba se pasó a esto como se indica a continuación.  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 A continuación, escribimos la fase de TestSetup, en el que es asegurarse de que el entorno está en un estado coherente para ejecutar la prueba. En este ejemplo, se elimina los mensajes XML que se encuentran en el directorio TestData. Esto se realiza mediante la **FileDeleteMultipleStep**.  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 A continuación, escribimos ¿qué es la sección más importante de la prueba, la fase de ejecución de prueba. Esta fase puede contener varios pasos de prueba. En este ejemplo se usa el FileCreateStep para copiar un documento (InDoc1.xml que puede verse en la \<SourcePath > etiqueta) a una caída del archivo que se usa por nuestro ubicación de recepción. Es importante tener en cuenta que BizUnit admite el uso de identificadores únicos para los nombres de archivo en este paso; Esto puede verse con el Guid % referencia en la etiqueta de CreationPath %.  
  
 Una vez finalizado este procedimiento, es necesario usar el **FileValidateStep** validar el mensaje saliente se ha creado. Puede observar que este paso le permite especificar un valor de tiempo de espera (Esto está en milisegundos), el directorio y el patrón de búsqueda. Además, el **DeleteFile** etiqueta le permite especificar si desea que el archivo que debe quitarse después de que se ha validado. Por último, también tenga en cuenta que la validación incluye una consulta XPath, que valida el nodo PONumber dentro del mensaje XML (comprueba que el valor es PONumber_0). Examen y validación de la carga de todos los mensajes salientes es otro ejemplo de una directriz principal que debe seguir al utilizar BizUnit.  
  
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
  
 La fase final del caso de prueba es la limpieza de nuevo. Como puede ver en este caso, el **FileDelete** paso de prueba se utiliza para limpiar los directorios utilizados por la prueba.  
  
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
  
 Espero que este ejemplo se muestra que la definición de pruebas en BizUnit es relativamente sencilla y que mediante el uso de este marco de pruebas, podrá para desarrollar con rapidez los casos de prueba para proporcionar las pruebas funcionales de la aplicación.  
  
### <a name="full-test-case-example"></a>Ejemplo de caso de prueba completa  
 El contenido del archivo de configuración completa de los casos de prueba se incluyen aquí para su referencia:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Usando BizUnit para facilitar la prueba automatizada](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)