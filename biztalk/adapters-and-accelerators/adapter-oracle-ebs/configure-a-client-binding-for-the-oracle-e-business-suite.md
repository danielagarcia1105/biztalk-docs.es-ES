---
title: Configurar un cliente de enlace de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dadf91973bdee181050f420ed611eb0c502fc988
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a><span data-ttu-id="e875b-102">Configurar a un cliente de enlace de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="e875b-102">Configure a client binding for the Oracle E-Business Suite</span></span>
<span data-ttu-id="e875b-103">Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e875b-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="e875b-104">Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace.</span><span class="sxs-lookup"><span data-stu-id="e875b-104">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="e875b-105">La dirección de punto de conexión debe contener un URI de conexión de Oracle E-Business Suite válido y el enlace debe ser una instancia de un enlace de Oracle E-Business Suite (**OracleEBSBinding**).</span><span class="sxs-lookup"><span data-stu-id="e875b-105">The endpoint address must contain a valid Oracle E-Business Suite connection URI, and the binding must be an instance of an Oracle E-Business Suite binding (**OracleEBSBinding**).</span></span> <span data-ttu-id="e875b-106">Para obtener más información sobre el URI de conexión de Oracle E-Business Suite, consulte [crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="e875b-106">For more information about the Oracle E-Business Suite connection URI, see [Create a Connection to the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).</span></span> <span data-ttu-id="e875b-107">Se recomienda que no especifique las credenciales de usuario como parte del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="e875b-107">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="e875b-108">Puede utilizar el **ClientCredentials** propiedad del cliente WCF, como se explica en este tema.</span><span class="sxs-lookup"><span data-stu-id="e875b-108">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="e875b-109">Puede especificar el enlace de Oracle E-Business Suite y la dirección del extremo en el código o en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e875b-109">You can specify the Oracle E-Business Suite binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="e875b-110">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e875b-110">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="e875b-111">Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta a Oracle E-Business Suite con la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e875b-111">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle E-Business Suite with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="e875b-112">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="e875b-112">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="e875b-113">El código siguiente muestra cómo crear un cliente de WCF mediante la especificación de la dirección de enlace y el punto de conexión en el código mediante el **ClientCredentials** propiedad del cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="e875b-113">The following code shows how to create a WCF client by specifying the binding and endpoint address in code using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="e875b-114">Especificar el enlace y dirección de punto de conexión en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e875b-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="e875b-115">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="e875b-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 <span data-ttu-id="e875b-116">El siguiente XML muestra el archivo de configuración creado para el **interfaz cliente** programa simultáneo por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e875b-116">The following XML shows the configuration file created for the **Customer Interface** concurrent program by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="e875b-117">Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e875b-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="e875b-118">Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e875b-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="e875b-119">Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de Oracle E-Business Suite de destino.</span><span class="sxs-lookup"><span data-stu-id="e875b-119">Each WCF client entry will have a unique name based on its binding configuration and target Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="e875b-120">Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="e875b-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="e875b-121">Estas entradas de configuración de enlace se denominará de la siguiente manera: OracleEBSBinding, OracleEBSBinding1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e875b-121">These binding configuration entries will be named in the following manner: OracleEBSBinding, OracleEBSBinding1, and so on.</span></span> <span data-ttu-id="e875b-122">Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.</span><span class="sxs-lookup"><span data-stu-id="e875b-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e875b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e875b-123">See Also</span></span>  
 [<span data-ttu-id="e875b-124">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="e875b-124">Develop Oracle E-Business Suite Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)