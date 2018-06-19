---
title: Recibir llamadas de RFC de entrada en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving inbound RFC calls
- RFC calls, receiving inbound using the WCF service model
ms.assetid: 064d70d7-1603-467f-9aba-ecab78a567ff
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a415e3ab0ecbaab8778254d817241e5cafb61a92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218460"
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="3e29b-102">Recibir llamadas de RFC de entrada en SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="3e29b-102">Receive Inbound RFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="3e29b-103">La [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] puede actuar como un servidor RFC para recibir las solicitudes de cambio invocados por un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] can act as an RFC server to receive RFCs invoked by a SAP system.</span></span>  
  
 <span data-ttu-id="3e29b-104">Para recibir las RFC entrantes en el modelo de servicio WCF, debe:</span><span class="sxs-lookup"><span data-stu-id="3e29b-104">To receive the inbound RFCs in the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="3e29b-105">Asegúrese de que un destino RFC existe en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-105">Ensure that an RFC destination exists on the SAP system.</span></span>  
  
-   <span data-ttu-id="3e29b-106">Asegúrese de que la solicitud de cambio se define en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-106">Ensure that the RFC is defined on the SAP system.</span></span>  
  
-   <span data-ttu-id="3e29b-107">Generar un contrato de servicio WCF (interfaz) para la operación de RFC de los metadatos expuestos por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3e29b-107">Generate a WCF service contract (interface) for the RFC operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="3e29b-108">Para ello, use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe).</span><span class="sxs-lookup"><span data-stu-id="3e29b-108">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
-   <span data-ttu-id="3e29b-109">Implementar un servicio WCF de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e29b-109">Implement a WCF service from this interface.</span></span> <span data-ttu-id="3e29b-110">Los métodos del servicio WCF contienen la lógica necesaria para procesar la solicitud de cambio y devolver una respuesta al adaptador (y por lo tanto, el sistema SAP).</span><span class="sxs-lookup"><span data-stu-id="3e29b-110">The methods of the WCF service contain the logic necessary to process the RFC and return a response to the adapter (and hence the SAP system).</span></span>  
  
-   <span data-ttu-id="3e29b-111">Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).</span><span class="sxs-lookup"><span data-stu-id="3e29b-111">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
 <span data-ttu-id="3e29b-112">Las secciones siguientes muestran cómo recibir las solicitudes de cambio desde el sistema SAP mediante el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e29b-112">The following sections show you how to receive RFCs from the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a><span data-ttu-id="3e29b-113">Cómo configurar el sistema de SAP para enviar una solicitud de cambio para el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="3e29b-113">How to Set up the SAP System to Send an RFC to the SAP Adapter</span></span>  
 <span data-ttu-id="3e29b-114">Para poder enviar una solicitud de cambio del sistema SAP para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe asegurarse de que los siguientes son ciertas en el sistema SAP:</span><span class="sxs-lookup"><span data-stu-id="3e29b-114">Before you can send an RFC from the SAP system to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must ensure that the following are true on the SAP system:</span></span>  
  
