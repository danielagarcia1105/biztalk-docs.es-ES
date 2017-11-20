---
title: Contadores de rendimiento de los adaptadores WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236eaed7401c79540274e0419b99d14d0f128332
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters-performance-counters"></a><span data-ttu-id="2bc3c-102">Contadores de rendimiento de los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="2bc3c-102">WCF Adapters Performance Counters</span></span>
<span data-ttu-id="2bc3c-103">Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por un servicio en el sitio o sistema.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-103">Performance counters enable you to monitor specific aspects of work performed on the site or system by a service.</span></span> <span data-ttu-id="2bc3c-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span> <span data-ttu-id="2bc3c-105">Los adaptadores de WCF no proporcionan sus propios contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-105">The WCF adapters do not provide their own performance counters.</span></span> <span data-ttu-id="2bc3c-106">No obstante, puede supervisar los contadores de rendimiento de Windows Communication Foundation (WCF) para calibrar el rendimiento de las ubicaciones de recepción WCF.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-106">However, you can monitor the performance counters of Windows Communication Foundation (WCF) to gauge the performance of the WCF receive locations.</span></span> <span data-ttu-id="2bc3c-107">Con el fin de usar los contadores de rendimiento de WCF para las ubicaciones de recepción WCF, tiene que habilitar los contadores de rendimiento para las instancias de host que ejecutan las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-107">To use the WCF performance counters for the WCF receive locations, you have to enable the performance counters for the host instances running the receive locations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bc3c-108">Los contadores de rendimiento de WCF no están disponibles para los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-108">The WCF performance counters are not available for WCF send ports.</span></span>  
  
 <span data-ttu-id="2bc3c-109">Para los adaptadores de WCF de tipo En curso, puede habilitar los contadores de rendimiento a través del archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-109">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="2bc3c-110">En el caso de los adaptadores de WCF aislados, puede modificar el archivo Web.config para habilitar los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-110">For the isolated WCF adapters, you can modify the Web.config file to enable the performance counters.</span></span> <span data-ttu-id="2bc3c-111">Para obtener más información acerca de los contadores de rendimiento de WCF, vea "WCF Performance Counters" en [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245).</span><span class="sxs-lookup"><span data-stu-id="2bc3c-111">For more information about the WCF performance counters, see "WCF Performance Counters" at [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245).</span></span>  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a><span data-ttu-id="2bc3c-112">Habilitar los contadores de rendimiento de WCF para las ubicaciones de recepción WCF</span><span class="sxs-lookup"><span data-stu-id="2bc3c-112">Enabling the WCF Performance Counters for the WCF Receive Locations</span></span>  
 <span data-ttu-id="2bc3c-113">Para los adaptadores de WCF de tipo En curso, puede habilitar los contadores de rendimiento a través del archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-113">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span>  
  
 <span data-ttu-id="2bc3c-114">En el caso de los adaptadores de WCF aislados, puede habilitar el seguimiento de WCF mediante la modificación del archivo Web.config que el Asistente para publicación de Servicio WCF de BizTalk crea en la carpeta de la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-114">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder</span></span>  
  
 <span data-ttu-id="2bc3c-115">Para modificar los archivos BTSNtSvc.exe.config o Web.config, abra el archivo de configuración y, a continuación, configure el seguimiento de WCF, como se indica en el ejemplo de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc3c-115">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bc3c-116">El archivo BTSNTSvc.exe.config siempre está ubicado en el mismo directorio que el archivo BTSNTSvc.exe, que normalmente es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc3c-116">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 <span data-ttu-id="2bc3c-117">El **performanceCounters** atributo se puede establecer para habilitar un tipo específico de contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-117">The **performanceCounters** attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="2bc3c-118">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="2bc3c-118">Valid values are</span></span>  
  
-   <span data-ttu-id="2bc3c-119">**Todos los**: todos los contadores de categoría (**ServiceModelService**, **ServiceModelEndpoint**, y **ServiceModelOperation**) están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-119">**All**: All category counters (**ServiceModelService**, **ServiceModelEndpoint**, and **ServiceModelOperation**) are enabled.</span></span>  
  
-   <span data-ttu-id="2bc3c-120">**ServiceOnly**: solo **ServiceModelService** se habilitan los contadores de categoría.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-120">**ServiceOnly**: Only **ServiceModelService** category counters are enabled.</span></span>  
  
