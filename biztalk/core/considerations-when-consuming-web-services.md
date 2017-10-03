---
title: Consideraciones al consumir servicios Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea7038dc-4740-4c0a-b6a1-08bc22f42bc2
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5cbef60d968119950b6c426a45c94d2e9ab60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-consuming-web-services"></a>Consideraciones al consumir servicios Web
Esta sección proporciona información que es necesario tener en cuenta a la hora de consumir servicios Web.  
  
## <a name="using-two-underscore-characters-in-a-parameter-name"></a>Utilizar dos caracteres de subrayado del nombre de parámetro  
 Los nombres de parámetros de métodos Web no pueden empezar con "__" (dos caracteres de subrayado). Es posible que los nombres que empiezan con dos caracteres de subrayado creen entidades de mensajes Web que no son compatibles (inutilizables) en XLANG/s.  
  
## <a name="the-any-element-and-the-anyattribute-attributes-are-not-supported-in-web-methods"></a>El elemento any y los atributos anyAttribute no son compatibles en los métodos Web  
 No se puede utilizar el **cualquier** elemento o **anyAttribute** atributo en el esquema para un método Web.  
  
## <a name="using-xlangs-keywords"></a>Utilizar palabras clave para XLANG/s  
 Nombre de servicio Web o un nombre de método Web no puede ser una palabra clave en una XLANG/s. Si utiliza una palabra clave XLANG/s en el nombre del servicio Web o el nombre del método Web, obtendrá un error de compilación cuando se agrega el servicio Web. Para obtener una lista de palabras reservadas para el idioma XLANG/s, consulte [palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md).  
  
## <a name="required-xlangs-support-for-parameter-types"></a>Compatibilidad de XLANG/s necesaria para tipos de parámetros  
 Utilizar un tipo de parámetro de método Web que no sea compatible con XLANG/s producirá errores de compilación. Por ejemplo, BizTalk Server no es compatible con un parámetro compuesto por una matriz de dimensión de tipos de esquemas. Además, BizTalk Server no es compatible con matrices multidimensionales. Para obtener una lista de palabras que lenguaje XLANG/s reserva en BizTalk Server, vea [palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md).  
  
## <a name="avoiding-compilation-errors-caused-by-adding-web-references-containing-c-keywords-or-identifiers"></a>Evitar errores de compilación producidos al agregar referencias Web que contienen palabras clave o identificadores C#  
 Cuando se usa el **Agregar referencia de servicio** para agregar referencias de servicio a los proyectos de BizTalk, BizTalk Server convierte los tipos de esquema necesarios para llamar a cada método Web a los esquemas. BizTalk Server agrega estos esquemas a Reference.xsd. Si los esquemas contienen nombres de elementos que son palabras clave de C# o el nombre de elemento no es válido como identificador de C#, obtendrá un error en tiempo de ejecución. Para evitar que se produzcan errores en tiempo de ejecución, asegúrese de que el servicio Web que consume no contiene nombres de elementos que sean palabras clave C# o identificadores C# no válidos.  
  
## <a name="multiple-serviceport-type-definitions-are-unsupported"></a>Varias definiciones no admitidas de tipo de puerto/servicio  
 BizTalk Server admite que se agregue un archivo de servicio Web con una única definición de tipo de puerto y de servicio. Si agrega un archivo WSDL con varias definiciones de tipo de puerto o de servicio, es posible que reciba el siguiente error:  
  
 No se pudieron generar archivos de BizTalk. Referencia de objeto no definida a una instancia de un objeto.  
  
## <a name="support-for-consuming-arrays-exposed-by-web-services"></a>Compatibilidad para utilizar matrices expuestas por servicios Web  
 BizTalk Server puede consumir matrices de una dimensión y escalonadas expuestas por servicios Web que no son servicios Web de BizTalk. Para obtener más información acerca de cómo consumir matrices de servicios Web, consulte [cómo consumir matrices de servicios Web](../core/how-to-consume-web-service-arrays.md).  
  
> [!NOTE]
>  No se permite la sintaxis de matrices multidimensionales. Por ejemplo, `MyArray[1,5]`.  
  
> [!NOTE]
>  BizTalk Server no permite utilizar una matriz de **conjunto de datos** objetos expuestos por un servicio Web. El subservicio XLANG/s no admite, de forma nativa, la clase .NET DataSet, pero si crea un proyecto de BizTalk que contenga una referencia Web en un servicio Web que exponga una matriz de objetos .NET DataSet, se producirán errores al intentar compilar el proyecto.  
  
