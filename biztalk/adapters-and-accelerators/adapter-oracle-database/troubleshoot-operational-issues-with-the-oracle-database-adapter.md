---
title: Solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle | Documentos de Microsoft
description: "Problemas comunes y soluciones para el adaptador de base de datos de Oracle en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1de0198d26f804ee8d1974d5dd542387408ea53a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="32d82-103">Solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="32d82-103">Troubleshoot operational issues with the Oracle Database adapter</span></span>
<span data-ttu-id="32d82-104">Solución de problemas de técnicas para solucionar errores operativos que puede experimentar con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-104">Troubleshooting techniques to resolve operational errors that you may experience using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="enable-tracing"></a><span data-ttu-id="32d82-105">Habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="32d82-105">Enable tracing</span></span>  
 <span data-ttu-id="32d82-106">Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-106">For information about tracing support in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Diagnostic tracing and message logging for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="32d82-107">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="32d82-107">Known Issues</span></span>  
 <span data-ttu-id="32d82-108">Éstos son los errores más comunes que pueden surgir al usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], junto con sus causa probable y la resolución.</span><span class="sxs-lookup"><span data-stu-id="32d82-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with their probable cause and resolution.</span></span>   
  
### <span data-ttu-id="32d82-109"><a name="BKMK_OraDBLoading"></a>Error al cargar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="32d82-109"><a name="BKMK_OraDBLoading"></a> Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="32d82-110">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-110">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-111">Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="32d82-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="32d82-112">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-112">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-113">Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados.</span><span class="sxs-lookup"><span data-stu-id="32d82-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="32d82-114">En cambio, los enlaces del adaptador están depende del software de cliente específico para la aplicación de empresa.</span><span class="sxs-lookup"><span data-stu-id="32d82-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="32d82-115">Es posible que tenga este problema para uno o ambos de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="32d82-115">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="32d82-116">El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.</span><span class="sxs-lookup"><span data-stu-id="32d82-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="32d82-117">Se realizó una instalación típica o completar del adaptador, que se instala todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="32d82-118">Sin embargo, podrían instalarse las bibliotecas de cliente LOB para solo una aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="32d82-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="32d82-119">Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.</span><span class="sxs-lookup"><span data-stu-id="32d82-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="32d82-120">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="32d82-121">Asegúrese de que las versiones de cliente LOB necesarias se instalan en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="32d82-122">[Línea de negocio (LOB) y los sistemas empresariales compatibles](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) se enumeran las versiones de cliente admitidos.</span><span class="sxs-lookup"><span data-stu-id="32d82-122">[Supported Line-of-Business (LOB) and Enterprise systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported client versions.</span></span>  
  
-   <span data-ttu-id="32d82-123">Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.</span><span class="sxs-lookup"><span data-stu-id="32d82-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32d82-124">Para asegurarse de que la aplicación funcione con la versión más reciente de ODP.NET, debe tener las "DLL de directiva" instalado en el equipo y registrado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="32d82-124">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="32d82-125">Para obtener más información, consulte [proveedor de datos de Oracle para .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) en el sitio Web de Oracle.</span><span class="sxs-lookup"><span data-stu-id="32d82-125">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle's website.</span></span>  
  
###  <span data-ttu-id="32d82-126"><a name="BKMK_OraDBAdapDisplay"></a>El adaptador de la base de datos de Oracle no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="32d82-126"><a name="BKMK_OraDBAdapDisplay"></a> The Oracle database adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="32d82-127">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-127">**Problem**</span></span>  
  
<span data-ttu-id="32d82-128">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] incluidos con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparece en la lista de adaptadores en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] inlcuded with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not listed in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="32d82-129">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-129">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-130">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="32d82-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="32d82-131">Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-131">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="32d82-132">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-132">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-133">Puede agregar explícitamente la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de la base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-133">You can explicitly add the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <span data-ttu-id="32d82-134"><a name="BKMK_OraDBXMLRetrieve"></a>Error al recuperar la salida XML con más de 65.536 nodos</span><span class="sxs-lookup"><span data-stu-id="32d82-134"><a name="BKMK_OraDBXMLRetrieve"></a> Error while retrieving XML output with more than 65,536 nodes</span></span>  
 <span data-ttu-id="32d82-135">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-135">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-136">El adaptador produce el siguiente error al recuperar el XML de salida que tiene más de 65.536 nodos.</span><span class="sxs-lookup"><span data-stu-id="32d82-136">The adapter gives the following error when retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="32d82-137">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-137">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-138">El adaptador no se puede serializar y deserializar un objeto con más de 65.536 elementos.</span><span class="sxs-lookup"><span data-stu-id="32d82-138">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="32d82-139">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-139">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-140">Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro.</span><span class="sxs-lookup"><span data-stu-id="32d82-140">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="32d82-141">Puede establecer en cualquiera de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="32d82-141">You can set this in either of the following two ways:</span></span>  
  
