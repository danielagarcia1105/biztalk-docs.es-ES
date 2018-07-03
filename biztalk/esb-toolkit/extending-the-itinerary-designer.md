---
title: Ampliar el Diseñador de itinerarios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f26b825b-ebab-4dac-b7ed-0608c79e146a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fbe9e24560f8f00f4b3d806c76ebc326240add5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980749"
---
# <a name="extending-the-itinerary-designer"></a>Ampliar el Diseñador de itinerarios
El Diseñador de itinerario es un lenguaje visual específicos de dominio (DSL) para Microsoft Visual Studio que permite el modelado gráfico de itinerarios para su uso con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. El diseñador expone varios puntos de extensión para que los desarrolladores pueden escribir extensiones personalizadas para habilitar la funcionalidad nueva o nuevas opciones de configuración.  
  

  
 **Creación de un exportador de itinerarios personalizado**  
  
 La arquitectura del Diseñador de itinerario permite la creación de exportadores de modelos personalizados que serializar y conservar los datos en un modelo de itinerario.  
  
 **Creación de un extensor personalizado para un servicio de mensajería**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerarios que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por los servicios de mensajería.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Creación de un extensor personalizado para un servicio de itinerarios de orquestación**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerarios que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por los servicios de itinerario de orquestación.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Crear un extensor de resolución personalizada**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de los solucionadores personalizados. Estos extensores proporcionan una interfaz gráfica para configurar los pares de nombre-valor en la cadena de conexión de la resolución, que se asignan a las propiedades de la clase de extensor de resolución específico.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Creación de un archivo de manifiesto para las propiedades de adaptador personalizado**  
  
 Al crear un proveedor de adaptador personalizado, también debe proporcionar compatibilidad con el diseñador para el proveedor del adaptador a los extensores de resolución que mostrar una propiedad de configuración de punto de conexión. Para habilitar la compatibilidad con el diseñador, es necesario crear un archivo de manifiesto del proveedor de adaptador.  
  
 El archivo de manifiesto del proveedor de adaptador define las propiedades asociadas con un proveedor de adaptador específico, sus tipos, descripciones y el ensamblado en el que puede encontrarse. Estos archivos de manifiesto deben colocarse en la misma carpeta que los archivos binarios del Diseñador de itinerario (por ejemplo, Microsoft.Practices.Itineary.DslPackage.dll) con un nombre único (por ejemplo, FTPPropertyManifest.xml).  
  
 La siguiente es una instancia de la referencia de un archivo de manifiesto del proveedor de adaptador; los archivos de manifiesto personalizados deben estar estructurados del mismo modo.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<adapterPropertyManifest adapterName="FTP">  
     <aliases>  
          <alias name="globalPropertySchemas" value="Microsoft.BizTalk.GlobalPropertySchemas, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     </aliases>  
     <properties>  
          <property name="UserName" type="FTP.UserName" description="The user name for the connection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="Password" type="FTP.Password" description="The password for the conection." encrypted="true" assembly="globalPropertySchemas" />  
          <property name="MaxConnections" type="FTP.MaxConnections" description="The maximun number of connections." assembly="globalPropertySchemas" />  
          <property name="EventArgs" type="System.EventArgs" assembly="mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
     </properties>  
</adapterPropertyManifest>  
```  
  
 **Crear un extensor de filtro personalizado**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de filtros personalizados. Estos extensores proporcionan una interfaz gráfica para configurar los pares de nombre-valor en la cadena de conexión de filtro, que se asignan a las propiedades de la clase de extender un filtro específico.  
  
- / Samples/diseñador extensibilidad Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample  
  
- / Samples/diseñador extensibilidad Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample  
  
  **Creación de reglas de validación personalizadas**  
  
  La última extensión importante introducida por el Diseñador de itinerarios es un mecanismo de validación que permite externamente, con respecto a un lenguaje específico de dominio (DSL), especificar e implementar las reglas de validación del modelo. El mecanismo de "enlaza a" el marco de validación de DSL y se activa cuando el usuario hace clic **validar** o **validar todos** en el menú contextual de un modelo. Esto invoca el marco DSL **DslCommandSet** objeto que, a su vez, llama al motor de validación en el Diseñador de itinerario.  
  
  El **ValidationEngine** clase realiza la validación del elemento de modelo mediante el bloque de aplicación de Enterprise Library validación y registra los errores de validación en la ventana Lista de errores en el IDE de Microsoft Visual Studio. La validación que debe realizarse para cada tipo de elemento de un modelo se define en el archivo de configuración de Enterprise Library. El archivo se denomina Ruleset.config y se encuentra en la carpeta binaria donde se encuentran todos los archivos binarios de diseñador de itinerario. El ejemplo siguiente es un fragmento del archivo de configuración e incluye dos reglas de validación (denominadas validadores) para el **UddiResolver** extensor, uno para el **ServerUrl** propiedad y otro para el  **Valor de ServiceKey** propiedad.  
  
```  
<!--   
UddiResolver  
-->  
<type assemblyName="Microsoft.Practices.Services.Extenders.Resolvers.UDDI"  
 name="Microsoft.Practices.Services.Extenders.Resolvers.UDDI.UddiResolver">  
<ruleset name="Menu">  
<properties>  
<property name="ServerUrl">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServerUrl not null validator"/>  
</property>  
<property name="ServiceKey">  
<validator type="Microsoft.Practices.Modeling.Validation.NotEmptyStringValidator, Microsoft.Practices.Modeling.Validation"  
          messageTemplate="The '{1}' property value should not be empty or null."  
          name="UddiResolver.ServiceKey not null validator"/>  
</property>  
</properties>  
</ruleset>  
</type>  
```  
  
 Cada regla identifica el control de validación que implementa la regla. El Diseñador de itinerario viene con un conjunto grande de las clases de validación. Todos se encuentran en el proyecto Microsoft.Practices.Modeling.Validation en la carpeta binario del diseñador.  
  
 El resultado final del uso de este mecanismo de validación es ese diseñador de itinerario los usuarios pueden modificar cómo se validan los modelos cambiando las reglas proporcionadas y validadores o agregando sus propias reglas y los validadores. Esto puede realizarse sin abrir, modificar, recompilar y volver a implementar los DSL mediante la realización de los dos pasos siguientes:  
  
1.  Cree una clase de validador y colóquela en una biblioteca dentro de la carpeta binaria donde el **Microsoft.Practices.Modeling.Validation.dll** biblioteca se encuentra.  
  
2.  Agregue entradas al archivo Rules.config para definir qué propiedad de qué clase de elemento de modelo se debe aplicar el control de validación.