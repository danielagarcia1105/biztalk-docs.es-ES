---
title: Crear una resolución personalizada con un contenedor de Unity | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4a96542bcf2a7deae4911c6ee81fa846d0766f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975618"
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a>Crear a una resolución personalizada con un contenedor de Unity
Puede crear una resolución personalizada mediante la [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) para la inyección de dependencia de tiempo de ejecución de los orígenes de lógica y los metadatos de resolución.
  
 **Proveedores de hechos**  
  
 Proveedores de hechos son instancias de clases que implementan la **IFactProvider** interfaz. Esta interfaz expone tres diferentes sobrecargas de un método denominado **RegisterFact**. Este método toma el mensaje, la configuración de la resolución y, en algunos casos, el contexto de canalización y devuelve un objeto. Este objeto puede ser información extraída de las entradas de alguna manera, puede ser un cálculo de algún tipo o se puede buscar desde algún origen externo. Cada objeto devuelto por un proveedor de datos puede hacer referencia como un hecho y normalmente se agrega a una lista por el contenedor de resolución para su uso posterior por un traductor de hechos.  
  
 Una resolución de Unity puede tener cero o más proveedores de hechos que pueden agregarse ni quitarse en cualquier momento con un cambio de configuración único.  
  
 El código siguiente es un ejemplo de la lógica de contenidos en un proveedor de hechos. Este código también puede encontrarse en el archivo ItineraryStaticFactProvider.cs de ESB. Proyecto de Resolver.Itinerary.Facts. Es un componente en la resolución de itinerario ESTÁTICOS que recopila el nombre y la versión de un itinerario de la cadena de conexión de resolución.  
  
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
  
 **Traductores de hechos**  
  
 Traductores de hechos son instancias de clases que implementan la **IFactTranslator** interfaz. Esta interfaz expone un método único denominado **TranslateFact**. Este método se realiza en una matriz de objetos que contiene una lista de hechos y el diccionario de resolución que se devolverá más adelante mediante el solucionador mediante el traductor de hechos. Un traductor de hechos es responsable de procesar los datos proporcionados por los proveedores de datos de forma significativa y, a continuación, rellenar el diccionario de resolución.  
  
 Una resolución de Unity puede tener cero o más traductores de hechos que pueden agregarse ni quitarse en cualquier momento con un cambio de configuración único.  
  
 El código siguiente es un ejemplo de la lógica de un traductor de hechos. Este código también puede encontrarse en el archivo ItineraryStaticFactTranslator.cs de ESB. Proyecto de Resolver.Itinerary.Facts. Es un componente en la resolución de itinerario estático que se realiza una consulta de base de datos para recopilar el itinerario XML para un itinerario por nombre y, opcionalmente, por versión.  
  
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
  
 **Resolver contenedores**  
  
 Un contenedor de resolución es una clase que implementa el **IResolveContainer** interfaz. Normalmente, también implementa el **IResolveProvider** interfaz. El **IResolveContainer** interfaz expone un método único denominado **inicializar** que toma un **IUnityContainer**. El contenedor que se pasa a este método contendrá todas las dependencias (es decir, instancias de las clases **IFactProvider** y **IFactTranslator**y cualquier otro tipo necesaria) necesarios para el resolución para completar su procesamiento.  
  
 El código siguiente es un ejemplo de una implementación de la **IResolveContainer** interfaz. Este código también puede encontrarse en el archivo StaticItineraryResolveContainer.cs de ESB. Proyecto de Resolver.Itinerary.  
  
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
  
 En un contenedor de resolución, en las implementaciones de la **resolver** métodos desde el **IResolveProvider** interfaz, es necesario recorrer en iteración todos los proveedores de hechos y traductores de hechos en la unidad contenedor para permitir que cada uno de ellos para realizar su procesamiento.  
  
 El código siguiente es un ejemplo de la lógica de incluidos en un contenedor de resolución. Este código también puede encontrarse en el archivo StaticItineraryResolveContainer.cs de ESB. Proyecto de Resolver.Itinerary.  
  
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
  
 **Configurar a una resolución de Unity personalizado**  
  
 Para configurar a una resolución personalizada de Unity, los mismos pasos de configuración se aplican al crear a una resolución personalizada; Sin embargo, hay alguna configuración adicional que se debe incluir para registrar correctamente los componentes que constituyen la resolución.  
  
 Primero, en el archivo Esb.config, en la declaración de resolución, un **resolverConfig** nodo debe agregarse con las dos propiedades siguientes:  
  
-   **unitySectionName**. Esta propiedad contiene el nombre de la sección de configuración en el archivo de configuración que contiene la configuración para el bloque de aplicación de Unity; de forma predeterminada, el valor de esta propiedad es **esb.resolver**.  
  
-   **unityContainerName**. Esta propiedad contiene el nombre del contenedor Unity definido en la configuración de Unity correspondiente a la resolución personalizada.  
  
 El siguiente código XML es un ejemplo de la configuración necesaria en el **resoluciones** nodo.  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 El siguiente código XML es un ejemplo de la configuración necesaria en el **esb.resolver** nodo.  
  
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
  
 Para obtener información detallada sobre la configuración necesaria en el **esb.resolvers** nodo, consulte [esquema de origen para el bloque de aplicaciones de Unity](http://go.microsoft.com/fwlink/?LinkId=188288) ([http://go.microsoft.com/fwlink/ ? LinkId = 188288](http://go.microsoft.com/fwlink/?LinkId=188288)) en MSDN.  
  
 **Crear a una resolución personalizada de Unity**  
  
 **Para crear a una resolución personalizada de Unity**  
  
1.  (Opcional) Crear un ensamblado o ensamblados con una clase que implementa el **IFactProvider** de interfaz y contiene un **RegisterFact** método que proporciona la información necesaria para la resolución que se produzca.  
  
2.  (Opcional) Crear un ensamblado o ensamblados con una clase que implementa el **IFactTranslator** de interfaz y contiene un **TranslateFact** método que traduce los hechos proporcionados para pares de clave/valor el diccionario de resolución.  
  
3.  Crear un ensamblado con una clase que implementa el **IResolveContainer** y **IResolveProvider** interfaz y que contiene un **resolver** método que valida el configuración de la resolución, recopila todos los hechos de los proveedores de hechos, realiza cualquier procesamiento especializados, traduce mediante los traductores de hechos y devuelve los hechos traducidos como una instancia de la **diccionario** clase.  
  
4.  Registre el solucionador, éste se agrega al archivo de configuración Esb.config utilizando un  **\<resolución\>**  elemento que contiene el moniker raíz como la **nombre** atributo y totalmente nombre del ensamblado completo como el **tipo** atributo.  
  
5.  Agregue la configuración específica de Unity para el archivo Esb.config para esta resolución.  
  
6.  (Opcional) Crear un esquema que define el moniker raíz y los parámetros de consulta y, a continuación, guárdelo en ESB. Carpeta Schemas.Resolvers. El nombre debe seguir convenciones de nomenclatura de ESB existentes; Esto significa que debe usar el nombre del moniker raíz anexado "_Resolution.xsd".  
  
7.  (Opcional) Generar una clase desde el nuevo esquema y lo guarda en el ensamblado de la resolución personalizada. Esto expondrá los parámetros de tipo en la resolución personalizada.  
  
8.  Registrar todos los ensamblados en la caché global de ensamblados.