-   <span data-ttu-id="32d82-142">Establezca este parámetro cambiando el `maxItemsInObjectGraph` parámetro en el `ServiceBehavior` atributo en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="32d82-142">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="32d82-143">Agregue lo siguiente al archivo app.config de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="32d82-143">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="32d82-144">Un ejemplo app.config tiene el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="32d82-144">A sample app.config looks like this.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  \<system.serviceModel>  
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
  \</system.serviceModel>  
</configuration>  
```  
  
###  <span data-ttu-id="32d82-145"><a name="BKMK_OraDBPerfOps"></a>Error al realizar operaciones en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="32d82-145"><a name="BKMK_OraDBPerfOps"></a> Error while performing operations on the Oracle database</span></span>  
 <span data-ttu-id="32d82-146">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-146">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-147">El adaptador produce el siguiente error al realizar cualquier operación en la base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-147">The adapter gives the following error when performing any operation on the Oracle database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="32d82-148">**Para[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="32d82-148">**For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="32d82-149">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-149">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-150">No se especifica la acción de WCF para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="32d82-150">The WCF action for the message is not specified.</span></span> <span data-ttu-id="32d82-151">WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="32d82-151">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="32d82-152">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-152">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-153">Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32d82-153">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="32d82-154">Para obtener instrucciones, consulte [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-154">For instructions, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span> <span data-ttu-id="32d82-155">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para ver una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="32d82-155">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) to see a list of actions for each operation.</span></span>  
  
###  <span data-ttu-id="32d82-156"><a name="BKMK_OraDBXmlParsing"></a>XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada</span><span class="sxs-lookup"><span data-stu-id="32d82-156"><a name="BKMK_OraDBXmlParsing"></a> XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="32d82-157">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-157">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-158">La consola de administración de BizTalk Server produce el siguiente error al enviar mensajes a una base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="32d82-158">The BizTalk Server Administration Console gives the following error when sending messages to an Oracle database:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="32d82-159">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-159">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-160">Si configura un puerto de WCF-Custom importando el archivo de enlace de puerto creado por el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], se especifica la acción en el puerto en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="32d82-160">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="32d82-161">En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="32d82-161">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="32d82-162">Por ejemplo, si ha generado el esquema para la operación de inserción en una tabla, el nombre de la operación en la acción será "Insertar".</span><span class="sxs-lookup"><span data-stu-id="32d82-162">For example, if you generated schema for the Insert operation on a table, the operation name in the action will be "Insert".</span></span> <span data-ttu-id="32d82-163">Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="32d82-163">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="32d82-164">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-164">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-165">Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.</span><span class="sxs-lookup"><span data-stu-id="32d82-165">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
###  <span data-ttu-id="32d82-166"><a name="BKMK_OraDBConnURI"></a>Error al especificar un URI de conexión para un puerto personalizado de WCF de BizTalk</span><span class="sxs-lookup"><span data-stu-id="32d82-166"><a name="BKMK_OraDBConnURI"></a> Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="32d82-167">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-167">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="32d82-168">produce el siguiente error cuando se especifica un URI de conexión para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="32d82-168"> gives the following error when you specify a connection URI to connect to the Oracle database.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="32d82-169">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-169">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-170">El URI de conexión no cumple con el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="32d82-170">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="32d82-171">Por ejemplo, el valor de un parámetro podría contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="32d82-171">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="32d82-172">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-172">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-173">Asegúrese de que la conexión URI especifica cumple el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="32d82-173">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="32d82-174">Por ejemplo, un espacio en blanco debe sustituirse por "% 20".</span><span class="sxs-lookup"><span data-stu-id="32d82-174">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <span data-ttu-id="32d82-175"><a name="BKMK_OraDBInvalCursor"></a>Excepción de cursor no válido al invocar procedimientos almacenados que toman parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="32d82-175"><a name="BKMK_OraDBInvalCursor"></a> Invalid cursor exception while invoking stored procedures that take REF CURSOR parameters</span></span>  
 <span data-ttu-id="32d82-176">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-176">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-177">Al invocar los procedimientos de la base de datos de Oracle que toman entradas de REF CURSOR, puede obtener la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="32d82-177">When you invoke procedures in the Oracle database that take REF CURSOR inputs, you might get the following exception:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 <span data-ttu-id="32d82-178">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-178">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-179">El bloque de PL/SQL para conocer el procedimiento que se está invocando podría ser canalizando los cursores REF CURSOR, es decir, en REF CURSOR podría obtener asignarse a cabo REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="32d82-179">The PL/SQL block for the procedure that you are invoking could be piping the REF CURSORs, that is, the IN REF CURSOR could be getting assigned to the OUT REF CURSOR.</span></span>  
  
 <span data-ttu-id="32d82-180">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-180">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-181">El bloque de PL/SQL no debe canalizar la en la salida cursores REF cursor sin que se procese correctamente.</span><span class="sxs-lookup"><span data-stu-id="32d82-181">The PL/SQL block must not pipe the IN to the OUT REF CURSORs without proper processing.</span></span>  
  
###  <span data-ttu-id="32d82-182"><a name="BKMK_OraDBValidateResp"></a>Error al validar la respuesta para la operación de ReadLOB con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="32d82-182"><a name="BKMK_OraDBValidateResp"></a> Error while validating the response for the ReadLOB operation using BizTalk Server</span></span>  
 <span data-ttu-id="32d82-183">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-183">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-184">Mientras se realiza una operación de ReadLOB con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], la respuesta de la base de datos de Oracle se produce un error de validación en el lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="32d82-184">While performing a ReadLOB operation using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the response from the Oracle database fails validation against the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="32d82-185">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-185">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-186">El archivo WSDL contiene un nombre de nodo StreamBody que se define para la ejecución de las solicitudes de servicio, pero no es necesario para escenarios de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32d82-186">The WSDL contains a StreamBody node name that is defined for execution of service-based requests, but is not needed for BizTalk scenarios.</span></span> <span data-ttu-id="32d82-187">Por lo tanto, cuando la salida XML, que no contiene el nodo StreamBody, se compara con el WSDL, se produce un error en validación.</span><span class="sxs-lookup"><span data-stu-id="32d82-187">Therefore, when the output XML, which does not contain the StreamBody node, is compared with the WSDL, validation fails.</span></span>  
  
 <span data-ttu-id="32d82-188">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-188">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-189">Quite el nodo StreamBody desde WSDL al validarlo con el resultado generado con el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-189">Remove the StreamBody node from the WSDL when validating against the output that was generated using BizTalk Server.</span></span> <span data-ttu-id="32d82-190">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="32d82-190">Perform the following steps to do so:</span></span>  
  
1.  <span data-ttu-id="32d82-191">El archivo WSDL que contiene el nodo StreamBody tiene el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="32d82-191">The WSDL containing the StreamBody node looks like this.</span></span>  
  
    ```  
    \<xs:element name="ReadLOBResponse">  
        \<xs:annotation>  
          \<xs:documentation>  
            \<doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
          \</xs:documentation>  
        \</xs:annotation>  
        \<xs:complexType>  
          \<xs:sequence>  
            \<xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
          \</xs:sequence>  
        \</xs:complexType>  
      \</xs:element>  
    ```  
  
     <span data-ttu-id="32d82-192">Reemplace los anteriores con lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="32d82-192">Replace the preceding with the following.</span></span>  
  
    ```  
    \<xs:element name="ReadLOBResponse">  
     \<xs:annotation>  
     \<xs:documentation>  
      \<doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
      \</xs:documentation>  
      \</xs:annotation>  
     \<xs:complexType>  
     \<xs:sequence>  
      \<xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
      \</xs:sequence>  
      \</xs:complexType>  
      \</xs:element>  
    ```  
  
     <span data-ttu-id="32d82-193">En este paso, ha quitado la referencia al tipo = "ns3:StreamBody" en el documento XSD original y sustituirla por otra con el tipo = "base64Binary".</span><span class="sxs-lookup"><span data-stu-id="32d82-193">In this step, you removed the reference to type="ns3:StreamBody" in the original XSD and replaced it with type="xs:base64Binary".</span></span> <span data-ttu-id="32d82-194">Además, se quita el valor "true" nillable = de XSD original.</span><span class="sxs-lookup"><span data-stu-id="32d82-194">Also, you removed the nillable="true" value from the original XSD.</span></span>  
  
2.  <span data-ttu-id="32d82-195">Extraiga los siguientes elementos de WSDL.</span><span class="sxs-lookup"><span data-stu-id="32d82-195">Remove the following from the WSDL.</span></span>  
  
    ```  
    \<xs:complexType name="StreamBody">  
        \<xs:sequence>  
          \<xs:element minOccurs="1" maxOccurs="1" name="Stream">  
            \<xs:simpleType>  
              \<xs:restriction base="xs:base64Binary">  
                \<xs:minLength value="0" />  
              \</xs:restriction>  
            \</xs:simpleType>  
          \</xs:element>  
        \</xs:sequence>  
      \</xs:complexType>  
      \<xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="32d82-196">No se admite la operación de ReadLOB con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-196">ReadLOB operation is not supported with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="32d82-197">Debe usar una operación de selección de tabla para leer los datos LOB de una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="32d82-197">You should use a table Select operation to read LOB data from a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