-   <span data-ttu-id="3e29b-115">Un destino RFC para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] debe existir.</span><span class="sxs-lookup"><span data-stu-id="3e29b-115">An RFC destination for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] must exist.</span></span> <span data-ttu-id="3e29b-116">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se registra con un destino RFC para recibir las solicitudes de cambio desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] registers itself with an RFC destination to receive RFCs from the SAP system.</span></span> <span data-ttu-id="3e29b-117">Especifica los parámetros con el URI, como el Host de puerta de enlace de SAP y el servicio de puerta de enlace de SAP, el identificador de programa de SAP que utiliza el adaptador registrarse a sí mismo de la conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-117">You supply parameters in the SAP connection URI such as the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that the adapter uses to register itself.</span></span> <span data-ttu-id="3e29b-118">Para obtener información acerca de cómo configurar un destino RFC en SAP, consulte [crear una solicitud de cambio, el destino de RFC y enviar una solicitud de cambio de sistema SAP](creating-an-rfc-in-an-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="3e29b-118">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
-   <span data-ttu-id="3e29b-119">La solicitud de cambio debe definirse en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-119">The RFC must be defined on the SAP system.</span></span> <span data-ttu-id="3e29b-120">Debe crear un módulo de función que define la solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-120">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="3e29b-121">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la definición de RFC en el sistema SAP para recuperar metadatos sobre la solicitud de cambio (tanto en tiempo de diseño y en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="3e29b-121">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design time and at run time).</span></span> <span data-ttu-id="3e29b-122">Para obtener más información, consulte [crear una solicitud de cambio en un sistema SAP](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="3e29b-122">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e29b-123">Debe definir la solicitud de cambio en el sistema SAP; Sin embargo implementa la solicitud de cambio en el código de cliente del adaptador.</span><span class="sxs-lookup"><span data-stu-id="3e29b-123">You must define the RFC on the SAP system; however you implement the RFC in your adapter client code.</span></span> <span data-ttu-id="3e29b-124">La solicitud de cambio debe definirse en el sistema SAP para que el adaptador puede recuperar metadatos para la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="3e29b-124">The RFC must be defined on the SAP system so that the adapter can retrieve metadata for the RFC.</span></span>  
  
 <span data-ttu-id="3e29b-125">El siguiente es un ejemplo del código fuente en el sistema SAP para una solicitud de cambio que agrega dos enteros y devuelve su resultado.</span><span class="sxs-lookup"><span data-stu-id="3e29b-125">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="3e29b-126">El código llama simplemente la solicitud de cambio a través de un destino especificado.</span><span class="sxs-lookup"><span data-stu-id="3e29b-126">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="3e29b-127">La implementación de la función se realiza mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] código de cliente.</span><span class="sxs-lookup"><span data-stu-id="3e29b-127">The implementation of the function is done by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] client code.</span></span>  
  
```  
FUNCTION Z_RFC_SAMPLE_ADD.  
*"---------------------------------------------------------------------*"*"Local interface:  
*"  IMPORTING  
*"     VALUE(X) TYPE  INT4  
*"     VALUE(Y) TYPE  INT4  
*"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
*"  EXPORTING  
*"     VALUE(RESULT) TYPE  INT4  
*"---------------------------------------------------------------------CALL FUNCTION 'Z_RFC_MKD_ADD' DESTINATION DEST  
  EXPORTING X = X  
            Y = Y  
  IMPORTING RESULT = RESULT.  
  
ENDFUNCTION.  
```  
  
## <a name="the-wcf-service-contract-for-an-rfc"></a><span data-ttu-id="3e29b-128">El contrato de servicio WCF para una solicitud de cambio</span><span class="sxs-lookup"><span data-stu-id="3e29b-128">The WCF Service Contract for an RFC</span></span>  
 <span data-ttu-id="3e29b-129">Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un contrato de servicio WCF para los documentos de RFC que se desea recibir desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-129">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the RFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="3e29b-130">Las secciones siguientes muestran las clases de código administrado e interfaces que se genera para la operación de Z_RFC_MKD_ADD.</span><span class="sxs-lookup"><span data-stu-id="3e29b-130">The following sections show the managed code classes and interfaces generated for the Z_RFC_MKD_ADD operation.</span></span>  
  
