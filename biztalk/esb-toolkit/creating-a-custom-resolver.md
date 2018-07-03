---
title: Creación de un solucionador personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3752348a5cc9273ad203b78b77b58bde33bd141
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981717"
---
# <a name="creating-a-custom-resolver"></a>Creación de un solucionador personalizado
La implementación del marco de proveedores de adaptador y la resolución en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa un componente de canalización con nombre distribuidor y canalizaciones con nombre ItineraryReceive y ItinerarySend.  
  
 El componente de canalización de distribuidor tiene cuatro propiedades: **Validate, Enabled, punto de conexión,** y **Nombredemapa**. El **extremo** propiedad puede contener cadenas de conexión de la resolución con valores como el siguiente, donde **UDDI:\\ \\**  representa el tipo de resolución debe usar (la raíz moniker).  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 Otros monikers admitidos incluyen **XPATH:\\\\estática:\\\\,** y **BRE:\\\\**. Cada tipo de moniker utiliza una clase específica que implementa el **IResolveProvider** interfaz. Puede crear a sus propias resoluciones personalizadas para otros tipos de moniker y registrarlas para su uso por el sistema de resolución dinámica.  
  
 El moniker equivale a una cadena de conexión de la resolución. Esquemas individuales definen los parámetros y su moniker raíz. Una resolución toma la resolución de cadena de conexión, lo valida y usa el resultado para consultar y rellenar un **diccionario** objeto que se puede usar para enrutamiento, transformación, selección de itinerarios o cualquier otro propósito específico para su servicio.  
  
## <a name="resolver-configuration"></a>Configuración de la resolución  
 Debe registrar a todos los solucionadores en el archivo de configuración Esb.config. El siguiente XML muestra un ejemplo del contenido del archivo de configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
     <configSections>  
          <section name="esb" type="Microsoft.Practices.ESB.Configuration.ESBConfigurationSection, Microsoft.Practices.ESB.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
          <!-- Other Section Definitions Here -->  
     </configSections>  
  
     <esb>  
          <resolvers cacheManager= "Resolver Providers Cache Manager"  absoluteExpiration="3600">  
               <resolver name="UDDI" type="Microsoft.Practices.ESB.Resolver.UDDI.ResolveProvider, Microsoft.Practices.ESB.Resolver.UDDI, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
                    <resolverConfig>  
                         <add name="cacheTimeoutValue" value="120" />  
                         <add name="cacheName" value="UDDI Cache Manager" />  
                    </resolverConfig>  
               </resolver>  
               <resolver name="XPATH" type="Microsoft.Practices.ESB.Resolver.XPATH.ResolveProvider, Microsoft.Practices.ESB.Resolver.XPATH, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
               <!-- Other Resolver Definitions Here -->  
          </resolvers>  
          <!-- Other ESB Configuration Settings Here -->  
     </esb>  
     <!-- Other Configuration Sections Here -->  
</configuration>  
```  
  
 El **resolverConfig** sección en cada nodo de resolución le permite configurar propiedades adicionales que puede requerir su resolución para que funcione en un entorno específico. Para tener acceso a la configuración, la resolución debe exponer un constructor que toma un parámetro de tipo **Microsoft.Practices.ESB.Configuration.Resolver**. En la implementación de la resolución, propiedades de configuración, a continuación, se pueden acceder mediante el **ReadResolverConfigByKey** método de la **ResolverConfigHelper** clase; para ello, pase el parámetro se pasaron originalmente al constructor y, a continuación, pase el nombre del valor en cuestión. Si no hay ningún par nombre-valor se especifica en el **resolverConfig** nodo, el constructor sin parámetros predeterminado se usará para crear una instancia de su resolución.  
  
 Dos Universal Description, Discovery and Integration (UDDI) 3 se han definido en la configuración de resoluciones: UDDI 3 y 3-SOASOFTWARE de UDDI. Estos solucionadores usan el mismo ensamblado subyacente, pero proporcionan distintas configuraciones para admitir diferentes registros UDDI 3.0: compatible con distintos formatos de identificador uniforme de recursos (URI) y los requisitos de seguridad. Si necesita configurar un moniker adicional para un registro UDDI 3.0 – compatible además de los que ya se admite, se pueden usar las siguientes propiedades de configuración:  
  
- **cacheTimeoutValue**  
  
- **cacheName**  
  
- **publisherKey**  
  
- **useUddiAuth**  
  
- **baseUri**  
  
- **inquireUriSuffix**  
  
- **securityUriSuffix**  
  
- **securityMode**. Para los valores válidos, vea la enumeración [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)). El valor predeterminado es **TransportCredentialOnly**.  
  
- **credentialType**. Para los valores válidos, vea la enumeración [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)). El valor predeterminado es **Windows**.  
  
- **Nombre de usuario**  
  
- **password**  
  
  Si desea crear a una resolución que se basa en las funcionalidades de inserción de dependencias de Unity Application Block, se requiere configuración adicional. Para obtener más información, consulte [creación de un solucionador personalizado con un contenedor Unity](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).  
  
## <a name="the-iresolveprovider-interface"></a>La interfaz IResolveProvider  
 Deben implementar todos los solucionadores el **IResolveProvider** interfaz. El **IResolveProvider** interfaz, ubicado en el proyecto Microsoft.Practices.ESB.Resolver, consta de tres sobrecargas de los **resolver** método que devuelva una instancia de la  **Diccionario** (clase), que contiene los datos de resolución proporcionados por la instancia de clase de resolución concreto. En el ejemplo de código siguiente se muestra la firma de estas sobrecargas de método.  
  
```csharp  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from a Microsoft BizTalk   
// Server pipeline component.  
// </summary>  
// <param name="config">Configuration string entered into   
// pipeline component as argument</param>  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">IBaseMessage passed from pipeline</param>.  
// <param name="pipelineContext">IPipelineContext passed from   
// pipeline</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(string config, string resolver,  
              IBaseMessage message, IPipelineContext pipelineContext);  
  
