---
title: Configurar un enlace de cliente para el adaptador de SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 146e6f51-e33b-45be-a302-8c9250e79501
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 947666ce63160425896564b20e91bd1fd70c95a9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configure-a-client-binding-for-the-sql-adapter"></a><span data-ttu-id="2ecdc-102">Configurar un enlace de cliente para el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="2ecdc-102">Configure a Client Binding for the SQL Adapter</span></span>
<span data-ttu-id="2ecdc-103">Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecdc-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="2ecdc-104">Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="2ecdc-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
 <span data-ttu-id="2ecdc-105">Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="2ecdc-106">La dirección de punto de conexión debe contener un URI de conexión de SQL válido y el enlace debe ser una instancia de un enlace de SQL (**sqlBinding**).</span><span class="sxs-lookup"><span data-stu-id="2ecdc-106">The endpoint address must contain a valid SQL connection URI, and the binding must be an instance of a SQL Binding (**sqlBinding**).</span></span> <span data-ttu-id="2ecdc-107">Para obtener más información sobre el URI de conexión de SQL, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="2ecdc-107">For more information about the SQL connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> <span data-ttu-id="2ecdc-108">Debe especificar las credenciales de usuario como parte del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-108">You must specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="2ecdc-109">Puede usar el **ClientCredentials** propiedad del cliente WCF, como se explica en este tema.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-109">You may use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="2ecdc-110">Puede especificar el enlace de SQL y la dirección del extremo en el código o en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-110">You can specify the SQL binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="2ecdc-111">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="2ecdc-112">Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta a la base de datos SQL con el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecdc-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SQL database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="2ecdc-113">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="2ecdc-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="2ecdc-114">El código siguiente muestra cómo crear un cliente de WCF mediante la especificación de la dirección de enlace y el punto de conexión en el código mediante el uso de la **ClientCredentials** propiedad del cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code by using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="2ecdc-115">Especificar el enlace y dirección de punto de conexión en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="2ecdc-115">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="2ecdc-116">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-116">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 <span data-ttu-id="2ecdc-117">El siguiente XML muestra el archivo de configuración creado para la tabla Customer por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecdc-117">The following XML shows the configuration file created for the Customer table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2ecdc-118">Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://<sql_server_name>//<database_name>?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="TableOp_dbo_Customer"  
                name="SqlAdapterBinding_TableOp_dbo_Customer" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2ecdc-119">Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="2ecdc-120">Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de SQL Server de destino; Por ejemplo, "`SqlAdapterBinding_TableOp_dbo_Customer`".</span><span class="sxs-lookup"><span data-stu-id="2ecdc-120">Each WCF client entry will have a unique name based on its binding configuration and target SQL Server artifact; for example, "`SqlAdapterBinding_TableOp_dbo_Customer`".</span></span> <span data-ttu-id="2ecdc-121">Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="2ecdc-122">Estas entradas de configuración de enlace se denominará de la siguiente manera: SqlAdapterBinding, SqlAdapterBinding1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-122">These binding configuration entries will be named in the following manner: SqlAdapterBinding, SqlAdapterBinding1, and so on.</span></span> <span data-ttu-id="2ecdc-123">Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.</span><span class="sxs-lookup"><span data-stu-id="2ecdc-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ecdc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ecdc-124">See Also</span></span>  
<span data-ttu-id="2ecdc-125">[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="2ecdc-125">[Develop SQL applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="2ecdc-126">[Generar un cliente de WCF o un contrato de servicio WCF de artefactos SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="2ecdc-126">[Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span></span>  
[<span data-ttu-id="2ecdc-127">Crear el URI de conexión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ecdc-127">Create the SQL Server connection URI</span></span>](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)