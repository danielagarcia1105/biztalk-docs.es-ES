---
title: Solucionar problemas de funcionamiento con el adaptador de base de datos de Oracle | Microsoft Docs
description: Problemas comunes y soluciones para el adaptador de base de datos de Oracle en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dfe903e897ebc3d26e6dc380233f80253ddfc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968421"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="8d546-103">Solucionar problemas de funcionamiento con el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8d546-103">Troubleshoot operational issues with the Oracle Database adapter</span></span>
<span data-ttu-id="8d546-104">Solución de problemas de técnicas para solucionar errores operativos que puede experimentar con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-104">Troubleshooting techniques to resolve operational errors that you may experience using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="enable-tracing"></a><span data-ttu-id="8d546-105">Habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="8d546-105">Enable tracing</span></span>  
 <span data-ttu-id="8d546-106">Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="8d546-106">For information about tracing support in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Diagnostic tracing and message logging for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="8d546-107">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8d546-107">Known Issues</span></span>  
 <span data-ttu-id="8d546-108">Los siguientes son los errores más comunes que pueden surgir al usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], junto con su causa y resolución.</span><span class="sxs-lookup"><span data-stu-id="8d546-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with their probable cause and resolution.</span></span>   
  
### <a name="BKMK_OraDBLoading"></a> <span data-ttu-id="8d546-109">Error al cargar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="8d546-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="8d546-110">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-110">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-111">Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="8d546-112">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-112">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-113">Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados.</span><span class="sxs-lookup"><span data-stu-id="8d546-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="8d546-114">A su vez, los enlaces del adaptador dependen del software cliente específica de la aplicación de empresa.</span><span class="sxs-lookup"><span data-stu-id="8d546-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="8d546-115">Que puede enfrentarse a este problema para uno o ambos de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="8d546-115">You might face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="8d546-116">El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.</span><span class="sxs-lookup"><span data-stu-id="8d546-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="8d546-117">Realizó una instalación típica o completo del adaptador, que se instala en todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8d546-118">Sin embargo, podrían instalarse las bibliotecas de cliente de línea de negocio para sólo una aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="8d546-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="8d546-119">Como resultado, la interfaz gráfica de usuario no se puede cargar los enlaces para los demás adaptadores.</span><span class="sxs-lookup"><span data-stu-id="8d546-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="8d546-120">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-120">**Resolution**</span></span>  
  
- <span data-ttu-id="8d546-121">Asegúrese de que las versiones de cliente de línea de negocio necesarias están instaladas en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8d546-122">[Admite la línea de negocio (LOB) y sistemas empresariales](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) se enumeran las versiones de cliente compatible.</span><span class="sxs-lookup"><span data-stu-id="8d546-122">[Supported Line-of-Business (LOB) and Enterprise systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported client versions.</span></span>  
  
- <span data-ttu-id="8d546-123">Asegúrese de que realizar una instalación personalizada de los adaptadores que se va a instalar a sólo el adaptador que necesita.</span><span class="sxs-lookup"><span data-stu-id="8d546-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8d546-124">Para asegurarse de que la aplicación funciona con la versión más reciente de ODP.NET, debe tener el "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="8d546-124">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="8d546-125">Para obtener más información, consulte [proveedor de datos de Oracle para .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) en el sitio Web de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8d546-125">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle's website.</span></span>  
  
###  <a name="BKMK_OraDBAdapDisplay"></a> <span data-ttu-id="8d546-126">El adaptador de base de datos de Oracle no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d546-126">The Oracle database adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="8d546-127">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-127">**Problem**</span></span>  
  
<span data-ttu-id="8d546-128">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] incluido en [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparece en la lista de adaptadores en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] inlcuded with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not listed in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="8d546-129">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-129">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-130">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="8d546-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="8d546-131">Por lo tanto, aunque el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no muestra basada en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-131">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="8d546-132">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-132">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-133">Puede agregar explícitamente la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="8d546-133">You can explicitly add the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a> <span data-ttu-id="8d546-134">Error al recuperar la salida XML con más de 65.536 nodos</span><span class="sxs-lookup"><span data-stu-id="8d546-134">Error while retrieving XML output with more than 65,536 nodes</span></span>  
 <span data-ttu-id="8d546-135">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-135">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-136">El adaptador proporciona el siguiente error al recuperar el XML de salida que tiene más de 65.536 nodos.</span><span class="sxs-lookup"><span data-stu-id="8d546-136">The adapter gives the following error when retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="8d546-137">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-137">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-138">El adaptador no se puede serializar y deserializar un objeto con más de 65.536 elementos.</span><span class="sxs-lookup"><span data-stu-id="8d546-138">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="8d546-139">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-139">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-140">Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d546-140">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="8d546-141">Puede establecerlo en cualquiera de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d546-141">You can set this in either of the following two ways:</span></span>  
  
