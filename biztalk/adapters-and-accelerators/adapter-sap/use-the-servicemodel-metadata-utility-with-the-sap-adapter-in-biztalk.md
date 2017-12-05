---
title: Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
description: "Utilizar svcutil.exe para un enlace no predeterminado, o para crear una clase de cliente de WCF o el contrato de servicio WCF con el adaptador SAP - módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4612db6e3cde4e46385b1c5d1810fbb00eb70
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="c3a10-103">Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="c3a10-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="c3a10-104">Puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o un contrato de servicio WCF (interfaz) para las operaciones que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone.</span><span class="sxs-lookup"><span data-stu-id="c3a10-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes.</span></span> <span data-ttu-id="c3a10-105">Después de ejecutar svcutil.exe para generar una clase de cliente WCF o un contrato de servicio WCF, puede incluir el archivo generado en el código y crear instancias de la clase generada o implementar un servicio WCF desde la interfaz generada para realizar operaciones en el protocolo de SAP sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a10-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the generated interface to perform operations on the SAP system.</span></span>  
  
 <span data-ttu-id="c3a10-106">Mediante svcutil.exe requiere que proporcione un URI que contiene las credenciales de conexión.</span><span class="sxs-lookup"><span data-stu-id="c3a10-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="c3a10-107">Dado que, de forma predeterminada, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] deshabilita las credenciales en el URI de conexión, debe configurar svcutil.exe para utilizar un enlace no predeterminado para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a10-107">Because, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="c3a10-108">También puede configurar otras propiedades de enlace en el enlace no predeterminado; Por ejemplo, para crear un cliente WCF para las operaciones de BAPI, debe establecer el **EnableSafeTyping** enlazar la propiedad a **true**.</span><span class="sxs-lookup"><span data-stu-id="c3a10-108">You can also configure other binding properties in the non-default binding; for example, to create a WCF client for BAPI operations, you must set the **EnableSafeTyping** binding property to **true**.</span></span>  
  
 <span data-ttu-id="c3a10-109">Las secciones siguientes muestran cómo configurar svcutil.exe y cómo utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3a10-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="c3a10-110">Configuración de svcutil.exe para el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="c3a10-110">Configuring svcutil.exe for the SAP Adapter</span></span>  
 <span data-ttu-id="c3a10-111">Para configurar svcutil.exe para utilizar un enlace no predeterminado, debe crear una copia local de svcutil.exe y, a continuación, crear o modificar una copia local del archivo de configuración svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="c3a10-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1.  <span data-ttu-id="c3a10-112">Cree una carpeta y copie svcutil.exe en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="c3a10-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="c3a10-113">Normalmente puede encontrar svcutil.exe en la ubicación de instalación de Windows SDK, específicamente, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span><span class="sxs-lookup"><span data-stu-id="c3a10-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="c3a10-114">Cree un archivo denominado svcutil.exe.config en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="c3a10-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="c3a10-115">Agregar un enlace y un punto de conexión de cliente en el archivo svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="c3a10-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="c3a10-116">Debe ejecutar svcutil.exe desde la nueva carpeta para asegurarse de que se usa la configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="c3a10-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c3a10-117">El atributo de nombre del extremo del cliente debe especificar el esquema utilizado en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="c3a10-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="c3a10-118">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c3a10-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="sap"  
                    binding="sapBinding"  
                    bindingConfiguration="SAPBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <sapBinding>  
            <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
          </sapBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
 <span data-ttu-id="c3a10-119">Puede establecer cualquiera de las propiedades de enlace de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en la configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="c3a10-119">You can set any of the binding properties of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in the binding configuration.</span></span> <span data-ttu-id="c3a10-120">Por ejemplo, podría especificar el siguiente enlace no predeterminado al utilizar svcutil.exe para generar a un cliente WCF para las operaciones de BAPI.</span><span class="sxs-lookup"><span data-stu-id="c3a10-120">For example, you could specify the following non-default binding to use svcutil.exe to generate a WCF client for BAPI operations.</span></span>  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 <span data-ttu-id="c3a10-121">Para obtener más información acerca de cómo configurar un enlace no predeterminado para svcutil.exe, vea el [extremo de metadatos seguros personalizado](https://msdn.microsoft.com/library/aa395212.aspx).</span><span class="sxs-lookup"><span data-stu-id="c3a10-121">For more information about configuring a non-default binding for svcutil.exe, see the [Custom Secure Metadata Endpoint](https://msdn.microsoft.com/library/aa395212.aspx).</span></span>
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="c3a10-122">Crear una clase de cliente WCF o un contrato de servicio WCF con svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="c3a10-122">Creating a WCF Client Class or a WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="c3a10-123">Utilizar svcutil.exe para generar código de cliente WCF o un contrato de servicio WCF (interfaz) para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe proporcionar un URI que especifica un punto de conexión de WS-Metadata Exchange (MEX) y la o las operaciones que se desea svcutil.exe a de conexión generar código.</span><span class="sxs-lookup"><span data-stu-id="c3a10-123">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must supply a connection URI that specifies a WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="c3a10-124">También debe especificar las credenciales de conexión para el sistema SAP en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="c3a10-124">You must also specify connection credentials for the SAP system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3a10-125">Para poder usar svcutil.exe con la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe configurarlo para usar un valor no predeterminado enlace; para obtener información acerca de cómo hacerlo, consulte [configuración de svcutil.exe para el adaptador SAP](#BKMK_ConfigureSvcutil).</span><span class="sxs-lookup"><span data-stu-id="c3a10-125">Before you can use svcutil.exe with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the SAP Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="c3a10-126">Especificar una operación de punto de conexión y de destino MEX en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] URI de conexión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c3a10-126">You specify a MEX endpoint and target operations in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="c3a10-127">Debe incluir el parámetro "wsdl" en la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="c3a10-127">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="c3a10-128">Si es el primer parámetro de la cadena de consulta, se especifica justo después del signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="c3a10-128">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="c3a10-129">Si no es el primer parámetro, debe ir precedida por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="c3a10-129">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="c3a10-130">Debe seguir el parámetro "wsdl" por uno o más parámetros de "op".</span><span class="sxs-lookup"><span data-stu-id="c3a10-130">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="c3a10-131">Cada parámetro de "op" está precedido por una y comercial (&) y especifica el identificador del nodo de una operación de destino.</span><span class="sxs-lookup"><span data-stu-id="c3a10-131">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="c3a10-132">Los tres ejemplos siguientes muestran cómo elegir como destino varias operaciones mediante el uso de svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="c3a10-132">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="c3a10-133">En este ejemplo se crea una clase de cliente WCF para RFC_CALCULATE_TAXES.</span><span class="sxs-lookup"><span data-stu-id="c3a10-133">This example creates a WCF client class for RFC_CALCULATE_TAXES.</span></span>  
  
 <span data-ttu-id="c3a10-134">**.\svcutil "sap://User=YourUserName;Passwd=contraseñadeusuario;Cliente=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span><span class="sxs-lookup"><span data-stu-id="c3a10-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span></span>  
  
 <span data-ttu-id="c3a10-135">Este ejemplo crea una clase de cliente WCF para el SALESORDER_CREATEFROMDAT201 y SALESORDER_CREATEFROMDAT202 IDOC.</span><span class="sxs-lookup"><span data-stu-id="c3a10-135">This example creates a WCF client class for both the SALESORDER_CREATEFROMDAT201 and SALESORDER_CREATEFROMDAT202 IDOC.</span></span>  
  
 <span data-ttu-id="c3a10-136">**.\svcutil "sap://User=YourUserName;Passwd=contraseñadeusuario;Cliente=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span><span class="sxs-lookup"><span data-stu-id="c3a10-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span></span>  
  
 <span data-ttu-id="c3a10-137">Este ejemplo crea un contrato de servicio WCF para recibir el IDOC SALESORDER_CREATEFROMDAT201 desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="c3a10-137">This example creates a WCF service contract to receive the SALESORDER_CREATEFROMDAT201 IDOC from the SAP system.</span></span> <span data-ttu-id="c3a10-138">El identificador de nodo especifica una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="c3a10-138">The NODE ID specifies a Receive operation.</span></span> <span data-ttu-id="c3a10-139">Porque en este ejemplo se abordan la recuperación de metadatos, no hay ninguna necesidad de especificar los parámetros de agente de escucha en el query_string del URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="c3a10-139">Because this example deals with retrieving metadata, there is no need to specify the listener parameters in the query_string of the connection URI.</span></span>  
  
 <span data-ttu-id="c3a10-140">**.\svcutil "sap://User=YourUserName;Passwd=contraseñadeusuario;Cliente=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span><span class="sxs-lookup"><span data-stu-id="c3a10-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c3a10-141">Debe colocar el URI de conexión entre comillas en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c3a10-141">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="c3a10-142">En caso contrario, svcutil.exe intenta recuperar metadatos para las operaciones que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no admite.</span><span class="sxs-lookup"><span data-stu-id="c3a10-142">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support.</span></span> <span data-ttu-id="c3a10-143">Los resultados de un intento de este tipo son indefinidos.</span><span class="sxs-lookup"><span data-stu-id="c3a10-143">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="c3a10-144">De forma predeterminada, svcutil.exe coloca el código generado en el archivo output.cs; Sin embargo, puede cambiar el nombre del archivo de salida y muchas otras opciones que svcutil.exe utiliza estableciendo los modificadores de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c3a10-144">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="c3a10-145">Para obtener más información acerca de las opciones que svcutil.exe admite, consulte la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).</span><span class="sxs-lookup"><span data-stu-id="c3a10-145">For more information about the options that svcutil.exe supports, see the [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).</span></span>
  
 <span data-ttu-id="c3a10-146">Svcutil.exe no proporciona la capacidad de búsqueda para las operaciones (por ejemplo, mediante caracteres comodín).</span><span class="sxs-lookup"><span data-stu-id="c3a10-146">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="c3a10-147">Debe especificar explícitamente los identificadores de nodo para las operaciones específicas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="c3a10-147">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="c3a10-148">El identificador de nodo de una operación es equivalente a la cadena de acción de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c3a10-148">The node ID of an operation is equivalent to its message action string.</span></span> <span data-ttu-id="c3a10-149">No se puede especificar identificadores que hacen referencia solo a las categorías de nodo.</span><span class="sxs-lookup"><span data-stu-id="c3a10-149">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="c3a10-150">Para obtener más información acerca de los identificadores de nodo que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span><span class="sxs-lookup"><span data-stu-id="c3a10-150">For more information about the node IDs that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
 <span data-ttu-id="c3a10-151">El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] proporciona exploración avanzada y capacidades de búsqueda que pueden simplificar en gran medida la generación de una clase de cliente WCF y el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c3a10-151">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="c3a10-152">Para obtener más información sobre la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="c3a10-152">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
