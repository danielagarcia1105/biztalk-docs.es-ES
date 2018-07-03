---
title: Controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91cac57a7651e0ab0abaebe3de42f89e5f49179e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977285"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a>Controlador de propiedad XPath arbitrario (ejemplo de BizTalk Server)
El controlador de propiedad XPath arbitrario (ejemplo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]) muestra cómo escribir un componente de canalización personalizado para promover propiedades específicas en un documento XML que se envía a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede utilizar la funcionalidad contenida en el ejemplo para crear componentes de ensamblador y desensamblador normales personalizados para evaluar las expresiones XPath.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo incluye un documento XML de pedido de compra (PO) que se debe procesar, DocInstance.xml. El ejemplo realiza los siguientes pasos para procesar DocInstance.xml:  
  
1. Un puerto de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera DocInstance.xml y un componente de canalización personalizado denominado controlador de propiedad XPath arbitrario lo procesa.  
  
2. El componente de controlador de propiedad XPath arbitrario promueve todos \<precio\> y \<cantidad\> elementos con una expresión XPath arbitraria, como se definen en el esquema de pedido de compra. Además, la expresión XPath contiene la construcción de la posición que se va a usar con elementos secundarios ambiguos del elemento raíz del documento de pedido de compra.  
  
3. El componente de controlador de propiedad XPath arbitrario determina el tipo de mensaje y lo promueve en el contexto del mensaje.  
  
4. A continuación, el componente envía el documento XML con los elementos promocionados a una orquestación para su posterior procesamiento.  
  
5. La orquestación obtiene acceso a los elementos promocionados del documento de pedido de compra y calcula el número total de elementos del pedido de compra.  
  
6. La orquestación crea un nuevo documento de pedido de compra que contiene la información del pedido de compra original, así como el total actualizado.  
  
7. El nuevo documento de pedido de compra se escribe en un archivo del directorio \Output.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de la ruta de acceso\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|ArbitraryXPathPropertyHandler.sln|Archivo de solución del componente de canalización personalizado.|  
|ArbitraryXPathPropertyHandler.resX|Archivo de recursos.|  
|ArbitraryXPathPropertyHandlerComp.cs|Implementación del componente principal.|  
|AssemblyInfo.cs|Información sobre el ensamblado.|  
|Cleanup.bat|Archivo de limpieza de ejemplo.|  
|PromotingMap.cs|Promoción de propiedades como implementación de asignación de tipos CLR nativos.|  
|PropertyAttributes.cs|Atributos personalizados, descriptor de propiedades e implementación de ICustomTypePropertyDescriptor.|  
|SchemaMap.cs|Asignación de esquemas del tipo de mensaje a IDocumentSpec para resolver la ambigüedad del esquema.|  
|Setup.bat|Componente de canalización de ejemplo de configuración y de versión de compilación.|  
|VirtualStream.cs|Implementación de secuencia virtual.|  
|SeekableReadOnlyStream.cs|Implementación de secuencia de sólo lectura en la que se pueden efectuar búsquedas.|  
|ArbitraryXPathSample.sln|Archivo de solución de orquestación de ejemplo.|  
|CalculateTotalAmount.odx|Orquestación de ejemplo.|  
|PODocument.xsd|Esquema del pedido de compra.|  
|DocInstance.xml|Instancia del pedido de compra de ejemplo.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Este ejemplo está diseñado para ejecutarse en un entorno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] en ejecución en el mismo equipo. Si el entorno no coincide con esta configuración, debe modificar el controlador de propiedad XPath arbitrario (ejemplo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]) para elegir el equipo de servidor SQL Server correcto.  
  