- <span data-ttu-id="8d546-142">Establezca este parámetro cambiando el `maxItemsInObjectGraph` parámetro en el `ServiceBehavior` atributo en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="8d546-142">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
- <span data-ttu-id="8d546-143">Agregue lo siguiente al archivo app.config de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d546-143">Add the following to your application's app.config file.</span></span>  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  <span data-ttu-id="8d546-144">Un ejemplo app.config tiene este aspecto.</span><span class="sxs-lookup"><span data-stu-id="8d546-144">A sample app.config looks like this.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a> <span data-ttu-id="8d546-145">Error al realizar operaciones en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8d546-145">Error while performing operations on the Oracle database</span></span>  
 <span data-ttu-id="8d546-146">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-146">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-147">El adaptador produce el siguiente error al realizar cualquier operación en la base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-147">The adapter gives the following error when performing any operation on the Oracle database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="8d546-148">**Para que BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="8d546-148">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="8d546-149">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-149">**Cause**</span></span>  
  
  <span data-ttu-id="8d546-150">No se especifica la acción de WCF para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d546-150">The WCF action for the message is not specified.</span></span> <span data-ttu-id="8d546-151">WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador de la operación que se realizará en la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="8d546-151">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="8d546-152">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-152">**Resolution**</span></span>  
  
  <span data-ttu-id="8d546-153">Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8d546-153">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="8d546-154">Para obtener instrucciones, consulte [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="8d546-154">For instructions, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span> <span data-ttu-id="8d546-155">Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para ver una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="8d546-155">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_OraDBXmlParsing"></a> <span data-ttu-id="8d546-156">XmlReaderParsingException debido a un nombre de operación incorrecta en la acción especificada</span><span class="sxs-lookup"><span data-stu-id="8d546-156">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="8d546-157">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-157">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-158">La consola de administración de BizTalk Server proporciona el siguiente error al enviar mensajes a una base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="8d546-158">The BizTalk Server Administration Console gives the following error when sending messages to an Oracle database:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="8d546-159">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-159">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-160">Si configura un puerto de WCF-Custom importando el archivo de enlace de puerto creado por el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], se especifica la acción en el puerto en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-160">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="8d546-161">En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="8d546-161">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="8d546-162">Por ejemplo, si ha generado el esquema para la operación de inserción en una tabla, el nombre de la operación en la acción será "Insert".</span><span class="sxs-lookup"><span data-stu-id="8d546-162">For example, if you generated schema for the Insert operation on a table, the operation name in the action will be "Insert".</span></span> <span data-ttu-id="8d546-163">Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="8d546-163">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="8d546-164">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-164">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-165">Asegúrese de que los nombres de operación en ambos el puerto lógico (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.</span><span class="sxs-lookup"><span data-stu-id="8d546-165">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
###  <a name="BKMK_OraDBConnURI"></a> <span data-ttu-id="8d546-166">Error al especificar un URI de conexión para un puerto personalizado de WCF de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8d546-166">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="8d546-167">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-167">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8d546-168"> Muestra el siguiente error cuando se especifica un URI de conexión para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8d546-168"> gives the following error when you specify a connection URI to connect to the Oracle database.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="8d546-169">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-169">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-170">El URI de conexión no cumple con el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="8d546-170">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="8d546-171">Por ejemplo, el valor de un parámetro podría contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="8d546-171">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="8d546-172">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-172">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-173">Asegúrese de que la conexión que especifique el URI se ajusta al formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="8d546-173">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="8d546-174">Por ejemplo, un espacio en blanco debe reemplazarse por "% 20".</span><span class="sxs-lookup"><span data-stu-id="8d546-174">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_OraDBInvalCursor"></a> <span data-ttu-id="8d546-175">Excepción de cursor no válido al invocar procedimientos almacenados que toman parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8d546-175">Invalid cursor exception while invoking stored procedures that take REF CURSOR parameters</span></span>  
 <span data-ttu-id="8d546-176">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-176">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-177">Al invocar los procedimientos de la base de datos de Oracle que toman entradas de REF CURSOR, podría obtener la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="8d546-177">When you invoke procedures in the Oracle database that take REF CURSOR inputs, you might get the following exception:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 <span data-ttu-id="8d546-178">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-178">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-179">El bloque de PL/SQL para el procedimiento que se está invocando podría canalizar los cursores REF CURSOR, es decir, IN REF CURSOR podría obtener asignarse a OUT REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8d546-179">The PL/SQL block for the procedure that you are invoking could be piping the REF CURSORs, that is, the IN REF CURSOR could be getting assigned to the OUT REF CURSOR.</span></span>  
  
 <span data-ttu-id="8d546-180">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-180">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-181">El bloque de PL/SQL no debe canalizar IN a la horizontal cursores REF cursor sin que se procese correctamente.</span><span class="sxs-lookup"><span data-stu-id="8d546-181">The PL/SQL block must not pipe the IN to the OUT REF CURSORs without proper processing.</span></span>  
  
