---
title: Configurar un enlace para el sistema SAP del cliente | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proxy programming, creating a proxy
- creating a proxy
- how to, create a proxy
ms.assetid: bceef132-29ff-4207-a37d-bf94fab484dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75253251d18049363255f553ded833748e33875
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-sap-system"></a><span data-ttu-id="10f74-102">Configurar un enlace para el sistema SAP de cliente</span><span class="sxs-lookup"><span data-stu-id="10f74-102">Configure a client binding for the SAP system</span></span>
<span data-ttu-id="10f74-103">Una vez que haya generado la clase de cliente WCF, puede crear un cliente WCF (instancia) e invocar sus métodos para consumir el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10f74-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="10f74-104">Para obtener información sobre cómo generar el código de clase y la aplicación auxiliar de cliente WCF para las operaciones que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="10f74-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="10f74-105">Para crear al cliente de WCF, debe especificar una dirección de extremo y un enlace.</span><span class="sxs-lookup"><span data-stu-id="10f74-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="10f74-106">La dirección de punto de conexión debe contener un URI de conexión válida de SAP y el enlace debe ser una instancia de un enlace de SAP (**SAPBinding**).</span><span class="sxs-lookup"><span data-stu-id="10f74-106">The endpoint address must contain a valid SAP connection URI, and the binding must be an instance of an SAP Binding (**SAPBinding**).</span></span> <span data-ttu-id="10f74-107">Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="10f74-107">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="10f74-108">Puede especificar el enlace de SAP y la dirección del extremo en el código o en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="10f74-108">You can specify the SAP Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="10f74-109">Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar la clase de cliente WCF, también se crea un archivo de configuración (app.config) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="10f74-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="10f74-110">Este archivo contiene los valores de configuración que reflejan la conexión y propiedades de información de enlace (excepto las credenciales) que especificó cuando se conecta al sistema SAP con el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10f74-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SAP system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="10f74-111">Especificar el enlace y la dirección del extremo en el código</span><span class="sxs-lookup"><span data-stu-id="10f74-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="10f74-112">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y la dirección del extremo en el código.</span><span class="sxs-lookup"><span data-stu-id="10f74-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="10f74-113">Es recomendable para especificar las credenciales del sistema SAP mediante la **ClientCredentials** propiedad del cliente WCF, en lugar de en el URI proporcionado para la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="10f74-113">It is good practice to specify the SAP system credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by using a binding object and endpoint address  
SAPBinding sapBinding = new SAPBinding();  
EndpointAddress sapAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00");  
  
RfcClient rfcClient = new RfcClient(sapBinding, sapAddress);  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="10f74-114">Especificar el enlace y dirección de punto de conexión en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="10f74-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="10f74-115">El código siguiente muestra cómo crear a un cliente de WCF especificando el enlace y dirección de punto de conexión en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="10f74-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 <span data-ttu-id="10f74-116">El siguiente XML muestra el archivo de configuración creado para la tabla EMP por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10f74-116">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="10f74-117">Este archivo contiene la configuración de punto de conexión del cliente al que hace referencia en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="10f74-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" receiveIdocFormat="Typed"  
                    generateFlatFileCompatibleIdocSchema="true" maxConnectionsPerSystem="50"  
                    enableConnectionPooling="true" idleConnectionTimeout="00:15:00"  
                    flatFileSegmentIndicator="SegmentDefinition" enablePerformanceCounters="false"  
                    autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false" padReceivedIdocWithSpaces="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="Rfc"  
                name="SAPBinding_Rfc" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="10f74-118">Si un proyecto tiene más de un cliente WCF, habrá varios clientes entradas de punto de conexión definidas en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="10f74-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="10f74-119">Cada entrada de cliente WCF tendrá un nombre único basado en su configuración de enlace y los artefactos del sistema SAP de destino (por ejemplo, Rfc y Trfc); Por ejemplo, "SAPBinding_Rfc".</span><span class="sxs-lookup"><span data-stu-id="10f74-119">Each WCF client entry will have a unique name based on its binding configuration and target SAP system artifacts (such as Rfc and Trfc); for example, "SAPBinding_Rfc".</span></span> <span data-ttu-id="10f74-120">Si se conectan a varias veces para crear los clientes de WCF en el proyecto, varias entradas de configuración de enlace se creará, uno para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="10f74-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="10f74-121">Estas entradas de configuración de enlace se denominará de la siguiente manera: SAPBinding1, SAPBinding2, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="10f74-121">These binding configuration entries will be named in the following manner: SAPBinding1, SAPBinding2, and so on.</span></span> <span data-ttu-id="10f74-122">Cada entrada de punto de conexión de cliente creado durante una conexión de acceso hará referencia a la entrada de enlace creada durante esa conexión.</span><span class="sxs-lookup"><span data-stu-id="10f74-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10f74-123">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Emerge artefactos SAP diferentes del mismo tipo (por ejemplo, RFC, TRFC y IDOC) como operaciones diferentes del mismo contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="10f74-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces different SAP artifacts of the same type (such as RFC, TRFC, and IDOC) as different operations of the same service contract.</span></span> <span data-ttu-id="10f74-124">Por ejemplo, dos RFC diferentes, RFC_EXAMPLE_A y RFC_EXAMPLE_B, ambos se expone en el mismo contrato de servicio ("Rfc").</span><span class="sxs-lookup"><span data-stu-id="10f74-124">For example, two different RFCs, RFC_EXAMPLE_A and RFC_EXAMPLE_B, will both be surfaced under the same service contract ("Rfc").</span></span> <span data-ttu-id="10f74-125">Esto significa que ambos RFC invocará la misma clase de cliente WCF, **RfcClient**, y que se va a declarar los parámetros para ambos RFC en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="10f74-125">This means that both RFCs will be invoked by the same WCF client class, **RfcClient**, and that the parameters for both RFCs will be declared in the same namespace.</span></span> <span data-ttu-id="10f74-126">Por lo tanto, debe generar el cliente WCF para ambos RFC durante el mismo [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] sesión (conexión) para evitar experimentando una colisión de espacio de nombres al compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="10f74-126">Therefore, you must generate the WCF client for both RFCs during the same [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] session (connection) to avoid experiencing a namespace collision when you build your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f74-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="10f74-127">See Also</span></span>  
<span data-ttu-id="10f74-128">[Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="10f74-128">[Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="10f74-129">[Generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="10f74-129">[Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span></span>  
 [<span data-ttu-id="10f74-130">Crear el URI de conexión de sistema SAP</span><span class="sxs-lookup"><span data-stu-id="10f74-130">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)