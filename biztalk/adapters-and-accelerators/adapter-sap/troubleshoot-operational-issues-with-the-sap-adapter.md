---
title: Solucionar problemas de funcionamiento con el adaptador SAP en BizTalk | Documentos de Microsoft
description: "Comunes de los errores, problemas y soluciones con mySAP adaptador en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5298782f23cb8c7c32a2bcbd512f3a1b78f8a69d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a><span data-ttu-id="25ffb-103">Solucionar problemas de funcionamiento con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-103">Troubleshoot Operational Issues with the SAP adapter</span></span>
<span data-ttu-id="25ffb-104">Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
### <a name="enable-tracing"></a><span data-ttu-id="25ffb-105">Habilitar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="25ffb-105">Enable tracing</span></span>  
 <span data-ttu-id="25ffb-106">Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-106">For information about tracing support in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Diagnostic Tracing and Message Logging for the SAP adapter](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span></span>  
  
##  <span data-ttu-id="25ffb-107"><a name="client_dll"></a>Error al cargar el enlace</span><span class="sxs-lookup"><span data-stu-id="25ffb-107"><a name="client_dll"></a> Error loading the binding</span></span>  
 <span data-ttu-id="25ffb-108">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-108">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-109">Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], la interfaz gráfica de usuario produce el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="25ffb-109">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="25ffb-110">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-110">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-111">Al iniciar la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] carga los enlaces del adaptador para todos los adaptadores instalados.</span><span class="sxs-lookup"><span data-stu-id="25ffb-111">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="25ffb-112">En cambio, los enlaces del adaptador están depende del software de cliente específico para la aplicación de empresa.</span><span class="sxs-lookup"><span data-stu-id="25ffb-112">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="25ffb-113">Es posible que tenga este problema para uno o ambos de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="25ffb-113">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="25ffb-114">El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.</span><span class="sxs-lookup"><span data-stu-id="25ffb-114">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="25ffb-115">Se realizó una instalación típica o completar del adaptador, que se instala todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-115">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="25ffb-116">Sin embargo, podrían instalarse las bibliotecas de cliente LOB para solo una aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="25ffb-116">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="25ffb-117">Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.</span><span class="sxs-lookup"><span data-stu-id="25ffb-117">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="25ffb-118">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-118">**Resolution**</span></span>  
  
-   <span data-ttu-id="25ffb-119">Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.</span><span class="sxs-lookup"><span data-stu-id="25ffb-119">Make sure you do a Custom installation of the adapters to install only the adapter you need.</span></span>  
  