###  <a name="BKMK_OraDBValidateResp"></a> <span data-ttu-id="8d546-182">Error al validar la respuesta para la operación ReadLOB con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d546-182">Error while validating the response for the ReadLOB operation using BizTalk Server</span></span>  
 <span data-ttu-id="8d546-183">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-183">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-184">Mientras se realiza una operación de ReadLOB con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], la respuesta de la base de datos de Oracle se produce un error de validación en el lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="8d546-184">While performing a ReadLOB operation using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the response from the Oracle database fails validation against the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="8d546-185">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-185">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-186">El WSDL contiene un nombre de nodo StreamBody que está definido para la ejecución de solicitudes de servicio, pero no es necesario para escenarios de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8d546-186">The WSDL contains a StreamBody node name that is defined for execution of service-based requests, but is not needed for BizTalk scenarios.</span></span> <span data-ttu-id="8d546-187">Por lo tanto, cuando la salida XML, que no contiene el nodo StreamBody, se compara con el WSDL, falla la validación.</span><span class="sxs-lookup"><span data-stu-id="8d546-187">Therefore, when the output XML, which does not contain the StreamBody node, is compared with the WSDL, validation fails.</span></span>  
  
 <span data-ttu-id="8d546-188">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-188">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-189">Quite el nodo de StreamBody desde WSDL al validarlo con la salida que se ha generado mediante BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-189">Remove the StreamBody node from the WSDL when validating against the output that was generated using BizTalk Server.</span></span> <span data-ttu-id="8d546-190">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d546-190">Perform the following steps to do so:</span></span>  
  
1. <span data-ttu-id="8d546-191">El WSDL que contiene el nodo StreamBody tiene este aspecto.</span><span class="sxs-lookup"><span data-stu-id="8d546-191">The WSDL containing the StreamBody node looks like this.</span></span>  
  
   ```  
   <xs:element name="ReadLOBResponse">  
       <xs:annotation>  
         <xs:documentation>  
           <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
         </xs:documentation>  
       </xs:annotation>  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   ```  
  
    <span data-ttu-id="8d546-192">Reemplazar la anterior con el siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d546-192">Replace the preceding with the following.</span></span>  
  
   ```  
   <xs:element name="ReadLOBResponse">  
    <xs:annotation>  
    <xs:documentation>  
     <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
     </xs:documentation>  
     </xs:annotation>  
    <xs:complexType>  
    <xs:sequence>  
     <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
     </xs:sequence>  
     </xs:complexType>  
     </xs:element>  
   ```  
  
    <span data-ttu-id="8d546-193">En este paso, ha quitado la referencia al tipo = "ns3:StreamBody" en el documento XSD original y lo reemplazamos por tipo = "s: base64Binary".</span><span class="sxs-lookup"><span data-stu-id="8d546-193">In this step, you removed the reference to type="ns3:StreamBody" in the original XSD and replaced it with type="xs:base64Binary".</span></span> <span data-ttu-id="8d546-194">Además, se quita el valor "true" nillable = desde el documento XSD original.</span><span class="sxs-lookup"><span data-stu-id="8d546-194">Also, you removed the nillable="true" value from the original XSD.</span></span>  
  