## <a name="web-method-parameters-must-be-xml-serializable"></a>Parámetros del método Web deben ser serializables con Xml  
 Todos los parámetros de un servicio Web consumido deben ser serializables con Xml. Si agrega un método Web que contenga un parámetro que no es serializable con Xml, es posible que reciba el siguiente mensaje de error:  
  
 System.Xml.Element debe ser serializable con Xml para ser un tipo de parte de mensaje.  
  
> [!NOTE]
>  Los tipos de datos **XmlDocument** y **conjunto de datos**, al no serializables con Xml, son compatibles.  
  
## <a name="consuming-messaging-only-web-services"></a>Consumir servicios Web únicamente de mensajería  
 Al consumir servicios Web únicamente de mensajería, todos los nombres de partes del cuerpo del mensaje de BizTalk deben ajustarse a los nombres de parámetros del método Web. Por ejemplo, si la firma del servicio Web es `WebMethod(MyType1 type1, MyType2 type2)`, el nombre de parte debe ser type1 y type2. Si no es así, es posible que se produzca el siguiente error en tiempo de ejecución:  
  
 No se pudo recuperar la parte de mensaje para el parámetro %1  
  
 Para obtener más información, consulte [cómo consumir servicios Web en un escenario de mensajería solo](../core/how-to-consume-web-services-in-a-messaging-only-scenario.md).  
  
## <a name="configuring-a-soap-send-port-programmatically"></a>Configurar un puerto de envío SOAP mediante programación  
 Es posible establecer propiedades de configuración mediante programación en el contexto del mensaje. Se pueden establecer estas propiedades en una orquestación o en un componente de canalización personalizado, si el puerto de envío es estático o dinámico.  
  
> [!NOTE]
>  Para configurar el **MethodName** puerto de envío propiedad de SOAP estático mediante programación, es necesario establecer **nombre del método** a **[especificar más tarde]** en el **Web Servicio** pestaña de la **propiedades de transporte SOAP** cuadro de diálogo de la consola de administración de BizTalk Server.  
>   
>  Para obtener más información sobre la **MethodName** propiedad, vea [cómo establecer dinámicamente el URI de un servicio Web consumido](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md).  
>   
>  Para obtener más información acerca de **propiedades de transporte SOAP** cuadro de diálogo, vea el **cuadro de diálogo de propiedades de transporte SOAP, servicio Web** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="property-rules"></a>Reglas de propiedades  
 Si la propiedad de configuración se establece en una orquestación o en un componente de canalización personalizado de una canalización de recepción, se aplican las siguientes reglas:  
  
-   Si se envía un mensaje a un puerto de envío estático, el valor de la propiedad se sobrescribirá con el valor configurado para dicho puerto de envío.  
  
-   Si el mensaje se envía a un puerto de envío dinámico, el valor de la propiedad no se sobrescribirá.  
  
 Si una propiedad de configuración se establece en un componente de canalización personalizado de una canalización de envío, se aplica la siguiente regla:  
  
-   El valor no se sobrescribirá independientemente de que el mensaje se envíe a un puerto de envío estático o dinámico. En otras palabras, los componentes de canalización de envío sobrescriben la propiedad de configuración sin tener en cuenta dónde se ha definido.  
  
-   Para obtener más información acerca de los componentes de canalización personalizado, consulte [desarrollar componentes de canalización personalizados](../core/developing-custom-pipeline-components.md).  
  
-   Para obtener más información acerca de las propiedades de configuración del adaptador de envío SOAP, vea [cómo establecer dinámicamente el URI de un servicio Web consumido](../core/how-to-dynamically-set-the-uri-of-a-consumed-web-service.md).  
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-multi-rooted-schema-will-cause-a-compilation-error"></a>Agregar una referencia Web a un servicio Web consumido que contiene un esquema multiraíz producirá un error de compilación  
 Si agrega una referencia Web a su proyecto para un servicio Web que se ha derivado de una orquestación de BizTalk publicada y la orquestación contiene un esquema con varias raíces, se producirá un error al compilar el proyecto. Si agrega una referencia Web al proyecto que se ha derivado de una orquestación de BizTalk publicada, asegúrese de que la orquestación no contiene esquemas multiraíces.  
  
