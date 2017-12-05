---
title: Solucionar problemas de funcionamiento con el adaptador de BizTalk | Documentos de Microsoft
description: "Problemas comunes y soluciones para el adaptador de Siebel en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff6e36afd7cecc967069fd3ecf5414c6afdb014
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a><span data-ttu-id="a4b50-103">Solucionar problemas de funcionamiento con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-103">Troubleshoot Operational Issues with the Siebel adapter</span></span>
<span data-ttu-id="a4b50-104">Esta sección proporciona una ubicación centralizada para obtener información acerca de problemas de funcionamiento que pueden surgir al usar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-104">This section provides a centralized location for information about operational issues you might encounter when using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="a4b50-105">La habilitación del seguimiento</span><span class="sxs-lookup"><span data-stu-id="a4b50-105">Enabling Tracing</span></span>  
 <span data-ttu-id="a4b50-106">Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="a4b50-106">For information about tracing support in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Diagnostic Tracing and Message Logging for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="a4b50-107">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="a4b50-107">Known Issues</span></span>  
 <span data-ttu-id="a4b50-108">Los siguientes son algunos problemas y soluciones recomendadas que pueden surgir al usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-108">The following are some issues and recommended solutions that you might encounter while using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  
###  <a name="BKMK_SiebelBindingError"></a><span data-ttu-id="a4b50-109">Error al cargar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="a4b50-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="a4b50-110">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-110">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-111">Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], la interfaz gráfica de usuario produce el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="a4b50-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="a4b50-112">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-112">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-113">Al iniciar la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados.</span><span class="sxs-lookup"><span data-stu-id="a4b50-113">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="a4b50-114">En cambio, los enlaces del adaptador están depende del software de cliente de aplicación empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="a4b50-114">In turn, the adapter bindings are dependent on the specific enterprise application client software.</span></span> <span data-ttu-id="a4b50-115">Por lo tanto, podría enfrentarse a este problema para uno o ambos de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="a4b50-115">So, you could face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="a4b50-116">El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.</span><span class="sxs-lookup"><span data-stu-id="a4b50-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="a4b50-117">Se realizó una instalación "Típica" o "Completar" del adaptador, que se instala todos los adaptadores de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-117">You did a "Typical" or "Complete" installation of the adapter, which installs all the adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="a4b50-118">Sin embargo, las bibliotecas de cliente podrían estar instaladas para solo una aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="a4b50-118">However, the client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="a4b50-119">Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.</span><span class="sxs-lookup"><span data-stu-id="a4b50-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="a4b50-120">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="a4b50-121">Asegúrese de que las versiones de cliente necesarias están instaladas en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-121">Make sure the required client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a4b50-122">Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.</span><span class="sxs-lookup"><span data-stu-id="a4b50-122">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SiebelDispAdap"></a><span data-ttu-id="a4b50-123">El adaptador no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a4b50-123">The Siebel adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="a4b50-124">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-124">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-125">A diferencia de la versión anterior de los adaptadores que se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] que acompaña a [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a4b50-125">Unlike the earlier version of the adapters that shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] that shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="a4b50-126">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-126">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-127">La versión más reciente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="a4b50-127">The latest [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="a4b50-128">Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-128">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="a4b50-129">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-129">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-130">Puede agregar explícitamente la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="a4b50-130">You can explicitly add the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_SiebelConnecting"></a><span data-ttu-id="a4b50-131">Error al conectarse al sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-131">Error while connecting to the Siebel system</span></span>  
 <span data-ttu-id="a4b50-132">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-132">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-133">El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] produce el siguiente error al intentar conectarse al sistema Siebel:</span><span class="sxs-lookup"><span data-stu-id="a4b50-133">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] gives the following error when you try to connect to the Siebel system:</span></span>  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 <span data-ttu-id="a4b50-134">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-134">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-135">El cliente Siebel Web no puede instalarse en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a4b50-135">The Siebel Web client might not be installed on the computer.</span></span>  
  
 <span data-ttu-id="a4b50-136">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-136">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-137">Asegúrese de que la versión admitida del cliente Siebel Web está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a4b50-137">Make sure the supported version of the Siebel Web client is installed on the computer.</span></span> <span data-ttu-id="a4b50-138">Consulte la Guía de instalación de cliente admitida y las versiones de servidor para Siebel.</span><span class="sxs-lookup"><span data-stu-id="a4b50-138">Refer to the installation guide for supported client and server versions for Siebel.</span></span> <span data-ttu-id="a4b50-139">La Guía de instalación está disponible en \<unidad del sistema\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span><span class="sxs-lookup"><span data-stu-id="a4b50-139">The installation guide is available at \<system drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a><span data-ttu-id="a4b50-140">Error al recuperar el XML con más de 65536 nodos</span><span class="sxs-lookup"><span data-stu-id="a4b50-140">Error while retrieving XMLs with more than 65536 nodes</span></span>  
 <span data-ttu-id="a4b50-141">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-141">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-142">El adaptador produce el siguiente error al recuperar la salida XML que tiene más de 65536 nodos.</span><span class="sxs-lookup"><span data-stu-id="a4b50-142">The adapter gives the following error while retrieving XML output that has more than 65536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="a4b50-143">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-143">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-144">El adaptador no se puede serializar y deserializar un objeto con más de 65536 elementos.</span><span class="sxs-lookup"><span data-stu-id="a4b50-144">The adapter cannot serialize and deserialize an object with more than 65536 items.</span></span>  
  
 <span data-ttu-id="a4b50-145">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-145">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-146">Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a4b50-146">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="a4b50-147">Esto se puede establecer en cualquiera de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4b50-147">You can set this in any of the following two ways:</span></span>  
  