> [!IMPORTANT]
>  Setup.bat supone que el directorio de instalación de Microsoft Windows es C:\Windows. Si la instalación de Windows se encuentra en otro directorio, debe modificar el archivo ArbitraryXPathPropertyHandler.csproj para reflejar la ubicación del ensamblado Microsoft.BizTalk.Component.Utilities en la caché de ensamblados global. En el elemento de referencia, cambie \<SYSTEMROOT\> a la ubicación donde está instalado Windows (por ejemplo, C:\WINNT\\).  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 Utilice el siguiente procedimiento para generar e inicializar el controlador de propiedad XPath arbitrario (ejemplo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1. En una ventana de comandos, cambie los directorios (**cd**) a la siguiente carpeta:  
  
    *\<Ejemplos de la ruta de acceso\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  
  
   - Genera el componente de canalización del controlador de propiedad XPath arbitrario.  
  
   - Componente de canalización integradas de copias del  *\<ruta de instalación\>* directorio \Pipeline Components.  
  
   - Crea los puertos de envío y recepción.  
  
   - Crea los directorios de entrada y salida utilizados en el ejemplo.  
  
   - Instala la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de ejemplo ArbitraryXPathSample.  
  
   - Enlaza los puertos en la orquestación de ejemplo.  
  
   - Inicia la orquestación.  
  
   > [!NOTE]
   >  No se deben generar informes de errores durante la generación y la inicialización. En caso de que se produzca algún error, asegúrese de que tiene instalado todo el software necesario y que las herramientas de generación de Microsoft se encuentran disponibles en la ruta.  
   > 
   > [!NOTE]
   >  Para deshacer los cambios realizados por Setup.bat, debe detener y reiniciar, en primer lugar, la instancia de host de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. A continuación, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Use el siguiente procedimiento para ejecutar el controlador de propiedad XPath arbitrario (ejemplo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1.  Copie el archivo de pedido de compra (PO) DocInstance.xml en el directorio \Input. Un puerto de recepción recoge el archivo de pedido de compra y envía los datos XML al componente de canalización del controlador de propiedad Xpath arbitrario.  
  
2.  Vea el contenido del directorio \Output. Tenga en cuenta que se crea un archivo nuevo que contiene toda la información del archivo DocInstance.xml que ha copiado en el directorio \Input. La diferencia en el archivo es que ahora el \<TotalAmount\> elemento se ha rellenado con la cantidad total del pedido de compra.  
  
## <a name="comments"></a>Comentarios  
 Las expresiones XPath canónicas son expresiones simples, como "/ * [local-name () = 'element-name' and namespaceURI() ='http://MyUri.org'] /\*[local-name () = 'element-name'] / @\*[local-name = 'attribute name']".  
  
 Una expresión XPath arbitraria puede ser tan compleja como "//element-name//*[local-name()='element-name' and position()=2]". Dado el caso, recibirá un error de tiempo de ejecución que indica que las expresiones XPath no canónicas no son compatibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] si el esquema tiene un XPath no canónico utilizado en el cuerpo de XPath o en una propiedad de XPath. Una solución para admitir expresiones XPath arbitrarias es crear componentes de desensamblador y de ensamblador personalizados que admiten un cuerpo de XPath arbitrario, así como expresiones de propiedad de XPath arbitrarias.  
  
 Este ejemplo utiliza la siguiente secuencia de pasos en el componente de canalización personalizado cuando **IComponent.Execute** se implementa:  
  
1.  Crea una secuencia virtual que permite efectuar búsquedas en la secuencia de parte del cuerpo del mensaje de entrada. (Puesto que es posible que el mensaje de entrada sea grande y la secuencia no permita efectuar búsquedas, debe tener un pequeño volumen de memoria y poder cambiar las posiciones de la secuencia).  
  
2.  Crea un nuevo mensaje saliente y una nueva parte del cuerpo para ello, asigna una secuencia virtual a la nueva parte del cuerpo y clona las propiedades de la parte del cuerpo y el contexto del mensaje.  
  
3.  Obtiene un esquema para el mensaje de entrada o se basa en los esquemas especificados durante el tiempo de diseño.  
  
4.  Carga la secuencia en una instancia de **System.Xml.XmlDocument**.  
  
5.  Inspecciona las propiedades promocionadas y los campos distinguidos, además de promoverlos o escribirlos en el contexto del mensaje saliente.  
  
6.  Devuelve el mensaje saliente.  
  
7.  Escribe el mensaje saliente en un archivo.  
  
## <a name="see-also"></a>Vea también  
 [Canalizaciones (carpeta de ejemplos de BizTalk Server)](../core/pipelines-biztalk-server-samples-folder.md)