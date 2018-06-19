---
title: Crear un solucionador personalizado | Documentos de Microsoft
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
ms.openlocfilehash: 57fb0073437c32c8a8f064a4c77f267ee6806858
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975906"
---
# <a name="creating-a-custom-resolver"></a>Crear a una resolución personalizada
La implementación de resolución y marco de proveedores de adaptador en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] utiliza un componente de canalización con nombre distribuidor y canalizaciones con nombre ItineraryReceive y ItinerarySend.  
  
 El componente de canalización de distribuidor tiene cuatro propiedades: **validar, Enabled, extremo,** y **Nombredemapa**. El **extremo** propiedad puede contener cadenas de conexión de resolución con valores como el siguiente, donde **UDDI:\\ \\**  representa el tipo de resolución que se usará (la raíz moniker).  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 Otros monikers admitidos incluyen **XPATH:\\\\estática:\\\\,** y **BRE:\\\\**. Cada tipo de moniker utiliza una clase específica que implementa el **IResolveProvider** interfaz. Puede crear a sus propios solucionadores personalizados para otros tipos de moniker y registrar para su uso por el sistema de resolución dinámica.  
  
 El moniker equivale a una cadena de conexión de resolución. Esquemas individuales definen los parámetros y su moniker raíz. Una resolución toma la resolución de cadena de conexión, lo valida y utiliza el resultado para consultar y rellenar un **diccionario** objeto que puede utilizarse para el enrutamiento, transformación, selección de itinerarios o cualquier otro propósito específico para su servicio.  
  
## <a name="resolver-configuration"></a>Configuración de la resolución  
 Debe registrar a todas las resoluciones en el archivo de configuración Esb.config. El siguiente XML muestra un ejemplo del contenido del archivo de configuración.  
  
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
  
 El **resolverConfig** sección en cada nodo de resolución le permite configurar las propiedades adicionales que puede requerir la resolución para que funcione en un entorno concreto. Para tener acceso a la configuración, la resolución debe exponer un constructor que toma un parámetro de tipo **Microsoft.Practices.ESB.Configuration.Resolver**. En la implementación de la resolución, propiedades de configuración, a continuación, se pueden acceder mediante la **ReadResolverConfigByKey** método de la **ResolverConfigHelper** clase; para ello, pase el parámetro se pasó originalmente al constructor y, a continuación, pasa el nombre del valor en cuestión. Si no hay ningún par nombre-valor se especifica en el **resolverConfig** nodo, el constructor sin parámetros predeterminado que se utilizará para crear una instancia de la resolución.  
  
 Dos Universal Description, Discovery y Integration (UDDI) 3 resoluciones se han definido en la configuración: 3 de UDDI y 3-SOASOFTWARE de UDDI. Ambos de estos solucionadores utilizan el mismo ensamblado subyacente, pero proporcionan distintas configuraciones para admitir diferentes registros UDDI 3.0: compatible con diferentes formatos de identificador uniforme de recursos (URI) y los requisitos de seguridad. Si tiene que configurar un moniker adicional para un registro UDDI compatible con 3.0 Además de los que ya se admite, se pueden utilizar las siguientes propiedades de configuración:  
  
-   **cacheTimeoutValue**  
  
-   **cacheName**  
  
-   **publisherKey**  
  
-   **useUddiAuth**  
  
-   **baseUri**  
  
-   **inquireUriSuffix**  
  
-   **securityUriSuffix**  
  
-   **securityMode**. Para los valores válidos, vea la enumeración [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)). El valor predeterminado es **TransportCredentialOnly**.  
  
-   **credentialType**. Para los valores válidos, vea la enumeración [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)). El valor predeterminado es **Windows**.  
  
-   **nombre de usuario**  
  
-   **contraseña**  
  
 Si desea crear a una resolución que se basa en las capacidades de inyección de dependencia del bloque de aplicación de Unity, se requiere configuración adicional. Para obtener más información, consulte [crear una resolución personalizada con un contenedor de Unity](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).  
  
## <a name="the-iresolveprovider-interface"></a>La interfaz de IResolveProvider  
 Todos los solucionadores deben implementar la **IResolveProvider** interfaz. El **IResolveProvider** interfaz, ubicado en el proyecto Microsoft.Practices.ESB.Resolver, consta de tres sobrecargas de la **resolver** método que devuelva una instancia de la  **Diccionario** (clase), que contiene información sobre la resolución proporcionada por la instancia de clase de resolución concretos. En el ejemplo de código siguiente se muestra la firma de estas sobrecargas del método.  
  
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
  
 El **resolución** estructura, que se encuentra en el proyecto de Microsoft.Practices.ESB.Resolver, también define los pares de nombre/valor que se almacena en la **diccionario** instancia. El **resolución** estructura expone varias propiedades; en la tabla siguiente se enumera los más importantes. El **CreateResolverDictionary** método de la **ResolutionHelper** clase puede usarse para generar un diccionario de resolución que contiene las claves más usadas, con valores de cadena vacía. El **diccionario** instancia admite la adición de pares de nombre/valor de resolución personalizada a través de una implementación concreta de la **resolución** clase.  
  
|Propiedad|Tipo de datos|Tipo de datos|Tipo de datos|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|String|**ActionField**|String|  
|**Success**|Boolean|**EpmRRCorrelationTokenField**|String|  
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
  
## <a name="creating-a-custom-resolver"></a>Crear a una resolución personalizada  
 En tiempo de ejecución, una canalización recupera la cadena de conexión de resolución y llama a la resolución de administrador (una instancia de la **ResolverMgr** clase). El Administrador de resolución analiza, rellena y valida la cadena de conexión de resolución. Para ello, realice lo siguiente:  
  
-   Analiza la cadena de conexión para determinar qué **resolución** tipo a cargar.  
  
-   Coincide con este tipo de un moniker definido en el archivo de configuración (la clave es el moniker raíz, por ejemplo, UDDI).  
  
-   Lee el nombre del ensamblado de la resolución para este moniker.  
  
-   Carga el ensamblado especificado.  
  
 El mecanismo de resolución dinámica almacena en caché cargadas todas las implementaciones de la **IResolveProvider** interfaz para evitar lecturas repetidas de información de configuración y el ensamblado que se carga cuando varios mensajes entrantes utilizan el mismo resolución.  
  
 Por último, se ejecuta el Administrador de la resolución del **resolver** método el hormigón **IResolveProvider** implementación y devuelve el rellenado **diccionario** instancia.  
  
 **Para crear a una resolución personalizada**  
  
1.  Crear un ensamblado con una clase que implementa el **IResolveProvider** de interfaz y contiene un **resolver** método que devuelve los hechos de resolución como una instancia de la **diccionario**clase.  
  
2.  Registre el solucionador, éste se agrega al archivo de configuración Esb.config utilizando un  **\<resolución\>**  elemento que contiene el moniker raíz como la **nombre** atributo y totalmente nombre del ensamblado completo como el **tipo** atributo.  
  
3.  (Opcional) Crear un esquema que define el moniker raíz y los parámetros de consulta y, a continuación, guárdelo en ESB. Carpeta Schemas.Resolvers. El nombre debe seguir convenciones de nomenclatura de ESB existentes; Esto significa que debe usar el nombre del moniker raíz anexado "_Resolution.xsd".  
  
4.  (Opcional) Generar una clase desde el nuevo esquema y lo guarda en el ensamblado de la resolución personalizada. Esto expone los parámetros de tipo en la resolución personalizada.  
  
5.  Registrar el nuevo ensamblado en la caché global de ensamblados.