-   <span data-ttu-id="a4b50-148">Establezca este parámetro cambiando el `maxItemsInObjectGraph` parámetro en el `ServiceBehavior` atributo en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4b50-148">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="a4b50-149">Agregue lo siguiente al archivo app.config de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4b50-149">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="a4b50-150">Un ejemplo app.config será similar:</span><span class="sxs-lookup"><span data-stu-id="a4b50-150">A sample app.config will look like:</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a><span data-ttu-id="a4b50-151">Error al especificar un URI de conexión para un puerto personalizado de WCF de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a4b50-151">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="a4b50-152">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-152">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a4b50-153">produce el siguiente error cuando se especifica un URI de conexión para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="a4b50-153"> gives the following error when you specify a connection URI to connect to the Siebel system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="a4b50-154">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-154">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-155">El URI de conexión no cumple con el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="a4b50-155">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="a4b50-156">Por ejemplo, el valor de un parámetro podría contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="a4b50-156">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="a4b50-157">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-157">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-158">Asegúrese de que la conexión URI especifica cumple el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="a4b50-158">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="a4b50-159">Por ejemplo, un espacio en blanco debe sustituirse por "% 20".</span><span class="sxs-lookup"><span data-stu-id="a4b50-159">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_SiebelPerfOps"></a><span data-ttu-id="a4b50-160">Error al realizar la operación en el sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-160">Error while performing operation on the Siebel system</span></span>  
 <span data-ttu-id="a4b50-161">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-161">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-162">El adaptador produce el siguiente error al realizar cualquier operación en el sistema Siebel mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-162">The adapter gives the following error when performing any operation on the Siebel system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a4b50-163">**Para que BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="a4b50-163">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="a4b50-164">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-164">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-165">No se especifica la acción de WCF para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a4b50-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="a4b50-166">WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="a4b50-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="a4b50-167">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-167">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-168">Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4b50-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="a4b50-169">Para obtener instrucciones, consulte [configurar la acción SOAP para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="a4b50-169">For instructions, see [Configure the SOAP action for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md).</span></span> <span data-ttu-id="a4b50-170">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="a4b50-170">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SiebelXmlParsing"></a><span data-ttu-id="a4b50-171">XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada</span><span class="sxs-lookup"><span data-stu-id="a4b50-171">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="a4b50-172">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-172">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-173">La consola de administración de BizTalk Server proporciona el siguiente error al enviar mensajes a un sistema Siebel:</span><span class="sxs-lookup"><span data-stu-id="a4b50-173">The BizTalk Server Administration console gives the following error when sending messages to a Siebel system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="a4b50-174">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-174">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-175">Si configura un puerto de WCF-Custom importando el archivo de enlace de puerto creado por el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], se especifica la acción en el puerto en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="a4b50-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="a4b50-176">En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="a4b50-176">In the preceding format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="a4b50-177">Por ejemplo, si ha generado el esquema para una operación de consulta en un componente de negocio de Siebel, el nombre de la operación en la acción será "Query".</span><span class="sxs-lookup"><span data-stu-id="a4b50-177">For example, if you generated schema for a Query operation on a Siebel business component, the operation name in the action will be "Query".</span></span> <span data-ttu-id="a4b50-178">Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="a4b50-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="a4b50-179">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-179">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-180">Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.</span><span class="sxs-lookup"><span data-stu-id="a4b50-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration console) are the same.</span></span>  
  