-   <span data-ttu-id="25ffb-120">Asegúrese de que las versiones de cliente LOB necesarias se instalan en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-120">Make sure the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="25ffb-121">[Los sistemas LOB](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) enumera las versiones compatibles.</span><span class="sxs-lookup"><span data-stu-id="25ffb-121">[Supported LOB systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions.</span></span> <span data-ttu-id="25ffb-122">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] también requiere determinado archivos DLL interactuar con el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-122">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] also requires certain DLLs to interface with the SAP system.</span></span> <span data-ttu-id="25ffb-123">Para obtener más información acerca de los archivos DLL requerida por el adaptador, vea [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-123">For more information about the DLLs required by the adapter, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <span data-ttu-id="25ffb-124"><a name="BKMK_SAPDisplay"></a>El adaptador SAP es falta en la consola de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="25ffb-124"><a name="BKMK_SAPDisplay"></a> The SAP adapter is missing in BizTalk Administration console</span></span>  
 <span data-ttu-id="25ffb-125">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-125">**Problem**</span></span>  
  
<span data-ttu-id="25ffb-126">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] incluido con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="25ffb-126">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] included with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="25ffb-127">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-127">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-128">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="25ffb-128">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="25ffb-129">Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="25ffb-130">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-130">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-131">Puede agregar explícitamente la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-131">You can explicitly add the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
##  <span data-ttu-id="25ffb-132"><a name="BKMK_SAPConnOpen"></a>Error al abrir una conexión a SAP no tienen archivos DLL</span><span class="sxs-lookup"><span data-stu-id="25ffb-132"><a name="BKMK_SAPConnOpen"></a> DLLs are missing error opening a connection to SAP</span></span>  
 <span data-ttu-id="25ffb-133">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-133">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-134">Al intentar abrir una conexión con el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], aparece un cuadro de diálogo en el sistema SAP, que le informa de que faltan algunos archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="25ffb-134">When you try to open a connection to the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], a dialog box appears in the SAP system, informing that some DLLs are missing.</span></span>  
  
 <span data-ttu-id="25ffb-135">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-135">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-136">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] librfc32u.dll se utiliza para establecer una conexión con el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses librfc32u.dll to establish a connection with the SAP system.</span></span> <span data-ttu-id="25ffb-137">Librfc32u.dll, a su vez, se requiere un conjunto de archivos DLL en la función.</span><span class="sxs-lookup"><span data-stu-id="25ffb-137">The librfc32u.dll, in turn, requires a set of DLLs to function.</span></span> <span data-ttu-id="25ffb-138">Este error aparece si estas DLL compatibles no se agregan a la variable de ruta de acceso en el equipo donde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="25ffb-138">You get this error if these supporting DLLs are not added to the PATH variable on the computer where the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is installed.</span></span>  
  
 <span data-ttu-id="25ffb-139">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-139">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-140">Hacer referencia a la tabla proporcionada como una resolución para el [Error al cargar los enlaces del adaptador](#client_dll) problema.</span><span class="sxs-lookup"><span data-stu-id="25ffb-140">Refer to the table provided as a resolution to the [Error in loading the adapter bindings](#client_dll) issue.</span></span> <span data-ttu-id="25ffb-141">La tabla enumeran los archivos DLL auxiliares necesarias para interactuar con el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-141">The table lists the supporting DLLs required to interface with the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <span data-ttu-id="25ffb-142"><a name="BKMK_SAPXmlRetrieve"></a>Error al recuperar el XML con más de 65.536 nodos</span><span class="sxs-lookup"><span data-stu-id="25ffb-142"><a name="BKMK_SAPXmlRetrieve"></a> Error retrieving XML with more than 65,536 nodes</span></span>  
 <span data-ttu-id="25ffb-143">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-143">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-144">El adaptador produce el siguiente error al recuperar la salida XML que tiene más de 65.536 nodos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-144">The adapter gives the following error while retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="25ffb-145">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-145">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-146">El adaptador no se puede serializar y deserializar un objeto con más de 65.536 elementos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-146">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="25ffb-147">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-147">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-148">Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro de cualquiera de las dos maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="25ffb-148">You can fix this issue by setting the `maxItemsInObjectGraph` parameter in either of the following two ways:</span></span>  
  
-   <span data-ttu-id="25ffb-149">Establezca este parámetro cambiando el `maxItemsInObjectGraph` parámetro en el `ServiceBehavior` atributo en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="25ffb-149">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="25ffb-150">Agregue lo siguiente al archivo app.config de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25ffb-150">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="25ffb-151">Un ejemplo app.config tendrá un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="25ffb-151">A sample app.config will look like the following.</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  \</system.serviceModel>  
</configuration>  
```  
  
##  <span data-ttu-id="25ffb-152"><a name="BKMK_SAPConnURI"></a>Error al escribir un URI de conexión para un puerto personalizado de WCF en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="25ffb-152"><a name="BKMK_SAPConnURI"></a> Error entering a connection URI for a WCF-Custom port in BizTalk Server</span></span>  
 <span data-ttu-id="25ffb-153">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-153">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="25ffb-154">produce el siguiente error cuando se especifica un URI de conexión para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-154"> gives the following error when you specify a connection URI to connect to the SAP system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="25ffb-155">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-155">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-156">El URI de conexión no cumple con el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="25ffb-156">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="25ffb-157">Por ejemplo, el valor de un parámetro podría contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="25ffb-157">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="25ffb-158">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-158">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-159">Asegúrese de que la conexión URI especifica cumple el formato de codificación estándar.</span><span class="sxs-lookup"><span data-stu-id="25ffb-159">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="25ffb-160">Por ejemplo, un espacio en blanco debe sustituirse por "% 20".</span><span class="sxs-lookup"><span data-stu-id="25ffb-160">For example, a blank space must be replaced by "%20".</span></span>  
  
##  <span data-ttu-id="25ffb-161"><a name="BKMK_SAPOperate"></a>Error de System.ArgumentNullException mientras se completa una operación en SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-161"><a name="BKMK_SAPOperate"></a> System.ArgumentNullException error while completing an operation on SAP</span></span>  
 <span data-ttu-id="25ffb-162">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-162">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-163">El adaptador produce el siguiente error al realizar cualquier operación en el sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-163">The adapter gives the following error when performing any operation on the SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 <span data-ttu-id="25ffb-164">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-164">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-165">No se especifica la acción de WCF para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="25ffb-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="25ffb-166">WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="25ffb-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="25ffb-167">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-167">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-168">Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25ffb-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="25ffb-169">Para obtener instrucciones, consulte [configurar la acción SOAP para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-169">For instructions, see [Configure the SOAP action for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span></span> <span data-ttu-id="25ffb-170">Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para ver una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="25ffb-170">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) to see a list of actions for each operation.</span></span>  
  
##  <span data-ttu-id="25ffb-171"><a name="BKMK_SAPXmlParsing"></a>XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada</span><span class="sxs-lookup"><span data-stu-id="25ffb-171"><a name="BKMK_SAPXmlParsing"></a> XmlReaderParsingException due to incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="25ffb-172">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-172">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-173">La consola de administración de BizTalk Server produce el siguiente error al enviar mensajes a un sistema SAP:</span><span class="sxs-lookup"><span data-stu-id="25ffb-173">The BizTalk Server Administration Console gives the following error when sending messages to an SAP system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="25ffb-174">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-174">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-175">Si configura un puerto de WCF-Custom importando el archivo de enlace de puerto creado por el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], se especifica la acción en el puerto en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="25ffb-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="25ffb-176">En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="25ffb-176">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="25ffb-177">Por ejemplo, si ha generado el esquema para RFC_CUSTOMER_GET, el nombre de la operación en la acción será "RFC_CUSTOMER_GET".</span><span class="sxs-lookup"><span data-stu-id="25ffb-177">For example, if you generated schema for RFC_CUSTOMER_GET, the operation name in the action will be "RFC_CUSTOMER_GET".</span></span> <span data-ttu-id="25ffb-178">Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="25ffb-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="25ffb-179">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-179">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-180">Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
##  <span data-ttu-id="25ffb-181"><a name="BKMK_SAPHundredCons"></a>Error al abrir más de 100 conexiones para SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-181"><a name="BKMK_SAPHundredCons"></a> Error opening more than 100 connections to SAP</span></span>  
 <span data-ttu-id="25ffb-182">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-182">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-183">El adaptador devuelve la siguiente excepción al abrir más de 100 conexiones al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-183">The adapter throws the following exception when opening more than 100 connections to the SAP system.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 <span data-ttu-id="25ffb-184">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-184">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-185">De forma predeterminada, SAP no habilita más de 100 conexiones en el sistema.</span><span class="sxs-lookup"><span data-stu-id="25ffb-185">By default, SAP does not enable more than 100 connections into the system.</span></span>  
  
 <span data-ttu-id="25ffb-186">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-186">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-187">Para aumentar el número máximo de conexiones, debe crear una variable de entorno en el equipo que tenga las bibliotecas de cliente SAP instalado y configurado en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-187">To increase the maximum number of connections, you must create an environment variable on the computer that has the SAP client libraries installed and set it to a numeric value.</span></span> <span data-ttu-id="25ffb-188">El valor especificado para esta variable de entorno es el número máximo de conexiones que pueden realizarse en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-188">The value you specify for this environment variable is the maximum number of connections that can be made into the SAP system.</span></span> <span data-ttu-id="25ffb-189">Crear la variable de entorno con los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="25ffb-189">Create the environment variable with the following details:</span></span>  
  
-   <span data-ttu-id="25ffb-190">**Nombre de la variable**: CPIC_MAX_CONV</span><span class="sxs-lookup"><span data-stu-id="25ffb-190">**Variable name**: CPIC_MAX_CONV</span></span>  
  
-   <span data-ttu-id="25ffb-191">**Valor de la variable**: cualquier valor numérico positivo.</span><span class="sxs-lookup"><span data-stu-id="25ffb-191">**Variable value**: any positive numeric value.</span></span> <span data-ttu-id="25ffb-192">Por ejemplo, para habilitar 200 conexiones en el sistema SAP, especifique el valor 200.</span><span class="sxs-lookup"><span data-stu-id="25ffb-192">For example, to enable 200 connections into the SAP system, specify the value as 200.</span></span>  
  
 <span data-ttu-id="25ffb-193">Para obtener instrucciones sobre cómo crear una variable de entorno, consulte "Cómo crear Variables del sistema en Windows 2000" en [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span><span class="sxs-lookup"><span data-stu-id="25ffb-193">For instructions on creating an environment variable, see "How To Create System Variables in Windows 2000" at [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span></span>  
  
##  <span data-ttu-id="25ffb-194"><a name="BKMK_SAPIDOCMetadata"></a>Generar errores o recuperar los metadatos para IDOC</span><span class="sxs-lookup"><span data-stu-id="25ffb-194"><a name="BKMK_SAPIDOCMetadata"></a> Error generating or retrieving metadata for IDOCs</span></span>  
 <span data-ttu-id="25ffb-195">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-195">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-196">Al generar metadatos para la **recepción** operación para un IDOC en un sistema SAP, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce el siguiente error.</span><span class="sxs-lookup"><span data-stu-id="25ffb-196">While generating metadata for the **Receive** operation for an IDOC in an SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives the following error.</span></span>  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 <span data-ttu-id="25ffb-197">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-197">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-198">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la RFC IDOCTYPE_READ_COMPLETE para recuperar los metadatos de la **recepción** operación para un IDOC.</span><span class="sxs-lookup"><span data-stu-id="25ffb-198">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the IDOCTYPE_READ_COMPLETE RFC to retrieve the metadata for the **Receive** operation for an IDOC.</span></span> <span data-ttu-id="25ffb-199">Invocar esta RFC requiere permisos de usuario específico en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-199">Invoking this RFC requires specific user permissions in the SAP system.</span></span> <span data-ttu-id="25ffb-200">Para generar los metadatos, si se ha conectado al sistema SAP mediante una credencial que no tiene permiso para invocar la RFC IDOCTYPE_READ_COMPLETE, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce un error.</span><span class="sxs-lookup"><span data-stu-id="25ffb-200">To generate metadata, if you have connected to the SAP system using a credential that does not have permission to invoke the IDOCTYPE_READ_COMPLETE RFC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an error.</span></span>  
  
 <span data-ttu-id="25ffb-201">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-201">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-202">Inicie sesión en la GUI de SAP con las mismas credenciales que se hubiera usado para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="25ffb-202">Log in to the SAP GUI using the same credentials you had used for the adapter.</span></span> <span data-ttu-id="25ffb-203">Navegue hasta la transacción SE37 y escriba el nombre de la solicitud de cambio para ejecutar como IDOCTYPE_READ_COMPLETE.</span><span class="sxs-lookup"><span data-stu-id="25ffb-203">Navigate to transaction SE37, and enter the name of the RFC to execute as IDOCTYPE_READ_COMPLETE.</span></span>  
  
 <span data-ttu-id="25ffb-204">Para los parámetros de entrada PI_IDOCTYP y PI_CIMTYP, escriba los valores correspondientes a lo IDoc personalizado.</span><span class="sxs-lookup"><span data-stu-id="25ffb-204">For the input parameters PI_IDOCTYP and PI_CIMTYP, enter the values corresponding to the custom IDoc.</span></span> <span data-ttu-id="25ffb-205">Para los parámetros PI_VERSION y PI_RELEASE, especifique los mismos valores que se haya elegido en la interfaz de usuario de metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="25ffb-205">For the parameters PI_VERSION and PI_RELEASE, enter the same values as being chosen in the Adapter Metadata UI.</span></span> <span data-ttu-id="25ffb-206">Y presione F8 para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="25ffb-206">And, press F8 to execute.</span></span>  
  
 <span data-ttu-id="25ffb-207">Debe obtener la misma excepción como lo que el adaptador recibe, con más información sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="25ffb-207">You should get the same exception as what the adapter receives, with more information about the issue.</span></span>  
  
 <span data-ttu-id="25ffb-208">Si está aún no se ha podido resolver el problema, generar un esquema para el **ReceiveIdoc** operación en lugar de la **recepción** operación.</span><span class="sxs-lookup"><span data-stu-id="25ffb-208">If you are still not able to resolve the issue, generate a schema for the **ReceiveIdoc** operation instead of the **Receive** operation.</span></span> <span data-ttu-id="25ffb-209">En este caso, el adaptador SAP no usa IDOCTYPE_READ_COMPLETE y no produce ningún error.</span><span class="sxs-lookup"><span data-stu-id="25ffb-209">In this case, the SAP adapter does not use IDOCTYPE_READ_COMPLETE, and does not throw any error.</span></span>  
  
##  <span data-ttu-id="25ffb-210"><a name="BKMK_SAPIDOCReceive"></a>Error al enviar o recibir IDOC que haya no lanzados segmentos</span><span class="sxs-lookup"><span data-stu-id="25ffb-210"><a name="BKMK_SAPIDOCReceive"></a> Error sending or receiving IDOCs that have unreleased segments</span></span>  
 <span data-ttu-id="25ffb-211">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-211">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-212">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ofrece un XmlReaderParsingException al enviar IDOC (mediante **enviar** operación) o recibir IDOC (mediante **recepción** operación) que han no lanzados segmentos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-212">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException while sending IDOCs (using **Send** operation) or receiving IDOCs (using **Receive** operation) that have unreleased segments.</span></span>  
  
 <span data-ttu-id="25ffb-213">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-213">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-214">IDOC se constituye de segmentos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-214">IDOCs are constituted of segments.</span></span> <span data-ttu-id="25ffb-215">Durante la generación de metadatos, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera todos los segmentos de lanzamiento que se encuentran en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-215">While generating metadata, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] retrieves all the released segments that are present in the SAP system.</span></span> <span data-ttu-id="25ffb-216">Sin embargo, si el cliente de adaptador usa los metadatos para realizar una operación como la recepción de un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ofrece un XmlReaderParsingException.</span><span class="sxs-lookup"><span data-stu-id="25ffb-216">However, when the adapter client uses the metadata to perform an operation such as receiving an IDOC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException.</span></span> <span data-ttu-id="25ffb-217">Esto ocurre porque cuando se recibe el IDOC, el sistema SAP posible que haya enviado algunos segmentos no lanzados así, los metadatos para el que no fue generado por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="25ffb-217">This occurs because when the IDOC is received, the SAP system might have sent some unreleased segments as well, the metadata for which was not generated by the adapter.</span></span>  
  
 <span data-ttu-id="25ffb-218">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-218">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-219">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="25ffb-219">Do any of the following:</span></span>  
  
-   <span data-ttu-id="25ffb-220">Actualizar el sistema SAP mediante la aplicación de revisiones apropiadas para los segmentos no lanzados.</span><span class="sxs-lookup"><span data-stu-id="25ffb-220">Upgrade your SAP system by applying appropriate patches for the unreleased segments.</span></span>  
  
-   <span data-ttu-id="25ffb-221">Use **SendIdoc** o **ReceiveIdoc** operaciones para enviar y recibir IDOC respectivamente.</span><span class="sxs-lookup"><span data-stu-id="25ffb-221">Use **SendIdoc** or **ReceiveIdoc** operations to send and receive IDOCs respectively.</span></span> <span data-ttu-id="25ffb-222">Para obtener más información acerca de estas operaciones, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-222">For more information about these operations, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <span data-ttu-id="25ffb-223"><a name="BKMK_SAPIDOCSend"></a>Error al enviar el archivo sin formato IDOC a SAP que se han recibido mediante el FilePort de SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-223"><a name="BKMK_SAPIDOCSend"></a> Error sending flat-file IDOCs to SAP that were received using the SAP FilePort</span></span>  
 <span data-ttu-id="25ffb-224">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-224">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-225">Si intenta enviar (mediante **enviar** operación) un IDOC de archivo sin formato a un sistema SAP que se ha generado mediante una FilePort de SAP, el analizador de archivos sin formato en la orquestación de BizTalk no puede convertir el archivo flatf en un formato XML, con lo que se producen errores en el IDOD **enviar** operación.</span><span class="sxs-lookup"><span data-stu-id="25ffb-225">If you try to send (using **Send** operation) a flat-file IDOC to an SAP system that was generated using an SAP FilePort, the flat-file parser in the BizTalk orchestration fails to convert the flatf-file to an XML format, thereby failing the IDOD **Send** operation.</span></span>  
  
 <span data-ttu-id="25ffb-226">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-226">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-227">Cuando el sistema SAP genera un IDOC mediante un FilePort, que recorta desactivar todos los espacios en blanco al final de un segmento de.</span><span class="sxs-lookup"><span data-stu-id="25ffb-227">When the SAP system generates an IDOC using a FilePort, it trims off all the empty spaces at the end of a segment.</span></span> <span data-ttu-id="25ffb-228">Sin embargo, el analizador de archivos sin formato espera que los datos del último campo en el segmento que se va a estar presente para convertir correctamente el archivo sin formato en XML.</span><span class="sxs-lookup"><span data-stu-id="25ffb-228">However, the flat-file parser expects the data of the last field in the segment to be present to successfully convert the flat-file to XML.</span></span> <span data-ttu-id="25ffb-229">Como los espacios vacíos que no se encuentran en el segmento, el analizador de archivos sin formato no se puede analizar el archivo sin formato a XML.</span><span class="sxs-lookup"><span data-stu-id="25ffb-229">Because the empty spaces are not present in the segment, the flat-file parser fails to parse the flat-file to XML.</span></span>  
  
 <span data-ttu-id="25ffb-230">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-230">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-231">Para este tipo IDOC de archivo sin formato generado mediante la FilePort de SAP, use la **SendIdoc** operación en su lugar.</span><span class="sxs-lookup"><span data-stu-id="25ffb-231">For such flat-file IDOCs generated using the SAP FilePort, use the **SendIdoc** operation instead.</span></span> <span data-ttu-id="25ffb-232">Para obtener más información acerca de esta operación, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="25ffb-232">For more information about this operation, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <span data-ttu-id="25ffb-233"><a name="BKMK_SAPRecIDOCCompat"></a>Error al recibir IDOC desde SAP si EnableBizTalkCompatibilityMode propiedad se establece en true</span><span class="sxs-lookup"><span data-stu-id="25ffb-233"><a name="BKMK_SAPRecIDOCCompat"></a> Error receiving IDOCs from SAP if EnableBizTalkCompatibilityMode property is set to true</span></span>  
 <span data-ttu-id="25ffb-234">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-234">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-235">La siguiente excepción se produce al recibir un IDOC con el **EnableBizTalkCompatibilityMode** enlace propiedad establecida en true:</span><span class="sxs-lookup"><span data-stu-id="25ffb-235">The following exception is encountered while receiving an IDOC with the **EnableBizTalkCompatibilityMode** binding property set to true:</span></span>  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 <span data-ttu-id="25ffb-236">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-236">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-237">Si la propiedad de enlace **EnableBizTalkCompatibilityMode** está establecido en **true**, debe agregar el esquema de propiedades de BizTalk DLL para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un recurso en la aplicación de BizTalk, es decir, el en el que se implementa el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="25ffb-237">If the binding property **EnableBizTalkCompatibilityMode** is set to **true**, you must add the BizTalk property schema DLL for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a resource in your BizTalk application, that is, the application in which your project is deployed.</span></span>  
  
 <span data-ttu-id="25ffb-238">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-238">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-239">El nombre para el esquema de propiedad de BizTalk para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span><span class="sxs-lookup"><span data-stu-id="25ffb-239">The name for the BizTalk property schema for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span></span> <span data-ttu-id="25ffb-240">Este servicio se instala mediante el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación en \<unidad de instalación >: \ Archivos de programa\Microsoft BizTalk adaptador Pack\bin.</span><span class="sxs-lookup"><span data-stu-id="25ffb-240">This is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup under \<installation drive>:\ Program Files\Microsoft BizTalk Adapter Pack\bin.</span></span> <span data-ttu-id="25ffb-241">Realice las tareas siguientes para agregar este ensamblado como un recurso en la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25ffb-241">Perform the following tasks to add this assembly as a resource in your BizTalk application.</span></span>  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a><span data-ttu-id="25ffb-242">Agregar un ensamblado como un recurso de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="25ffb-242">Add an assembly as a resource in BizTalk application</span></span>  
  
1.  <span data-ttu-id="25ffb-243">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="25ffb-243">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="25ffb-244">En el árbol de consola, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, la aplicación a la que desea agregar un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25ffb-244">In the console tree, expand **BizTalk Group**, expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="25ffb-245">Expanda **aplicaciones** y la aplicación a la que desea agregar un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25ffb-245">Expand **Applications** and the application to which you want to add a BizTalk assembly.</span></span>  
  
4.  <span data-ttu-id="25ffb-246">Haga clic en **recursos**, seleccione **agregar**y, a continuación, haga clic en **ensamblados de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="25ffb-246">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
5.  <span data-ttu-id="25ffb-247">Haga clic en **agregar**, navegue hasta la carpeta que contiene el archivo de ensamblado de BizTalk, seleccione el archivo de ensamblado de BizTalk y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="25ffb-247">Click **Add**, navigate to the folder containing the BizTalk assembly file, select the BizTalk assembly file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="25ffb-248">En **opciones**, especifique las opciones para instalar el ensamblado de BizTalk en la GAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25ffb-248">In **Options**, specify the options for installing the BizTalk assembly to the GAC, and then click **OK**.</span></span>  
  
##  <span data-ttu-id="25ffb-249"><a name="BKMK_SAPIDOCValidate"></a>Error en la validación al recibir IDOC desde un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-249"><a name="BKMK_SAPIDOCValidate"></a> Error in validation while receiving IDOCs from an SAP system</span></span>  
 <span data-ttu-id="25ffb-250">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-250">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-251">Un IDOC recibido desde un sistema SAP no puede validar con un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-251">An IDOC received from an SAP system fails validation with an error similar to the following:</span></span>  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 <span data-ttu-id="25ffb-252">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-252">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-253">Los metadatos generados para recibir un IDOC contienen los valores permitidos que se pueden recibir de una determinada columna como parte de la operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="25ffb-253">The metadata generated for receiving an IDOC contains the permissible values that can be received for a particular column as part of the receive operation.</span></span> <span data-ttu-id="25ffb-254">Estos valores se exponen como enumeración de los metadatos generados.</span><span class="sxs-lookup"><span data-stu-id="25ffb-254">These values are exposed as enumeration in the generated metadata.</span></span> <span data-ttu-id="25ffb-255">Sin embargo, cuando realmente se recibe el IDOC, el valor recibido podría ser diferente de los valores enumerados.</span><span class="sxs-lookup"><span data-stu-id="25ffb-255">However, when the IDOC is actually received, the value received could be different from the enumerated values.</span></span> <span data-ttu-id="25ffb-256">Por lo tanto, la operación de recepción se produce un error al validar los valores.</span><span class="sxs-lookup"><span data-stu-id="25ffb-256">Hence the receive operation fails while validating the values.</span></span> <span data-ttu-id="25ffb-257">Por ejemplo, en el error anterior mensaje falla la validación de la columna TAXBS.</span><span class="sxs-lookup"><span data-stu-id="25ffb-257">For example, in the above error message validation fails for the TAXBS column.</span></span>  
  
 <span data-ttu-id="25ffb-258">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-258">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-259">Debe editar manualmente la enumeración en el esquema (para los proyectos de BizTalk) o el proxy de cliente (para los proyectos de .NET mediante WCF el modelo de servicio) para incluir el valor recibido desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-259">You must manually edit the enumeration in schema (for BizTalk projects) or the client proxy (for .NET projects using WCF service model) to include the value received from the SAP system.</span></span>  
  
##  <span data-ttu-id="25ffb-260"><a name="BKMK_SAPFFIDOC"></a>IDOC de archivo sin formato, antes y después de convertir a XML, no es idéntico</span><span class="sxs-lookup"><span data-stu-id="25ffb-260"><a name="BKMK_SAPFFIDOC"></a> Flat-file IDOCs, before and after converting to XML, are not identical</span></span>  
 <span data-ttu-id="25ffb-261">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-261">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-262">Si utiliza un analizador de archivos planos para convertir un IDOC de archivo sin formato a un XML con el esquema y, a continuación, convertir el código XML en un IDOC de archivo sin formato a través de una canalización mediante el esquema, lo dos IDOC de archivo sin formato no es idéntico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-262">If you use a flat file parser to convert a flat-file IDOC to an XML using the schema, and then convert the XML back to a flat-file IDOC through a pipeline using the schema, the two flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="25ffb-263">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-263">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-264">Al generar el XML de un IDOC de archivo sin formato, el analizador de archivos planos no genera los nodos XML con valores en blanco.</span><span class="sxs-lookup"><span data-stu-id="25ffb-264">When generating the XML from a flat-file IDOC, the flat file parser does not generate the XML nodes with blank values.</span></span> <span data-ttu-id="25ffb-265">Cuando este XML se convierte a un archivo sin formato, los nodos que faltan en el código XML no se reflejan en el IDOC de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="25ffb-265">When this XML is converted back to a flat-file, the nodes missing from the XML are not reflected in the flat-file IDOC.</span></span> <span data-ttu-id="25ffb-266">Por lo tanto, el IDOC de archivo sin formato no es idéntico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-266">Hence the flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="25ffb-267">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-267">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-268">En el esquema que se utiliza para convertir el archivo sin formato XML y viceversa, dentro de la definición de nodo de "Envío" o "Recepción", haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-268">In the schema used to convert the flat-file to XML and vice-versa, within the "Send" or "Receive" node definition, do the following:</span></span>  
  
1.  <span data-ttu-id="25ffb-269">Establecer el **suppress_empty_nodes** propiedad **false** y establezca el **generate_empty_nodes** propiedad **true**.</span><span class="sxs-lookup"><span data-stu-id="25ffb-269">Set the **suppress_empty_nodes** property to **false** and set the **generate_empty_nodes** property to **true**.</span></span> <span data-ttu-id="25ffb-270">De forma predeterminada, el **suppress_empty_nodes** propiedad está establecida en **true** y **generate_empty_nodes** propiedad está establecida en **false**, y por lo tanto, todos los nodos vacíos no se reflejan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="25ffb-270">By default, the **suppress_empty_nodes** property is set to **true** and the **generate_empty_nodes** property is set to **false**, and hence all empty nodes are not reflected in the XML.</span></span>  
  
2.  <span data-ttu-id="25ffb-271">El archivo sin formato puede contener un retorno de carro adicional al final.</span><span class="sxs-lookup"><span data-stu-id="25ffb-271">The flat-file may contain an extra carriage return at the end.</span></span> <span data-ttu-id="25ffb-272">Puede establecer la **suppress_trailing_delimiters** propiedad **Sí** para evitar este retorno de carro adicional.</span><span class="sxs-lookup"><span data-stu-id="25ffb-272">You can set the **suppress_trailing_delimiters** property to **Yes** to avoid this extra carriage return.</span></span> <span data-ttu-id="25ffb-273">Esta propiedad también se expone como la **Suprimir delimitadores finales** propiedad si abre el esquema en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-273">This property is also exposed as the **Suppress Trailing Delimiters** property if you open the schema in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
##  <span data-ttu-id="25ffb-274"><a name="BKMK_SAPAction"></a>Error de acción incorrecta con un puerto físico crear con un archivo de enlace</span><span class="sxs-lookup"><span data-stu-id="25ffb-274"><a name="BKMK_SAPAction"></a> Incorrect Action error using a physical port creating with a binding file</span></span>  
 <span data-ttu-id="25ffb-275">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-275">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-276">Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en el sistema SAP, el complemento también crea un archivo de enlace de puerto.</span><span class="sxs-lookup"><span data-stu-id="25ffb-276">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the SAP system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="25ffb-277">Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="25ffb-277">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="25ffb-278">Sin embargo, cuando se envían mensajes al sistema SAP usando estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-278">However, when you send messages to the SAP system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="25ffb-279">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-279">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-280">Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación para la que generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="25ffb-280">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="25ffb-281">Por ejemplo, si genera metadatos para RFC_CUSTOMER_GET, se establecerá la acción a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-281">For example, if you generate metadata for RFC_CUSTOMER_GET, the action will be set to the following:</span></span>  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 <span data-ttu-id="25ffb-282">Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-282">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="25ffb-283">Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="25ffb-283">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="25ffb-284">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-284">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-285">Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-285">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="25ffb-286">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="25ffb-286">Do one of the following:</span></span>  
  
-   <span data-ttu-id="25ffb-287">Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo RFC_CUSTOMER_GET.</span><span class="sxs-lookup"><span data-stu-id="25ffb-287">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example RFC_CUSTOMER_GET.</span></span>  
  
-   <span data-ttu-id="25ffb-288">Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico.</span><span class="sxs-lookup"><span data-stu-id="25ffb-288">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="25ffb-289">Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-289">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <span data-ttu-id="25ffb-290"><a name="BKMK_SAPTableParams"></a>El mensaje de respuesta de una operación que se ejecutó en SAP no contiene ningún parámetro de tabla</span><span class="sxs-lookup"><span data-stu-id="25ffb-290"><a name="BKMK_SAPTableParams"></a> The response message for an operation ran on SAP does not contain any table parameters</span></span>  
 <span data-ttu-id="25ffb-291">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-291">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-292">Si utiliza el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para ejecutar una operación en el sistema SAP que devuelve un gran número de tablas y cada tabla tiene un gran número de registros, que se importe a un conjunto de datos grande que se devuelve como parte del mensaje de respuesta desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-292">If you use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to execute an operation on the SAP system that returns a large number of tables, and each table has a large number of records, that will amount to a large dataset being returned as part of the response message from the SAP system.</span></span> <span data-ttu-id="25ffb-293">Por lo tanto, de forma predeterminada, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no devuelve ningún parámetro de tabla como parte del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="25ffb-293">So, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not return any table parameters as part of the response message.</span></span>  
  
 <span data-ttu-id="25ffb-294">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-294">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-295">Puede solicitar las tablas que desea [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para devolver como parte de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="25ffb-295">You can request the tables that you want [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to return as part of the response.</span></span> <span data-ttu-id="25ffb-296">Para ello, puede proporcionar un parámetro de una tabla vacía como parte del mensaje de solicitud que envía al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-296">You can do so by providing an empty table parameter as part of the request message that you send to the SAP system.</span></span> <span data-ttu-id="25ffb-297">Por ejemplo, `<table_parameter_name />`.</span><span class="sxs-lookup"><span data-stu-id="25ffb-297">For example, `<table_parameter_name />`.</span></span>  
  
##  <span data-ttu-id="25ffb-298"><a name="BKMK_SAPIncorrectCreds"></a>Los clientes de adaptador no recibir la respuesta de SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-298"><a name="BKMK_SAPIncorrectCreds"></a> Adapter Clients do not receive the response from SAP</span></span>
 <span data-ttu-id="25ffb-299">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-299">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-300">Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales de WCF-custom puerto son correctos, no se procesan los mensajes de solicitud de envío.</span><span class="sxs-lookup"><span data-stu-id="25ffb-300">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="25ffb-301">Después de especificar las credenciales correctas, el mensaje se envía al sistema SAP y se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="25ffb-301">After you specify the correct credentials, the message is sent to the SAP system and a response is received.</span></span> <span data-ttu-id="25ffb-302">Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida.</span><span class="sxs-lookup"><span data-stu-id="25ffb-302">However, the response message is not available to the out port.</span></span>  
  
 <span data-ttu-id="25ffb-303">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-303">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-304">Reinicie la instancia de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="25ffb-304">Restart the BizTalk host instance.</span></span>  
  
##  <span data-ttu-id="25ffb-305"><a name="BKMK_SAPInboundConn"></a>Problemas de conectividad de recibir un mensaje entrante desde el servidor SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-305"><a name="BKMK_SAPInboundConn"></a> Connectivity issues receiving an inbound message from the SAP server</span></span>  
 <span data-ttu-id="25ffb-306">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-306">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-307">Muestra el siguiente error sólo al recibir un mensaje entrante desde el servidor SAP utilizando un WCF-Custom puerto de recepción para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-307">You get the following error only while receiving an inbound message from the SAP server using a WCF-Custom receive port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 <span data-ttu-id="25ffb-308">Sin embargo, es posible correctamente enviar mensajes al sistema SAP mediante un WCF-Custom puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="25ffb-308">However, you are successfully able to send messages to the SAP system using a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="25ffb-309">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-309">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-310">Instale la GUI de SAP en el mismo equipo donde se está ejecutando al cliente de adaptador e intente volver a recibir el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="25ffb-310">Install the SAP GUI on the same computer where you are running the adapter client and try receiving the inbound message again.</span></span> <span data-ttu-id="25ffb-311">Para obtener más información acerca de cómo instalar la GUI de SAP, consulte la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-311">For more information about how to install the SAP GUI, refer to SAP documentation.</span></span>  
  
##  <span data-ttu-id="25ffb-312"><a name="BKMK_SAPRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="25ffb-312"><a name="BKMK_SAPRootNode"></a> Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="25ffb-313">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-313">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-314">En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :</span><span class="sxs-lookup"><span data-stu-id="25ffb-314">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="25ffb-315">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-315">**Resolution**</span></span>  
  
1.  <span data-ttu-id="25ffb-316">Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25ffb-316">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="25ffb-317">Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).</span><span class="sxs-lookup"><span data-stu-id="25ffb-317">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
##  <span data-ttu-id="25ffb-318"><a name="BKMK_SAPVS2008"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25ffb-318"><a name="BKMK_SAPVS2008"></a> Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="25ffb-319">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-319">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-320">Cuando se utiliza el adaptador para crear una aplicación en Visual Studio y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="25ffb-320">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="25ffb-321">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-321">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-322">Esta advertencia aparece porque la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace, `sapBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25ffb-322">This warning appears because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding, `sapBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="25ffb-323">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-323">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-324">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="25ffb-324">You can safely ignore this warning.</span></span>  
  
##  <span data-ttu-id="25ffb-325"><a name="BKMK_SAPSimilarSchema"></a>Excepción de XLANG en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="25ffb-325"><a name="BKMK_SAPSimilarSchema"></a> XLANG exception in BizTalk Server</span></span>
 <span data-ttu-id="25ffb-326">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25ffb-326">**Problem**</span></span>  
  
 <span data-ttu-id="25ffb-327">BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="25ffb-327">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="25ffb-328">**Causa**</span><span class="sxs-lookup"><span data-stu-id="25ffb-328">**Cause**</span></span>  
  
 <span data-ttu-id="25ffb-329">Esto se debe a alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="25ffb-329">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="25ffb-330">Ha generado más de un esquema de una operación genérica (por ejemplo, SendIdoc y ReceiveIdoc) en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para realizar operaciones respectivas en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-330">You have generated more than one schema of a generic operation (such as SendIdoc and ReceiveIdoc) in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to perform respective operations on an SAP system.</span></span> <span data-ttu-id="25ffb-331">Dado que los esquemas son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="25ffb-331">Because the schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="25ffb-332">En el caso de varios proyectos, tiene un esquema de operación genérica generado para cada uno de los proyectos de BizTalk Server, implementado cada proyecto en otro aplicación de BizTalk Server en el mismo host y, a continuación, se ejecutó de una aplicación o las aplicaciones puedan realizar respectivos operaciones en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="25ffb-332">In case of multiple projects, you have generated a generic operation schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to perform respective operations on an SAP system.</span></span> <span data-ttu-id="25ffb-333">Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="25ffb-333">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="25ffb-334">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="25ffb-334">**Resolution**</span></span>  
  
 <span data-ttu-id="25ffb-335">Utilizar un archivo de esquema de operación genérico único para una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="25ffb-335">Use a single generic operation schema file for a BizTalk Server application.</span></span> <span data-ttu-id="25ffb-336">Si necesita usar un esquema de operación genérica en varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contiene un esquema de operación genérico único y, a continuación, utilice el esquema de operación genérica de todas las demás aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="25ffb-336">If you need to use a generic operation schema in multiple BizTalk Server applications on the same host, create an application containing a single generic operation schema, and then use the generic operation schema from all other applications in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ffb-337">Vea también</span><span class="sxs-lookup"><span data-stu-id="25ffb-337">See Also</span></span>  
[<span data-ttu-id="25ffb-338">Solucionar problemas del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="25ffb-338">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)