## <a name="using-typeddatasets-as-parameters-to-web-methods"></a>Utilizar TypedDataSets como parámetros en métodos Web  
 A continuación, se muestran los pasos necesarios para permitir que se utilice TypedDataSets como parámetros en métodos Web:  
  
1.  Agregue la referencia Web a un proyecto C# y genere el proxy.  
  
2.  Cree un puerto de envío SOAP y especifique el proxy en el puerto de envío y seleccione el método.  
  
3.  En la orquestación, defina un puerto enlazado en tiempo de ejecución y los tipos de mensajes. Para la mayoría de los casos que no se necesita ninguna promoción de propiedades o acceso de campo distintivo, se puede definir el tipo como **XMLDocument**. Seleccione las canalizaciones PassThrough con este tipo.  
  
4.  En la consola de administración de BizTalk Server, en la **servicio Web** pestaña en el **propiedades de transporte SOAP** cuadro de diálogo de SOAP puerto de envío, especifique que desea utilizar el proxy que creó. También será necesario especificar el ensamblado, tipo y método. Para obtener más información, consulte el **cuadro de diálogo de propiedades de transporte SOAP, servicio Web** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="adding-a-web-reference-to-a-consumed-web-service-that-contains-a-web-method-expecting-generic-based-parameters-will-cause-a-compilation-error"></a>Agregar una referencia Web a un servicio Web consumido que contiene un método Web que espera que los parámetros basados en tipos genéricos produzcan un error de compilación  
 Si agrega una referencia Web a su proyecto para un servicio Web que contiene un método Web que espera que los parámetros basados en tipos genéricos como los parámetros anulables, se producirá un error al compilar el proyecto. Esto no se admite. Debe utilizar especialización explícita para llamar a la clase genérica de XLANG/s.  
  
## <a name="biztalk-schema-generation-using-the-add-service-reference"></a>Generación de esquemas de BizTalk mediante la opción Agregar referencia de servicio  
 Cuando se usa el **Agregar referencia de servicio** para agregar referencias de servicio a los proyectos de BizTalk, BizTalk Server convierte los tipos de esquema necesarios para llamar a cada método Web a los esquemas. BizTalk Server agrega estos esquemas a Reference.xsd. Para asegurarse de que el **Agregar referencia de servicio** genera los esquemas de BizTalk correctamente, los servicios Web deben ajustarse a las siguientes directrices:  
  
-   Métodos Web deben tener **SoapDocumentMethodAttribute** en lugar de **SoapRpcMethodAttribute**.  
  
-   Servicios Web y métodos deben utilizar el **Literal** enlace en lugar de **Encoded** como **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**.  
  
-   Parámetros del método Web y devolver los tipos deben tener **XmlRootAttribute** con válido **Namespace** propiedad a menos que sean tipos XSD nativos y el tipo XmlNode.  
  
-   Métodos Web no deben utilizar el **RequestNamespace** y **ResponseNamespace** propiedades en **SoapDocumentMethodAttribute**.  
  
-   Los servicios Web deben ser compatibles con la versión 1.1 del perfil básico de Interoperabilidad de servicios Web (WSI).  
  
## <a name="xsd-will-not-contain-nodes-for-simple-parameter-types"></a>XSD no contendrá nodos para tipos de parámetro simples  
 Cuando se agrega una referencia Web y el método Web tiene un parámetro de tipo simple, el XSD generado no contendrá nodos para ese parámetro. En cambio, el mensaje de varias partes que se genere contendrá una parte de tipo simple. La orquestación debe controlar esta parte de mensaje de forma adecuada. Si es una parte de la solicitud al servicio Web, asigne manualmente el valor para esa parte con un mensaje de forma de asignación. Si es una parte de la respuesta del servicio Web, obtenga acceso manualmente a esa parte, en una forma de expresión, para ver el valor.  
  
## <a name="the-add-service-reference-do-not-support-the-web-services-description-language-wsdl-import-element"></a>La opción Agregar referencia de servicio no es compatible con el elemento de importación de Lenguaje de descripción de servicios Web (WSDL)  
 Se ha producido un error en la opción Agregar referencia de servicio al agregar referencias de servicio para el archivo WSDL con el elemento de importación.  
  
## <a name="see-also"></a>Vea también  
 [Construcción de mensajes Web](../core/constructing-web-messages.md)