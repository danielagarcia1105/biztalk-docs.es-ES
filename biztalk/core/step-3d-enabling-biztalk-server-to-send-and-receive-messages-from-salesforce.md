---
title: 'Paso 3d: Habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea447687ab6b5eeaacf990acb5467e3f67adc60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991677"
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a>Paso 3d: Habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce
Debemos autenticarnos en Salesforce cuando enviamos mensajes con la interfaz REST. Los métodos de autenticación para llamadas REST que admite Salesforce no están disponibles listos para usar con el adaptador WCF-WebHttp, que es el que usaremos para invocar a la interfaz REST de Salesforce. Por tanto, vamos a crear un comportamiento de extremo WCF personalizado y lo asociaremos al adaptador de envío WCF-WebHttp que configuraremos para invocar a la interfaz REST de Salesforce.  
  
 De manera similar, la respuesta XML recibida de Salesforce no contendrá ningún espacio de nombres. Para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese el mensaje de respuesta con el esquema de respuesta, el mensaje de respuesta debe incluir el espacio de nombres de destino. Por tanto, crearemos una canalización personalizada usando [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para agregar un espacio de nombres al mensaje de respuesta. A continuación, usaremos esta canalización personalizada como canalización de recepción para el puerto de envío WCF-WebHttp de petición-respuesta.  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a>Agregar un comportamiento de WCF personalizado para la autenticación en Salesforce  
 Salesforce proporciona diferentes opciones para que las aplicaciones cliente se autentiquen en Salesforce. Vamos a usar qué términos de Salesforce como el [nombre de usuario-contraseña](http://go.microsoft.com/fwlink/?LinkId=287082) flujo. En el lado cliente, WCF permite crear [inspectores de mensaje](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx) para modificar los mensajes antes de enviarlos o después de que se reciben. Un inspector de mensajes es una extensión del motor en tiempo de ejecución del cliente y se configura como un comportamiento. Un comportamiento, a su vez, se agrega a un elemento de extensión de comportamiento. Este elemento de extensión de comportamiento se registra en el archivo machine.config con un nombre de elemento, lo que permite configurarlo como un comportamiento personalizado en un puerto WCF. Para obtener más información, consulte [Extending WCF con comportamientos personalizados](http://msdn.microsoft.com/magazine/cc163302.aspx). Vamos a usar esta estrategia para incorporar el flujo nombreDeUsuario-autenticación con Salesforce. Los pasos que seguiremos son:  
  
-   Crear un inspector de mensajes que realice una llamada HTTP POST al extremo de autenticación de Salesforce y reciba un token de acceso. El inspector de mensajes agrega después el token de autenticación como valor del encabezado Authorization del mensaje de consulta que se envía a Salesforce. El inspector de mensajes agrega también el encabezado Accept al mensaje de solicitud para que la respuesta recibida tenga el formato XML. De lo contrario, Salesforce envía el mensaje con el formato JSON predeterminado.  
  
-   Crear un comportamiento de extremo para aplicar el inspector de mensajes al extremo del cliente.  
  
-   Crear un elemento de extensión de comportamiento para habilitar la configuración del comportamiento del extremo.  
  
#### <a name="to-create-a-message-inspector"></a>Para crear un inspector de mensajes  
  
1. Como parte de la **BtsSalesforceIntegration** solución en Visual Studio, cree una biblioteca de clases de C#. Asígnele el nombre `Microsoft.BizTalk.Adapter.Behaviors` y agregue los espacios de nombres siguientes:  
  
   ```  
   using System.ServiceModel.Description;  
   using System.ServiceModel.Dispatcher;  
   using System.ServiceModel.Channels;  
   using System.Xml;  
   using System.Net;  
   using System.IO;  
   using System.ServiceModel.Configuration;  
   using System.Configuration;  
   using System.Web.Script.Serialization;  
   ```  
  
2. En el Explorador de soluciones, agregue referencias a `System.ServiceModel`, `System.Web.Extensions` y `System.Configuration`.  
  
3. Agregue una clase `SalesforceOAuthToken` con las siguientes propiedades. Esta clase representa el token de autorización que se recibe de Salesforce.  
  
   ```  
   public class SalesforceOAuthToken  
   {  
       public string id { get; set; }  
       public string issued_at { get; set; }  
       public string refresh_token { get; set; }  
       public string instance_url { get; set; }  
       public string signature { get; set; }  
       public string access_token { get; set; }  
   }  
   ```  
  
4. Agregue una clase `SalesforceRESTSecurityBehavior` que implemente `IClientMessageInspector` y `IEndpointBehavior`. Esta clase incluye los métodos `HttpPost()` y `FetchOAuthToken()` que realizan una llamada HTTP POST al extremo de autenticación de Salesforce para recuperar el token de autorización.  
  
    Puesto que la clase `SalesforceRESTSecurityBehavior` implementa la interfaz `IClientMessageInspector`, debe implementar los dos métodos, `AfterReceiveReply()` y `BeforeSendRequest()`. Para este escenario, no es necesario hacer nada más con el método `AfterReceiverReply()`. Sin embargo, el método `BeforeSendRequest()` invoca al método `FetchOAuthToken()` que, a su vez, llama al método `HttpPost()`. El método `BeforeSendRequest()` agrega entonces el token de autorización como parte del encabezado del mensaje. También agrega el **Accept** encabezado para garantizar que la respuesta recibida de Salesforce está en un formato XML.  
  
    La implementación de `IEndpointBehavior` simplemente agrega la clase del inspector de mensajes al comportamiento de extremo del cliente.  
  
   ```  
   public class SalesforceRESTSecurityBehavior : IClientMessageInspector, IEndpointBehavior  
   {  
       // Some constants  
       private static string SalesforceAuthEndpoint = "https://login.salesforce.com/services/oauth2/token";  
  
       // Configuration Properties  
       private string username_;  
       private string password_;  
       private string consumerKey_;  
       private string consumerSecret_;  
       private int sessionTimeout_;  
  
       // Private Properties  
       private SalesforceOAuthToken token_;  
       private DateTime tokenExpiryTime_;  
  
       public SalesforceRESTSecurityBehavior(  
           string username,  
           string password,  
           string consumerKey,  
           string consumerSecret,  
           int sessionTimeout)  
       {  
           this.username_ = username;  
           this.password_ = password;  
           this.consumerKey_ = consumerKey;  
           this.consumerSecret_ = consumerSecret;  
           this.sessionTimeout_ = sessionTimeout;  
       }  
  
       private void FetchOAuthToken()  
       {  
           if ((tokenExpiryTime_ == null) || (tokenExpiryTime_.CompareTo(DateTime.Now) <= 0))  
           {  
               StringBuilder body = new StringBuilder();  
               body.Append("grant_type=password&")  
                   .Append("client_id=" + consumerKey_ + "&")  
                   .Append("client_secret=" + consumerSecret_ + "&")  
                   .Append("username=" + username_ + "&")  
                   .Append("password=" + password_);  
  
               string result;  
  
               try  
               {  
                   result = HttpPost(SalesforceAuthEndpoint, body.ToString());  
               }  
               catch (WebException)  
               {  
                   // do something  
                   return;  
               }  
  
               // Convert the JSON response into a token object  
               JavaScriptSerializer ser = new JavaScriptSerializer();  
               this.token_ = ser.Deserialize<SalesforceOAuthToken>(result);  
               this.tokenExpiryTime_ = DateTime.Now.AddSeconds(this.sessionTimeout_);  
           }  
       }  
  
       public string HttpPost(string URI, string Parameters)  
       {  
           WebRequest req = WebRequest.Create(URI);  
           req.ContentType = "application/x-www-form-urlencoded";  
           req.Method = "POST";  
  
           // Add parameters to post  
           byte[] data = Encoding.ASCII.GetBytes(Parameters);  
           req.ContentLength = data.Length;  
           System.IO.Stream os = req.GetRequestStream();  
           os.Write(data, 0, data.Length);  
           os.Close();  
  
           // Do the post and get the response.  
           System.Net.WebResponse resp = null;  
           resp = req.GetResponse();  
  
           StreamReader sr = new StreamReader(resp.GetResponseStream());  
           return sr.ReadToEnd().Trim();  
       }  
       #region IClientMessageInspector  
  
       public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
       {  
           // do nothing  
       }  
       public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
       {  
           // We are going to send a request to Salesforce  
           // Overview:  
           // This behavior will do the following:  
           // (1) Fetch Token from Salesforce, if required  
           // (2) Add the token to the message  
           // (3) Insert an Http Accept header so we get XML data in response, instead of JSON, which is default  
           // Reference: http://www.salesforce.com/us/developer/docs/api_rest/index.htm  
           //  
           // (1) Authentication with Salesforce  
           // (2) The token is added to the HTTP Authorization Header   
           // (3) Add the Accept Header  
           //  
  
           HttpRequestMessageProperty httpRequest = null;  
  
           if (request.Properties.ContainsKey(HttpRequestMessageProperty.Name))  
           {  
               httpRequest = request.Properties[HttpRequestMessageProperty.Name] as HttpRequestMessageProperty;  
           }  
  
           if (httpRequest == null)  
           {  
               // NOTE: Ideally, we shouldn’t get here for WebHttp  
               httpRequest = new HttpRequestMessageProperty()  
               {  
                   Method = "GET",  
                   SuppressEntityBody = true  
               };  
               request.Properties.Add(HttpRequestMessageProperty.Name, httpRequest);  
           }  
  
           WebHeaderCollection headers = httpRequest.Headers;  
           FetchOAuthToken();  
  
           headers.Add(HttpRequestHeader.Authorization, "OAuth " + this.token_.access_token);  
           headers.Add(HttpRequestHeader.Accept, "application/xml");  
  
           return null;  
       }  
  
       #endregion IClientMessageInspector  
  
       #region IEndpointBehavior  
  
       public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
       {  
           // do nothing  
       }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
       {  
           clientRuntime.MessageInspectors.Add(this);  
       }  
  
       public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
       {  
           // do nothing  
       }  
  
       public void Validate(ServiceEndpoint endpoint)  
       {  
           // do nothing  
       }  
  
       #endregion IEndpointBehavior  
   }  
   ```  
  
5. En el paso anterior, creamos una clase de comportamiento que aplica el inspector de mensajes al extremo del cliente. Ahora debemos hacer que este comportamiento esté disponible para la configuración del adaptador WCF-WebHttp que enviará el mensaje de solicitud a Salesforce. Para que este comportamiento esté disponible para la configuración, debemos hacer dos cosas:  
  
   - Crear una clase que se derive de `BehaviorExtensionElement`  
  
   - Registrar BehavaiorExtensionElement en el \<extensiones\>\\< behaviorExtensions\> elemento en el archivo machine.config con un nombre de elemento.  
  
     Agregaremos también propiedades de configuración a esta clase para que estén disponibles en la interfaz de usuario de configuración del adaptador WCF-WebHttp.  
  
   ```  
   public class SalesforceRESTBehaviorElement : BehaviorExtensionElement  
   {  
       public override Type BehaviorType  
       {  
           get { return typeof(SalesforceRESTSecurityBehavior); }  
       }  
  
       protected override object CreateBehavior()  
       {  
           return new SalesforceRESTSecurityBehavior(Username, Password, ConsumerKey, ConsumerSecret, SessionTimeout);  
       }  
  
       [ConfigurationProperty("username", IsRequired = true)]  
       public string Username  
       {  
           get { return (string)this["username"]; }  
           set { this["username"] = value; }  
       }  
  
       [ConfigurationProperty("password", IsRequired = true)]  
       public string Password  
       {  
           get { return (string)this["password"]; }  
           set { this["password"] = value; }  
       }  
  
       [ConfigurationProperty("consumerKey", IsRequired = true)]  
       public string ConsumerKey  
       {  
           get { return (string)this["consumerKey"]; }  
           set { this["consumerKey"] = value; }  
       }  
  
       [ConfigurationProperty("consumerSecret", IsRequired = true)]  
       public string ConsumerSecret  
       {  
           get { return (string)this["consumerSecret"]; }  
           set { this["consumerSecret"] = value; }  
       }  
  
       [ConfigurationProperty("sessionTimeout", IsRequired = false, DefaultValue = 300)]  
       public int SessionTimeout  
       {  
           get { return (int)this["sessionTimeout"]; }  
           set { this["sessionTimeout"] = value; }  
       }  
   }  
   ```  
  
6. Agregar un archivo de clave de nombre seguro al proyecto y compilar el proyecto. Una vez compilado correctamente el proyecto, agregue el ensamblado `Microsoft.BizTalk.Adapter.Behaviors` a la GAC.  
  
7. Agregue la siguiente entrada al archivo machine.config en System.ServiceModel\Extensions\BehaviorExtensions.  
  
   ```  
   <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
   ```  
  
    Puede recuperar el token de clave pública para el ensamblado de la GAC. Asimismo, si crea esta aplicación en un equipo de 64 bits, debe agregar esta entrada tanto a la versión de 32 bits como a la de 64 bits del archivo machine.config.  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a>Agregar una canalización personalizada para agregar un espacio de nombres a la respuesta de Salesforce  
 La respuesta recibida de Salesforce no incluye un espacio de nombres. Sin embargo, para procesar el mensaje de respuesta con el esquema de respuesta (QueryResult.xsd), debemos incluir el espacio de nombres en la respuesta de Salesforce. En esta sección, crearemos una canalización personalizada y usaremos un componente de canalización personalizada que se distribuye con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para agregar un espacio de nombres al mensaje de respuesta. Esta canalización personalizada se implementa con la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se usará como canalización de recepción cuando se configure el adaptador WCF-WebHttp.  
  
 Antes de llevar a cabo los pasos de este procedimiento, asegúrese de que [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está instalado y configurado en el equipo donde va a crear esta aplicación.  
  
#### <a name="to-add-a-custom-pipeline"></a>Para agregar una canalización personalizada  
  
1. Dentro de la **BtsSalesforceIntegration** solución, cree un nuevo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto. Denomine el proyecto `CustomPipeline`.  
  
2. Dentro de la **CustomPipeline** proyecto, agregue una nueva canalización de recepción. Nombre de la canalización como `AddNamespace.btp`.  
  
3. Dentro de la **Decode** fase de la canalización, en el cuadro de herramientas, arrastre y coloque el **ESB agregar Namespace** componente de canalización. Dentro de la **desensamblar** almacenar provisionalmente, arrastre y coloque el **desensamblador XML** componente de canalización.  
  
   > [!NOTE]
   >  Si el **ESB agregar Namespace** componente de canalización no aparece en el cuadro de herramientas, puede agregarlo. Haga clic en el **componentes de canalización de BizTalk** pestaña y, a continuación, haga clic en **elegir elementos**. En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha, active la casilla de verificación para **ESB agregar Namespace** componente y, a continuación, haga clic en **Aceptar**.  
  
4. Agregue un archivo de clave de nombre seguro al proyecto y guarde el proyecto.  
  
5. Haga clic en el **CustomPipeline** del proyecto y seleccione **propiedades**. En el **implementación** ficha, para **nombre de la aplicación**, escriba `SalesforceIntegration`.  
  
6. Guarde los cambios del proyecto.  
  
   En este tema, hemos agregado un comportamiento personalizado para la autenticación en Salesforce y una canalización personalizada para agregar un espacio de nombres a la respuesta de Salesforce. Usaremos estos componentes personalizados para configurar los puertos físicos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear la solución de BizTalk Server en Visual Studio](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)