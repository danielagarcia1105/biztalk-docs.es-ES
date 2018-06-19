---
title: Configurar un cliente WCF para un sistema Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, create a WCF client by specifying binding and endpoint address in a configuration file
- how to, create a WCF client by specifying binding and endpoint address in code
- WCF service model, configuring a WCF client for a Siebel system
ms.assetid: 6b4c5b06-d5ff-4dbf-8dc2-89c547a59864
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d122c3300f3c1e52194a10332fbb7fb6c45d81
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963610"
---
# <a name="configure-a-wcf-client-for-a-siebel-system"></a><span data-ttu-id="0f1bc-102">Configurar a un cliente WCF para un sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="0f1bc-102">Configure a WCF Client for a Siebel System</span></span>
<span data-ttu-id="0f1bc-103">Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f1bc-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="0f1bc-104">Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio WCF para la solución de Siebel artefactos](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="0f1bc-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes, see [Generate a WCF Client or a WCF service contract for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="0f1bc-105">Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="0f1bc-106">La dirección de punto de conexión debe contener una conexión válida de Siebel URI y el enlace debe ser una instancia de un enlace de Siebel (**SiebelBinding**).</span><span class="sxs-lookup"><span data-stu-id="0f1bc-106">The endpoint address must contain a valid Siebel connection URI, and the binding must be an instance of a Siebel Binding (**SiebelBinding**).</span></span> <span data-ttu-id="0f1bc-107">Para obtener más información sobre el URI de conexión de Siebel, consulte [conectar con el sistema Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0f1bc-107">For more information about the Siebel connection URI, see [Connect to the Siebel System in Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="0f1bc-108">Puede especificar el enlace de Siebel y la dirección del extremo en el código o en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-108">You can specify the Siebel Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="0f1bc-109">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="0f1bc-110">Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta al sistema Siebel con la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f1bc-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Siebel system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="0f1bc-111">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="0f1bc-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="0f1bc-112">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="0f1bc-113">Es recomendable para especificar las credenciales de Siebel mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-113">It is good practice to specify the Siebel credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by using a binding object and endpoint address  
SiebelBinding sblBinding = new SiebelBinding();  
EndpointAddress sblAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu");  
  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient(sblBinding, sblAddress);  
  
    client.ClientCredentials.UserName.UserName = "SADMIN";  
    client.ClientCredentials.UserName.Password = "SADMIN";  
  
    client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="0f1bc-114">Especificar el enlace y dirección de punto de conexión en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0f1bc-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="0f1bc-115">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by specifying the client endpoint information in app.config  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
client.ClientCredentials.UserName.UserName = "SADMIN";  
client.ClientCredentials.UserName.Password = "SADMIN";  
  
client.Open();  
```  
  
### <a name="the-appconfig-file"></a><span data-ttu-id="0f1bc-116">El archivo App.config</span><span class="sxs-lookup"><span data-stu-id="0f1bc-116">The App.config File</span></span>  
 <span data-ttu-id="0f1bc-117">El siguiente XML muestra el archivo de configuración creado para el servicio de negocio de marca de tiempo por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f1bc-117">The following XML shows the configuration file created for the TimeStamp business service by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="0f1bc-118">Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <siebelBinding>  
                <binding name="SiebelBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    enablePerformanceCounters="false" enableConnectionPooling="true"  
                    maxConnectionsPerSystem="5" idleConnectionTimeout="00:01:00"  
                    acceptCredentialsInUri="false" />  
            </siebelBinding>  
        </bindings>  
        <client>  
            <endpoint address="siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu"  
                binding="siebelBinding" bindingConfiguration="SiebelBinding"  
                contract="BusinessServices_TimeStamp_Operation" name="SiebelBinding_BusinessServices_TimeStamp_Operation" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="0f1bc-119">Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="0f1bc-120">Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y el artefacto de Siebel de destino; Por ejemplo, "SiebelBinding_BusinessServices_TimeStamp_Operation".</span><span class="sxs-lookup"><span data-stu-id="0f1bc-120">Each WCF client entry will have a unique name based on its binding configuration and target Siebel artifact; for example, " SiebelBinding_BusinessServices_TimeStamp_Operation ".</span></span> <span data-ttu-id="0f1bc-121">Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="0f1bc-122">Estas entradas de configuración de enlace se denominará de la siguiente manera: SiebelBinding, SiebelBinding1, SiebelBinding2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-122">These binding configuration entries will be named in the following manner: SiebelBinding, SiebelBinding1, SiebelBinding2, and so on.</span></span> <span data-ttu-id="0f1bc-123">Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f1bc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f1bc-124">See Also</span></span>  
 [<span data-ttu-id="0f1bc-125">Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="0f1bc-125">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)