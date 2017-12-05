---
title: "Crear una resolución personalizada con un contenedor de Unity | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4a96542bcf2a7deae4911c6ee81fa846d0766f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a><span data-ttu-id="e389e-102">Crear a una resolución personalizada con un contenedor de Unity</span><span class="sxs-lookup"><span data-stu-id="e389e-102">Creating a Custom Resolver with a Unity Container</span></span>
<span data-ttu-id="e389e-103">Puede crear una resolución personalizada mediante la [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) para la inyección de dependencia de tiempo de ejecución de los orígenes de lógica y los metadatos de resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-103">You can create a custom resolver using the [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) for run-time dependency injection of resolution logic and metadata sources.</span></span>
  
 <span data-ttu-id="e389e-104">**Proveedores de hechos**</span><span class="sxs-lookup"><span data-stu-id="e389e-104">**Fact Providers**</span></span>  
  
 <span data-ttu-id="e389e-105">Proveedores de hechos son instancias de clases que implementan la **IFactProvider** interfaz.</span><span class="sxs-lookup"><span data-stu-id="e389e-105">Fact providers are instances of classes that implement the **IFactProvider** interface.</span></span> <span data-ttu-id="e389e-106">Esta interfaz expone tres diferentes sobrecargas de un método denominado **RegisterFact**.</span><span class="sxs-lookup"><span data-stu-id="e389e-106">This interface exposes three different overloads of a method named **RegisterFact**.</span></span> <span data-ttu-id="e389e-107">Este método toma el mensaje, la configuración de la resolución y, en algunos casos, el contexto de canalización y devuelve un objeto.</span><span class="sxs-lookup"><span data-stu-id="e389e-107">This method takes in the message, the resolver configuration, and, in some cases, the pipeline context, and returns an object.</span></span> <span data-ttu-id="e389e-108">Este objeto puede ser información extraída de las entradas de alguna manera, puede ser un cálculo de algún tipo o se puede buscar desde algún origen externo.</span><span class="sxs-lookup"><span data-stu-id="e389e-108">This object may be information extracted from the inputs in some way, it may be a calculation of some form, or it may be looked up from some external source.</span></span> <span data-ttu-id="e389e-109">Cada objeto devuelto por un proveedor de datos puede hacer referencia como un hecho y normalmente se agrega a una lista por el contenedor de resolución para su uso posterior por un traductor de hechos.</span><span class="sxs-lookup"><span data-stu-id="e389e-109">Each object returned by a fact provider can be referred to as a fact and is typically added to a list by the resolve container for later use by a fact translator.</span></span>  
  
 <span data-ttu-id="e389e-110">Una resolución de Unity puede tener cero o más proveedores de hechos que pueden agregarse ni quitarse en cualquier momento con un cambio de configuración único.</span><span class="sxs-lookup"><span data-stu-id="e389e-110">A Unity resolver may have zero or more fact providers that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="e389e-111">El código siguiente es un ejemplo de la lógica de contenidos en un proveedor de hechos.</span><span class="sxs-lookup"><span data-stu-id="e389e-111">The following code is an example of the logic contained in a fact provider.</span></span> <span data-ttu-id="e389e-112">Este código también puede encontrarse en el archivo ItineraryStaticFactProvider.cs de ESB. Proyecto de Resolver.Itinerary.Facts.</span><span class="sxs-lookup"><span data-stu-id="e389e-112">This code can also be found in the ItineraryStaticFactProvider.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="e389e-113">Es un componente en la resolución de itinerario ESTÁTICOS que recopila el nombre y la versión de un itinerario de la cadena de conexión de resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-113">It is a component in the ITINERARY-STATIC resolver that gathers the name and version of an itinerary from the resolver connection string.</span></span>  
  
