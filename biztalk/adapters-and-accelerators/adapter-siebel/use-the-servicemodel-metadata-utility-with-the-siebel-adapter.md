---
title: Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
description: Utilizar svcutil.exe para un enlace no predeterminado, o para crear una clase de cliente de WCF o el contrato de servicio WCF con el adaptador de Siebel - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bcf80d4a1ea9fc6b54403faa14084816e413be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
ms.locfileid: "25963514"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="7acde-103">Usar la herramienta de utilidad de metadatos de ServiceModel con el adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="7acde-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="7acde-104">Puede usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF para las operaciones que el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone.</span><span class="sxs-lookup"><span data-stu-id="7acde-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class for operations that the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes.</span></span> <span data-ttu-id="7acde-105">Después de ejecutar svcutil.exe para generar una clase de cliente WCF, puede incluir el archivo generado en el código y crear instancias de la clase de cliente WCF para realizar operaciones en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="7acde-105">After you run svcutil.exe to generate a WCF client class, you can include the generated file in your code and create instances of the WCF client class to perform operations on the Siebel system.</span></span>  
  
 <span data-ttu-id="7acde-106">Mediante svcutil.exe requiere que proporcione un URI que contiene las credenciales de conexión.</span><span class="sxs-lookup"><span data-stu-id="7acde-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="7acde-107">Dado que, de forma predeterminada, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] deshabilita las credenciales en el URI de conexión, debe configurar svcutil.exe para utilizar un enlace no predeterminado para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7acde-107">Because, by default, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="7acde-108">También puede configurar otras propiedades de enlace en el enlace no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7acde-108">You can also configure other binding properties in the non-default binding.</span></span>  
  
 <span data-ttu-id="7acde-109">Las secciones siguientes muestran cómo configurar svcutil.exe y cómo utilizar svcutil.exe para generar el código de cliente WCF con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7acde-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="7acde-110">Configurar svcutil.exe para un enlace no predeterminado</span><span class="sxs-lookup"><span data-stu-id="7acde-110">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="7acde-111">Para configurar svcutil.exe para utilizar un enlace no predeterminado, debe crear una copia local de svcutil.exe y, a continuación, crear o modificar una copia local del archivo de configuración svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7acde-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
 
