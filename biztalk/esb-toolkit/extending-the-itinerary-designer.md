---
title: "Extender el Diseñador de itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f26b825b-ebab-4dac-b7ed-0608c79e146a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78490c7b6447ddb097c0ca61154aab20c44086c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="extending-the-itinerary-designer"></a><span data-ttu-id="96e43-102">Extender el Diseñador de itinerarios</span><span class="sxs-lookup"><span data-stu-id="96e43-102">Extending the Itinerary Designer</span></span>
<span data-ttu-id="96e43-103">El Diseñador de itinerario es un lenguaje específico de dominio visual (DSL) para Microsoft Visual Studio que permite el modelado del gráfico de itinerarios para su uso con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96e43-103">The Itinerary Designer is a visual domain-specific language (DSL) for Microsoft Visual Studio that enables the graphical modeling of itineraries for use with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="96e43-104">El diseñador expone varios puntos de extensión para que los programadores pueden escribir extensiones personalizadas para habilitar la funcionalidad nueva o nuevas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="96e43-104">The designer exposes various extension points for which developers can write custom extensions to enable new functionality and/or new configuration options.</span></span>  
  

  
 <span data-ttu-id="96e43-105">**Crear un exportador itinerario personalizado**</span><span class="sxs-lookup"><span data-stu-id="96e43-105">**Creating a Custom Itinerary Exporter**</span></span>  
  
 <span data-ttu-id="96e43-106">La arquitectura del Diseñador de itinerario permite la creación de exportadores de modelos personalizados que serializar y conservar los datos en un modelo de itinerario.</span><span class="sxs-lookup"><span data-stu-id="96e43-106">The architecture of the Itinerary Designer allows for the creation of custom model exporters that serialize and persist the data in an Itinerary model.</span></span>  
  
 <span data-ttu-id="96e43-107">**Creación de un extensor personalizado para un servicio de mensajería**</span><span class="sxs-lookup"><span data-stu-id="96e43-107">**Creating a Custom Extender for a Messaging Service**</span></span>  
  
 <span data-ttu-id="96e43-108">La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerario que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por los servicios de mensajería.</span><span class="sxs-lookup"><span data-stu-id="96e43-108">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by Messaging Services.</span></span>  
  
 <span data-ttu-id="96e43-109">Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span><span class="sxs-lookup"><span data-stu-id="96e43-109">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="96e43-110">**Creación de un extensor personalizado para un servicio de itinerarios basado en la orquestación**</span><span class="sxs-lookup"><span data-stu-id="96e43-110">**Creating a Custom Extender for an Orchestration-Based Itinerary Service**</span></span>  
  
 <span data-ttu-id="96e43-111">La arquitectura del Diseñador de itinerario permite crear extensores personalizados para los elementos del modelo de servicio de itinerario que pueden usarse para agregar propiedades a la bolsa de propiedades para su uso por servicios de itinerario en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="96e43-111">The architecture of the Itinerary Designer allows you to create custom extenders for Itinerary Service model elements that can be used to add properties to the property bag for use by orchestration-based itinerary services.</span></span>  
  
 <span data-ttu-id="96e43-112">Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span><span class="sxs-lookup"><span data-stu-id="96e43-112">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="96e43-113">**Creación de un extensor de resolución personalizada**</span><span class="sxs-lookup"><span data-stu-id="96e43-113">**Creating a Custom Resolver Extender**</span></span>  
  
 <span data-ttu-id="96e43-114">La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de los solucionadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="96e43-114">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom resolvers.</span></span> <span data-ttu-id="96e43-115">Estos extensores ofrecen una interfaz gráfica para configurar los pares de nombre y valor en la cadena de conexión de la resolución, que se asignan a las propiedades de la clase de dispositivo extender de resolución específico.</span><span class="sxs-lookup"><span data-stu-id="96e43-115">These extenders provide a graphical interface for configuring the name-value pairs in the resolver connection string, which map to properties in the specific resolver extender class.</span></span>  
  
 <span data-ttu-id="96e43-116">Para obtener un ejemplo de cómo crear un extensor de este tipo, consulte [instalar y ejecutar el ejemplo de extensibilidad del diseñador](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span><span class="sxs-lookup"><span data-stu-id="96e43-116">For a sample of how to create such an extender, see [Installing and Running the Designer Extensibility Sample](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md).</span></span>  
  
 <span data-ttu-id="96e43-117">**Crear un archivo de manifiesto para las propiedades de adaptador personalizado**</span><span class="sxs-lookup"><span data-stu-id="96e43-117">**Creating a Manifest File for Custom Adapter Properties**</span></span>  
  
 <span data-ttu-id="96e43-118">Al crear un proveedor de adaptador personalizado, también debe proporcionar compatibilidad con el diseñador para el proveedor del adaptador a los extensores de resolución que mostrar una propiedad de configuración de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="96e43-118">When creating a custom adapter provider, you must also provide designer support for the adapter provider to those resolver extenders that display an endpoint configuration property.</span></span> <span data-ttu-id="96e43-119">Para habilitar la compatibilidad con el diseñador, es necesario crear un archivo de manifiesto del proveedor de adaptador.</span><span class="sxs-lookup"><span data-stu-id="96e43-119">To enable designer support, it is necessary to create an adapter provider manifest file.</span></span>  
  
 <span data-ttu-id="96e43-120">El archivo de manifiesto del proveedor de adaptador define las propiedades asociadas a un proveedor de adaptador específico, sus tipos, descripciones y el ensamblado en el que se pueden encontrar.</span><span class="sxs-lookup"><span data-stu-id="96e43-120">The adapter provider manifest file defines the properties associated with a specific adapter provider, their types, descriptions, and the assembly in which they can be found.</span></span> <span data-ttu-id="96e43-121">Estos archivos de manifiesto deben colocarse en la misma carpeta que los archivos binarios del Diseñador de itinerario (por ejemplo, Microsoft.Practices.Itineary.DslPackage.dll) con un nombre único (por ejemplo, FTPPropertyManifest.xml).</span><span class="sxs-lookup"><span data-stu-id="96e43-121">These manifest files should be placed in the same folder as the Itinerary Designer binaries (for example, Microsoft.Practices.Itineary.DslPackage.dll) with a unique name (for example, FTPPropertyManifest.xml).</span></span>  
  
 <span data-ttu-id="96e43-122">La siguiente es una instancia de la referencia de un archivo de manifiesto del proveedor de adaptador; archivos de manifiesto personalizados deben estructurarse del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="96e43-122">The following is a reference instance of an adapter provider manifest file; custom manifest files should be structured likewise.</span></span>  
  
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
  
 <span data-ttu-id="96e43-123">**Creación de un extensor de filtro personalizado**</span><span class="sxs-lookup"><span data-stu-id="96e43-123">**Creating a Custom Filter Extender**</span></span>  
  
 <span data-ttu-id="96e43-124">La arquitectura del Diseñador de itinerario permite crear extensores personalizados para la configuración de filtros personalizados.</span><span class="sxs-lookup"><span data-stu-id="96e43-124">The architecture of the Itinerary Designer allows you to create custom extenders for the configuration of custom filters.</span></span> <span data-ttu-id="96e43-125">Estos extensores ofrecen una interfaz gráfica para configurar los pares de nombre y valor en la cadena de conexión de filtro, que se asignan a las propiedades de la clase de extender filtros específicos.</span><span class="sxs-lookup"><span data-stu-id="96e43-125">These extenders provide a graphical interface for configuring the name-value pairs in the filter connection string, which map to properties in the specific filter extender class.</span></span>  
  
-   <span data-ttu-id="96e43-126">/ Samples/diseñador extensibilidad Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span><span class="sxs-lookup"><span data-stu-id="96e43-126">/Samples/Designer Extensibility Samples/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample/Extenders.Itinerary.OrchestrationSample</span></span>  
  
-   <span data-ttu-id="96e43-127">/ Samples/diseñador extensibilidad Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span><span class="sxs-lookup"><span data-stu-id="96e43-127">/Samples/Designer Extensibility Samples/Extenders.Resolvers.ResolverSample/Extenders.Resolvers.ResolverSample</span></span>  
  
 <span data-ttu-id="96e43-128">**Crear reglas de validación personalizadas**</span><span class="sxs-lookup"><span data-stu-id="96e43-128">**Creating Custom Validation Rules**</span></span>  
  
 <span data-ttu-id="96e43-129">La última extensión importante introducida por el Diseñador de itinerario es un mecanismo de validación que le permite externamente, con respecto a un lenguaje específico de dominio (DSL), especificar e implementar las reglas de validación del modelo.</span><span class="sxs-lookup"><span data-stu-id="96e43-129">The last significant extension introduced by the Itinerary Designer is a validation mechanism that allows you to externally, with respect to a domain-specific language (DSL), specify and implement the model validation rules.</span></span> <span data-ttu-id="96e43-130">El mecanismo de "enlaza en" el marco de validación de DSL y se activa cuando el usuario hace clic en **validar** o **todas las validar** en el menú contextual de un modelo.</span><span class="sxs-lookup"><span data-stu-id="96e43-130">The mechanism "hooks into" the DSL validation framework and is activated when the user clicks **Validate** or **Validate all** on the shortcut menu of a model.</span></span> <span data-ttu-id="96e43-131">Esto invoca el marco de trabajo DSL **DslCommandSet** objeto que, a su vez, llama al motor de validación en el Diseñador de itinerario.</span><span class="sxs-lookup"><span data-stu-id="96e43-131">This invokes the DSL framework's **DslCommandSet** object that, in turn, calls the validation engine in the Itinerary Designer.</span></span>  
  
 <span data-ttu-id="96e43-132">El **ValidationEngine** clase realiza la validación de elemento de modelo mediante el bloque de aplicaciones de Enterprise Library validación y registra los errores de validación en la ventana Lista de errores de Microsoft Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="96e43-132">The **ValidationEngine** class performs the model element validation using the Enterprise Library Validation Application Block and logs the validation errors to the Error List window in Microsoft Visual Studio IDE.</span></span> <span data-ttu-id="96e43-133">La validación que se debe realizar para cada tipo de elemento de un modelo se define en el archivo de configuración de Enterprise Library.</span><span class="sxs-lookup"><span data-stu-id="96e43-133">The validation that should be performed for each type of element in a model is defined in the Enterprise Library configuration file.</span></span> <span data-ttu-id="96e43-134">El archivo se denomina Ruleset.config y se encuentra en la carpeta binaria donde se encuentran todos los binarios de diseñador de itinerario.</span><span class="sxs-lookup"><span data-stu-id="96e43-134">The file is named Ruleset.config and is located in the binary folder where all the Itinerary Designer binaries are located.</span></span> <span data-ttu-id="96e43-135">En el ejemplo siguiente se muestra un fragmento del archivo de configuración e incluye dos reglas de validación (denominadas validadores) para la **UddiResolver** dispositivo extender, uno para la **ServerUrl** propiedad y otra para el  **ServiceKey** propiedad.</span><span class="sxs-lookup"><span data-stu-id="96e43-135">The following example is a fragment of the configuration file and includes two validation rules (named validators) for the **UddiResolver** extender, one for the **ServerUrl** property and one for the **ServiceKey** property.</span></span>  
  
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
  
 <span data-ttu-id="96e43-136">Cada regla identifica el validador que implementa la regla.</span><span class="sxs-lookup"><span data-stu-id="96e43-136">Each rule identifies the validator that implements the rule.</span></span> <span data-ttu-id="96e43-137">El Diseñador de itinerario incluye un conjunto grande de las clases de validación.</span><span class="sxs-lookup"><span data-stu-id="96e43-137">The Itinerary Designer comes with a large set of validator classes.</span></span> <span data-ttu-id="96e43-138">Todos están en el proyecto Microsoft.Practices.Modeling.Validation en la carpeta binaria del diseñador.</span><span class="sxs-lookup"><span data-stu-id="96e43-138">They are all in the Microsoft.Practices.Modeling.Validation project in the Designer binary folder.</span></span>  
  
 <span data-ttu-id="96e43-139">El resultado final del uso de este mecanismo de validación es que ese diseñador de itinerario los usuarios pueden modificar cómo se validan los modelos mediante la modificación de las reglas proporcionadas y validadores o agregando sus propias reglas y validadores.</span><span class="sxs-lookup"><span data-stu-id="96e43-139">The final result of using this validation mechanism is that Itinerary Designer users can modify how the models are validated by changing the provided rules and validators or by adding their own rules and validators.</span></span> <span data-ttu-id="96e43-140">Esto puede realizarse sin abrir, modificar, volver a generar y volver a implementar la DSL mediante la realización de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="96e43-140">This can be done without opening, modifying, rebuilding, and re-deploying the DSLs by performing the following two steps:</span></span>  
  
1.  <span data-ttu-id="96e43-141">Cree una clase de validador y colóquelo en una biblioteca dentro de la carpeta binaria donde la **Microsoft.Practices.Modeling.Validation.dll** biblioteca se encuentra.</span><span class="sxs-lookup"><span data-stu-id="96e43-141">Create a validator class and put it in a library inside the binary folder where the **Microsoft.Practices.Modeling.Validation.dll** library is located.</span></span>  
  
2.  <span data-ttu-id="96e43-142">Agregar entradas en el archivo Rules.config para definir qué propiedad de qué clase de elemento de modelo se debe aplicar el validador.</span><span class="sxs-lookup"><span data-stu-id="96e43-142">Add entries to the Rules.config file to define what property of what model element class the validator should be applied.</span></span>