-   <span data-ttu-id="2bc3c-121">**Desactivar**: contadores de rendimiento ServiceModel * están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-121">**Off**: ServiceModel* performance counters are disabled.</span></span> <span data-ttu-id="2bc3c-122">Es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-122">This is the default value.</span></span>  
  
 <span data-ttu-id="2bc3c-123">Después de modificar el archivo BTSNTSvc.exe.config, debe reiniciar las instancias de host que ejecutan las ubicaciones de recepción WCF de tipo En curso.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-123">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="2bc3c-124">Tipos de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="2bc3c-124">Types of Performance Counters</span></span>  
 <span data-ttu-id="2bc3c-125">Contadores de rendimiento de WCF abarcan tres niveles diferentes: servicio, extremo y operación.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-125">WCF performance counters are scoped to three different levels: service, endpoint, and operation.</span></span>  
  
 <span data-ttu-id="2bc3c-126">**Contadores de rendimiento de servicio**</span><span class="sxs-lookup"><span data-stu-id="2bc3c-126">**Service performance counters**</span></span>  
  
 <span data-ttu-id="2bc3c-127">Los contadores de rendimiento de servicio miden el comportamiento del servicio en su conjunto y pueden emplearse para diagnosticar el rendimiento del servicio completo.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-127">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="2bc3c-128">Se encuentran en el **ServiceModelService 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-128">They are found under the **ServiceModelService 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="2bc3c-129">Los nombres de las instancias se asignan mediante el patrón siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc3c-129">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 <span data-ttu-id="2bc3c-130">Puesto que los adaptadores de WCF crean un host de servicio independiente para cada ubicación de recepción, se crea una instancia de contador de rendimiento para cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-130">Because the WCF adapters create a separate service host for each receive location, a performance counter instance is created for each receive location.</span></span> <span data-ttu-id="2bc3c-131">Para obtener más información acerca de la clase de servicio implementa WCF contratos de servicio, consulte la **BizTalkServiceInstance (clase)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc3c-131">For more information about the service class implementing the WCF service contracts, see the **BizTalkServiceInstance Class** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
 <span data-ttu-id="2bc3c-132">**Contadores de rendimiento de punto de conexión**</span><span class="sxs-lookup"><span data-stu-id="2bc3c-132">**Endpoint performance counters**</span></span>  
  
 <span data-ttu-id="2bc3c-133">Los contadores de rendimiento de extremo permiten observar los datos que reflejan el modo en que un extremo acepta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-133">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="2bc3c-134">Se encuentran en el **ServiceModelEndpoint 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-134">They are found under the **ServiceModelEndpoint 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="2bc3c-135">Los nombres de las instancias se asignan mediante el patrón siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc3c-135">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 <span data-ttu-id="2bc3c-136">Se crea una instancia de contador de rendimiento para cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-136">A performance counter instance is created for each receive location.</span></span> <span data-ttu-id="2bc3c-137">En el patrón anterior, el nombre del contrato de servicio de WCF representa el contrato de servicio que los adaptadores de WCF eligen para recibir los mensajes a través de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-137">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="2bc3c-138">Para obtener más información acerca de cómo los adaptadores de WCF eligen un contrato de servicio de WCF disponible contratos de servicio, consulte **referencia de contrato de servicio de adaptadores de WCF** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc3c-138">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="2bc3c-139">**Contadores de rendimiento de operación**</span><span class="sxs-lookup"><span data-stu-id="2bc3c-139">**Operation performance counters**</span></span>  
  
 <span data-ttu-id="2bc3c-140">Contadores de rendimiento de la operación se encuentran en el **ServiceModelOperation 3.0.0.0** objeto de rendimiento cuando se ven con el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-140">Operation performance counters are found under the **ServiceModelOperation 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="2bc3c-141">Se crean dos instancias de contadores de rendimiento para cada ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-141">Two performance counter instances are created for each receive location.</span></span> <span data-ttu-id="2bc3c-142">El nombre de una de las instancias de objetos se asigna mediante el patrón siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc3c-142">One of the object instances is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 <span data-ttu-id="2bc3c-143">En el patrón anterior, el nombre del contrato de servicio de WCF representa el contrato de servicio que los adaptadores de WCF eligen para recibir los mensajes a través de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-143">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="2bc3c-144">**biztalksubmit** es un nombre de operación declarado en el contrato de servicio y hace que el tiempo de ejecución cree operaciones de WSDL en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-144">**biztalksubmit** is an operation name declared in the service contract, and causes the runtime to create WSDL operations in the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bc3c-145">Para obtener más información acerca de cómo los adaptadores de WCF eligen un contrato de servicio de WCF disponible contratos de servicio, consulte **referencia de contrato de servicio de adaptadores de WCF** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc3c-145">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="2bc3c-146">El nombre de la otra instancia de objetos se asigna mediante el patrón siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc3c-146">The other object instance is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 <span data-ttu-id="2bc3c-147">Esta instancia del contador de rendimiento representa la operación que procesa de forma asíncrona los mensajes entrantes a través de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-147">This performance counter instance represents the operation that asynchronously processes messages incoming through the receive location.</span></span> <span data-ttu-id="2bc3c-148">La parte del nombre de operación de esta instancia puede ser **twowaymethod** o **onewaymethod** según el tipo de adaptador WCF usado en la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-148">The operation name part of this instance can be **twowaymethod** or **onewaymethod** depending on the type of WCF adapter used in the receive location.</span></span> <span data-ttu-id="2bc3c-149">Si usa el adaptador de WCF-NetMsmq, una instancia con la **onewaymethod** se crea el nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-149">If you use the WCF-NetMsmq adapter, an instance having the **onewaymethod** operation name is created.</span></span> <span data-ttu-id="2bc3c-150">Para los demás adaptadores, **twowaymethod** se utiliza para la parte del nombre de operación.</span><span class="sxs-lookup"><span data-stu-id="2bc3c-150">For the other adapters, **twowaymethod** is used for the operation name part.</span></span>