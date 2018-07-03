---
title: Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea3a13b-e41f-4920-bf0d-26f7bb145aa3
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42980d93c7872811ea26fb9fc21a97f7e4e8e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991325"
---
# <a name="development-best-practices-using-the-wcf-lob-adapter-sdk"></a>Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF
Puede usar los procedimientos recomendados en este tema para mejorar sus aplicaciones y adaptadores.  

## <a name="call-abort-before-close-on-channel-exception"></a>Anulación de llamada antes de cerrar en la excepción de canal  
 Al escribir una aplicación que utiliza el modelo de canal WCF, debe llamar a `IRequestChannel.Abort` antes de llamar a `ChannelFactory.Close`. Si no, `ChannelFactory.Close` produce una excepción.  

 En el ejemplo siguiente, las operaciones del canal intenta usar dentro de un bloque try/catch. Si se produce una excepción, se anula el canal.  

```csharp  
ChannelFactory<IRequestChannel> cf = new  ChannelFactory<IRequestChannel>();  
IRequestChannel channel = null;  
try  
{  
  cf.Open();  
  channel = cf.CreateChannel();  
  channel.Open();  
  channel.Request();// This causes the channel to go into a faulted state.  
  channel.Close();  
}  
catch (Exception e)  
{  
  // Abort the channel if we have one  
  if(channel != null)  
    channel.Abort();  
}  
finally  
{  
  if (cf.State == CommunicationState.Opened)  
  {  
    cf.Close(); // It throws an exception that the channel is in a faulted state.  
  }  
}  
```  

## <a name="implement-both-asynchronous-and-synchronous-handlers"></a>Implemente los controladores sincrónicos y asincrónicos  
 Si es posible, implemente controladores asincrónicos y sincrónicos en el adaptador. Si el adaptador sólo implementa las llamadas sincrónicas, pueden surgir problemas de bloqueo de al procesar un gran volumen de mensajes o cuando se usa el adaptador en un entorno multiproceso.  

## <a name="use-connection-pooling"></a>Usar la agrupación de conexiones  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] admite la agrupación de conexiones de forma predeterminada. Sin embargo, es depende del desarrollador de adaptador para determinar qué propiedades para exponer como propiedades de enlace de la agrupación de conexiones. La configuración del grupo de conexión disponible se define dentro de `Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`.  

 No hay ninguna opción dentro de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para exponer fácilmente estas propiedades como propiedades de conexión del adaptador. El programador de adaptadores debe definir manualmente las propiedades en la implementación del adaptador.  

```csharp  
public CustomAdapter(): base()  
{  
   this.Settings.ConnectionPool.EnablePooling = true;  
   this.Settings.ConnectionPool.HandlersShareSameConnection = true;  
   this.Settings.ConnectionPool.MaxConnectionsPerSystem = 50;  
   this.Settings.ConnectionPool.MaxAvailableConnections = 5;  
}  
```  

## <a name="ensure-that-the-adapter-supports-two-way-operations"></a>Asegúrese de que el adaptador admite operaciones bidireccionales  
 Si se llama a su adaptador de BizTalk Server, debe admitir operaciones bidireccionales, incluso si el valor devuelto es void. Esto es porque BizTalk Server espera una respuesta devuelta por cualquier solicitud de salida y produce una excepción si el adaptador sólo implementa las operaciones unidireccionales.  

 Este es un ejemplo de un contrato de solicitud-respuesta que devuelve void.  

```csharp  
[ServiceContract(Namespace=”Http:Microsoft.BizTalk.Samples.WCFAdapterSample”)]  
public interface ICalculator  
{  
   [OperationContract]  
   void Add(double n1, double n2);  
}  
```  

