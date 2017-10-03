---
title: Recibir llamadas de RFC de entrada en SAP mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving inbound RFC calls
- RFC calls, receiving inbound using the WCF service model
ms.assetid: 064d70d7-1603-467f-9aba-ecab78a567ff
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a415e3ab0ecbaab8778254d817241e5cafb61a92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a>Recibir llamadas de RFC de entrada en SAP mediante el modelo de servicio de WCF
La [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] puede actuar como un servidor RFC para recibir las solicitudes de cambio invocados por un sistema SAP.  
  
 Para recibir las RFC entrantes en el modelo de servicio WCF, debe:  
  
-   Asegúrese de que un destino RFC existe en el sistema SAP.  
  
-   Asegúrese de que la solicitud de cambio se define en el sistema SAP.  
  
-   Generar un contrato de servicio WCF (interfaz) para la operación de RFC de los metadatos expuestos por el adaptador. Para ello, use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe).  
  
-   Implementar un servicio WCF de esta interfaz. Los métodos del servicio WCF contienen la lógica necesaria para procesar la solicitud de cambio y devolver una respuesta al adaptador (y por lo tanto, el sistema SAP).  
  
-   Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  
  
 Las secciones siguientes muestran cómo recibir las solicitudes de cambio desde el sistema SAP mediante el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a>Cómo configurar el sistema de SAP para enviar una solicitud de cambio para el adaptador de SAP  
 Para poder enviar una solicitud de cambio del sistema SAP para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe asegurarse de que los siguientes son ciertas en el sistema SAP:  
  
-   Un destino RFC para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] debe existir. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se registra con un destino RFC para recibir las solicitudes de cambio desde el sistema SAP. Especifica los parámetros con el URI, como el Host de puerta de enlace de SAP y el servicio de puerta de enlace de SAP, el identificador de programa de SAP que utiliza el adaptador registrarse a sí mismo de la conexión de SAP. Para obtener información acerca de cómo configurar un destino RFC en SAP, consulte [crear una solicitud de cambio, el destino de RFC y enviar una solicitud de cambio de sistema SAP](creating-an-rfc-in-an-sap-system.md).  
  
-   La solicitud de cambio debe definirse en el sistema SAP. Debe crear un módulo de función que define la solicitud de cambio en el sistema SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la definición de RFC en el sistema SAP para recuperar metadatos sobre la solicitud de cambio (tanto en tiempo de diseño y en tiempo de ejecución). Para obtener más información, consulte [crear una solicitud de cambio en un sistema SAP](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).  
  
    > [!NOTE]
    >  Debe definir la solicitud de cambio en el sistema SAP; Sin embargo implementa la solicitud de cambio en el código de cliente del adaptador. La solicitud de cambio debe definirse en el sistema SAP para que el adaptador puede recuperar metadatos para la solicitud de cambio.  
  
 El siguiente es un ejemplo del código fuente en el sistema SAP para una solicitud de cambio que agrega dos enteros y devuelve su resultado. El código llama simplemente la solicitud de cambio a través de un destino especificado. La implementación de la función se realiza mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] código de cliente.  
  
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
  
## <a name="the-wcf-service-contract-for-an-rfc"></a>El contrato de servicio WCF para una solicitud de cambio  
 Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o los metadatos de herramienta de utilidad ServiceModel (svcutil.exe) para generar un contrato de servicio WCF para los documentos de RFC que se desea recibir desde el sistema SAP. Las secciones siguientes muestran las clases de código administrado e interfaces que se genera para la operación de Z_RFC_MKD_ADD.  
  
### <a name="the-rfc-interface-wcf-service-contract"></a>La interfaz de Rfc (contrato de servicio WCF)  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies todas las operaciones de RFC bajo un contrato de servicio único, "Rfc". Esto significa que una única interfaz **Rfc**, se crea para todas las operaciones de RFC que desea recibir. Cada operación de RFC de destino se representa como un método de esta interfaz. Cada método toma un único parámetro, que representa el contrato de mensaje para el mensaje de solicitud de la operación y devuelve un objeto que representa el contrato de mensaje del mensaje de respuesta de la operación.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a>La solicitud y los mensajes de respuesta  
 Cada operación de RFC toma un parámetro que representa el mensaje de solicitud y devuelve un objeto que representa el mensaje de respuesta. Las propiedades del mensaje de solicitud contienen la importación y parámetros de CHANGING (entrada) de la solicitud de cambio. Las propiedades del mensaje de respuesta contienen la exportación y (salida) cambiando parámetros para la operación.  
  
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
  
### <a name="the-generated-wcf-service"></a>El servicio WCF generado  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un servicio WCF que implementa el contrato de servicio WCF (**Rfc**). Los métodos de esta clase son auxiliares. Esta clase se genera en un archivo independiente. Puede implementar el código directamente en los métodos de esta clase.  
  
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
  
## <a name="how-to-create-an-rfc-server-application"></a>Cómo crear una aplicación de servidor RFC  
 Para recibir las solicitudes de cambio desde el sistema SAP mediante el modelo de servicio WCF, puede seguir los pasos descritos en [información general sobre el modelo de servicio de WCF con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md). No olvide especificar 'Rfc' para el contrato de servicio cuando se agrega el punto de conexión de servicio (paso 6 del procedimiento para crear e implementar un servicio WCF).  
  
 El código siguiente muestra un ejemplo completo de cómo recibir la Z_RFC_MKD_RFC desde un sistema SAP mediante el uso de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Este RFC toma dos parámetros enteros y devuelve el resultado al sistema SAP.  
  
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
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [Esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)