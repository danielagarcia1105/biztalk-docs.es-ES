---
title: Información general sobre el modelo de servicio WCF con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121b425abe1c7c34ba75e535799770031b931525
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997333"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="5b881-102">Información general sobre el modelo de servicio WCF con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="5b881-102">Overview of the WCF service model with the SQL adapter</span></span>
<span data-ttu-id="5b881-103">La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone una operación de SQL Server como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes a SQL Server operation as a WCF service.</span></span> <span data-ttu-id="5b881-104">Para llevar a cabo operaciones en los artefactos de SQL Server, por ejemplo, para invocar un procedimiento almacenado, invoca una operación en el adaptador, que, a su vez, realiza la operación en el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b881-104">To perform operations on SQL Server artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the SQL Server.</span></span> <span data-ttu-id="5b881-105">Por lo tanto, el código actúa como un cliente al servicio de WCF presentado por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5b881-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="5b881-106">En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="5b881-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="5b881-107">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y WCF proporcionan herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5b881-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="5b881-108">Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones expuestas en la interfaz de servicio.</span><span class="sxs-lookup"><span data-stu-id="5b881-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="5b881-109">Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="5b881-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="5b881-110">Para implementar un servicio para recibir operaciones de entrada desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], implemente la interfaz generada para las operaciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="5b881-110">To implement a service to receive inbound operations from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you implement the interface generated for the inbound operations.</span></span>  
  
 <span data-ttu-id="5b881-111">La siguiente sección explica cómo usar el modelo de servicio WCF para invocar operaciones con un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-111">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a><span data-ttu-id="5b881-112">Invocar operaciones en el servidor SQL Server con un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="5b881-112">Invoking Operations on the SQL Server with a WCF Client</span></span>  
 <span data-ttu-id="5b881-113">Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], primero debe generar una clase de cliente WCF para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="5b881-113">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="5b881-114">A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para llevar a cabo estas operaciones en el sistema de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b881-114">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the SQL Server system.</span></span> <span data-ttu-id="5b881-115">Esta sección proporciona un esquema de una aplicación de cliente de .NET adaptador típica aspecto.</span><span class="sxs-lookup"><span data-stu-id="5b881-115">This section provides an outline of how a typical .NET adapter client application looks like.</span></span> <span data-ttu-id="5b881-116">Una explicación detallada sobre cómo realizar distintas operaciones en la base de datos de SQL Server mediante el adaptador se proporciona en temas específicos.</span><span class="sxs-lookup"><span data-stu-id="5b881-116">Detailed explanations on how to perform different operations on the SQL Server database using the adapter are provided in specific topics.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a><span data-ttu-id="5b881-117">Para invocar operaciones en el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="5b881-117">To invoke operations on the SQL adapter</span></span>  
  
1. <span data-ttu-id="5b881-118">Generar un código de clase y la aplicación auxiliar de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-118">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="5b881-119">Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]generar una clase de cliente WCF dirigido a los artefactos de la base de datos de SQL Server con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="5b881-119">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]to generate a WCF client class targeted at the SQL Server database artifacts with which you want to work.</span></span> <span data-ttu-id="5b881-120">Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="5b881-120">For more information about how to generate a WCF client, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
2. <span data-ttu-id="5b881-121">Crear una instancia de cliente WCF y configurar al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-121">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="5b881-122">Configurar al cliente de WCF implica especificar el enlace y dirección de punto de conexión (conexión de URI) que utilizará el cliente.</span><span class="sxs-lookup"><span data-stu-id="5b881-122">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="5b881-123">Puede hacerlo imperativamente en código o mediante declaración en configuración.</span><span class="sxs-lookup"><span data-stu-id="5b881-123">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="5b881-124">El código siguiente crea un cliente WCF que tiene como destino el **seleccione** operación en el **empleado** tabla en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b881-124">The following code creates a WCF client that targets the **Select** operation on the **Employee** table in a SQL Server database.</span></span> <span data-ttu-id="5b881-125">También establece las credenciales de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b881-125">It also sets the credentials for the SQL Server database.</span></span> <span data-ttu-id="5b881-126">El cliente de WCF se inicializa a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="5b881-126">The WCF client is initialized from configuration.</span></span>  
  
   ```  
   TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="5b881-127">Puede especificar la dirección de enlace y el punto de conexión de cliente en el código o declárelo en el archivo de configuración app.config.</span><span class="sxs-lookup"><span data-stu-id="5b881-127">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="5b881-128">El fragmento de código anterior usa el último.</span><span class="sxs-lookup"><span data-stu-id="5b881-128">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="5b881-129">Para obtener más información sobre cómo usar ambos enfoques, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="5b881-129">For more information on how to use either approaches, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
3. <span data-ttu-id="5b881-130">Abra al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-130">Open the WCF client.</span></span>  
  
   ```  
   client.Open();  
   ```  
  
4. <span data-ttu-id="5b881-131">Invocar métodos en el cliente de WCF que creó en el paso anterior para realizar una operación Select en la base de datos SQL server.</span><span class="sxs-lookup"><span data-stu-id="5b881-131">Invoke methods on the WCF client created in preceding step to perform a Select operation on the SQL server database.</span></span> <span data-ttu-id="5b881-132">El código siguiente invoca el método Select del cliente WCF para invocar la instrucción SELECT en una tabla de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b881-132">The following code invokes the Select method of the WCF client to invoke the SELECT statement on a SQL Server database table.</span></span>  
  
   ```  
   client.Select("*", "where [Name] = ‘John Smith’");  
   ```  
  
5. <span data-ttu-id="5b881-133">Cierre al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="5b881-133">Close the WCF client.</span></span>  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="5b881-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b881-134">See Also</span></span>  
[<span data-ttu-id="5b881-135">Desarrollar aplicaciones de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="5b881-135">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)