---
title: Utilizar un comportamiento de servicio para especificar las credenciales con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b203cfa-6331-4498-b656-8cd8339f8613
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc494e55aee70a9a441eccbe056f4651448752d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e3ac4-102">Utilizar un comportamiento de servicio para especificar las credenciales con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e3ac4-102">Use a service behavior to enter credentials with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="e3ac4-103">En muchas ocasiones, los consumidores de adaptadores se requerirá para pasar credenciales a la línea de destino del sistema de negocio.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-103">Many times, adapter consumers will be required to pass credentials to the target line of business system.</span></span> <span data-ttu-id="e3ac4-104">Para proporcionar esta funcionalidad, debe proporcionar un comportamiento de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-104">To provide this functionality, you will need to provide a WCF service behavior.</span></span>  
  
 <span data-ttu-id="e3ac4-105">Ejemplo de código siguiente muestra cómo derivar un comportamiento de servicio.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-105">The following example code demonstrates how to derive a service behavior.</span></span> <span data-ttu-id="e3ac4-106">Delega las credenciales obtenidas del consumidor del adaptador al adaptador.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-106">It delegates the credentials obtained from the consumer of the adapter to the adapter.</span></span> <span data-ttu-id="e3ac4-107">A continuación, el adaptador debe usar protocolos de línea de negocio para autenticar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-107">The adapter then must use line-of-business protocols to authenticate the credentials.</span></span> <span data-ttu-id="e3ac4-108">Una vez que se autentican las credenciales, puede iniciar el servicio de escucha de eventos de entrada de la aplicación de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-108">Once the credentials are authenticated, the service can start listening for incoming events from the line of business application.</span></span>  
  
```  
/// <summary>  
/// This class derives from a WCF service behavior.  It is used in the inbound scenario  
/// for the Inbound Service to pass the line-of-business credentials to the adapter using  
/// WCF ClientCredentials class.  
/// </summary>  
public class InboundClientCredentialsServiceBehavior : ClientCredentials, IServiceBehavior  
{  
    public InboundClientCredentialsServiceBehavior() { }  
  
    public InboundClientCredentialsServiceBehavior(InboundClientCredentialsServiceBehavior other)  
         : base(other)  
    {  
    }  
  
    #region IServiceBehavior Members  
  
    public void AddBindingParameters(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
        bindingParameters.Add(this);  
    }  
  
    public void ApplyDispatchBehavior(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    public void Validate(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    #endregion  
  
    protected override ClientCredentials CloneCore()  
    {  
        return new InboundClientCredentialsServiceBehavior(this);  
    }  
}  
```  
  
 <span data-ttu-id="e3ac4-109">Ejemplo de código siguiente muestra cómo utilizar el comportamiento del servicio para pasar las credenciales para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="e3ac4-109">The following example code shows how to use the service behavior to pass credentials to the adapter.</span></span>  
  
```  
// Create a ServiceHost for the EchoServiceImpl type  
// and use the base address from app.config  
ServiceHost host = new ServiceHost(typeof(EchoServiceImpl));  
  
// Set service behavior to pass the line-of-business credentials.  
InboundClientCredentialsServiceBehavior credentialsBehavior = new InboundClientCredentialsServiceBehavior();  
credentialsBehavior.UserName.UserName = "username";  
credentialsBehavior.UserName.Password = "****";  
host.Description.Behaviors.Add(credentialsBehavior);  
  
// Open the ServiceHost to start listening for messages  
host.Open();  
  
Console.WriteLine("The service is ready.");  
Console.WriteLine("Press <ENTER> to terminate service.");  
Console.ReadLine();  
  
// Close the ServiceHost  
host.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3ac4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3ac4-110">See Also</span></span>  
 [<span data-ttu-id="e3ac4-111">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e3ac4-111">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)