// <summary>  
// This is the main interface that is called from the ResolverMgr   
// class.  
// This interface supports being called from a Web service interface.  
// </summary>  
// <param name="config">Configuration string entered into Web   
// service as argument</param>.  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">XML document passed from Web   
// service</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string,string> Resolve(string config, string resolver, System.Xml.XmlDocument message);  
  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from an orchestration.  
// </summary>  
// <param name="resolverInfo">Configuration string containing   
// configuration and resolver</param>.  
// <param name="message">XLANGMessage passed from   
// orchestration</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(ResolverInfo resolverInfo, XLANGs.BaseTypes.XLANGMessage message);  
```  
  
 El **resolución** estructura, que se encuentra en el proyecto Microsoft.Practices.ESB.Resolver, también define los pares nombre/valor almacenados en el **diccionario** instancia. El **resolución** estructura expone varias propiedades; en la tabla siguiente se enumera las más relevantes. El **CreateResolverDictionary** método de la **ResolutionHelper** clase puede usarse para generar un diccionario de resolución que contiene las claves más usadas, con valores de cadena vacía. El **diccionario** instancia admite la adición de pares de nombre/valor de resolución personalizada a través de una implementación concreta de la **resolución** clase.  
  
|Property|Tipo de datos|Tipo de datos|Tipo de datos|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|String|**ActionField**|String|  
|**Correcto**|Boolean|**EpmRRCorrelationTokenField**|String|  
|**TransportNamespace**|String|**InboundTransportLocationField**|String|  
|**TransportType**|String|**InterchangeIDField**|String|  
|**TransportLocation**|String|**ReceiveLocationNameField**|String|  
|**Acción**|String|**ReceivePortNameField**|String|  
|**MessageExchangePattern**|String|**InboundTransportTypeField**|String|  
|**EndpointConfig**|String|**IsRequestResponseField**|String|  
|**TargetNamespace**|String|**DocumentSpecStrongNameField**|String|  
|**FixJaxRPC**|Boolean|**DocumentSpecNameField**|String|  
|**WindowUserField**|String|**MessageType**|String|  
|**CacheTimeout**|String|**OutboundTransportCLSID**|String|  
|**MethodNameField**|String|||  
  
## <a name="creating-a-custom-resolver"></a>Creación de un solucionador personalizado  
 En tiempo de ejecución, una canalización recupera la cadena de conexión de la resolución y llama al administrador de la resolución (una instancia de la **ResolverMgr** clase). El Administrador de solucionador analiza, rellena y valida la cadena de conexión de la resolución. Para ello, haga lo siguiente:  
  
- Analiza la cadena de conexión para determinar qué **resolución** tipo para cargar.  
  
- Coincide con este tipo de un moniker que se define en el archivo de configuración (la clave es el moniker raíz, por ejemplo, UDDI).  
  
- Lee el nombre del ensamblado de la resolución de este moniker.  
  
- Carga el ensamblado especificado.  
  
  El mecanismo de resolución dinámica almacena en caché cargadas todas las implementaciones de la **IResolveProvider** interfaz para evitar lecturas repetidas de información de configuración y del ensamblado que se carga cuando varios mensajes entrantes utilizan la misma resolución.  
  
  Por último, se ejecuta el Administrador de solucionador el **resolver** método el hormigón **IResolveProvider** implementación y devuelve el rellenado **diccionario** instancia.  
  
  **Para crear a una resolución personalizada**  
  
1.  Crear un ensamblado con una clase que implementa el **IResolveProvider** interfaz y contiene un **resolver** método que devuelve los hechos de resolución como una instancia de la **diccionario**clase.  
  
2.  Registrar la resolución, éste se agrega al archivo de configuración Esb.config utilizando un **\<resolución\>** elemento que contiene el moniker raíz como el **nombre** atributo y totalmente nombre de ensamblado completo como el **tipo** atributo.  
  
3.  (Opcional) Crear un esquema que define el moniker raíz y los parámetros de consulta y, a continuación, guárdela en el ESB. Carpeta Schemas.Resolvers. El nombre debe seguir convenciones de nomenclatura de ESB existentes; Esto significa que debe usar el nombre del moniker raíz anexado con "_Resolution.xsd".  
  
4.  (Opcional) Generar una clase desde el nuevo esquema y guardarlo en el ensamblado de resolución personalizada. Esto expone los parámetros con tipo en la resolución personalizada.  
  
5.  Registre el nuevo ensamblado en la caché global de ensamblados.