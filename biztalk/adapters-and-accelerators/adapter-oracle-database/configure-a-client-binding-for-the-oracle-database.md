---
title: Configurar un cliente de enlace de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- client binding, specifying in code
- WCF client, creating
- client binding, specifying in configuration file
ms.assetid: f18c7296-c28a-4dec-9514-5299c8c2dffe
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de5eeb9a7b0022ce4da5f56591e863f48bd0b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214612"
---
# <a name="configure-a-client-binding-for-the-oracle-database"></a><span data-ttu-id="67aa6-102">Configurar a un cliente de enlace de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="67aa6-102">Configure a client binding for the Oracle Database</span></span>
<span data-ttu-id="67aa6-103">Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67aa6-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="67aa6-104">Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio de WCF para artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="67aa6-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes, see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="67aa6-105">Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace.</span><span class="sxs-lookup"><span data-stu-id="67aa6-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="67aa6-106">La dirección de punto de conexión debe contener un URI de conexión de Oracle válido y el enlace debe ser una instancia de un enlace de la base de datos de Oracle (**OracleDBBinding**).</span><span class="sxs-lookup"><span data-stu-id="67aa6-106">The endpoint address must contain a valid Oracle connection URI, and the binding must be an instance of an Oracle DB Binding (**OracleDBBinding**).</span></span> <span data-ttu-id="67aa6-107">Para obtener más información sobre el URI de conexión de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="67aa6-107">For more information about the Oracle connection URI, see [Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span> <span data-ttu-id="67aa6-108">Se recomienda que no especifique las credenciales de usuario como parte del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="67aa6-108">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="67aa6-109">Puede utilizar el **ClientCredentials** propiedad del cliente WCF, como se explica en este tema.</span><span class="sxs-lookup"><span data-stu-id="67aa6-109">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="67aa6-110">Puede especificar el enlace de la base de datos de Oracle y la dirección del extremo en el código o en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="67aa6-110">You can specify the Oracle DB Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="67aa6-111">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="67aa6-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="67aa6-112">Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta a la base de datos de Oracle con el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67aa6-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="67aa6-113">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="67aa6-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="67aa6-114">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código.</span><span class="sxs-lookup"><span data-stu-id="67aa6-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="67aa6-115">Es recomendable para especificar las credenciales de Oracle mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="67aa6-115">It is good practice to specify the Oracle credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by using a binding object and endpoint address  
OracleDBBinding odbBinding = new OracleDBBinding();  
EndpointAddress odbAddress = new EndpointAddress("OracleDb://ADAPTER");  
  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient(odbBinding, odbAddress);  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="67aa6-116">Especificar el enlace y dirección de punto de conexión en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="67aa6-116">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="67aa6-117">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="67aa6-117">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 <span data-ttu-id="67aa6-118">El siguiente XML muestra el archivo de configuración creado para la tabla EMP por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67aa6-118">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="67aa6-119">Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="67aa6-119">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00"  
                    dataFetchSize="65536" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" longDatatypeColumnSize="32767" pollingStatement=""  
                    postPollStatement="" pollingInterval="500" useOracleConnectionPool="false"  
                    minPoolSize="1" maxPoolSize="100" incrPoolSize="5" decrPoolSize="1"  
                    connectionLifetime="0" transactionIsolationLevel="ReadCommitted"  
                    enablePerformanceCounters="false" acceptCredentialsInUri="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="SCOTTTableEMP"  
                name="OracleDBBinding_SCOTT.Table.EMP" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="67aa6-120">Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="67aa6-120">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="67aa6-121">Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de base de datos de Oracle de destino; Por ejemplo, "OracleDBBinding_SCOTT. Table.EMP".</span><span class="sxs-lookup"><span data-stu-id="67aa6-121">Each WCF client entry will have a unique name based on its binding configuration and target Oracle database artifact; for example, "OracleDBBinding_SCOTT.Table.EMP".</span></span> <span data-ttu-id="67aa6-122">Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="67aa6-122">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="67aa6-123">Estas entradas de configuración de enlace se denominará de la siguiente manera: OracleDBBinding1, OracleDBBinding2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="67aa6-123">These binding configuration entries will be named in the following manner: OracleDBBinding1, OracleDBBinding2, and so on.</span></span> <span data-ttu-id="67aa6-124">Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.</span><span class="sxs-lookup"><span data-stu-id="67aa6-124">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67aa6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="67aa6-125">See Also</span></span>  
 <span data-ttu-id="67aa6-126">[Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="67aa6-126">[Develop Oracle Database Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="67aa6-127">[Generar un cliente WCF o un contrato de servicio WCF para los artefactos de solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="67aa6-127">[Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span></span>  
 <span data-ttu-id="67aa6-128">[Crear el URI de conexión de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span><span class="sxs-lookup"><span data-stu-id="67aa6-128">[Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span></span>  
 [<span data-ttu-id="67aa6-129">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="67aa6-129">Develop Oracle Database Applications by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)