###  <a name="BKMK_SiebelTerminate"></a><span data-ttu-id="a4b50-181">No finalizar la aplicación con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-181">Application using the Siebel adapter does not terminate</span></span>  
 <span data-ttu-id="a4b50-182">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-182">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-183">Una aplicación que utiliza el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Siebel no termina con la versión 7.5 de cliente.</span><span class="sxs-lookup"><span data-stu-id="a4b50-183">An application that uses the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Siebel client version 7.5 does not terminate.</span></span>  
  
 <span data-ttu-id="a4b50-184">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-184">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-185">Esto es debido a un problema de cliente de Siebel donde el proceso no finaliza al cerrar la sesión de un servidor de Siebel.</span><span class="sxs-lookup"><span data-stu-id="a4b50-185">This is because of a Siebel client issue where the process does not terminate when logging off from a Siebel server.</span></span>  
  
 <span data-ttu-id="a4b50-186">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-186">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-187">Asegúrese de que tiene la revisión 7.5.3.17 instalado para el servidor de Siebel, junto con la corrección rápida QF0H05.</span><span class="sxs-lookup"><span data-stu-id="a4b50-187">Make sure you have the patch 7.5.3.17 installed for the Siebel server, along with the quick fix QF0H05.</span></span>  
  
###  <a name="BKMK_SiebelHang"></a><span data-ttu-id="a4b50-188">Adaptador de Siebel puede bloquearse si se reinicia el servidor de Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-188">Siebel adapter may hang if the Siebel server is restarted</span></span>  
 <span data-ttu-id="a4b50-189">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-189">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-190">Si se reinicia el servidor de Siebel mientras el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] está enviando un mensaje en el servidor de Siebel mediante, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede bloquearse.</span><span class="sxs-lookup"><span data-stu-id="a4b50-190">If the Siebel server is restarted while the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is sending a message to the Siebel server using, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] may hang.</span></span>  
  
 <span data-ttu-id="a4b50-191">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-191">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-192">Reinicie la instancia de host de aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4b50-192">Restart the BizTalk application host instance.</span></span> <span data-ttu-id="a4b50-193">Para hacerlo desde la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] expanda consola de administración, en el árbol de consola **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**.</span><span class="sxs-lookup"><span data-stu-id="a4b50-193">To do so from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="a4b50-194">En el panel derecho, haga clic en el nombre de host y, a continuación, seleccione **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="a4b50-194">From the right pane, right-click the host name, and then select **Restart**.</span></span>  
  
