---
title: Seguro de programación con el adaptador de Oracle EBS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b494f8-cb21-45c2-9bb4-097ba59ec52c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eae7e2c1be56a886578f7bba83901f218c42b94e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972181"
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a><span data-ttu-id="e4d46-102">Programación segura con el adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="e4d46-102">Secure programming with the Oracle EBS adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="e4d46-103">¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="e4d46-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="e4d46-104">Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="e4d46-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the Oracle E-Business Suite.</span></span> <span data-ttu-id="e4d46-105">Debe hacerlo desde el **seguridad** ficha la **configurar el adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e4d46-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="e4d46-106">Escribiendo el Oracle credenciales desde el **seguridad** pestaña en lugar de directamente en el **configurar un URI** campo, se asegura de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d46-106">By entering the Oracle credentials from the **Security** tab instead of directly into the **Configure a URI** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="e4d46-107">Las credenciales no se mostrará en el **configurar un URI** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] donde cualquiera con acceso a la pantalla del equipo puede leer el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e4d46-107">The credentials will not be displayed in the **Configure a URI** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="e4d46-108">Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="e4d46-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="e4d46-109">Para obtener más información acerca de cómo generar un cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para Oracle E-Business Suite, consulte [obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e4d46-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the Oracle E-Business Suite, see [Get metadata for Oracle E-Business Suite operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="e4d46-110">¿Cuáles son los procedimientos recomendados para la configuración de credenciales en el código?</span><span class="sxs-lookup"><span data-stu-id="e4d46-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="e4d46-111"> proporciona el **ClientCredentials** clase que le ayudarán a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="e4d46-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="e4d46-112">Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma cualquier mecanismo de autenticación se especifica en la pila de canales del objeto y aplica el intercambio entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="e4d46-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="e4d46-113">Dado que el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] se hospeda en proceso con su aplicación de consumo, no es imprescindible usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que usa la aplicación de consumo.</span><span class="sxs-lookup"><span data-stu-id="e4d46-113">Because the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="e4d46-114">Sin embargo, se, considera recomendable hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e4d46-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="e4d46-115">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] fomenta el uso de la **ClientCredentials** clase.</span><span class="sxs-lookup"><span data-stu-id="e4d46-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] encourages the use of the **ClientCredentials** class.</span></span> <span data-ttu-id="e4d46-116">Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para la base de datos de Oracle en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="e4d46-116">This property specifies whether the adapter will accept the user name and password for the Oracle database in the connection URI.</span></span> <span data-ttu-id="e4d46-117">**AcceptCredentialsInUri** el valor predeterminado es **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales.</span><span class="sxs-lookup"><span data-stu-id="e4d46-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="e4d46-118">Puede establecer **AcceptCredentialsInUri** a **true** que proporcione las credenciales en la conexión URI, si es necesario en la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="e4d46-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI, if required in the client application.</span></span>  
  
 <span data-ttu-id="e4d46-119">El ejemplo siguiente muestra cómo usar el **credenciales** propiedad para establecer credenciales para Oracle E-Business Suite en un **ChannelFactory**.</span><span class="sxs-lookup"><span data-stu-id="e4d46-119">The following example shows how to use the **Credentials** property to set credentials for the Oracle E-Business Suite on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
OracleEBSBinding binding = new OracleEBSBinding();  
EndpointAddress address = new EndpointAddress("oracleebs://ebs-instance");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="e4d46-120">El ejemplo siguiente muestra cómo usar el **ClientCredentials** clase para establecer credenciales para Oracle E-Business Suite en un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="e4d46-120">The following example shows how to use the **ClientCredentials** class to set credentials for the Oracle E-Business Suite on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
ConcurrentPrograms_ARClient client =   
  new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="e4d46-121">¿Cómo proporcionar para el intercambio de datos más segura a través de los límites del proceso?</span><span class="sxs-lookup"><span data-stu-id="e4d46-121">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="e4d46-122">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa.</span><span class="sxs-lookup"><span data-stu-id="e4d46-122">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="e4d46-123">Dado que el adaptador se hospeda en proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4d46-123">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="e4d46-124">Sin embargo, si la aplicación o servicio envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e4d46-124">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="e4d46-125"> proporciona muchas opciones para ayudar a proteger los mensajes enviados entre clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="e4d46-125"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="e4d46-126">Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte "Protección de servicios y clientes" en [ http://go.microsoft.com/fwlink/?LinkId=89725 ](http://go.microsoft.com/fwlink/?LinkId=89725).</span><span class="sxs-lookup"><span data-stu-id="e4d46-126">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see "Securing Services and Clients" at [http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725).</span></span> <span data-ttu-id="e4d46-127">Para obtener información general sobre seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, vea "Seguridad de Windows Communication Foundation" en [ http://go.microsoft.com/fwlink/?LinkId=89726 ](http://go.microsoft.com/fwlink/?LinkId=89726).</span><span class="sxs-lookup"><span data-stu-id="e4d46-127">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see "Windows Communication Foundation Security" at [http://go.microsoft.com/fwlink/?LinkId=89726](http://go.microsoft.com/fwlink/?LinkId=89726).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d46-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4d46-128">See Also</span></span>  
 [<span data-ttu-id="e4d46-129">Proteger las aplicaciones de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="e4d46-129">Secure your Oracle EBS applications</span></span>](secure-your-oracle-ebs-applications.md)