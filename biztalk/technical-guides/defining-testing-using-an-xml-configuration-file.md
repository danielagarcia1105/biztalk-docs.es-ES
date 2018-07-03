---
title: Definición de pruebas mediante un archivo de configuración XML | Microsoft Docs
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
ms.openlocfilehash: dd869d69ca11a41daac459229d7b58684e43afe7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992949"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a>Definición de pruebas mediante un archivo de configuración XML
BizUnit ofrece dos formas de definir las pruebas: a través de un archivo de configuración XML y a través de una hoja de cálculo de Excel. En este tema se centra en usar un archivo de configuración XML para definir pruebas; Sin embargo, también debe consultar en el SDK de BizUnit, puesto que ofrece un ejemplo interesante de cómo definir los casos de prueba de BizUnit con Excel. Además, puede que desee investigar la herramienta Diseñador de BizUnit, que proporciona una interfaz gráfica de usuario que permite la rápida creación de casos de prueba de BizUnit. En este tema se proporciona información general de cómo definir casos de prueba mediante el uso de un escenario muy simplificado de configuración de XML.  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>Información general de la definición de un caso de prueba de BizUnit mediante la configuración XML  
 Como solo se indicó, este escenario se ha simplificado para fines ilustrativos. Considere un ejemplo de aplicación como el que se muestra a continuación de mensajería. Supongamos que el comportamiento funcional normal para esta aplicación es que BizTalk recibe un archivo XML a través de un archivo de ubicación de recepción, envía a un suscriptor adecuado en función de una suscripción. Para validar este escenario de forma eficaz, es importante realice los pasos siguientes en la prueba:  
  
1. Configurar el entorno para asegurarse de que se encuentra en un estado coherente y listo para la prueba se ejecute:  
  
   -   Para ello, elimine los archivos que se encuentran en las ubicaciones de dos archivos.  
  
2. Ejecute la prueba para comprobar la funcionalidad:  
  
   -   Crear un mensaje XML válido en la carpeta que el archivo de sondeos de la ubicación de recepción.  
  
   -   Validar que el mensaje XML correcto se coloca en la ubicación de carpeta de salida.  
  
   -   La validación debe cubrir el esquema y la información de carga para el mensaje. (Normalmente un par de los campos clave debe examinarse.)  
  
3. Limpiar el entorno para asegurarse de que el entorno está en el mismo estado que antes de la prueba que se ejecuta:  
  
   -   Elimine los archivos que se encuentran en las ubicaciones de dos archivos.  
  
   ![Aplicación de mensajería de BizTalk de ejemplo](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
   Aplicación de mensajería de BizTalk de ejemplo  
  
   Cada caso de prueba comienza y termina con la etiqueta TestCase XML; el parámetro testName se pasa en esto como se indica aquí.  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 A continuación, escribimos la fase de TestSetup, en el que nos aseguramos de que el entorno está en un estado coherente para ejecutar la prueba. En este ejemplo, se eliminación los mensajes XML que se encuentran en nuestro directorio TestData. Esto se realiza mediante el **FileDeleteMultipleStep**.  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 Escribimos, a continuación, ¿qué es la sección más importante de la prueba, la fase de ejecución de pruebas. Esta fase puede contener varios pasos de prueba. En este ejemplo usamos la FileCreateStep para copiar un documento (InDoc1.xml que pueden verse en el \<SourcePath\> etiqueta) a un destino de archivo que se usa por nuestra ubicación de recepción. Es importante tener en cuenta que BizUnit admite el uso de identificadores únicos para los nombres de archivo en este paso; Esto puede verse con el Guid % referencia en la etiqueta CreationPath %.  
  
 Una vez finalizado este procedimiento, es necesario usar el **FileValidateStep** validar el mensaje saliente se ha creado. Observará que este paso le permite especificar un valor de tiempo de espera (Esto está en milisegundos), el directorio y el patrón de búsqueda. Además, el **DeleteFile** etiqueta le permite especificar si desea quitar después de que se ha validado el archivo. Por último, también debe observar que la validación incluye una consulta XPath, que valida el nodo PONumber dentro del mensaje XML (comprueba que el valor es PONumber_0). Examen y la validación de la carga de los mensajes de salida es otro ejemplo de una entidad de seguridad fundamentales que debe seguir al uso de BizUnit.  
  
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
  
 La fase final del caso de prueba es la limpieza. Como puede verse en este caso, el **FileDelete** paso de prueba se utiliza para limpiar los directorios utilizados por la prueba.  
  
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
  
 Espero que este ejemplo se muestra que la definición de las pruebas en BizUnit es relativamente sencillo y que mediante el uso de este marco de prueba, podrá desarrollar rápidamente los casos de prueba proporcionan unas pruebas funcionales de la aplicación.  
  
### <a name="full-test-case-example"></a>Ejemplo de caso de prueba completa  
 El contenido del archivo de configuración de casos de prueba completos se incluyen aquí para su referencia:  
  
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
 [Uso de BizUnit para facilitar las pruebas automatizadas](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)