### <a name="the-rfc-interface-wcf-service-contract"></a><span data-ttu-id="3e29b-131">La interfaz de Rfc (contrato de servicio WCF)</span><span class="sxs-lookup"><span data-stu-id="3e29b-131">The Rfc Interface (WCF service contract)</span></span>  
 <span data-ttu-id="3e29b-132">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies todas las operaciones de RFC bajo un contrato de servicio único, "Rfc".</span><span class="sxs-lookup"><span data-stu-id="3e29b-132">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="3e29b-133">Esto significa que una única interfaz **Rfc**, se crea para todas las operaciones de RFC que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="3e29b-133">This means that a single interface, **Rfc**, is created for all of the RFC operations that you want to receive.</span></span> <span data-ttu-id="3e29b-134">Cada operación de RFC de destino se representa como un método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e29b-134">Each target RFC operation is represented as a method of this interface.</span></span> <span data-ttu-id="3e29b-135">Cada método toma un único parámetro, que representa el contrato de mensaje para el mensaje de solicitud de la operación y devuelve un objeto que representa el contrato de mensaje del mensaje de respuesta de la operación.</span><span class="sxs-lookup"><span data-stu-id="3e29b-135">Each method takes a single parameter, which represents the message contract for the request message of the operation, and returns an object, which represents the message contract of the response message of the operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a><span data-ttu-id="3e29b-136">La solicitud y los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="3e29b-136">The Request and Response Messages</span></span>  
 <span data-ttu-id="3e29b-137">Cada operación de RFC toma un parámetro que representa el mensaje de solicitud y devuelve un objeto que representa el mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3e29b-137">Each RFC operation takes a parameter that represents the request message and returns an object that represents the response message.</span></span> <span data-ttu-id="3e29b-138">Las propiedades del mensaje de solicitud contienen la importación y parámetros de CHANGING (entrada) de la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="3e29b-138">The properties of the request message contain the IMPORT and (input) CHANGING parameters of the RFC.</span></span> <span data-ttu-id="3e29b-139">Las propiedades del mensaje de respuesta contienen la exportación y (salida) cambiando parámetros para la operación.</span><span class="sxs-lookup"><span data-stu-id="3e29b-139">The properties of the response message contain the EXPORT and (output) CHANGING parameters for the operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDRequest {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public string DEST;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=1)]  
    public System.Nullable<int> X;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=2)]  
    public System.Nullable<int> Y;  
  
    public Z_RFC_MKD_ADDRequest() {  
    }  
  
    public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y) {  
        this.DEST = DEST;  
        this.X = X;  
        this.Y = Y;  
    }  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADDResponse", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDResponse {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public int RESULT;  
  
    public Z_RFC_MKD_ADDResponse() {  
    }  
  
    public Z_RFC_MKD_ADDResponse(int RESULT) {  
        this.RESULT = RESULT;  
    }  
}  
```  
  
### <a name="the-generated-wcf-service"></a><span data-ttu-id="3e29b-140">El servicio WCF generado</span><span class="sxs-lookup"><span data-stu-id="3e29b-140">The Generated WCF Service</span></span>  
 <span data-ttu-id="3e29b-141">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un servicio WCF que implementa el contrato de servicio WCF (**Rfc**).</span><span class="sxs-lookup"><span data-stu-id="3e29b-141">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a WCF service that implements the WCF service contract (**Rfc**).</span></span> <span data-ttu-id="3e29b-142">Los métodos de esta clase son auxiliares.</span><span class="sxs-lookup"><span data-stu-id="3e29b-142">The methods of this class are stubbed.</span></span> <span data-ttu-id="3e29b-143">Esta clase se genera en un archivo independiente.</span><span class="sxs-lookup"><span data-stu-id="3e29b-143">This class is generated in a separate file.</span></span> <span data-ttu-id="3e29b-144">Puede implementar el código directamente en los métodos de esta clase.</span><span class="sxs-lookup"><span data-stu-id="3e29b-144">You can implement your code directly in the methods of this class.</span></span>  
  
```  
namespace SAPBindingNamespace {  
  
