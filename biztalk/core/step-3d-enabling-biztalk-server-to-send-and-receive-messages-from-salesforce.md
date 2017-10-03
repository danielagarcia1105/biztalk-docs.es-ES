---
title: 'Paso 3d: Habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470c4a72-1e97-4493-8958-33a13f793ffd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c38a58e376bbc8908ff0fe578aa54cbb009c58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce"></a><span data-ttu-id="027b5-102">Paso 3d: Habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce</span><span class="sxs-lookup"><span data-stu-id="027b5-102">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>
<span data-ttu-id="027b5-103">Debemos autenticarnos en Salesforce cuando enviamos mensajes con la interfaz REST.</span><span class="sxs-lookup"><span data-stu-id="027b5-103">We must authenticate with Salesforce while sending messages using the REST interface.</span></span> <span data-ttu-id="027b5-104">Los métodos de autenticación para llamadas REST que admite Salesforce no están disponibles listos para usar con el adaptador WCF-WebHttp, que es el que usaremos para invocar a la interfaz REST de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-104">The authentication methods for REST calls supported by Salesforce are not available out of the box with the WCF-WebHttp adapter, which we’ll use to invoke Salesforce’s REST interface.</span></span> <span data-ttu-id="027b5-105">Por tanto, vamos a crear un comportamiento de extremo WCF personalizado y lo asociaremos al adaptador de envío WCF-WebHttp que configuraremos para invocar a la interfaz REST de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-105">So, we’ll create a custom WCF endpoint behavior and then attach it to WCF-WebHttp send adapter that we’ll configure to invoke the Salesforce REST interface.</span></span>  
  
 <span data-ttu-id="027b5-106">De manera similar, la respuesta XML recibida de Salesforce no contendrá ningún espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="027b5-106">Similarly, the XML response received from Salesforce will not contain any namespace.</span></span> <span data-ttu-id="027b5-107">Para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procese el mensaje de respuesta con el esquema de respuesta, el mensaje de respuesta debe incluir el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="027b5-107">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process the response message against the response schema, the response message must include the target namespace.</span></span> <span data-ttu-id="027b5-108">Por tanto, crearemos una canalización personalizada usando [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para agregar un espacio de nombres al mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="027b5-108">So, we’ll create a custom pipeline using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="027b5-109">A continuación, usaremos esta canalización personalizada como canalización de recepción para el puerto de envío WCF-WebHttp de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="027b5-109">We’ll then use this custom pipeline as the receive pipeline for request-response WCF-WebHttp send port.</span></span>  
  
## <a name="add-a-custom-wcf-behavior-for-salesforce-authentication"></a><span data-ttu-id="027b5-110">Agregar un comportamiento de WCF personalizado para la autenticación en Salesforce</span><span class="sxs-lookup"><span data-stu-id="027b5-110">Add a Custom WCF Behavior for Salesforce Authentication</span></span>  
 <span data-ttu-id="027b5-111">Salesforce proporciona diferentes opciones para que las aplicaciones cliente se autentiquen en Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-111">Salesforce provides different options for client applications to authenticate with Salesforce.</span></span> <span data-ttu-id="027b5-112">Vamos a usar los términos de Salesforce como el [usuario y contraseña](http://go.microsoft.com/fwlink/?LinkId=287082) flujo.</span><span class="sxs-lookup"><span data-stu-id="027b5-112">We’ll use what Salesforce terms as the [Username-password](http://go.microsoft.com/fwlink/?LinkId=287082) flow.</span></span> <span data-ttu-id="027b5-113">En el lado cliente, WCF permite crear [inspectores de mensaje](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx) para modificar los mensajes antes de enviarlos o después de que se reciben.</span><span class="sxs-lookup"><span data-stu-id="027b5-113">On the client side, WCF enables you to create [Message Inspectors](http://msdn.microsoft.com/library/aa717047\(v=VS.90\).aspx) to alter messages before they are sent or after they are received.</span></span> <span data-ttu-id="027b5-114">Un inspector de mensajes es una extensión del motor en tiempo de ejecución del cliente y se configura como un comportamiento.</span><span class="sxs-lookup"><span data-stu-id="027b5-114">A message inspector is an extension to the client runtime and is configured as a behavior.</span></span> <span data-ttu-id="027b5-115">Un comportamiento, a su vez, se agrega a un elemento de extensión de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="027b5-115">A behavior, in turn, is added to a behavior extension element.</span></span> <span data-ttu-id="027b5-116">Este elemento de extensión de comportamiento se registra en el archivo machine.config con un nombre de elemento, lo que permite configurarlo como un comportamiento personalizado en un puerto WCF.</span><span class="sxs-lookup"><span data-stu-id="027b5-116">This behavior extension element is registered in the machine.config with an element name, which makes it available to be configured as a custom behavior on a WCF port.</span></span> <span data-ttu-id="027b5-117">Para obtener más información, consulte [extensión de WCF con comportamientos personalizados](http://msdn.microsoft.com/magazine/cc163302.aspx).</span><span class="sxs-lookup"><span data-stu-id="027b5-117">For more information, see [Extending WCF with Custom Behaviors](http://msdn.microsoft.com/magazine/cc163302.aspx).</span></span> <span data-ttu-id="027b5-118">Vamos a usar esta estrategia para incorporar el flujo nombreDeUsuario-autenticación con Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-118">We are going to use this approach to incorporate the username-authentication flow for authenticating with Salesforce.</span></span> <span data-ttu-id="027b5-119">Los pasos que seguiremos son:</span><span class="sxs-lookup"><span data-stu-id="027b5-119">The broad steps that we’ll follow are:</span></span>  
  
-   <span data-ttu-id="027b5-120">Crear un inspector de mensajes que realice una llamada HTTP POST al extremo de autenticación de Salesforce y reciba un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="027b5-120">Create a message inspector that makes an HTTP POST call to the Salesforce authentication endpoint and receives an access token.</span></span> <span data-ttu-id="027b5-121">El inspector de mensajes agrega después el token de autenticación como valor del encabezado Authorization del mensaje de consulta que se envía a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-121">The message inspector then adds the authentication token as the value of the Authorization header of the query message being sent to Salesforce.</span></span> <span data-ttu-id="027b5-122">El inspector de mensajes agrega también el encabezado Accept al mensaje de solicitud para que la respuesta recibida tenga el formato XML.</span><span class="sxs-lookup"><span data-stu-id="027b5-122">The message inspector also adds the Accept header to the request message so that the response received is in an XML format.</span></span> <span data-ttu-id="027b5-123">De lo contrario, Salesforce envía el mensaje con el formato JSON predeterminado.</span><span class="sxs-lookup"><span data-stu-id="027b5-123">Otherwise, Salesforce sends the message in the default JSON format.</span></span>  
  
-   <span data-ttu-id="027b5-124">Crear un comportamiento de extremo para aplicar el inspector de mensajes al extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="027b5-124">Create an endpoint behavior to apply the message inspector to the client endpoint.</span></span>  
  
-   <span data-ttu-id="027b5-125">Crear un elemento de extensión de comportamiento para habilitar la configuración del comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="027b5-125">Create a behavior extension element to enable configuration of the endpoint behavior.</span></span>  
  
#### <a name="to-create-a-message-inspector"></a><span data-ttu-id="027b5-126">Para crear un inspector de mensajes</span><span class="sxs-lookup"><span data-stu-id="027b5-126">To create a message inspector</span></span>  
  
1.  <span data-ttu-id="027b5-127">Como parte de la **BtsSalesforceIntegration** solución en Visual Studio, cree una biblioteca de clases de C#.</span><span class="sxs-lookup"><span data-stu-id="027b5-127">As part of the **BtsSalesforceIntegration** solution in Visual Studio, create a C# Class Library.</span></span> <span data-ttu-id="027b5-128">Asígnele el nombre `Microsoft.BizTalk.Adapter.Behaviors` y agregue los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="027b5-128">Name it `Microsoft.BizTalk.Adapter.Behaviors` and add the following namespaces:</span></span>  
  
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
  
2.  <span data-ttu-id="027b5-129">En el Explorador de soluciones, agregue referencias a `System.ServiceModel`, `System.Web.Extensions` y `System.Configuration`.</span><span class="sxs-lookup"><span data-stu-id="027b5-129">From the Solution Explorer, add references to `System.ServiceModel`, `System.Web.Extensions`, and `System.Configuration`.</span></span>  
  
3.  <span data-ttu-id="027b5-130">Agregue una clase `SalesforceOAuthToken` con las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="027b5-130">Add a class `SalesforceOAuthToken` with the following properties.</span></span> <span data-ttu-id="027b5-131">Esta clase representa el token de autorización que se recibe de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-131">This class represents the authorization token that is received from Salesforce.</span></span>  
  
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
  
4.  <span data-ttu-id="027b5-132">Agregue una clase `SalesforceRESTSecurityBehavior` que implemente `IClientMessageInspector` y `IEndpointBehavior`.</span><span class="sxs-lookup"><span data-stu-id="027b5-132">Add a class `SalesforceRESTSecurityBehavior` that implements the `IClientMessageInspector` and the `IEndpointBehavior`.</span></span> <span data-ttu-id="027b5-133">Esta clase incluye los métodos `HttpPost()` y `FetchOAuthToken()` que realizan una llamada HTTP POST al extremo de autenticación de Salesforce para recuperar el token de autorización.</span><span class="sxs-lookup"><span data-stu-id="027b5-133">This class includes the `HttpPost()` and `FetchOAuthToken()` methods that make an HTTP POST call to the Salesforce authentication endpoint to retrieve the authorization token.</span></span>  
  
     <span data-ttu-id="027b5-134">Puesto que la clase `SalesforceRESTSecurityBehavior` implementa la interfaz `IClientMessageInspector`, debe implementar los dos métodos, `AfterReceiveReply()` y `BeforeSendRequest()`.</span><span class="sxs-lookup"><span data-stu-id="027b5-134">Because the `SalesforceRESTSecurityBehavior` class implements the `IClientMessageInspector` interface, it must implement the two methods, `AfterReceiveReply()` and `BeforeSendRequest()`.</span></span> <span data-ttu-id="027b5-135">Para este escenario, no es necesario hacer nada más con el método `AfterReceiverReply()`.</span><span class="sxs-lookup"><span data-stu-id="027b5-135">For this scenario we do not need to do anything as part of the `AfterReceiverReply()` method.</span></span> <span data-ttu-id="027b5-136">Sin embargo, el método `BeforeSendRequest()` invoca al método `FetchOAuthToken()` que, a su vez, llama al método `HttpPost()`.</span><span class="sxs-lookup"><span data-stu-id="027b5-136">However, the `BeforeSendRequest()` method invokes the `FetchOAuthToken()` method, which in turn calls the `HttpPost()` method.</span></span> <span data-ttu-id="027b5-137">El método `BeforeSendRequest()` agrega entonces el token de autorización como parte del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="027b5-137">The `BeforeSendRequest()` method then adds the authorization token as part of the message header.</span></span> <span data-ttu-id="027b5-138">También agrega la **Accept** encabezado para asegurarse de que la respuesta recibida de Salesforce está en un formato XML.</span><span class="sxs-lookup"><span data-stu-id="027b5-138">It also adds the **Accept** header to ensure that that the response received from Salesforce is in an XML format.</span></span>  
  
     <span data-ttu-id="027b5-139">La implementación de `IEndpointBehavior` simplemente agrega la clase del inspector de mensajes al comportamiento de extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="027b5-139">The `IEndpointBehavior` implementation simply adds the message inspector class to the client endpoint behavior.</span></span>  
  
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
  
5.  <span data-ttu-id="027b5-140">En el paso anterior, creamos una clase de comportamiento que aplica el inspector de mensajes al extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="027b5-140">In the previous step we created a behavior class that applies the message inspector to the client endpoint.</span></span> <span data-ttu-id="027b5-141">Ahora debemos hacer que este comportamiento esté disponible para la configuración del adaptador WCF-WebHttp que enviará el mensaje de solicitud a Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-141">We now need to make this behavior available to the configuration experience for the WCF-WebHttp adapter that will send the request message to Salesforce.</span></span> <span data-ttu-id="027b5-142">Para que este comportamiento esté disponible para la configuración, debemos hacer dos cosas:</span><span class="sxs-lookup"><span data-stu-id="027b5-142">To make this behavior available for configuration we need to do two things:</span></span>  
  
    -   <span data-ttu-id="027b5-143">Crear una clase que se derive de `BehaviorExtensionElement`</span><span class="sxs-lookup"><span data-stu-id="027b5-143">Create a class that derives from the `BehaviorExtensionElement`</span></span>  
  
    -   <span data-ttu-id="027b5-144">Registrar BehavaiorExtensionElement en el \<extensiones >\\< behaviorExtensions\> elemento en el archivo machine.config con un nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="027b5-144">Register your BehavaiorExtensionElement in the \<extensions>\\<behaviorExtensions\> element in the machine.config using an element name.</span></span>  
  
     <span data-ttu-id="027b5-145">Agregaremos también propiedades de configuración a esta clase para que estén disponibles en la interfaz de usuario de configuración del adaptador WCF-WebHttp.</span><span class="sxs-lookup"><span data-stu-id="027b5-145">We’ll also add configuration properties to this class so that they are available from the WCF-WebHttp adapter configuration UI.</span></span>  
  
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
  
6.  <span data-ttu-id="027b5-146">Agregar un archivo de clave de nombre seguro al proyecto y compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="027b5-146">Add a strong name key file to the project and build the project.</span></span> <span data-ttu-id="027b5-147">Una vez compilado correctamente el proyecto, agregue el ensamblado `Microsoft.BizTalk.Adapter.Behaviors` a la GAC.</span><span class="sxs-lookup"><span data-stu-id="027b5-147">Once the project builds successfully, add the assembly `Microsoft.BizTalk.Adapter.Behaviors` to the GAC.</span></span>  
  
7.  <span data-ttu-id="027b5-148">Agregue la siguiente entrada al archivo machine.config en System.ServiceModel\Extensions\BehaviorExtensions.</span><span class="sxs-lookup"><span data-stu-id="027b5-148">Add the following entry in the machine.config under System.ServiceModel\Extensions\BehaviorExtensions.</span></span>  
  
    ```  
    <add name="Microsoft.BizTalk.Adapter.Behaviors.Demo.Salesforce" type="Microsoft.BizTalk.Adapter.Behaviors.SalesforceRESTBehaviorElement, Microsoft.BizTalk.Adapter.Behaviors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=45bd7fe67ef032db"/>  
    ```  
  
     <span data-ttu-id="027b5-149">Puede recuperar el token de clave pública para el ensamblado de la GAC.</span><span class="sxs-lookup"><span data-stu-id="027b5-149">You can retrieve the public key token for the assembly from the GAC.</span></span> <span data-ttu-id="027b5-150">Asimismo, si crea esta aplicación en un equipo de 64 bits, debe agregar esta entrada tanto a la versión de 32 bits como a la de 64 bits del archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="027b5-150">Also, if you are creating this application on a 64-bit computer, you must add this entry to both 32-bit and 64-bit versions of the machine.config.</span></span>  
  
## <a name="add-a-custom-pipeline-to-add-namespace-to-the-salesforce-response"></a><span data-ttu-id="027b5-151">Agregar una canalización personalizada para agregar un espacio de nombres a la respuesta de Salesforce</span><span class="sxs-lookup"><span data-stu-id="027b5-151">Add a Custom Pipeline to Add Namespace to the Salesforce Response</span></span>  
 <span data-ttu-id="027b5-152">La respuesta recibida de Salesforce no incluye un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="027b5-152">The response received from Salesforce does not include a namespace.</span></span> <span data-ttu-id="027b5-153">Sin embargo, para procesar el mensaje de respuesta con el esquema de respuesta (QueryResult.xsd), debemos incluir el espacio de nombres en la respuesta de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-153">However, to process the response message against the response schema (QueryResult.xsd) we must include the namespace in the Salesforce response.</span></span> <span data-ttu-id="027b5-154">En esta sección, crearemos una canalización personalizada y usaremos un componente de canalización personalizada que se distribuye con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] para agregar un espacio de nombres al mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="027b5-154">In this section, we create a custom pipeline and use a custom pipeline component shipped with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] to add a namespace to the response message.</span></span> <span data-ttu-id="027b5-155">Esta canalización personalizada se implementa con la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se usará como canalización de recepción cuando se configure el adaptador WCF-WebHttp.</span><span class="sxs-lookup"><span data-stu-id="027b5-155">This custom pipeline is deployed with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application and will be used as the receive pipeline while configuring the WCF-WebHttp adapter.</span></span>  
  
 <span data-ttu-id="027b5-156">Antes de llevar a cabo los pasos de este procedimiento, asegúrese de que [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está instalado y configurado en el equipo donde va a crear esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="027b5-156">Before performing the steps in this procedure, ensure that [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is installed and configured on the computer where you are creating this application.</span></span>  
  
#### <a name="to-add-a-custom-pipeline"></a><span data-ttu-id="027b5-157">Para agregar una canalización personalizada</span><span class="sxs-lookup"><span data-stu-id="027b5-157">To add a custom pipeline</span></span>  
  
1.  <span data-ttu-id="027b5-158">En el **BtsSalesforceIntegration** solución, cree un nuevo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="027b5-158">Within the **BtsSalesforceIntegration** solution, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="027b5-159">Denomine el proyecto `CustomPipeline`.</span><span class="sxs-lookup"><span data-stu-id="027b5-159">Name the project `CustomPipeline`.</span></span>  
  
2.  <span data-ttu-id="027b5-160">En el **CustomPipeline** del proyecto, agregue una nueva canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="027b5-160">Within the **CustomPipeline** project, add a new receive pipeline.</span></span> <span data-ttu-id="027b5-161">Nombre de la canalización como `AddNamespace.btp`.</span><span class="sxs-lookup"><span data-stu-id="027b5-161">Name the pipeline as `AddNamespace.btp`.</span></span>  
  
3.  <span data-ttu-id="027b5-162">En el **Decode** fase de la canalización, en el cuadro de herramientas, arrastre y coloque el **ESB agregar Namespace** componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="027b5-162">Within the **Decode** stage of the pipeline, from the toolbox, drag and drop the **ESB Add Namespace** pipeline component.</span></span> <span data-ttu-id="027b5-163">En el **desensamblar** almacenar provisionalmente, arrastre y coloque el **desensamblador XML** componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="027b5-163">Within the **Disassemble** stage, drag and drop the **XML disassembler** pipeline component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="027b5-164">Si el **ESB agregar Namespace** componente de canalización no aparece en el cuadro de herramientas, puede agregarlo.</span><span class="sxs-lookup"><span data-stu-id="027b5-164">If the **ESB Add Namespace** pipeline component is not listed in the toolbox, you can add it.</span></span> <span data-ttu-id="027b5-165">Haga clic en el **componentes de canalización de BizTalk** ficha y, a continuación, haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="027b5-165">Right-click the **BizTalk Pipeline Components** tab, and then click **Choose Items**.</span></span> <span data-ttu-id="027b5-166">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, haga clic en el **componentes de canalización de BizTalk** ficha, active la casilla de verificación para **ESB agregar Namespace** componente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="027b5-166">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the check box for **ESB Add Namespace** component, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="027b5-167">Agregue un archivo de clave de nombre seguro al proyecto y guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="027b5-167">Add a strong name key file to the project and save the project.</span></span>  
  
5.  <span data-ttu-id="027b5-168">Haga clic en el **CustomPipeline** de proyecto y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="027b5-168">Right-click the **CustomPipeline** project and select **Properties**.</span></span> <span data-ttu-id="027b5-169">En el **implementación** ficha, para **nombre de la aplicación**, escriba `SalesforceIntegration`.</span><span class="sxs-lookup"><span data-stu-id="027b5-169">In the **Deployment** tab, for **Application Name**, enter `SalesforceIntegration`.</span></span>  
  
6.  <span data-ttu-id="027b5-170">Guarde los cambios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="027b5-170">Save changes to the project.</span></span>  
  
 <span data-ttu-id="027b5-171">En este tema, hemos agregado un comportamiento personalizado para la autenticación en Salesforce y una canalización personalizada para agregar un espacio de nombres a la respuesta de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="027b5-171">In this topic, added a custom behavior to authenticate with Salesforce and a custom pipeline to add a namespace to the Salesforce response.</span></span> <span data-ttu-id="027b5-172">Usaremos estos componentes personalizados para configurar los puertos físicos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="027b5-172">We’ll use these custom components while configuring the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027b5-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="027b5-173">See Also</span></span>  
 [<span data-ttu-id="027b5-174">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="027b5-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)