## <a name="implement-tracing"></a>Implementar el seguimiento  
 Durante el ciclo de desarrollo, puede no parecer importante agregar seguimiento a su adaptador, ya que puede recorrer el código y depurar los problemas. Sin embargo, una vez que el adaptador está instalado en un entorno de producción, es posible que no pueda usar la depuración de tiempo de ejecución para aislar problemas. Si ha habilitado el seguimiento a lo largo de su adaptador, puede usar para aislar dónde se producen errores.  

 Consulte [un adaptador con el SDK de adaptador LOB de WCF de seguimiento](../../adapters-and-accelerators/wcf-lob-adapter-sdk/trace-an-adapter-with-the-wcf-lob-adapter-sdk.md) para obtener más detalles.  

## <a name="use-uri-properties-for-frequently-changed-settings"></a>Utilizar propiedades de URI para la configuración cambian con frecuencia  
 Al decidir si desea exponer una propiedad personalizada como un enlace o una propiedad de identificador URI, se recomienda usar una propiedad URI si el valor cambia con frecuencia. Propiedades de enlace se deben reservar para los valores que cambian con poca frecuencia.  

 Una propiedad de enlace de ejemplo sería un nombre de servidor de base de datos que se usa por todas las conexiones. Un ejemplo de la propiedad de identificador URI sería una tabla específica o un procedimiento almacenado que va a usar esa conexión concreta.  

## <a name="do-not-pass-user-name-or-password-values-in-the-uri"></a>El URI no pasar valores de contraseña o nombre de usuario  
 Si el adaptador requiere las credenciales del llamador, se recomienda utilizar la **ClientCredentials** clase para recuperar los valores de credenciales en lugar de pasar las credenciales del cliente como parte del URI. El **ClientCredentials** clase es una característica estándar de WCF que está pensado para pasar información de credenciales del cliente al servicio de forma más segura. Pasar la información de usuario como parte de la cadena de URI puede exponer la información de usuario mientras están en tránsito.  

 Los métodos recomendados para pasar las credenciales se muestran en la tabla siguiente.  


|      Método       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Tiempo de diseño    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], puede especificar los tipos de credencial de cliente que admite el adaptador.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     Tiempo de ejecución      | Cuando se usa a un proxy de .NET CLR generado, se pueden establecer mediante programación el cliente las credenciales.<br /><br /> `static void Main(string[] args) {    EchoServiceClient client = new EchoServiceClient();    client.ClientCredentials.UserName.UserName = "TestUser";    client.ClientCredentials.UserName.Password = "TestPassword";    string response=client.EchoString("Test String"); }`<br /><br /> Como alternativa, si necesita interactuar directamente con el canal, puede usar el modelo de canal WCF para especificar las credenciales del cliente al crear un generador de canales.<br /><br /> `EchoAdapterBinding binding = new EchoAdapterBinding(); binding.Count = 3; ClientCredentials clientCredentials = new ClientCredentials(); clientCredentials.UserName.UserName = "TestUser"; clientCredentials.UserName.Password = "TestPassword"; BindingParameterCollection bindingParms = new BindingParameterCollection(); bindingParms.Add(clientCredentials); EndpointAddress address = new EndpointAddress("echo://"); IChannelFactory<IRequestChannel> requestChannelFactory = binding.BuildChannelFactory<IRequestChannel>(bindingParms); requestChannelFactory.Open();` |
| Configuración de WCF |                                                                                                                                                                                                                                               En el archivo de configuración de cliente, agregue un \<endpointBehaviors\> elemento que incluya \<clientCredentials\>.<br /><br /> `<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">       <system.serviceModel>           . . . . .           <behaviors>             <endpointBehaviors>               <behavior name="clientEndpointCredential">                 <clientCredentials>                   <windows allowNtlm="false" allowedImpersonationLevel="Delegation" />                    </clientCredentials>               </behavior>             </endpointBehaviors>           </behaviors>       </system.serviceModel>   </configuration>`                                                                                                                                                                                                                                               |
|   Uso de BizTalk   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Cuando se usa el adaptador de WCF para utilizar el adaptador, puede agregar el **clientCredentials** extensión de comportamiento en el **comportamiento** ficha. Una vez que se ha agregado, puede establecer las credenciales del cliente que desee en el comportamiento del extremo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <a name="do-not-return-both-strongdatasettype-and-weakdatasettype"></a>No se devuelven ambos StrongDataSetType y WeakDataSetType  
 Si el adaptador devuelve un `DataSet`, usar `Microsoft.ServiceModel.Channels.Common.QualifiedType.StrongDataSetType%2A` o `Microsoft.ServiceModel.Channels.Common.QualifiedType.WeakDataSetType%2A`, pero no use ambos al mismo tiempo. El nombre del nodo raíz y el espacio de nombres generado por ambos tipos son idénticos y no pueden existir simultáneamente en un archivo WSDL.  

 Mientras `WeakDataSetType` y `StrongDataSetType` ambos representan un `System.Data.DataSet`, `StrongDataSetType` es más fácil de usar en aplicaciones. NET, ya que el proxy generado aparece como `System.Data.Dataset`. El proxy generado por `WeakDataSetType` es `XmlElement[]`, que es más difícil de utilizar en una aplicación. NET.  BizTalk Server no puede usar el esquema devuelto por `StrongDataSet`, pero puede consumir `WeakDataSetType`.  