2. <span data-ttu-id="8d546-195">Quite el siguiente desde WSDL.</span><span class="sxs-lookup"><span data-stu-id="8d546-195">Remove the following from the WSDL.</span></span>  
  
   ```  
   <xs:complexType name="StreamBody">  
       <xs:sequence>  
         <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
           <xs:simpleType>  
             <xs:restriction base="xs:base64Binary">  
               <xs:minLength value="0" />  
             </xs:restriction>  
           </xs:simpleType>  
         </xs:element>  
       </xs:sequence>  
     </xs:complexType>  
     <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="8d546-196">No se admite la operación de ReadLOB con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-196">ReadLOB operation is not supported with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8d546-197">Debe usar una operación de selección de tabla para leer los datos LOB desde un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="8d546-197">You should use a table Select operation to read LOB data from a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a> <span data-ttu-id="8d546-198">Puede producir un error de validación del esquema en escenarios de sondeo</span><span class="sxs-lookup"><span data-stu-id="8d546-198">Schema validation may fail in polling scenarios</span></span>  
 <span data-ttu-id="8d546-199">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-199">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-200">Se produce un error de validación del esquema en escenarios donde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] tablas que contienen los campos de tipo ROWID o UNROWID sondea la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d546-200">Schema validation fails in scenarios where the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] polls database tables that contain fields of type ROWID or UNROWID.</span></span>  
  
 <span data-ttu-id="8d546-201">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-201">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-202">En tiempo de diseño, cuando el adaptador genera metadatos de la tabla que contiene los campos de tipo ROWID o UNROWID, el esquema incluye "nillable = false", lo que significa que los campos de tipo ROWID o UNROWID no pueden ser nulos.</span><span class="sxs-lookup"><span data-stu-id="8d546-202">At design-time, when the adapter generates metadata for the table containing fields of type ROWID or UNROWID, the schema includes “nillable=false”, which means that fields of type ROWID or UNROWID cannot be null.</span></span> <span data-ttu-id="8d546-203">Sin embargo, en tiempo de ejecución cuando el adaptador recupera los metadatos, los campos de tipo ROWID o UNROWID contienen valores null.</span><span class="sxs-lookup"><span data-stu-id="8d546-203">However, at run-time when the adapter retrieves the metadata, the fields of type ROWID or UNROWID contain null values.</span></span> <span data-ttu-id="8d546-204">Por lo tanto, se produce un error en la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="8d546-204">Hence the schema validation fails.</span></span>  
  
 <span data-ttu-id="8d546-205">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-205">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-206">Si usas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede optar por deshabilitar la validación de esquema.</span><span class="sxs-lookup"><span data-stu-id="8d546-206">If you are using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you may choose to disable schema validation.</span></span> <span data-ttu-id="8d546-207">Como alternativa, puede editar manualmente el esquema para cambiar "nillbale = true" para tipos de datos ROWID y UNROWID.</span><span class="sxs-lookup"><span data-stu-id="8d546-207">Alternatively, you may manually edit the schema to change “nillbale=true” for ROWID and UNROWID data types.</span></span>  
  
###  <a name="BKMK_OraDBUnreasonConv"></a> <span data-ttu-id="8d546-208">Error de 'Razonable conversión solicitada' al ejecutar procedimientos almacenados con tipos de registros como parámetros</span><span class="sxs-lookup"><span data-stu-id="8d546-208">'Unreasonable conversion requested' error when executing stored procedures with Record Types as parameters</span></span>  
 <span data-ttu-id="8d546-209">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-209">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-210">Considere un escenario donde Oracle procedimiento almacenado toma un tipo de registro como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d546-210">Consider a scenario where an Oracle stored procedure takes a Record Type as a parameter.</span></span> <span data-ttu-id="8d546-211">Se supone que el tipo de registro se declara como \<nombre de la tabla\>% ROWTYPE, donde la tabla tiene una columna de tipo de datos de tipo LONG.</span><span class="sxs-lookup"><span data-stu-id="8d546-211">Assume that the Record Type is declared as \<table name\>%ROWTYPE, where the table has a column of LONG data type.</span></span> <span data-ttu-id="8d546-212">Cuando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encuentra los datos grandes de tipo, Establece el tamaño del tipo de datos igual que el valor especificado para el **LongDatatypeColumnSize** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8d546-212">When the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encounters the LONG data type, it sets the size of the data type equal to the value specified for the **LongDatatypeColumnSize** binding property.</span></span> <span data-ttu-id="8d546-213">Sin embargo, la base de datos de Oracle no definen un tamaño para el tipo de datos de tipo LONG.</span><span class="sxs-lookup"><span data-stu-id="8d546-213">However, the Oracle database does not define a size for the LONG data type.</span></span> <span data-ttu-id="8d546-214">Por lo tanto, cuando el adaptador invoca el procedimiento almacenado, produce un error de 'Poco razonable conversión solicitada'.</span><span class="sxs-lookup"><span data-stu-id="8d546-214">So, when the adapter invokes the stored procedure, it results in an ‘Unreasonable conversion requested’ error.</span></span>  
  
 <span data-ttu-id="8d546-215">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-215">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-216">Si un tipo de registro tiene un tipo de datos largo, debe definir explícitamente como parte de un paquete.</span><span class="sxs-lookup"><span data-stu-id="8d546-216">If a Record Type has a LONG data type, you must explicitly define it as part of a package.</span></span>  
  
###  <a name="BKMK_OraDBAdapRecognize"></a> <span data-ttu-id="8d546-217">El adaptador no reconoce la acción en el puerto físico incluso aunque use el archivo de enlace generado por el complemento Consume Adapter Service para crear los puertos</span><span class="sxs-lookup"><span data-stu-id="8d546-217">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="8d546-218">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-218">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-219">Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en la base de datos de Oracle, el complemento también crea un archivo de enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="8d546-219">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Oracle database, the add-in also creates a port binding file.</span></span> <span data-ttu-id="8d546-220">Se puede importar utilizando el archivo de enlace el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-220">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="8d546-221">Sin embargo, al enviar mensajes a la base de datos de Oracle utiliza estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-221">However, when you send messages to the Oracle database using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="8d546-222">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-222">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-223">Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados, como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación de base de datos de Oracle para el que generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8d546-223">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the Oracle database operation for which you generate metadata.</span></span> <span data-ttu-id="8d546-224">Por ejemplo, si se generan los metadatos de la operación de selección en la tabla ACCOUNTACTIVITY en la base de datos de Oracle, se establecerá la acción a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-224">For example, if you generate metadata for Select operation on ACCOUNTACTIVITY table in the Oracle database, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 <span data-ttu-id="8d546-225">Al importar el archivo de enlace, la misma acción se establece en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="8d546-225">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="8d546-226">Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="8d546-226">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="8d546-227">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-227">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-228">Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="8d546-228">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="8d546-229">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="8d546-229">Do one of the following:</span></span>  
  
-   <span data-ttu-id="8d546-230">Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que generar metadatos, por ejemplo Select.</span><span class="sxs-lookup"><span data-stu-id="8d546-230">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Select.</span></span>  
  
-   <span data-ttu-id="8d546-231">Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="8d546-231">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="8d546-232">Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-232">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a> <span data-ttu-id="8d546-233">Adaptador lanza una excepción de desbordamiento ("System.OverflowException") en la ejecución de una operación</span><span class="sxs-lookup"><span data-stu-id="8d546-233">Adapter throws an overflow exception (“System.OverflowException”) on executing an operation</span></span>  
 <span data-ttu-id="8d546-234">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-234">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-235">Usa el adaptador, si se intenta realizar una operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada parámetros REF CURSOR, el adaptador podría generar una excepción de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="8d546-235">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="8d546-236">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-236">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-237">Esto sucede si proporciona un valor grande para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF cursor que no quepan en el tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8d546-237">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="8d546-238">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-238">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-239">Si desea pasar valores grandes para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada parámetros REF CURSOR, debe habilitar seguro escribiendo estableciendo el valor de la **EnableSafeTyping** enlazar la propiedad a **true**.</span><span class="sxs-lookup"><span data-stu-id="8d546-239">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="8d546-240">Habilitar seguro escribiendo expone el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o cursores REF cursor de débilmente tipada como cadenas.</span><span class="sxs-lookup"><span data-stu-id="8d546-240">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <a name="BKMK_OraDBRootNode"></a> <span data-ttu-id="8d546-241">Error con RootNode TypeName en proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="8d546-241">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="8d546-242">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-242">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-243">En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :</span><span class="sxs-lookup"><span data-stu-id="8d546-243">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="8d546-244">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-244">**Resolution**</span></span>  
  
1.  <span data-ttu-id="8d546-245">Haga clic en el nodo raíz al que hace referencia en el error y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8d546-245">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8d546-246">Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o palabras reservadas, por ejemplo, punto (.).</span><span class="sxs-lookup"><span data-stu-id="8d546-246">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_OraDBInvalBinding"></a> <span data-ttu-id="8d546-247">Advertencia de enlace no válido al usar el adaptador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8d546-247">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="8d546-248">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-248">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-249">Cuando se usa el adaptador para crear una aplicación en [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d546-249">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="8d546-250">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-250">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-251">Esta advertencia aparece porque la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enlace, `oracleDBBinding`, no un enlace estándar incluye el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d546-251">This warning appears because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding, `oracleDBBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="8d546-252">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-252">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-253">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="8d546-253">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_OraDBNotification"></a> <span data-ttu-id="8d546-254">BizTalk Server produce una excepción si usa más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host</span><span class="sxs-lookup"><span data-stu-id="8d546-254">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="8d546-255">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-255">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-256">BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no puede encontrar la especificación de documento; varios esquemas coincidieron con el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="8d546-256">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="8d546-257">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-257">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-258">Esto sucede debido a una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d546-258">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="8d546-259">Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8d546-259">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="8d546-260">Dado que los esquemas de notificaciones son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-260">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="8d546-261">En el caso de varios proyectos, han generado un esquema de notificación para cada uno de los proyectos, que se implementan cada proyecto para una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, ejecutó una aplicación o aplicaciones para recibir notificaciones de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8d546-261">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="8d546-262">Dado que los ensamblados y esquemas son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en varias aplicaciones de BizTalk Server y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8d546-262">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="8d546-263">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-263">**Resolution**</span></span>  
  
  <span data-ttu-id="8d546-264">Utilizar un único archivo de esquema de notificación para una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-264">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="8d546-265">Si tiene que usar el esquema de notificación en varias aplicaciones de BizTalk Server en el mismo host, cree una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8d546-265">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="8d546-266">Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada con transacciones</span><span class="sxs-lookup"><span data-stu-id="8d546-266">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="8d546-267">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8d546-267">**Problem**</span></span>  
  
 <span data-ttu-id="8d546-268">En una operación de entrada con transacciones, como el sondeo, **si no hay ningún dato disponible en la tabla que se sondea** y while sigue sondeando el adaptador, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8d546-268">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="8d546-269">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8d546-269">**Cause**</span></span>  
  
 <span data-ttu-id="8d546-270">**Si no hay ningún dato disponible en la tabla que se sondea**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un subproceso nuevo para continuar la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="8d546-270">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="8d546-271">Por lo tanto, el uso de memoria y recuento de subprocesos aumenta durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="8d546-271">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="8d546-272">Sin embargo, si la tabla que se sondea tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="8d546-272">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="8d546-273">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8d546-273">**Resolution**</span></span>  
  
 <span data-ttu-id="8d546-274">Se recomienda establecer el **ReceiveTimeout** en el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que un nuevo subproceso se genera solo cada 24 días.</span><span class="sxs-lookup"><span data-stu-id="8d546-274">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="8d546-275">Esto garantizará que el recuento de subprocesos y de uso de memoria no aumentan demasiado demasiado pronto.</span><span class="sxs-lookup"><span data-stu-id="8d546-275">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d546-276">Si se ha establecido SqlAdapterInboundTransactionBehavior, asegúrese de que el TransactionTimeout también está configurado para el valor máximo posible, que es 24.20:31:23.6470000 (24 días).</span><span class="sxs-lookup"><span data-stu-id="8d546-276">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="8d546-277">Cuando se usa esta solución alternativa, podemos agregar la SqlAdapterInboundTransactionBehavior sólo si el nivel de aislamiento de transacción debe estar configurada.</span><span class="sxs-lookup"><span data-stu-id="8d546-277">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="8d546-278">En caso contrario, es una práctica recomendada para quitar ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8d546-278">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="8d546-279">Para obtener más información sobre la **ReceiveTimeout** enlaza la propiedad, vea [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8d546-279">For more information about the **ReceiveTimeout** binding property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="8d546-280">Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="8d546-280">For instructions on specifying binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d546-281">Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="8d546-281">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d546-282">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d546-282">See Also</span></span>  
[<span data-ttu-id="8d546-283">Solucionar problemas del adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8d546-283">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[<span data-ttu-id="8d546-284">Solucionar problemas de instalación con el adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="8d546-284">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)