```csharp  
public object RegisterFact(IBaseMessage message, IPipelineContext pipelineContext, Dictionary\<string, string\> resolverContents)  
{  
    return GetItineraryFactFromResolver(resolverContents);  
}  
  
private static object GetItineraryFactFromResolver(Dictionary\<string, string\> resolverContents)  
{              
    if (resolverContents == null)  
        throw new ArgumentNullException("resolverContents");  
  
    ItineraryFact itineraryFact = new ItineraryFact();  
    itineraryFact.Name = ResolverMgr.GetConfigValue(resolverContents, true, "name");  
    string version = ResolverMgr.GetConfigValue(resolverContents, false, "version");  
    if (!string.IsNullOrEmpty(version))  
    {  
        EventLogger.Write(string.Format("Version set with value {0}.", version));  
        itineraryFact.SetVersion(version);  
    }  
    return itineraryFact;  
}  
```  
  
 <span data-ttu-id="e389e-114">**Traductores de hechos**</span><span class="sxs-lookup"><span data-stu-id="e389e-114">**Fact Translators**</span></span>  
  
 <span data-ttu-id="e389e-115">Traductores de hechos son instancias de clases que implementan la **IFactTranslator** interfaz.</span><span class="sxs-lookup"><span data-stu-id="e389e-115">Fact translators are instances of classes that implement the **IFactTranslator** interface.</span></span> <span data-ttu-id="e389e-116">Esta interfaz expone un método único denominado **TranslateFact**.</span><span class="sxs-lookup"><span data-stu-id="e389e-116">This interface exposes a single method named **TranslateFact**.</span></span> <span data-ttu-id="e389e-117">Este método se realiza en una matriz de objetos que contiene una lista de hechos y el diccionario de resolución que se devolverá más adelante mediante el solucionador mediante el traductor de hechos.</span><span class="sxs-lookup"><span data-stu-id="e389e-117">This method takes in an object array that contains a list of facts and the resolver dictionary that will later be returned by the resolver using the fact translator.</span></span> <span data-ttu-id="e389e-118">Un traductor de hechos es responsable de procesar los datos proporcionados por los proveedores de datos de forma significativa y, a continuación, rellenar el diccionario de resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-118">A fact translator is responsible for processing the facts provided by the fact providers in a meaningful way and then populating the resolver dictionary.</span></span>  
  
 <span data-ttu-id="e389e-119">Una resolución de Unity puede tener cero o más traductores de hechos que pueden agregarse ni quitarse en cualquier momento con un cambio de configuración único.</span><span class="sxs-lookup"><span data-stu-id="e389e-119">A Unity resolver may have zero or more fact translators that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="e389e-120">El código siguiente es un ejemplo de la lógica de un traductor de hechos.</span><span class="sxs-lookup"><span data-stu-id="e389e-120">The following code is an example of the logic contained in a fact translator.</span></span> <span data-ttu-id="e389e-121">Este código también puede encontrarse en el archivo ItineraryStaticFactTranslator.cs de ESB. Proyecto de Resolver.Itinerary.Facts.</span><span class="sxs-lookup"><span data-stu-id="e389e-121">This code can also be found in the ItineraryStaticFactTranslator.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="e389e-122">Es un componente en la resolución de itinerario estático que se realiza una consulta de base de datos para recopilar el itinerario XML para un itinerario por nombre y, opcionalmente, por versión.</span><span class="sxs-lookup"><span data-stu-id="e389e-122">It is a component in the ITINERARY-STATIC resolver that performs a database query to gather the itinerary XML for an itinerary by name and, optionally, by version.</span></span>  
  