> [!NOTE]
>  `StrongDataSetType` y `WeakDataSetType` solo controlan cómo la aplicación cliente interpreta los mensajes XML que se pasa por el adaptador. El mensaje XML es la misma con independencia de qué tipo se especifica.  

> [!NOTE]
>  Cuando se devuelven `StrongDataSetType`, debe establecer `Microsoft.ServiceModel.Channels.Common.MetadataSettings.CompileWsdl%2A` a `false`. Cuando se establece en `true`, el valor predeterminado, `XmlSchemaSet::Compile` se llama en el adaptador para asegurarse de que no hay ningún error en el archivo WSDL, pero el esquema generado por `StrongDataSetType` genera una excepción en `XmlSchemaSet`.  
>   
>  Establecer `CompileWsdl` a `false` omite la validación del esquema WSDL dentro del adaptador y la validación se produce durante la generación de proxy.  Son capaces de generar un proxy para ambas utilidades como svcutil.exe `StrongDataSetType` y `WeakDataSetType`.  

 Para trabajar con entornos de BizTalk y. NET, considere la posibilidad de implementar una propiedad de enlace que permite cambiar entre los dos tipos de valor devueltos, como se indica en el entorno.  

```csharp  
internal static QualifiedType GetDataSetQualifiedType(MyAdapterBindingProperties bindingProperties)  
{  
   if (bindingProperties.EnableBizTalkCompatibility)  
      return QualifiedType.WeakDataSetType;  
   else  
      return QualifiedType.StrongDataSetType;  
}  
```  

## <a name="create-meaningful-xsd-schema-names-in-biztalk-server"></a>Crear nombres de esquema XSD significativo en BizTalk Server  
 Cuando se usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] herramienta en tiempo de diseño, el nombre del esquema XSD generado en el proyecto de BizTalk se crea mediante la `DefaultXsdFileNamePrefix` propiedad, el `fileNameHint` anotación en WSDL y, si es necesario, un valor entero único.  

 Por ejemplo, si `DefaultXsdFileNamePrefix` está establecido en "MyAdapter" y el `fileNameHint` anotación está establecida en "Stream", el esquema XSD que se crea se denomina MyAdapterStream.xsd.  

```  
<xs:schema elementFormDefault='qualified' targetNamespace='http://schemas.microsoft.com/Message' xmlns:xs='http://www.w3.org/2001/XMLSchema' xmlns:tns='http://schemas.microsoft.com/Message'>  
<xs:annotation>  
<xs:appinfo>  
<fileNameHint xmlns='http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd'>Stream</fileNameHint>  
</xs:appinfo>  
</xs:annotation>  
<xs:simpleType name='StreamBody'>  
<xs:restriction base='xs:base64Binary' />  
</xs:simpleType>  
</xs:schema>  

```  

