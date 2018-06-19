---
title: ¿Qué es el interceptor de BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9400e80a2f8e8acfdeb12e3d6e61a046151d1e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289804"
---
# <a name="what-is-the-bam-interceptor"></a><span data-ttu-id="fef83-103">¿Qué es el interceptor de BAM?</span><span class="sxs-lookup"><span data-stu-id="fef83-103">What Is the BAM Interceptor?</span></span>
## <a name="overview"></a><span data-ttu-id="fef83-104">Información general</span><span class="sxs-lookup"><span data-stu-id="fef83-104">Overview</span></span> 

<span data-ttu-id="fef83-105">El interceptor de BAM es un objeto que permite instrumentar la aplicación para que capture datos de interés.</span><span class="sxs-lookup"><span data-stu-id="fef83-105">The BAM Interceptor is an object that lets you instrument your application to capture data of interest.</span></span> <span data-ttu-id="fef83-106">En el diagrama siguiente se muestra el rol del interceptor de BAM y su interacción con los demás componentes de BAM:</span><span class="sxs-lookup"><span data-stu-id="fef83-106">The following diagram shows the role of the BAM interceptor and its interaction with the other BAM components:</span></span>  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
<span data-ttu-id="fef83-107">Interceptor de BAM</span><span class="sxs-lookup"><span data-stu-id="fef83-107">BAM Interceptor</span></span>  
  
 <span data-ttu-id="fef83-108">En cada paso de la aplicación donde pueda haber datos de interés, puede llamar a Interceptor OnStep, facilitar un identificador del paso y proporcionar algunos datos o un objeto arbitrario que esté utilizando en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fef83-108">In each step of your application where you could have data of interest, you call Interceptor OnStep, provide an identifier for the step, and provide some data or arbitrary object that you are using in your application.</span></span>  
  
 <span data-ttu-id="fef83-109">Deberá implementar una función de devolución de llamada de tal forma que, cuando se produzca la llamada, el procedimiento de devolución de llamada obtenga el Id. de paso actual y el objeto de datos.</span><span class="sxs-lookup"><span data-stu-id="fef83-109">You must implement a callback function so when the callback occurs, your callback procedure gets the current step ID and your data object.</span></span> <span data-ttu-id="fef83-110">Básicamente, el interceptor de BAM se encarga de propagar el objeto de datos a la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="fef83-110">Essentially, the BAM interceptor is simply propagating the data object to the callback.</span></span> <span data-ttu-id="fef83-111">La lógica real de extracción de datos reside en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fef83-111">The actual logic of extracting data resides in your application.</span></span> <span data-ttu-id="fef83-112">Por ejemplo, si los datos toman la forma de mensajes XML, la devolución de llamada utilizará XPaths.</span><span class="sxs-lookup"><span data-stu-id="fef83-112">For example, if your data takes the form of XML messages, then the callback will use XPaths.</span></span> <span data-ttu-id="fef83-113">Para obtener más información acerca de XPaths, consulte [utilizar XPaths en la asignación de mensajes](../core/using-xpaths-in-message-assignments.md).</span><span class="sxs-lookup"><span data-stu-id="fef83-113">For more information about XPaths, see [Using XPaths in Message Assignment](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
 <span data-ttu-id="fef83-114">El interceptor de BAM decide qué datos solicitar, en función de la configuración que pueda crear mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fef83-114">The BAM interceptor decides which data to request at each step, based on the configuration that you can create programmatically.</span></span> <span data-ttu-id="fef83-115">El interceptor de BAM utiliza entonces los datos obtenidos para llamar a la secuencia DirectEventStream o BufferedEventStream, necesarias para el mantenimiento y el paso como argumento un a OnStep.</span><span class="sxs-lookup"><span data-stu-id="fef83-115">The BAM Interceptor then uses the obtained data to call either DirectEventStream or BufferedEventStream that you need to keep around and pass each time as an argument to OnStep.</span></span>  
  
 <span data-ttu-id="fef83-116">La operación de llamada al interceptor en cada paso no utiliza una gran cantidad de recursos.</span><span class="sxs-lookup"><span data-stu-id="fef83-116">Calling the interceptor for each step is not a resource-intensive operation.</span></span> <span data-ttu-id="fef83-117">Si realiza la llamada y no efectúa ningún registro, el interceptor la devolverá inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fef83-117">If you call and you register nothing for this step, the interceptor returns immediately.</span></span> <span data-ttu-id="fef83-118">Esto significa que no habrá operaciones de disco, ni transacciones ni asignaciones y que, por lo tanto, casi no habrá impacto en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fef83-118">This means that there are no disk operations, no transactions, not even memory allocations, and thus almost no performance impact.</span></span> <span data-ttu-id="fef83-119">Al mismo tiempo, tendrá la posibilidad de extraer datos de BAM si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fef83-119">At the same time, you have the opportunity to extract any data for BAM if necessary.</span></span> <span data-ttu-id="fef83-120">El impacto de rendimiento en los pasos que implica la extracción de datos y la disponibilidad de los datos dependerá de la implementación de la `IBAMDataExtractor Interface`.</span><span class="sxs-lookup"><span data-stu-id="fef83-120">The performance impact on the steps involving data extraction and the availability of the data will depend on your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="fef83-121">Los siguientes ejemplos de código muestran el uso del interceptor durante la configuración y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fef83-121">The following code examples demonstrate the use of the interceptor during configuration and run time.</span></span>  
  
