---
title: Planeación para consumir servicios Web | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24863069-929b-4b0b-9643-073965fb5532
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d8373ffa078b0138979e34a154330b429a73664
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986077"
---
# <a name="planning-for-consuming-web-services"></a>Planeación de consumo de servicios Web
Planeación de servicios Web puede dividirse en dos categorías, planificación de publicación de servicios Web y para consumir servicios Web. En este tema se describe las consideraciones para consumir servicios Web. Para obtener información sobre la publicación de servicios Web, consulte [planificación para publicar Services1 Web](../technical-guides/planning-for-publishing-web-services1.md).  
  
 A medida que cree el plan, tenga en cuenta lo siguiente:  
  
- **Uso de dos caracteres de subrayado en un nombre de parámetro**  
  
   Los nombres de parámetros de métodos Web no pueden empezar con "__" (dos caracteres de subrayado). Es posible que los nombres que empiezan con dos caracteres de subrayado creen entidades de mensajes Web que no son compatibles (inutilizables) en XLANG/s.  
  
- **El elemento Any y la anyAttribute no se admiten atributos en los métodos Web**  
  
   No puede usar el **cualquier** elemento o **anyAttribute** atributo en el esquema para un método Web.  
  
- **Uso de palabras clave XLANG/s**  
  
   Nombre de servicio Web o un nombre de método Web no puede ser una palabra clave en un XLANG/s. Si utiliza una palabra clave XLANG/s en el nombre del servicio Web o el nombre del método Web, obtendrá un error de compilación al agregar el servicio Web. Para obtener una lista de palabras reservadas para el lenguaje XLANG/s, consulte el [palabras reservadas de XLANG/s](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).  
  