```csharp  
public void TranslateFact(object[] facts, Dictionary\<string, string\> factDictionary)  
{  
    #region Argument Check  
    if (null == facts) throw new ArgumentNullException("fact");  
    if (null == factDictionary) throw new ArgumentNullException("factDictionary");  
    #endregion  
  
    #region Local Variables  
    Version version = new Version(1, 0);                         
    #endregion  
    try  
    {  
        foreach (object fact in facts)  
        {  
            if (fact is ItineraryFact)  
            {  
                ItineraryFact targetFact = (ItineraryFact)fact;  
                factDictionary.Add(_FactKeyItineraryName, targetFact.Name ?? string.Empty);  
                if (null != targetFact.Version)  
                {  
                    factDictionary.Add(_FactKeyItineraryVersion, targetFact.Version.ToString(2) ?? string.Empty);  
                    version = targetFact.Version;  
                }  
  
                string xml = null;  
  
                if (targetFact.Version != null)  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name, version.Major, version.Minor);  
                }  
                else  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name);  
                }  
                if (!string.IsNullOrEmpty(xml))  
                {  
                    factDictionary.Add(_FactKeyItinerary, xml);  
                }  
  
                break;  
            }  
        }  
    }  
    #region Exception Handling  
    catch (System.Exception)  
    {  
        throw;  
    }              
    #endregion  
}  
#endregion  
```  
  
 <span data-ttu-id="e389e-123">**Resolver contenedores**</span><span class="sxs-lookup"><span data-stu-id="e389e-123">**Resolve Containers**</span></span>  
  
 <span data-ttu-id="e389e-124">Un contenedor de resolución es una clase que implementa el **IResolveContainer** interfaz.</span><span class="sxs-lookup"><span data-stu-id="e389e-124">A resolve container is a class that implements the **IResolveContainer** interface.</span></span> <span data-ttu-id="e389e-125">Normalmente, también implementa el **IResolveProvider** interfaz.</span><span class="sxs-lookup"><span data-stu-id="e389e-125">Typically, it also implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="e389e-126">El **IResolveContainer** interfaz expone un método único denominado **inicializar** que toma un **IUnityContainer**.</span><span class="sxs-lookup"><span data-stu-id="e389e-126">The **IResolveContainer** interface exposes a single method named **Initialize** that takes in an **IUnityContainer**.</span></span> <span data-ttu-id="e389e-127">El contenedor que se pasa a este método contendrá todas las dependencias (es decir, instancias de las clases **IFactProvider** y **IFactTranslator**y cualquier otro tipo necesaria) necesarios para el resolución para completar su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e389e-127">The container passed to this method will contain all of the dependencies (that is, instances of the classes **IFactProvider** and **IFactTranslator**, and any other types required) necessary for the resolver to complete its processing.</span></span>  
  
 <span data-ttu-id="e389e-128">El código siguiente es un ejemplo de una implementación de la **IResolveContainer** interfaz.</span><span class="sxs-lookup"><span data-stu-id="e389e-128">The following code is an example of an implementation of the **IResolveContainer** interface.</span></span> <span data-ttu-id="e389e-129">Este código también puede encontrarse en el archivo StaticItineraryResolveContainer.cs de ESB. Proyecto de Resolver.Itinerary.</span><span class="sxs-lookup"><span data-stu-id="e389e-129">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
```csharp  
#region IResolveContainer Members  
  
private static IUnityContainer Container;  
  
// <summary>  
// This is used by the Unity resolver to initialize the current   
// object with the Unity container.  
// </summary>  
// <param name="container">Unity container used for dependency   
// injection.</param>  
// <remarks>  
// The container used is the ITINERARY container, although this is   
// configurable in Esb.config.  
// </remarks>  
  
public void Initialize(IUnityContainer container)  
{  
  if (container == null)  
    throw new ArgumentNullException("container");  
  
  Container = container;  
}  
#endregion  
```  
  
 <span data-ttu-id="e389e-130">En un contenedor de resolución, en las implementaciones de la **resolver** métodos desde el **IResolveProvider** interfaz, es necesario recorrer en iteración todos los proveedores de hechos y traductores de hechos en la unidad contenedor para permitir que cada uno de ellos para realizar su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e389e-130">In a resolve container, in the implementations of the **Resolve** methods from the **IResolveProvider** interface, it is necessary to iterate through all the fact providers and fact translators in the Unity container to allow each of them to perform their processing.</span></span>  
  
 <span data-ttu-id="e389e-131">El código siguiente es un ejemplo de la lógica de incluidos en un contenedor de resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-131">The following code is an example of the logic contained in a Resolve container.</span></span> <span data-ttu-id="e389e-132">Este código también puede encontrarse en el archivo StaticItineraryResolveContainer.cs de ESB. Proyecto de Resolver.Itinerary.</span><span class="sxs-lookup"><span data-stu-id="e389e-132">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