1.  <span data-ttu-id="7acde-112">Cree una carpeta y copie svcutil.exe en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="7acde-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="7acde-113">Normalmente puede encontrar svcutil.exe en la ubicación de instalación de Windows SDK, específicamente, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span><span class="sxs-lookup"><span data-stu-id="7acde-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="7acde-114">Cree un archivo denominado svcutil.exe.config en la nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="7acde-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="7acde-115">Agregar un enlace y un punto de conexión de cliente en el archivo svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7acde-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="7acde-116">Debe ejecutar svcutil.exe desde la nueva carpeta para asegurarse de que se usa la configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="7acde-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7acde-117">El atributo de nombre del extremo del cliente debe especificar el esquema utilizado en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="7acde-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="7acde-118">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7acde-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="siebel"  
            binding="siebelBinding"  
            bindingConfiguration="SiebelBinding"  
            contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <siebelBinding>  
            <binding name="SiebelBinding" acceptCredentialsInUri="true" />  
          </siebelBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="7acde-119">Puede establecer cualquiera de las propiedades de enlace de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en la configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="7acde-119">You can set any of the binding properties of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="7acde-120">Para obtener más información acerca de cómo configurar un enlace no predeterminado para svcutil.exe, vea el tema "Extremo de metadatos seguros personalizada" en la documentación de WCF en [ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077).</span><span class="sxs-lookup"><span data-stu-id="7acde-120">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a><span data-ttu-id="7acde-121">Crear una clase de cliente WCF con svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="7acde-121">Creating a WCF Client Class with svcutil.exe</span></span>  
 <span data-ttu-id="7acde-122">Utilizar svcutil.exe para generar código de cliente WCF para la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe proporcionar una conexión de URI que especifica un **IMetadataExchange** (mex) punto de conexión y la operación u operaciones desea svcutil.exe para generar código.</span><span class="sxs-lookup"><span data-stu-id="7acde-122">To use svcutil.exe to generate WCF client code for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must supply a connection URI that specifies an **IMetadataExchange** (mex) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="7acde-123">También debe especificar las credenciales de conexión para el sistema Siebel en el URI de conexión.</span><span class="sxs-lookup"><span data-stu-id="7acde-123">You must also specify connection credentials for the Siebel system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7acde-124">Para poder usar svcutil.exe con la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], debe configurarlo para usar un valor no predeterminado enlace; para obtener información acerca de cómo hacerlo, consulte [configuración de svcutil.exe para el adaptador de Siebel](#BKMK_ConfigureSvcutil).</span><span class="sxs-lookup"><span data-stu-id="7acde-124">Before you can use svcutil.exe with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Siebel Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="7acde-125">Especificar una operación de punto de conexión y de destino de mex en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] URI de conexión de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7acde-125">You specify a mex endpoint and target operations in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="7acde-126">Debe incluir el parámetro "wsdl" en el query_string.</span><span class="sxs-lookup"><span data-stu-id="7acde-126">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="7acde-127">Si es el primer parámetro de la query_string, se especifica justo después del signo de interrogación (?).</span><span class="sxs-lookup"><span data-stu-id="7acde-127">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="7acde-128">Si no es el primer parámetro, debe ir precedida por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="7acde-128">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="7acde-129">Debe seguir el parámetro "wsdl" por uno o más parámetros de "op".</span><span class="sxs-lookup"><span data-stu-id="7acde-129">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="7acde-130">Cada parámetro de "op" está precedido por una y comercial (&) y especifica el identificador del nodo de una operación de destino.</span><span class="sxs-lookup"><span data-stu-id="7acde-130">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="7acde-131">Los dos ejemplos siguientes muestran cómo elegir como destino varias operaciones mediante el uso de svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="7acde-131">The following two examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="7acde-132">Este ejemplo crea una clase de cliente WCF para una operación de inserción en el objeto de negocios ACCOUNT\ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="7acde-132">This example creates a WCF client class for an insert operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="7acde-133">**.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span><span class="sxs-lookup"><span data-stu-id="7acde-133">**.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span></span>  
  
 <span data-ttu-id="7acde-134">Este ejemplo crea una clase de cliente WCF para una operación de inserción y una operación de eliminación en el objeto de negocios ACCOUNT\ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="7acde-134">This example creates a WCF client class for both an insert operation and a delete operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="7acde-135">**.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span><span class="sxs-lookup"><span data-stu-id="7acde-135">**.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7acde-136">Debe colocar el URI de conexión entre comillas en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7acde-136">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="7acde-137">En caso contrario, svcutil.exe intenta recuperar metadatos para las operaciones que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite.</span><span class="sxs-lookup"><span data-stu-id="7acde-137">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support.</span></span> <span data-ttu-id="7acde-138">Los resultados de un intento de este tipo son indefinidos.</span><span class="sxs-lookup"><span data-stu-id="7acde-138">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="7acde-139">De forma predeterminada, svcutil.exe coloca el código generado en el archivo output.cs; Sin embargo, puede cambiar el nombre del archivo de salida y muchas otras opciones que svcutil.exe utiliza estableciendo los modificadores de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7acde-139">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span>  
  
 <span data-ttu-id="7acde-140">Svcutil.exe no proporciona la capacidad de búsqueda para las operaciones (por ejemplo, mediante caracteres comodín).</span><span class="sxs-lookup"><span data-stu-id="7acde-140">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="7acde-141">Debe especificar explícitamente los identificadores de nodo para las operaciones específicas que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="7acde-141">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="7acde-142">No se puede especificar identificadores que hacen referencia solo a las categorías de nodo.</span><span class="sxs-lookup"><span data-stu-id="7acde-142">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="7acde-143">Para obtener más información acerca de los identificadores de nodo que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span><span class="sxs-lookup"><span data-stu-id="7acde-143">For more information about the node IDs that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>  
  
 <span data-ttu-id="7acde-144">El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] proporciona funcionalidades de búsqueda que pueden simplificar en gran medida la generación de una clase de cliente WCF y examinar avanzada.</span><span class="sxs-lookup"><span data-stu-id="7acde-144">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class.</span></span> <span data-ttu-id="7acde-145">Para obtener más información sobre la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="7acde-145">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for Siebel solution artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