###  <span data-ttu-id="32d82-198"><a name="BKMK_OraDBSchemaValidateFail"></a>Puede producir un error de validación del esquema en escenarios de sondeo</span><span class="sxs-lookup"><span data-stu-id="32d82-198"><a name="BKMK_OraDBSchemaValidateFail"></a> Schema validation may fail in polling scenarios</span></span>  
 <span data-ttu-id="32d82-199">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-199">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-200">Se produce un error en la validación del esquema en escenarios donde la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] tablas que contienen campos de tipo ROWID o UNROWID sondea la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32d82-200">Schema validation fails in scenarios where the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] polls database tables that contain fields of type ROWID or UNROWID.</span></span>  
  
 <span data-ttu-id="32d82-201">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-201">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-202">En tiempo de diseño, cuando el adaptador genera los metadatos de la tabla que contiene campos de tipo ROWID o UNROWID, el esquema se incluye "nillable = false", lo que significa que los campos de tipo ROWID o UNROWID no pueden ser nulos.</span><span class="sxs-lookup"><span data-stu-id="32d82-202">At design-time, when the adapter generates metadata for the table containing fields of type ROWID or UNROWID, the schema includes “nillable=false”, which means that fields of type ROWID or UNROWID cannot be null.</span></span> <span data-ttu-id="32d82-203">Sin embargo, en tiempo de ejecución cuando el adaptador recupera los metadatos, los campos de tipo ROWID o UNROWID contienen valores null.</span><span class="sxs-lookup"><span data-stu-id="32d82-203">However, at run-time when the adapter retrieves the metadata, the fields of type ROWID or UNROWID contain null values.</span></span> <span data-ttu-id="32d82-204">Por lo tanto, se produce un error en la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="32d82-204">Hence the schema validation fails.</span></span>  
  
 <span data-ttu-id="32d82-205">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-205">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-206">Si usas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], quizá quiera deshabilitar la validación de esquema.</span><span class="sxs-lookup"><span data-stu-id="32d82-206">If you are using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you may choose to disable schema validation.</span></span> <span data-ttu-id="32d82-207">Como alternativa, puede editar manualmente el esquema que se va a cambiar "nillbale = true" para los tipos de datos ROWID y UNROWID.</span><span class="sxs-lookup"><span data-stu-id="32d82-207">Alternatively, you may manually edit the schema to change “nillbale=true” for ROWID and UNROWID data types.</span></span>  
  
