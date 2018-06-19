---
title: Programación segura con el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44886b490ce63e8c34e1a5bdb41554c96a0873ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224028"
---
# <a name="secure-programming-with-the-sql-adapter"></a><span data-ttu-id="2119d-102">Programación segura con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="2119d-102">Secure programming with the SQL adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="2119d-103">¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="2119d-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="2119d-104">Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, es posible que deba proporcionar un nombre de usuario y contraseña para la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2119d-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you might have to supply a user name and password for the SQL Server database.</span></span> <span data-ttu-id="2119d-105">Debe escribir las credenciales de la **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2119d-105">You must enter credentials from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="2119d-106">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no proporciona una opción para especificar el nombre de usuario y la contraseña como parte del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="2119d-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not provide an option to specify the user name and password as part of the connection URI.</span></span> <span data-ttu-id="2119d-107">Esto garantiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2119d-107">This ensures the following:</span></span>  
  
-   <span data-ttu-id="2119d-108">Las credenciales no se mostrará en el **configurar un URI** campo de la **agregar un complemento de referencia de servicio de adaptador** cuadro de diálogo donde cualquier persona con acceso a la pantalla del equipo puede leer.</span><span class="sxs-lookup"><span data-stu-id="2119d-108">The credentials will not be displayed in the **Configure a URI** field of the **Add Adapter Service Reference Plug-in** dialog box where anyone with access to your computer screen can read them.</span></span>  
  
-   <span data-ttu-id="2119d-109">Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="2119d-109">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="2119d-110">Para obtener más información acerca de cómo generar un cliente de WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de escribir un nombre de usuario y una contraseña para la base de datos de SQL Server, consulte [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="2119d-110">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SQL Server database, see [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="2119d-111">¿Cuáles son las prácticas recomendadas para establecer credenciales en el código?</span><span class="sxs-lookup"><span data-stu-id="2119d-111">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="2119d-112">proporciona el **ClientCredentials** clase para ayudarle a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="2119d-112"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="2119d-113">Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma los mecanismos de autenticación se especifican en la pila de canales de ese objeto y aplica en el intercambio entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="2119d-113">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="2119d-114">Dado que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con su aplicación que consume, que no es necesario usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que utiliza la aplicación que consume.</span><span class="sxs-lookup"><span data-stu-id="2119d-114">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="2119d-115">Sin embargo, se, considera recomendable hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2119d-115">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="2119d-116">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requiere el uso de la **ClientCredentials** clase para pasar mediante programación las credenciales.</span><span class="sxs-lookup"><span data-stu-id="2119d-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the use of the **ClientCredentials** class for programmatically passing credentials.</span></span> <span data-ttu-id="2119d-117">El **AcceptCredentialsInUri** propiedad de enlace pasa por alto el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para evitar la transferencia de credenciales en el URI.</span><span class="sxs-lookup"><span data-stu-id="2119d-117">The **AcceptCredentialsInUri** binding property is ignored by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to prevent passing credentials in the URI.</span></span>  
  
 <span data-ttu-id="2119d-118">En el ejemplo siguiente se muestra cómo utilizar el **credenciales** propiedad para establecer credenciales para la base de datos de SQL Server en un **ChannelFactory**.</span><span class="sxs-lookup"><span data-stu-id="2119d-118">The following example shows how to use the **Credentials** property to set credentials for the SQL Server database on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="2119d-119">En el ejemplo siguiente se muestra cómo utilizar el **ClientCredentials** clase para establecer credenciales para la base de datos de SQL Server en un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="2119d-119">The following example shows how to use the **ClientCredentials** class to set credentials for the SQL Server database on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="2119d-120">¿Cómo puedo proporcionan para el intercambio de datos más segura a través de límites de proceso?</span><span class="sxs-lookup"><span data-stu-id="2119d-120">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="2119d-121">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa.</span><span class="sxs-lookup"><span data-stu-id="2119d-121">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="2119d-122">Dado que el adaptador está alojado en el proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2119d-122">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="2119d-123">Sin embargo, si la aplicación o servicio usado envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2119d-123">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="2119d-124">proporciona muchas opciones para ayudar a proteger los mensajes enviados entre los clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="2119d-124"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="2119d-125">Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre los clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [protección de servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx).</span><span class="sxs-lookup"><span data-stu-id="2119d-125">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="2119d-126">Para obtener más información general acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span><span class="sxs-lookup"><span data-stu-id="2119d-126">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2119d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2119d-127">See Also</span></span>  
[<span data-ttu-id="2119d-128">Proteger las aplicaciones de SQL</span><span class="sxs-lookup"><span data-stu-id="2119d-128">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[<span data-ttu-id="2119d-129">Prácticas recomendadas para proteger el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="2119d-129">Best practices to secure the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)