###  <a name="BKMK_SiebelAction"></a><span data-ttu-id="a4b50-195">El adaptador no reconoce la acción en el puerto físico incluso aunque use el archivo de enlace generado por el complemento Consume Adapter Service para crear los puertos</span><span class="sxs-lookup"><span data-stu-id="a4b50-195">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="a4b50-196">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-196">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-197">Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en el sistema Siebel, el complemento también crea un archivo de enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="a4b50-197">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Siebel system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="a4b50-198">Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a4b50-198">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="a4b50-199">Sin embargo, cuando se envían mensajes al sistema Siebel usando estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4b50-199">However, when you send messages to the Siebel system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="a4b50-200">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-200">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-201">Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación para la que generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="a4b50-201">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="a4b50-202">Por ejemplo, si genera metadatos para la operación de inserción en el componente de negocio de la cuenta, la acción se establecerá al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4b50-202">For example, if you generate metadata for Insert operation on the Account business component, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 <span data-ttu-id="a4b50-203">Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="a4b50-203">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="a4b50-204">Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="a4b50-204">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="a4b50-205">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-205">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-206">Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="a4b50-206">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="a4b50-207">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="a4b50-207">Do one of the following:</span></span>  
  
-   <span data-ttu-id="a4b50-208">Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo Insert.</span><span class="sxs-lookup"><span data-stu-id="a4b50-208">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Insert.</span></span>  
  
-   <span data-ttu-id="a4b50-209">Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="a4b50-209">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="a4b50-210">Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4b50-210">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a><span data-ttu-id="a4b50-211">Adaptador de Siebel no controla los objetos de Siebel con cadenas XML codificado en el nombre</span><span class="sxs-lookup"><span data-stu-id="a4b50-211">Siebel adapter does not handle Siebel objects with XML encoded strings in the name</span></span>  
 <span data-ttu-id="a4b50-212">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-212">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-213">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no se puede realizar operaciones relacionadas con objetos de Siebel (objetos de negocios, los componentes empresariales, servicios para la empresa, lista de selección, métodos, campos, argumentos, etcetera) que contienen cadenas XML codificado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a4b50-213">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] cannot perform operations involving Siebel objects (business objects, business components, business services, picklist, methods, fields, arguments, etc) that have XML encoded strings in their name.</span></span> <span data-ttu-id="a4b50-214">Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no podrá invocar un método de servicio de negocio con el nombre Time_x0020_Stamp.</span><span class="sxs-lookup"><span data-stu-id="a4b50-214">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] will not be able to invoke a business service method with the name Time_x0020_Stamp.</span></span>  
  
 <span data-ttu-id="a4b50-215">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-215">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-216">Asegúrese de que los objetos de Siebel no contienen cadenas XML codificado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a4b50-216">Make sure the Siebel objects do not contain XML encoded strings in their name.</span></span>  
  
###  <a name="BKMK_SiebelRootNode"></a><span data-ttu-id="a4b50-217">Error con RootNode TypeName en proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a4b50-217">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="a4b50-218">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-218">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-219">En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :</span><span class="sxs-lookup"><span data-stu-id="a4b50-219">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="a4b50-220">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-220">**Resolution**</span></span>  
  
1.  <span data-ttu-id="a4b50-221">Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a4b50-221">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a4b50-222">Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).</span><span class="sxs-lookup"><span data-stu-id="a4b50-222">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SiebelVS2008"></a><span data-ttu-id="a4b50-223">Advertencia de enlace no válido al utilizar el adaptador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a4b50-223">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="a4b50-224">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a4b50-224">**Problem**</span></span>  
  
 <span data-ttu-id="a4b50-225">Cuando se utiliza el adaptador para crear una aplicación en Visual Studio y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4b50-225">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="a4b50-226">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a4b50-226">**Cause**</span></span>  
  
 <span data-ttu-id="a4b50-227">Esta advertencia aparece porque la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace, `siebelBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b50-227">This warning appears because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding, `siebelBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="a4b50-228">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a4b50-228">**Resolution**</span></span>  
  
 <span data-ttu-id="a4b50-229">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="a4b50-229">You can safely ignore this warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b50-230">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4b50-230">See Also</span></span>  
[<span data-ttu-id="a4b50-231">Solucionar problemas del adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="a4b50-231">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)