- **XLANG/s requiere compatibilidad con tipos de parámetro**  
  
   Utiliza tipos de parámetros de XLANG/s admitidos Web método provocará errores de compilación. Por ejemplo, BizTalk Server no es compatible con un parámetro compuesto por una matriz de dimensión de tipos de esquemas. Además, BizTalk Server no es compatible con matrices multidimensionales. Para obtener una lista de palabras que lenguaje XLANG/s reserva en BizTalk Server, consulte [palabras reservadas de XLANG/s](http://go.microsoft.com/fwlink/?LinkId=155765) (http://go.microsoft.com/fwlink/?LinkId=155765).  
  
- **Evitar errores de compilación producidos al agregar referencias Web que contiene palabras clave de C# o identificadores**  
  
   Cuando se usa el **Agregar referencia Web**para agregar referencias Web a proyectos de BizTalk, BizTalk Server convierte los tipos de esquema que son necesarios para llamar a cada método Web como esquemas. BizTalk Server agrega estos esquemas a Reference.xsd. Si los esquemas contienen nombres de elementos que son palabras clave de C# o el nombre del elemento no es válido como identificador C#, obtendrá un error en tiempo de ejecución. Para evitar que se produzcan errores en tiempo de ejecución, asegúrese de que el servicio Web que consume no contiene nombres de elementos que sean palabras clave C# o identificadores C# no válidos.  
  
- **No se admiten varias definiciones de tipo de puerto/servicio**  
  
   BizTalk Server admite que se agregue un archivo de servicio Web con una única definición de tipo de puerto y de servicio. Si agrega un archivo WSDL con varias definiciones de tipo de puerto o de servicio, es posible que reciba el siguiente error:  
  
   `Could not generate BizTalk files. Object reference not set to an instance of an object.`  
  
- **Compatibilidad para utilizar matrices expuestas por servicios Web**  
  
   BizTalk Server puede consumir una matrices de dimensión y escalonadas expuestas por servicios Web que no son servicios Web de BizTalk Server. Para obtener más información acerca de cómo consumir matrices de servicios Web, consulte [cómo consumir matrices de servicios Web](http://go.microsoft.com/fwlink/?LinkId=155766) (http://go.microsoft.com/fwlink/?LinkId=155766).  
  
  > [!NOTE]  
  >  No se permite la sintaxis de matrices multidimensionales. Por ejemplo, *MyArray [1,5]*.  
  
  > [!NOTE]  
  >  BizTalk Server no admite el consumo de una matriz de **DataSet** objetos expuestos por un servicio Web. El subservicio XLANG/s admite de forma nativa la clase DataSet de .NET pero, si crea un proyecto de BizTalk que contiene una referencia Web a un servicio Web que expone una matriz de objetos .NET DataSet obtendrá errores al intentar compilar el proyecto.  
  
- **Parámetros de método de Web deben ser serializables con Xml**  
  
   Todos los parámetros de un servicio Web consumido deben ser serializables con Xml. Si agrega un método Web que contenga un parámetro que no es serializable con Xml, es posible que reciba el siguiente mensaje de error:  
  
   System.Xml.Element debe ser serializable con Xml para ser un tipo de parte de mensaje.  
  
  > [!NOTE]  
  >  Los tipos de datos **XmlDocument** y **DataSet**, mientras no serializables con Xml, se admiten.  
  
- **Consumir servicios Web únicamente de mensajería**  
  
   Al consumir servicios Web únicamente de mensajería, todos los nombres de parte de cuerpo de mensaje de BizTalk Server deben coincidir con los nombres de parámetro de método Web. Por ejemplo, si la firma del servicio Web es `WebMethod(MyType1 type1, MyType2 type2)`, el nombre de parte debe ser type1 y type2. Si no es así, es posible que se produzca el siguiente error en tiempo de ejecución:  
  
   `Failed to retrieve the message part for parameter %1`  
  
   Para obtener más información, consulte [cómo consumir servicios Web en un escenario de Messaging-Only](http://go.microsoft.com/fwlink/?LinkId=155767) (http://go.microsoft.com/fwlink/?LinkId=155767).  
  
- **Configurar un puerto de envío SOAP mediante programación**  
  
   Es posible establecer propiedades de configuración mediante programación en el contexto del mensaje. Puede establecer estas propiedades en una orquestación o un componente de canalización personalizado si el puerto de envío es estático o dinámico.  
  
  > [!NOTE]  
  >  Para configurar el **MethodName** puerto de envío propiedad de SOAP estático mediante programación, deberá establecer **nombre del método** a **[especificar más tarde]** en el **Web Servicio** pestaña de la **propiedades de transporte SOAP** cuadro de diálogo en la consola de administración de BizTalk Server.  
  
   Para obtener más información sobre la **MethodName** propiedad, vea [cómo establecer dinámicamente el URI de un servicio Web consumido](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).  
  
- **Reglas de propiedad**  
  
   Si la propiedad de configuración se establece en una orquestación o en un componente de canalización personalizado de una canalización de recepción, se aplican las siguientes reglas:  
  
  - Si se envía un mensaje a un puerto de envío estático, el valor de la propiedad se sobrescribirá con el valor configurado para dicho puerto de envío.  
  
  - Si el mensaje se envía a un puerto de envío dinámico, el valor de la propiedad no se sobrescribirá.  
  
    Si una propiedad de configuración se establece en un componente de canalización personalizado de una canalización de envío, se aplica la siguiente regla:  
  
  - El valor no se sobrescribirá independientemente de que el mensaje se envíe a un puerto de envío estático o dinámico. En otras palabras, los componentes de canalización de envío sobrescriben la propiedad de configuración sin tener en cuenta dónde se ha definido.  
  
  - Para obtener más información acerca de los componentes de canalización personalizado, consulte [desarrollar componentes de canalización personalizados](http://go.microsoft.com/fwlink/?LinkId=155769) (http://go.microsoft.com/fwlink/?LinkId=155769).  
  
  - Para obtener más información acerca de las propiedades de configuración del adaptador de envío SOAP, vea [cómo establecer dinámicamente el URI de un servicio Web consumido](http://go.microsoft.com/fwlink/?LinkID=155768) (http://go.microsoft.com/fwlink/?LinkID=155768).  
  
- **Agregar una referencia Web a un servicio Web consumido que contiene un esquema multiraíz provocará un Error de compilación**  
  
   Si agrega una referencia Web a su proyecto para un servicio Web que se derivó de una orquestación de BizTalk publicada y la orquestación contiene un esquema con varias raíces, se producirá un error cuando se compila el proyecto. Si agrega una referencia Web al proyecto que se ha derivado de una orquestación de BizTalk publicada, asegúrese de que la orquestación no contiene esquemas multiraíces.  
  
- **Utilizar TypedDataSets como parámetros en métodos Web**  
  
   A continuación, se muestran los pasos necesarios para permitir que se utilice TypedDataSets como parámetros en métodos Web:  
  
  1.  Agregue la referencia Web a un proyecto C# y genere el proxy.  
  
  2.  Cree un puerto de envío SOAP y especifique el proxy en el puerto de envío y seleccione el método.  
  
  3.  En la orquestación, defina un puerto enlazado en tiempo de ejecución y los tipos de mensajes. Para la mayoría de los casos donde no se necesita ningún acceso de campo distintivo o promoción de propiedades, se puede definir el tipo como **XMLDocument**. Seleccione las canalizaciones PassThrough con este tipo.  
  
  4.  En la consola de administración de BizTalk Server, en el **servicio Web** pestaña en el **propiedades de transporte SOAP** cuadro de diálogo de SOAP, puerto de envío, especifique que desea utilizar el proxy que ha creado. También será necesario especificar el ensamblado, tipo y método.  
  
- **Agregar una referencia Web a un servicio Web consumido que contiene un método Web espera parámetros basados en genérico provocará un Error de compilación**  
  
   Si agrega una referencia Web a su proyecto para un servicio Web que contiene un método Web espera parámetros basadas en genéricos, como los parámetros que aceptan valores NULL, se producirá un error cuando se compila el proyecto. Esto no se admite. Debe utilizar especialización explícita para llamar a la clase genérica de XLANG/s.  
  
- **Generación de esquemas de BizTalk mediante el Agregar referencia Web**  
  
   Cuando se usa el **Agregar referencia Web**para agregar referencias Web a proyectos de BizTalk, BizTalk Server convierte los tipos de esquema que son necesarios para llamar a cada método Web como esquemas. BizTalk Server agrega estos esquemas a Reference.xsd. Para asegurarse de que el **Agregar referencia Web** genera los esquemas de BizTalk correctamente, los servicios Web deben ajustarse a las siguientes directrices:  
  
  -   Deben tener métodos Web **SoapDocumentMethodAttribute** en lugar de **SoapRpcMethodAttribute**.  
  
  -   Servicios Web y métodos deben utilizar el **Literal** enlace en lugar de **Encoded** como **[SoapDocumentMethod(Use=SoapBindingUse.Literal)]**.  
  
  -   Parámetros del método Web y devolver tipos deben tener **XmlRootAttribute** con válido **Namespace** propiedad a menos que sean tipos XSD nativos y el tipo XmlNode.  
  
  -   Los métodos Web no deben usar el **RequestNamespace** y **ResponseNamespace** propiedades en **SoapDocumentMethodAttribute**.  
  
  -   Los servicios Web deben ser compatibles con la versión 1.1 del perfil básico de Interoperabilidad de servicios Web (WSI).  
  
- **El Agregar referencia Web no admite el elemento de importación de Web Services Description Language (WSDL)**  
  
   Se ha producido un error en la opción Agregar referencia Web al agregar referencias Web para el archivo WSDL con el elemento de importación.  
  
## <a name="see-also"></a>Vea también  
 [Planificación del nivel de BizTalk Server](../technical-guides/planning-the-biztalk-server-tier.md)