###  <span data-ttu-id="32d82-208"><a name="BKMK_OraDBUnreasonConv"></a>Error de 'Conversion irrazonable solicitado' al ejecutar procedimientos almacenados con tipos de registros como parámetros</span><span class="sxs-lookup"><span data-stu-id="32d82-208"><a name="BKMK_OraDBUnreasonConv"></a> 'Unreasonable conversion requested' error when executing stored procedures with Record Types as parameters</span></span>  
 <span data-ttu-id="32d82-209">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-209">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-210">Considere un escenario donde un Oracle almacena procedimiento toma un tipo de registro como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="32d82-210">Consider a scenario where an Oracle stored procedure takes a Record Type as a parameter.</span></span> <span data-ttu-id="32d82-211">Suponga que se declara el tipo de registro como \<nombre de tabla > % ROWTYPE, donde la tabla tiene una columna de tipo de datos de tipo LONG.</span><span class="sxs-lookup"><span data-stu-id="32d82-211">Assume that the Record Type is declared as \<table name>%ROWTYPE, where the table has a column of LONG data type.</span></span> <span data-ttu-id="32d82-212">Cuando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encuentra los datos grandes de tipo, Establece el tamaño del tipo de datos igual que el valor especificado para la **LongDatatypeColumnSize** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="32d82-212">When the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encounters the LONG data type, it sets the size of the data type equal to the value specified for the **LongDatatypeColumnSize** binding property.</span></span> <span data-ttu-id="32d82-213">Sin embargo, la base de datos de Oracle no definen un tamaño para el tipo de datos de tipo LONG.</span><span class="sxs-lookup"><span data-stu-id="32d82-213">However, the Oracle database does not define a size for the LONG data type.</span></span> <span data-ttu-id="32d82-214">Por lo tanto, cuando el adaptador invoca el procedimiento almacenado, produce un error de 'Conversion irrazonable solicitado'.</span><span class="sxs-lookup"><span data-stu-id="32d82-214">So, when the adapter invokes the stored procedure, it results in an ‘Unreasonable conversion requested’ error.</span></span>  
  
 <span data-ttu-id="32d82-215">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-215">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-216">Si un tipo de registro tiene un tipo de datos de tipo LONG, debe definir explícitamente como parte de un paquete.</span><span class="sxs-lookup"><span data-stu-id="32d82-216">If a Record Type has a LONG data type, you must explicitly define it as part of a package.</span></span>  
  
