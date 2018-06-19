---
title: Extender el Diseñador de itinerarios | Documentos de Microsoft
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
ms.openlocfilehash: 78490c7b6447ddb097c0ca61154aab20c44086c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974482"
---
# <a name="extending-the-itinerary-designer"></a>Extender el Diseñador de itinerarios
El Diseñador de itinerario es un lenguaje específico de dominio visual (DSL) para Microsoft Visual Studio que permite el modelado del gráfico de itinerarios para su uso con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. El diseñador expone varios puntos de extensión para que los programadores pueden escribir extensiones personalizadas para habilitar la funcionalidad nueva o nuevas opciones de configuración.  
  

  
 **Crear un exportador itinerario personalizado**  
  
 La arquitectura del Diseñador de itinerario permite la creación de exportadores de modelos personalizados que serializar y conservar los datos en un modelo de itinerario.  
  
 **Creación de un extensor personalizado para un servicio de mensajería**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerario que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por los servicios de mensajería.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Creación de un extensor personalizado para un servicio de itinerarios basado en la orquestación**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerario que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por servicios de itinerario en la orquestación.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Creación de un extensor de resolución personalizada**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de los solucionadores personalizados. Estos extensores ofrecen una interfaz gráfica para configurar los pares de nombre y valor en la cadena de conexión de la resolución, que se asignan a las propiedades de la clase de dispositivo extender de resolución específico.  
  
 Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).  
  
 **Crear un archivo de manifiesto para las propiedades de adaptador personalizado**  
  
 Al crear un proveedor de adaptador personalizado, también debe proporcionar compatibilidad con el diseñador para el proveedor del adaptador a los extensores de resolución que mostrar una propiedad de configuración de punto de conexión. Para habilitar la compatibilidad con el diseñador, es necesario crear un archivo de manifiesto del proveedor de adaptador.  
  
 El archivo de manifiesto del proveedor de adaptador define las propiedades asociadas a un proveedor de adaptador específico, sus tipos, descripciones y el ensamblado en el que se pueden encontrar. Estos archivos de manifiesto deben colocarse en la misma carpeta que los archivos binarios del Diseñador de itinerario (por ejemplo, Microsoft.Practices.Itineary.DslPackage.dll) con un nombre único (por ejemplo, FTPPropertyManifest.xml).  
  
 La siguiente es una instancia de la referencia de un archivo de manifiesto del proveedor de adaptador; archivos de manifiesto personalizados deben estructurarse del mismo modo.  
  
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
  
 **Creación de un extensor de filtro personalizado**  
  
 La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de filtros personalizados. Estos extensores ofrecen una interfaz gráfica para configurar los pares de nombre y valor en la cadena de conexión de filtro, que se asignan a las propiedades de la clase de extender filtros específicos.  
  
-   / Samples/diseñador extensibilidad Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample  
  
-   / Samples/diseñador extensibilidad Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample  
  
 **Crear reglas de validación personalizadas**  
  
 La última extensión importante introducida por el Diseñador de itinerario es un mecanismo de validación que le permite externamente, con respecto a un lenguaje específico de dominio (DSL), especificar e implementar las reglas de validación del modelo. El mecanismo de "enlaza en" el marco de validación de DSL y se activa cuando el usuario hace clic en **validar** o **todas las validar** en el menú contextual de un modelo. Esto invoca el marco de trabajo DSL **DslCommandSet** objeto que, a su vez, llama al motor de validación en el Diseñador de itinerario.  
  
 El **ValidationEngine** clase realiza la validación de elemento de modelo mediante el bloque de aplicaciones de Enterprise Library validación y registra los errores de validación en la ventana Lista de errores de Microsoft Visual Studio IDE. La validación que se debe realizar para cada tipo de elemento de un modelo se define en el archivo de configuración de Enterprise Library. El archivo se denomina Ruleset.config y se encuentra en la carpeta binaria donde se encuentran todos los binarios de diseñador de itinerario. En el ejemplo siguiente se muestra un fragmento del archivo de configuración e incluye dos reglas de validación (denominadas validadores) para la **UddiResolver** dispositivo extender, uno para la **ServerUrl** propiedad y otra para el  **ServiceKey** propiedad.  
  
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
  
 Cada regla identifica el validador que implementa la regla. El Diseñador de itinerario incluye un conjunto grande de las clases de validación. Todos están en el proyecto Microsoft.Practices.Modeling.Validation en la carpeta binaria del diseñador.  
  
 El resultado final del uso de este mecanismo de validación es que ese diseñador de itinerario los usuarios pueden modificar cómo se validan los modelos mediante la modificación de las reglas proporcionadas y validadores o agregando sus propias reglas y validadores. Esto puede realizarse sin abrir, modificar, volver a generar y volver a implementar la DSL mediante la realización de los dos pasos siguientes:  
  
1.  Cree una clase de validador y colóquelo en una biblioteca dentro de la carpeta binaria donde la **Microsoft.Practices.Modeling.Validation.dll** biblioteca se encuentra.  
  
2.  Agregar entradas en el archivo Rules.config para definir qué propiedad de qué clase de elemento de modelo se debe aplicar el validador.