```csharp  
public Dictionary\<string, string\> Resolve(ResolverInfo resolverInfo,  
    XLANGMessage message)  
{  
    #region Argument Check  
    if (String.IsNullOrEmpty(resolverInfo.Config))  
        throw new ArgumentNullException("resolverInfo.Config");  
    if (String.IsNullOrEmpty(resolverInfo.Resolver))  
        throw new ArgumentNullException("resolverInfo.Resolver");  
    if (null == message)  
        throw new ArgumentNullException("message");  
    #endregion Argument Check  
  
    return ResolveStatic(resolverInfo.Config, resolverInfo.Resolver,  
        (factProvider, resolverContent) =>   
            factProvider.RegisterFact(message, resolverContent)  
     );  
}          
  
private Dictionary\<string, string\> ResolveStatic(string config, string resolver,   
    Func<IFactProvider, Dictionary\<string, string\>, object> RegisterFact)  
{  
    try  
    {  
        EventLogger.Write(string.Format("Received {0} value in ITINERARY STATIC resolver.", config));  
  
        Dictionary\<string, string\> queryParams =  
                ResolverMgr.GetFacts(config, resolver);  
  
        List<object> facts = new List<object>();  
  
        foreach (IFactProvider factProvider in Container.ResolveAll<IFactProvider>())  
        {  
            facts.Add(RegisterFact(factProvider, queryParams));  
        }  
  
        Dictionary\<string, string\> resolverDictionary = new Dictionary\<string, string\>();  
  
        object[] convertedFacts = facts.ToArray();  
  
        foreach (IFactTranslator translator in Container.ResolveAll<IFactTranslator>())  
        {  
            translator.TranslateFact(convertedFacts, resolverDictionary);  
        }  
  
        return resolverDictionary;  
    }  
    catch (System.Exception ex)  
    {  
        EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="e389e-133">**Configurar a una resolución de Unity personalizado**</span><span class="sxs-lookup"><span data-stu-id="e389e-133">**Configuring a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="e389e-134">Para configurar a una resolución personalizada de Unity, los mismos pasos de configuración se aplican al crear a una resolución personalizada; Sin embargo, hay alguna configuración adicional que se debe incluir para registrar correctamente los componentes que constituyen la resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-134">To configure a custom Unity resolver, the same configuration steps apply as when creating a custom resolver; however, there is some additional configuration that must be included to properly register the components that make up the resolver.</span></span>  
  
 <span data-ttu-id="e389e-135">Primero, en el archivo Esb.config, en la declaración de resolución, un **resolverConfig** nodo debe agregarse con las dos propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e389e-135">First, in the Esb.config file, under the resolver declaration, a **resolverConfig** node must be added with the following two properties:</span></span>  
  
-   <span data-ttu-id="e389e-136">**unitySectionName**.</span><span class="sxs-lookup"><span data-stu-id="e389e-136">**unitySectionName**.</span></span> <span data-ttu-id="e389e-137">Esta propiedad contiene el nombre de la sección de configuración en el archivo de configuración que contiene la configuración para el bloque de aplicación de Unity; de forma predeterminada, el valor de esta propiedad es **esb.resolver**.</span><span class="sxs-lookup"><span data-stu-id="e389e-137">This property contains the name of the configuration section in the configuration file that contains the configuration for the Unity Application Block; by default, the value for this property is **esb.resolver**.</span></span>  
  
-   <span data-ttu-id="e389e-138">**unityContainerName**.</span><span class="sxs-lookup"><span data-stu-id="e389e-138">**unityContainerName**.</span></span> <span data-ttu-id="e389e-139">Esta propiedad contiene el nombre del contenedor Unity definido en la configuración de Unity correspondiente a la resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="e389e-139">This property contains the name of the Unity container defined in the Unity configuration specific to your custom resolver.</span></span>  
  
 <span data-ttu-id="e389e-140">El siguiente código XML es un ejemplo de la configuración necesaria en el **resoluciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="e389e-140">The following XML is an example of the configuration necessary in the **resolvers** node.</span></span>  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 <span data-ttu-id="e389e-141">El siguiente código XML es un ejemplo de la configuración necesaria en el **esb.resolver** nodo.</span><span class="sxs-lookup"><span data-stu-id="e389e-141">The following XML is an example of the configuration necessary under the **esb.resolver** node.</span></span>  
  
```xml  
<typeAliases>  
     <!-- Lifetime manager types -->  
     <typeAlias alias="singleton" type="Microsoft.Practices.Unity.ContainerControlledLifetimeManager, Microsoft.Practices.Unity, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <!-- std type providers -->  
     <typeAlias alias="string" type="System.String, mscorlib"/>  
     <typeAlias alias="int" type="System.Int32, mscorlib"/>  
     <!-- repository providers -->  
     <typeAlias alias="IRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.Repository.IRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="SqlRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess.SqlRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- fact providers -->  
     <typeAlias alias="IFactProvider" type="Microsoft.Practices.ESB.Resolver.Facts.IFactProvider, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="IFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.IFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryStaticFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryStaticFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryHeaderFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryHeaderFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ResolutionFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ResolutionFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="DefaultFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.DefaultFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactTranslator" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactTranslator, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- resolve providers -->  
     <typeAlias alias="IResolveProvider" type="Microsoft.Practices.ESB.Resolver.IResolveProvider, Microsoft.Practices.ESB.Resolver, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.BREItineraryResolverContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
     <typeAlias alias="StaticItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.StaticItineraryResolveContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