###  <span data-ttu-id="32d82-217"><a name="BKMK_OraDBAdapRecognize"></a>El adaptador no reconoce la acción en el puerto físico incluso aunque use el archivo de enlace generado por el complemento Consume Adapter Service para crear los puertos</span><span class="sxs-lookup"><span data-stu-id="32d82-217"><a name="BKMK_OraDBAdapRecognize"></a> The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="32d82-218">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-218">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-219">Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en la base de datos de Oracle, el complemento también crea un archivo de enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="32d82-219">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Oracle database, the add-in also creates a port binding file.</span></span> <span data-ttu-id="32d82-220">Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-220">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="32d82-221">Sin embargo, cuando se envían mensajes a la base de datos de Oracle mediante estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="32d82-221">However, when you send messages to the Oracle database using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="32d82-222">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-222">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-223">Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación de base de datos de Oracle para el que generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="32d82-223">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the Oracle database operation for which you generate metadata.</span></span> <span data-ttu-id="32d82-224">Por ejemplo, si se generan metadatos para seleccionar operación en la tabla ACCOUNTACTIVITY en la base de datos de Oracle, se establecerá la acción a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="32d82-224">For example, if you generate metadata for Select operation on ACCOUNTACTIVITY table in the Oracle database, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 <span data-ttu-id="32d82-225">Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="32d82-225">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="32d82-226">Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="32d82-226">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="32d82-227">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-227">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-228">Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="32d82-228">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="32d82-229">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="32d82-229">Do one of the following:</span></span>  
  
-   <span data-ttu-id="32d82-230">Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo Select.</span><span class="sxs-lookup"><span data-stu-id="32d82-230">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Select.</span></span>  
  
-   <span data-ttu-id="32d82-231">Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="32d82-231">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="32d82-232">Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="32d82-232">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <span data-ttu-id="32d82-233"><a name="BKMK_OraDBOverflowExcep"></a>Adaptador lanza una excepción de desbordamiento ("System.OverflowException") en la ejecución de una operación</span><span class="sxs-lookup"><span data-stu-id="32d82-233"><a name="BKMK_OraDBOverflowExcep"></a> Adapter throws an overflow exception (“System.OverflowException”) on executing an operation</span></span>  
 <span data-ttu-id="32d82-234">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-234">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-235">Mediante el adaptador, si se intenta realizar una operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, el adaptador podría producir una excepción de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="32d82-235">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="32d82-236">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-236">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-237">Esto sucede si se proporciona un valor grande para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF cursor que no caben en el tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="32d82-237">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="32d82-238">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-238">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-239">Si desea pasar valores grandes para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, debe habilitar escribiendo segura estableciendo el valor de la **EnableSafeTyping** enlace propiedad **true**.</span><span class="sxs-lookup"><span data-stu-id="32d82-239">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="32d82-240">Habilitar escribiendo seguro, expone al tipo de datos numéricos de Oracle en conjuntos de datos o débilmente tipada cursores REF cursor como cadenas.</span><span class="sxs-lookup"><span data-stu-id="32d82-240">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <span data-ttu-id="32d82-241"><a name="BKMK_OraDBRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="32d82-241"><a name="BKMK_OraDBRootNode"></a> Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="32d82-242">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-242">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-243">En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :</span><span class="sxs-lookup"><span data-stu-id="32d82-243">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="32d82-244">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-244">**Resolution**</span></span>  
  