> [!NOTE]
>  El valor predeterminado de `DefaultXsdFileNamePrefix` es el nombre de su enlace. Para especificar un valor diferente, reemplace `DefaultXsdFileNamePrefix` en la clase de adaptador que se deriva de `Microsoft.ServiceModel.Channels.Common.AdapterBinding`.  

 Hay dos métodos posibles para agregar el `fileNameHint` anotación al esquema: invalidar la exportación... Métodos de esquema en OperationMetadata\TypeMetadata o invalidar la implementación de IWsdlRetrieval del adaptador. Para cualquiera de estos métodos, puede llamar a la implementación base y, a continuación, agregar la anotación a los esquemas en la colección de esquemas.  

> [!NOTE]
>  Cuando se reemplaza la exportación... Métodos de esquema, puede haber varias definiciones de tipo de operación o en el mismo esquema; el adaptador debe asegurarse de que varias apariciones de la `fileNameHints` anotación en el mismo esquema no entran en conflicto. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] usa la primera aparición de `fileNameHint` si se produce varias veces dentro de un esquema.  

 En el ejemplo siguiente, IWsdlRetrieval se usa para agregar la `fileNameHint` anotación a WSDL.  

```csharp  
sealed class MyAdapterWsdlRetrieval : IWsdlRetrieval  
{  
   IWsdlRetrieval mBaseWsdlRetrieval;  
   public MyAdapterWsdlRetrieval(IWsdlRetrieval baseWsdlRetrieval)  
   {  
      mBaseWsdlRetrieval = baseWsdlRetrieval;  
   }  

   ServiceDescription IWsdlRetrieval.GetWsdl(Microsoft.ServiceModel.Channels.MetadataRetrievalNode[] nodes, Uri uri, TimeSpan timeout)  
   {  
      ServiceDescription baseDesc = mBaseWsdlRetrieval.GetWsdl(nodes, uri, timeout);  
      foreach (XmlSchema schema in baseDesc.Types.Schemas)  
      {  
         CreateFileNameHint(schema);  
      }  
      return baseDesc;  
   }  

   void CreateFileNameHint(XmlSchema schema)  
   {  
      string targetNamespace = schema.TargetNamespace;  
      if (string.IsNullOrEmpty(targetNamespace))  
         return;  
      string fileNameHint = null;  
      //determine the filename based on namespace  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadaptpter/HelloWorld"))  
      {  
         fileNameHint = "HelloWorld";  
      }  
      if (targetNamespace.StartsWith("myadapter:// adapters.samples.myadapter/Hello"))  
      {  
         fileNameHint = "Hello";  
      }  
      //create the annotation and populate it with fileNameHint  
      XmlSchemaAnnotation annotation = new XmlSchemaAnnotation();  
      XmlSchemaAppInfo appInfo = new XmlSchemaAppInfo();  
      XmlDocument doc = new XmlDocument();  
      XmlNode[] fileNameHintNodes = new XmlNode[1];  
      fileNameHintNodes[0] = doc.CreateElement(null, "fileNameHint", "http://schemas.microsoft.com/servicemodel/adapters/metadata/xsd");  
      fileNameHintNodes[0].AppendChild(doc.CreateTextNode(fileNameHint));  
      appInfo.Markup = fileNameHintNodes;  
      annotation.Items.Add(appInfo);  
      schema.Items.Insert(0, annotation);  
   }  
```  

## <a name="do-not-modify-adapterenvironmentsettings-during-processing"></a>No modifique AdapterEnvironmentSettings durante el procesamiento  
 El adaptador solo debe establecer el **AdapterEnvironmentSettings**, **ConnectionPoolManager**, **ConnectionPool**, y **CommonCacheSize**durante la inicialización del adaptador y no debe intentar modificar los valores de una instancia en ejecución.  

 Si estos valores se modifican en una instancia del adaptador que se está ejecutando, esto puede producir en las nuevas conexiones, sobrescribiendo los valores de configuración para conexiones está ejecutando actualmente.  

## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)