</typeAliases>  
<containers>  
     <container name="ITINERARY">  
          <types>  
               <type type="IResolveProvider" mapTo="StaticItineraryResolveProvider" />  
               <type type="IRepositoryProvider" mapTo="SqlRepositoryProvider" name="CurrentRepositoryProvider">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="connectionStringName" parameterType="string">  
                                   <value value="ItineraryDb"/>  
                              </param>  
                              <param name="cacheManagerName" parameterType="string">  
                                   <value value="Itinerary Cache Manager"/>  
                              </param>  
                              <param name="cacheTimeout" parameterType="string">  
                                   <value value="120" />  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
               <type type="IFactProvider" mapTo="ResolutionFactProvider" name="ResolutionFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryHeaderFactProvider" name="HeaderFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryStaticFactProvider" name="StaticFactProvider"  />  
               <type type="IFactTranslator" mapTo="DefaultFactTranslator" name="DefaultFactTranslator">  
                    <lifetime type="singleton" />  
               </type>  
               <type type="IFactTranslator" mapTo="ItineraryFactTranslator" name="ItineraryFactTranslator">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="repositoryProvider" parameterType="IRepositoryProvider">  
                                   <dependency name="CurrentRepositoryProvider"/>  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
          </types>  
     </container>  
</containers>  
```  
  
 <span data-ttu-id="e389e-142">Para obtener información detallada sobre la configuración necesaria en el **esb.resolvers** nodo, consulte [esquema de origen para el bloque de aplicaciones de Unity](http://go.microsoft.com/fwlink/?LinkId=188288) ([http://go.microsoft.com/fwlink/ ? LinkId = 188288](http://go.microsoft.com/fwlink/?LinkId=188288)) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="e389e-142">For detailed information about the configuration that is necessary in the **esb.resolvers** node, see [Source Schema for the Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188288) ([http://go.microsoft.com/fwlink/?LinkId=188288](http://go.microsoft.com/fwlink/?LinkId=188288)) on MSDN.</span></span>  
  
 <span data-ttu-id="e389e-143">**Crear a una resolución personalizada de Unity**</span><span class="sxs-lookup"><span data-stu-id="e389e-143">**Creating a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="e389e-144">**Para crear a una resolución personalizada de Unity**</span><span class="sxs-lookup"><span data-stu-id="e389e-144">**To create a custom Unity resolver**</span></span>  
  
1.  <span data-ttu-id="e389e-145">(Opcional) Crear un ensamblado o ensamblados con una clase que implementa el **IFactProvider** de interfaz y contiene un **RegisterFact** método que proporciona la información necesaria para la resolución que se produzca.</span><span class="sxs-lookup"><span data-stu-id="e389e-145">(Optional) Create an assembly or assemblies with a class that implements the **IFactProvider** interface and contains a **RegisterFact** method that provides information necessary for resolution to occur.</span></span>  
  
2.  <span data-ttu-id="e389e-146">(Opcional) Crear un ensamblado o ensamblados con una clase que implementa el **IFactTranslator** de interfaz y contiene un **TranslateFact** método que traduce los hechos proporcionados para pares de clave/valor el diccionario de resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-146">(Optional) Create an assembly or assemblies with a class that implements the **IFactTranslator** interface and contains a **TranslateFact** method that translates the provided facts to key/value pairs within the resolver dictionary.</span></span>  
  
3.  <span data-ttu-id="e389e-147">Crear un ensamblado con una clase que implementa el **IResolveContainer** y **IResolveProvider** interfaz y que contiene un **resolver** método que valida el configuración de la resolución, recopila todos los hechos de los proveedores de hechos, realiza cualquier procesamiento especializados, traduce mediante los traductores de hechos y devuelve los hechos traducidos como una instancia de la **diccionario** clase.</span><span class="sxs-lookup"><span data-stu-id="e389e-147">Create an assembly with a class that implements the **IResolveContainer** and **IResolveProvider** interface and that contains a **Resolve** method that validates the resolver configuration, gathers all the facts from the fact providers, performs any specialized processing, translates them using the fact translators, and returns the translated facts as an instance of the **Dictionary** class.</span></span>  
  
4.  <span data-ttu-id="e389e-148">Registre el solucionador, éste se agrega al archivo de configuración Esb.config utilizando un  **\<resolución\>**  elemento que contiene el moniker raíz como la **nombre** atributo y totalmente nombre del ensamblado completo como el **tipo** atributo.</span><span class="sxs-lookup"><span data-stu-id="e389e-148">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver\>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
5.  <span data-ttu-id="e389e-149">Agregue la configuración específica de Unity para el archivo Esb.config para esta resolución.</span><span class="sxs-lookup"><span data-stu-id="e389e-149">Add the Unity-specific configuration to the Esb.config file for this resolver.</span></span>  
  
6.  <span data-ttu-id="e389e-150">(Opcional) Crear un esquema que define el moniker raíz y los parámetros de consulta y, a continuación, guárdelo en ESB. Carpeta Schemas.Resolvers.</span><span class="sxs-lookup"><span data-stu-id="e389e-150">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="e389e-151">El nombre debe seguir convenciones de nomenclatura de ESB existentes; Esto significa que debe usar el nombre del moniker raíz anexado "_Resolution.xsd".</span><span class="sxs-lookup"><span data-stu-id="e389e-151">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
7.  <span data-ttu-id="e389e-152">(Opcional) Generar una clase desde el nuevo esquema y lo guarda en el ensamblado de la resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="e389e-152">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="e389e-153">Esto expondrá los parámetros de tipo en la resolución personalizada.</span><span class="sxs-lookup"><span data-stu-id="e389e-153">This will expose typed parameters in the custom resolver.</span></span>  
  
8.  <span data-ttu-id="e389e-154">Registrar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e389e-154">Register all the assemblies in the global assembly cache.</span></span>