1.  <span data-ttu-id="32d82-245">Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="32d82-245">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="32d82-246">Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).</span><span class="sxs-lookup"><span data-stu-id="32d82-246">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <span data-ttu-id="32d82-247"><a name="BKMK_OraDBInvalBinding"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="32d82-247"><a name="BKMK_OraDBInvalBinding"></a> Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="32d82-248">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-248">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-249">Cuando usa el adaptador para crear una aplicación en [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="32d82-249">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="32d82-250">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-250">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-251">Esta advertencia aparece porque la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enlace, `oracleDBBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32d82-251">This warning appears because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding, `oracleDBBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="32d82-252">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-252">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-253">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="32d82-253">You can safely ignore this warning.</span></span>  
  
###  <span data-ttu-id="32d82-254"><a name="BKMK_OraDBNotification"></a>BizTalk Server produce una excepción si se utiliza más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host</span><span class="sxs-lookup"><span data-stu-id="32d82-254"><a name="BKMK_OraDBNotification"></a> BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="32d82-255">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-255">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-256">BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="32d82-256">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="32d82-257">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-257">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-258">Esto se debe a alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="32d82-258">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="32d82-259">Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="32d82-259">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="32d82-260">Dado que los esquemas de notificación son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-260">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="32d82-261">En el caso de varios proyectos, ha generado un esquema de notificación para cada uno de los proyectos que se implementan cada proyecto a una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, se ejecutaba una aplicación o aplicaciones reciban notificaciones de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="32d82-261">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="32d82-262">Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="32d82-262">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="32d82-263">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-263">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-264">Usar un único archivo de esquema de notificación para una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-264">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="32d82-265">Si tiene que usar el esquema de notificación de varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="32d82-265">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <span data-ttu-id="32d82-266"><a name="BKMK_MemUsage"></a>Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada de transacción</span><span class="sxs-lookup"><span data-stu-id="32d82-266"><a name="BKMK_MemUsage"></a> Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="32d82-267">**Problema**</span><span class="sxs-lookup"><span data-stu-id="32d82-267">**Problem**</span></span>  
  
 <span data-ttu-id="32d82-268">En una operación de entrada transacción, como el sondeo, **si no hay ningún dato disponible en la tabla se sondean,** y el adaptador while sigue sondeando, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="32d82-268">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="32d82-269">**Causa**</span><span class="sxs-lookup"><span data-stu-id="32d82-269">**Cause**</span></span>  
  
 <span data-ttu-id="32d82-270">**Si no hay ningún dato disponible en la tabla se sondean**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un nuevo subproceso para continuar con la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="32d82-270">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="32d82-271">Por lo tanto, el uso de memoria y el número de subprocesos aumenta durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="32d82-271">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="32d82-272">Sin embargo, si la tabla se sondean, tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="32d82-272">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="32d82-273">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="32d82-273">**Resolution**</span></span>  
  
 <span data-ttu-id="32d82-274">Se recomienda establecer el **ReceiveTimeout** para el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que se genera un subproceso nuevo solo cada 24 días.</span><span class="sxs-lookup"><span data-stu-id="32d82-274">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="32d82-275">Esto garantizará que el recuento de subprocesos y de uso de memoria no aumente demasiado demasiado pronto.</span><span class="sxs-lookup"><span data-stu-id="32d82-275">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32d82-276">Si se ha establecido SqlAdapterInboundTransactionBehavior, asegúrese de que el TransactionTimeout también está configurado para el valor máximo posible, que es 24.20:31:23.6470000 (24 días).</span><span class="sxs-lookup"><span data-stu-id="32d82-276">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="32d82-277">Al utilizar esta solución alternativa, podemos agregar la SqlAdapterInboundTransactionBehavior sólo si el nivel de aislamiento de transacción debe estar configurado.</span><span class="sxs-lookup"><span data-stu-id="32d82-277">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="32d82-278">En caso contrario, es una práctica recomendada para quitar ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="32d82-278">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="32d82-279">Para obtener más información sobre la **ReceiveTimeout** enlace de propiedad, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-279">For more information about the **ReceiveTimeout** binding property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="32d82-280">Para obtener instrucciones sobre cómo especificar propiedades de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="32d82-280">For instructions on specifying binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32d82-281">Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="32d82-281">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d82-282">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d82-282">See Also</span></span>  
[<span data-ttu-id="32d82-283">Solucionar problemas del adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="32d82-283">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[<span data-ttu-id="32d82-284">Solucionar problemas de instalación con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="32d82-284">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)