## <a name="configuration-time"></a><span data-ttu-id="fef83-122">Tiempo de configuración</span><span class="sxs-lookup"><span data-stu-id="fef83-122">Configuration time</span></span>  
 <span data-ttu-id="fef83-123">El siguiente código muestra cómo configurar el interceptor para que se detenga en el paso recvPO de la aplicación y solicite el nombre y número de seguridad social del cliente:</span><span class="sxs-lookup"><span data-stu-id="fef83-123">The following code shows how you configure the Interceptor to stop at step recvPO of the application, and ask for Customer Name and Customer SSN:</span></span>  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 <span data-ttu-id="fef83-124">Tras crear una instancia del interceptor, podrá almacenarla para utilizarla más tarde, durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fef83-124">After you create an interceptor instance, you can store it for later use at runtime.</span></span>  
  
 <span data-ttu-id="fef83-125">Puede crear diversos interceptores previamente creados, que representen distintas preferencias para los datos e hitos de BAM.</span><span class="sxs-lookup"><span data-stu-id="fef83-125">You may keep different pre-created interceptors representing different preferences for the data and milestones for BAM.</span></span> <span data-ttu-id="fef83-126">Para obtener un rendimiento óptimo, serialice las instancias del interceptor utilizando la clase BinaryFormatter.</span><span class="sxs-lookup"><span data-stu-id="fef83-126">For best performance, serialize the Interceptor instances using the BinaryFormatter class.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="fef83-127">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fef83-127">Run time</span></span>  
 <span data-ttu-id="fef83-128">Utilice este código para usar el interceptor durante el tiempo de ejecución en un entorno de producción:</span><span class="sxs-lookup"><span data-stu-id="fef83-128">Use this code to use the interceptor at runtime in a production environment:</span></span>  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 <span data-ttu-id="fef83-129">Donde:</span><span class="sxs-lookup"><span data-stu-id="fef83-129">Where:</span></span>  
  
-   <span data-ttu-id="fef83-130">*recvPO* y *approvePO* son objetos arbitrarios que se usan para identificar los pasos descritos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fef83-130">*recvPO* and *approvePO* are arbitrary objects you use to identify the steps in your application.</span></span>  
  
-   <span data-ttu-id="fef83-131">*Data1* y *data2* son objetos arbitrarios que tiene en ese momento y puede contener datos interesantes: por ejemplo, el documento XML del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="fef83-131">*data1* and *data2* are arbitrary objects that you have at that point and may contain interesting data – for example the XML document of the purchase order.</span></span>  
  
-   <span data-ttu-id="fef83-132">*es* es la secuencia DirectEventStream o bufferedevent, dependiendo de los requisitos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fef83-132">*es* is either DirectEventStream or BufferedEvent stream depending on your performance requirements.</span></span>  
  
-   <span data-ttu-id="fef83-133">*devolución de llamada* es la implementación de la `IBAMDataExtractor Interface`.</span><span class="sxs-lookup"><span data-stu-id="fef83-133">*callback* is your implementation of the `IBAMDataExtractor Interface`.</span></span>  
  
 <span data-ttu-id="fef83-134">El ejemplo de SDK [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md), se muestra el uso del Interceptor, que contiene tanto una herramienta y un ejemplo en tiempo de ejecución aplicación de configuración.</span><span class="sxs-lookup"><span data-stu-id="fef83-134">The SDK sample, [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md), demonstrates using the Interceptor, which contains both a configuration tool and example runtime application.</span></span>  
  
 <span data-ttu-id="fef83-135">El motor de orquestaciones de BizTalk permite la intercepción que, a su vez, permite cambiar los datos que deben recopilarse para BAM en el tiempo de ejecución mediante el Editor de perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fef83-135">The BizTalk Orchestration Engine accommodates interception, which allows changing what data is collected for BAM at runtime using the Tracking Profile Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fef83-136">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fef83-136">In This Section</span></span>  
  
-   [<span data-ttu-id="fef83-137">Cómo determinar y establecer Roles de sistema de escritura de eventos para las actividades</span><span class="sxs-lookup"><span data-stu-id="fef83-137">How to Determine and Set Event Writer Roles for Activities</span></span>](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="fef83-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef83-138">See Also</span></span>  
 [<span data-ttu-id="fef83-139">API de BAM (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="fef83-139">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)