    public class SAPBindingService : Rfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        public virtual Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="how-to-create-an-rfc-server-application"></a><span data-ttu-id="3e29b-145">Cómo crear una aplicación de servidor RFC</span><span class="sxs-lookup"><span data-stu-id="3e29b-145">How to Create an RFC Server Application</span></span>  
 <span data-ttu-id="3e29b-146">Para recibir las solicitudes de cambio desde el sistema SAP mediante el modelo de servicio WCF, puede seguir los pasos descritos en [información general sobre el modelo de servicio de WCF con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="3e29b-146">To receive RFCs from the SAP system by using the WCF service model, you can follow the steps in [Overview of the WCF Service Model with the SAP Adapter](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md).</span></span> <span data-ttu-id="3e29b-147">No olvide especificar 'Rfc' para el contrato de servicio cuando se agrega el punto de conexión de servicio (paso 6 del procedimiento para crear e implementar un servicio WCF).</span><span class="sxs-lookup"><span data-stu-id="3e29b-147">Be sure to specify 'Rfc' for the service contract when you add the service endpoint (step 6 of the procedure for creating and implementing a WCF service).</span></span>  
  
 <span data-ttu-id="3e29b-148">El código siguiente muestra un ejemplo completo de cómo recibir la Z_RFC_MKD_RFC desde un sistema SAP mediante el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e29b-148">The following code shows a complete example of how to receive the Z_RFC_MKD_RFC from an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="3e29b-149">Este RFC toma dos parámetros enteros y devuelve el resultado al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3e29b-149">This RFC takes two integer parameters and returns the result to the SAP system.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and SAP adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace SapRfcServerSM  
{  
    // Implement a WCF service callback class by sub-classing the generated service callback class (SAPBindingService).  
    // You must annotate this class with the InstanceContextMode.Single ServiceBehavior  
    // If you implement your code in SAPBindingService.cs be sure to annotate the SAPBindingService class  
    // The callback method should return a Z_RFC_MKD_ADDResponse to indicate successful processing  
    // or throw an exception to indicate an error.  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
    class RfcServerClass : SAPBindingNamespace.SAPBindingService  
    {  
  
        public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
        {  
            // If either parameter is null, throw an exception   
            if (request.X == null || request.Y == null)  
                throw new System.ArgumentNullException();  
  
            int result = (int) (request.X + request.Y);  
  
            Console.WriteLine("\nRfc Received");  
            Console.WriteLine("X =\t\t" + request.X.ToString());  
            Console.WriteLine("Y =\t\t" + request.Y.ToString());  
            Console.WriteLine("Result =\t" + result);  
            Console.WriteLine("\nHit <RETURN> to end");  
  
            return new Z_RFC_MKD_ADDResponse(result);  
        }  
  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Listener connection for the service URI -- the connection URI must contain credentials  
            Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/ADAPSAP47/00?ListenerGwServ=SAPGW00&ListenerGwHost=ADAPSAP47&ListenerProgramId=ADDER");  
  
            // The baseUri cannot contain userinfoparams or query_string parameters  
            Uri[] baseUri = new Uri[] { new Uri("sap://a/ADAPSAP47/00") };  
  
            Console.WriteLine("RFC server sample started");  
  
            // create service instance  
            RfcServerClass rfcServerInstance = new RfcServerClass();  
  
            try  
            {  
                Console.WriteLine("Initializing service host -- please wait");  
                // Create and initialize a service host  
                using (ServiceHost srvHost = new ServiceHost(rfcServerInstance, baseUri))  
                {  
  
                    // Add service endpoint   
                    // Specify AcceptCredentalsInUri=true for the binding  
                    // NOTE: The contract for the service endpoint is "Rfc".  
                    //       This is the generated WCF service callback interface (see SAPBindingInterface.cs).  
                    SAPBinding binding = new SAPBinding();  
                    binding.AcceptCredentialsInUri = true;  
                    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
                    srvHost.Open();  
  
                    Console.WriteLine("\nReady to receive Z_RFC_MKD_ADD RFC");  
                    Console.WriteLine("Hit <RETURN> to end");  
  
                    // Wait to receive request  
                    Console.ReadLine();  
                }  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e29b-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e29b-150">See Also</span></span>  
<span data-ttu-id="3e29b-151">[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="3e29b-151">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="3e29b-152">Esquemas de mensaje para las operaciones de RFC</span><span class="sxs-lookup"><span data-stu-id="3e29b-152">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)