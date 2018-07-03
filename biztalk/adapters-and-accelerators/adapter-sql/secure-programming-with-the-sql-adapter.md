---
title: Programación segura con el adaptador de SQL | Microsoft Docs
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
ms.openlocfilehash: 8e0c5e68eb1f07067a43995693cbb43bdcad76a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002389"
---
# <a name="secure-programming-with-the-sql-adapter"></a><span data-ttu-id="03847-102">Programación segura con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="03847-102">Secure programming with the SQL adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="03847-103">¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?</span><span class="sxs-lookup"><span data-stu-id="03847-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="03847-104">Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, es posible que deba proporcionar un nombre de usuario y contraseña para la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="03847-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you might have to supply a user name and password for the SQL Server database.</span></span> <span data-ttu-id="03847-105">Debe escribir las credenciales de la **seguridad** ficha la **configurar el adaptador** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="03847-105">You must enter credentials from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="03847-106">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no proporciona una opción para especificar el nombre de usuario y la contraseña como parte de la URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="03847-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not provide an option to specify the user name and password as part of the connection URI.</span></span> <span data-ttu-id="03847-107">Esto garantiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03847-107">This ensures the following:</span></span>  
  
- <span data-ttu-id="03847-108">Las credenciales no se mostrará en el **configurar un URI** campo de la **complemento Add Adapter Service Reference** donde cualquiera con acceso a la pantalla del equipo puede leer el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="03847-108">The credentials will not be displayed in the **Configure a URI** field of the **Add Adapter Service Reference Plug-in** dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="03847-109">Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="03847-109">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="03847-110">Para obtener más información acerca de cómo generar un cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para la base de datos de SQL Server, vea [obtener metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="03847-110">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SQL Server database, see [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="03847-111">¿Cuáles son los procedimientos recomendados para la configuración de credenciales en el código?</span><span class="sxs-lookup"><span data-stu-id="03847-111">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="03847-112"> proporciona el **ClientCredentials** clase que le ayudarán a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="03847-112"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="03847-113">Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma cualquier mecanismo de autenticación se especifica en la pila de canales del objeto y aplica el intercambio entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="03847-113">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="03847-114">Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con su aplicación de consumo, no es imprescindible usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que usa la aplicación de consumo.</span><span class="sxs-lookup"><span data-stu-id="03847-114">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="03847-115">Sin embargo, se, considera recomendable hacerlo.</span><span class="sxs-lookup"><span data-stu-id="03847-115">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="03847-116">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requiere el uso de la **ClientCredentials** clase para pasar mediante programación las credenciales.</span><span class="sxs-lookup"><span data-stu-id="03847-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the use of the **ClientCredentials** class for programmatically passing credentials.</span></span> <span data-ttu-id="03847-117">El **AcceptCredentialsInUri** enlaza la propiedad se pasa por alto el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para evitar la transferencia de credenciales en el URI.</span><span class="sxs-lookup"><span data-stu-id="03847-117">The **AcceptCredentialsInUri** binding property is ignored by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to prevent passing credentials in the URI.</span></span>  
  
 <span data-ttu-id="03847-118">El ejemplo siguiente muestra cómo usar el **credenciales** propiedad para establecer credenciales para la base de datos de SQL Server en un **ChannelFactory**.</span><span class="sxs-lookup"><span data-stu-id="03847-118">The following example shows how to use the **Credentials** property to set credentials for the SQL Server database on a **ChannelFactory**.</span></span>  
  
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
  
 <span data-ttu-id="03847-119">El ejemplo siguiente muestra cómo usar el **ClientCredentials** clase para establecer las credenciales para la base de datos de SQL Server en un cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="03847-119">The following example shows how to use the **ClientCredentials** class to set credentials for the SQL Server database on a WCF client.</span></span>  
  
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
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="03847-120">¿Cómo proporcionar para el intercambio de datos más segura a través de los límites del proceso?</span><span class="sxs-lookup"><span data-stu-id="03847-120">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="03847-121">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa.</span><span class="sxs-lookup"><span data-stu-id="03847-121">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="03847-122">Dado que el adaptador se hospeda en proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03847-122">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="03847-123">Sin embargo, si la aplicación o servicio envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="03847-123">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="03847-124"> proporciona muchas opciones para ayudar a proteger los mensajes enviados entre clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="03847-124"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="03847-125">Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [proteger servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx).</span><span class="sxs-lookup"><span data-stu-id="03847-125">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="03847-126">Para obtener información general sobre seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [seguridad de Windows Communication Foundation](https://msdn.microsoft.com/library/ms732362.aspx).</span><span class="sxs-lookup"><span data-stu-id="03847-126">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03847-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="03847-127">See Also</span></span>  
[<span data-ttu-id="03847-128">Proteger las aplicaciones SQL</span><span class="sxs-lookup"><span data-stu-id="03847-128">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[<span data-ttu-id="03847-129">Procedimientos recomendados para proteger el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="03847-129">Best practices to secure the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)