---
title: Programación segura con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security considerations, when programming on the adapter
- credentials, best practices for setting in code
- credentials, protecting when using the Add Adapter Service Reference Visual Studio Plug-in
- security, best practices for setting credentials in code
ms.assetid: 8c2b6b36-7bd9-4678-a9c2-450e818f607a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e7c96feecec12fa3962982faf81311cc9162e09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986973"
---
# <a name="secure-programming-with-the-siebel-adapter"></a><span data-ttu-id="98798-102">Programación segura con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="98798-102">Secure programming with the Siebel adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="98798-103">¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="98798-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="98798-104">Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="98798-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the Siebel system.</span></span> <span data-ttu-id="98798-105">Debe hacerlo desde el **seguridad** ficha la **configurar el adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="98798-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="98798-106">Escribiendo el Siebel credenciales desde el **seguridad** pestaña en lugar de directamente en el **Uri** campo, se asegura de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98798-106">By entering the Siebel credentials from the **Security** tab instead of directly into the **Uri** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="98798-107">Las credenciales no se mostrará en el **Uri** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] donde cualquiera con acceso a la pantalla del equipo puede leer el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="98798-107">The credentials will not be displayed in the **Uri** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="98798-108">Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="98798-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="98798-109">Para obtener más información acerca de cómo generar un cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para el sistema de Siebel, consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="98798-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the Siebel system, see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="98798-110">¿Cuáles son los procedimientos recomendados para la configuración de credenciales en el código?</span><span class="sxs-lookup"><span data-stu-id="98798-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="98798-111"> proporciona el **ClientCredentials** clase que le ayudarán a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="98798-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="98798-112">Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma cualquier mecanismo de autenticación se especifica en la pila de canales del objeto y aplica el intercambio entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="98798-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="98798-113">Dado que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se hospeda en proceso con su aplicación de consumo, no es imprescindible usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que usa la aplicación de consumo.</span><span class="sxs-lookup"><span data-stu-id="98798-113">Because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="98798-114">Sin embargo, se, considera recomendable hacerlo.</span><span class="sxs-lookup"><span data-stu-id="98798-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="98798-115">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] fomenta el uso de la **ClientCredentials** clase a través de la **AcceptCredentialsInUri** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="98798-115">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] encourages the use of the **ClientCredentials** class through the **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="98798-116">Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para el sistema Siebel en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="98798-116">This property specifies whether the adapter will accept the user name and password for the Siebel system in the connection URI.</span></span> <span data-ttu-id="98798-117">**AcceptCredentialsInUri** el valor predeterminado es **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales.</span><span class="sxs-lookup"><span data-stu-id="98798-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="98798-118">Puede establecer **AcceptCredentialsInUri** a **true** que proporcione las credenciales en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="98798-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI.</span></span> <span data-ttu-id="98798-119">De hecho, debe hacerlo en ciertos casos; Por ejemplo, cuando se usa ServiceModel Metadata Utility Tool (svcutil.exe) para generar una clase de cliente WCF para artefactos del sistema de Siebel.</span><span class="sxs-lookup"><span data-stu-id="98798-119">In fact, you must do this in certain cases; for example, when you use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class for Siebel system artifacts.</span></span>  
  
 <span data-ttu-id="98798-120">El ejemplo siguiente muestra cómo usar el **credenciales** clase para establecer credenciales para el sistema Siebel en un **ChannelFactory**.</span><span class="sxs-lookup"><span data-stu-id="98798-120">The following example shows how to use the **Credentials** class to set credentials for the Siebel system on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
SiebelBinding binding = new SiebelBinding();  
EndpointAddress endpointAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=entserver&Language=enu ");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="98798-121">El ejemplo siguiente muestra cómo usar el **ClientCredentials** clase para establecer credenciales para el sistema Siebel en un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="98798-121">The following example shows how to use the **ClientCredentials** class to set credentials for the Siebel system on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
BusinessObjects_Account_Account_OperationClient accountAccountClient = new BusinessObjects_Account_Account_OperationClient ("SiebelBinding_BusinessObjects_Account_Account_Operation");  
  
// Set user name and password  
accountAccountClient.ClientCredentials.UserName.UserName = "YourUserName";  
accountAccountClient.ClientCredentials.UserName.Password = "YourPassword";  
  
// Open the client  
accountAccountClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="98798-122">¿Cómo proporcionar para el intercambio de datos más segura a través de los límites del proceso?</span><span class="sxs-lookup"><span data-stu-id="98798-122">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="98798-123">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa.</span><span class="sxs-lookup"><span data-stu-id="98798-123">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="98798-124">Dado que el adaptador se hospeda en proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98798-124">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="98798-125">Sin embargo, si la aplicación o servicio envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="98798-125">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="98798-126"> proporciona muchas opciones para ayudar a proteger los mensajes enviados entre clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="98798-126"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="98798-127">Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [proteger servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx).</span><span class="sxs-lookup"><span data-stu-id="98798-127">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="98798-128">Para obtener información general sobre seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [seguridad de Windows Communication Foundation](https://msdn.microsoft.com/library/ms732362.aspx).</span><span class="sxs-lookup"><span data-stu-id="98798-128">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="98798-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="98798-129">See Also</span></span>  
 [<span data-ttu-id="98798-130">Proteger las aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="98798-130">Secure your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
[<span data-ttu-id="98798-131">Procedimientos recomendados para proteger el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="98798-131">Best practices to secure the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)