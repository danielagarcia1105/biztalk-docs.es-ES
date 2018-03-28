---
title: Problemas conocidos con el adaptador de MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f210d0e480a311aed0bed5d50f6a827bd6ea4e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="known-issues-with-the-msmq-adapter"></a><span data-ttu-id="c448d-102">Problemas conocidos del adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="c448d-102">Known Issues with the MSMQ Adapter</span></span>
<span data-ttu-id="c448d-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="c448d-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c448d-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="c448d-104">Known Issues</span></span>  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a><span data-ttu-id="c448d-105">Las ubicaciones de recepción del adaptador de MSMQ no procesa documentos</span><span class="sxs-lookup"><span data-stu-id="c448d-105">MSMQ Adapter receive locations do not process documents</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c448d-106">Problema</span><span class="sxs-lookup"><span data-stu-id="c448d-106">Problem</span></span>  
 <span data-ttu-id="c448d-107">Las ubicaciones de recepción del adaptador de MSMQ no procesan documentos.</span><span class="sxs-lookup"><span data-stu-id="c448d-107">MSMQ Adapter receive locations will not process documents.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c448d-108">Causa</span><span class="sxs-lookup"><span data-stu-id="c448d-108">Cause</span></span>  
 <span data-ttu-id="c448d-109">Si no hay suficientes subprocesos en el grupo de subprocesos .NET asociado a la instancia de host de BizTalk en la que se está ejecutando el controlador de recepción del adaptador de MSMQ, las ubicaciones de recepción del adaptador de MSMQ no pueden procesar documentos debido a la falta de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c448d-109">If there are insufficient threads available in the .NET thread pool associated with the BizTalk host instance that the MSMQ adapter receive handler is running in then MSMQ Adapter receive locations are unable to process documents due to thread starvation.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c448d-110">Solución</span><span class="sxs-lookup"><span data-stu-id="c448d-110">Resolution</span></span>  
 <span data-ttu-id="c448d-111">Para aumentar el número de subprocesos disponibles en el grupo de subprocesos de .NET para la instancia de host, siga los pasos descritos en la **valores de subprocesos que alojan CLR para el host** sección del tema [parámetros de configuración que afectan al adaptador Rendimiento](../core/configuration-parameters-that-affect-adapter-performance.md).</span><span class="sxs-lookup"><span data-stu-id="c448d-111">To increase the number of available threads in the .NET thread pool for the host instance, follow the steps in the **CLR Hosting thread values for the host** section of the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="c448d-112">Dado que cada MSMQ ubicación de recepción que está enlazado a un MSMQ recibir controlador requiere un subproceso del grupo de subprocesos. NET, establezca **MinIOThreads** y **MinWorkerThreads** en un valor que es mayor o igual que el número de ubicaciones de recepción MSMQ enlazadas al controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c448d-112">Because each MSMQ receive location that is bound to an MSMQ receive handler requires a thread from the .NET thread pool, set **MinIOThreads** and **MinWorkerThreads** to a value that is greater than or equal to the number of MSMQ receive locations bound to the receive handler.</span></span> <span data-ttu-id="c448d-113">En consecuencia, establezca el valor de **MaxIOThreads** y **MaxWorkerThreads** en un valor igual al número de MSMQ, ubicaciones de recepción vinculadas al controlador de recepción \* 2 para admitir una elevada capacidad:</span><span class="sxs-lookup"><span data-stu-id="c448d-113">Accordingly, set the value for **MaxIOThreads** and **MaxWorkerThreads** to a value equal to the number of MSMQ receive locations bound to the receive handler \* 2 to allow for headroom:</span></span>  
  
|<span data-ttu-id="c448d-114">Entrada DWORD</span><span class="sxs-lookup"><span data-stu-id="c448d-114">DWORD Entry</span></span>|<span data-ttu-id="c448d-115">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="c448d-115">Recommended value</span></span>|  
|-----------------|-----------------------|  
|<span data-ttu-id="c448d-116">MaxIOThreads</span><span class="sxs-lookup"><span data-stu-id="c448d-116">MaxIOThreads</span></span>|<span data-ttu-id="c448d-117">Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción \* 2 del adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-117">Number of MSMQ receive locations bound to the MSMQ adapter receive handler \* 2.</span></span>|  
|<span data-ttu-id="c448d-118">MaxWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="c448d-118">MaxWorkerThreads</span></span>|<span data-ttu-id="c448d-119">Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción \* 2 del adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-119">Number of MSMQ receive locations bound to the MSMQ adapter receive handler \* 2.</span></span>|  
|<span data-ttu-id="c448d-120">MinIOThreads</span><span class="sxs-lookup"><span data-stu-id="c448d-120">MinIOThreads</span></span>|<span data-ttu-id="c448d-121">Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción del adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-121">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
|<span data-ttu-id="c448d-122">MinWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="c448d-122">MinWorkerThreads</span></span>|<span data-ttu-id="c448d-123">Número de ubicaciones de recepción de MSMQ que están enlazadas al controlador de recepción del adaptador de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-123">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
  
 <span data-ttu-id="c448d-124">Estos valores recomendados no son un factor de los subprocesos que utilizan otros controladores de adaptador u orquestaciones que se ejecutan en la instancia de host; por lo que los valores deberían aumentar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="c448d-124">These recommended values do not factor in the threads used by other adapter handlers or orchestrations running in the host instance so the values should be increased accordingly.</span></span>  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a><span data-ttu-id="c448d-125">Las ubicaciones de recepción del adaptador de MSMQ se cierran poco después de que se habiliten</span><span class="sxs-lookup"><span data-stu-id="c448d-125">MSMQ Adapter receive locations shut down shortly after they are enabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c448d-126">Problema</span><span class="sxs-lookup"><span data-stu-id="c448d-126">Problem</span></span>  
 <span data-ttu-id="c448d-127">Las ubicaciones de recepción de MSMQ se cierran poco después de que se habiliten</span><span class="sxs-lookup"><span data-stu-id="c448d-127">MSMQ receive locations shut down shortly after they are enabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c448d-128">Causa</span><span class="sxs-lookup"><span data-stu-id="c448d-128">Cause</span></span>  
 <span data-ttu-id="c448d-129">Este problema puede producirse si una instancia local no en clúster del servicio Message Queue Server no se ejecuta en el mismo equipo en el que se ejecuta la instancia de host para el controlador de recepción de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-129">This problem can occur if a local non-clustered instance of the Message Queuing service is not running on the same computer that the host instance for the MSMQ receive handler is running on.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c448d-130">Solución</span><span class="sxs-lookup"><span data-stu-id="c448d-130">Resolution</span></span>  
 <span data-ttu-id="c448d-131">Inicie el servicio Message Queue Server en el equipo en el que se ejecuta la instancia de host para el controlador de recepción de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c448d-131">Start the Message Queuing service on the computer that the host instance for the MSMQ receive handler is running on.</span></span> <span data-ttu-id="c448d-132">El controlador de recepción del adaptador MSMQ necesita que una instancia local del servicio de Message Queue Server esté en ejecución aunque una instancia en clúster del servicio Message Queue Server esté en ejecución en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="c448d-132">The MSMQ adapter receive handler requires that a local instance of the Message Queuing service is running even if a clustered instance of the Message Queuing service is running on the same computer.</span></span>  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a><span data-ttu-id="c448d-133">La herramienta SC produce un error al intentar detener el servicio para la instancia de host</span><span class="sxs-lookup"><span data-stu-id="c448d-133">SC tool causes error when attempting to stop service for host instance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c448d-134">Problema</span><span class="sxs-lookup"><span data-stu-id="c448d-134">Problem</span></span>  
 <span data-ttu-id="c448d-135">Cuando intenta usar la herramienta SC (Sc.exe) para cerrar el servicio para la instancia de host de BizTalk, puede recibir un mensaje de error que se parezca al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c448d-135">When you try to use the SC tool (Sc.exe) to shut down the service for the BizTalk host instance, you may receive an error message that resembles the following:</span></span>  
  
 <span data-ttu-id="c448d-136">**Error de ControlService 1053:**</span><span class="sxs-lookup"><span data-stu-id="c448d-136">**ControlService FAILED 1053:**</span></span>  
  
 <span data-ttu-id="c448d-137">**El servicio no respondió a la solicitud de inicio o control de manera oportuna.**</span><span class="sxs-lookup"><span data-stu-id="c448d-137">**The service did not respond to the start or control request in a timely fashion.**</span></span>  
  
 <span data-ttu-id="c448d-138">Después de recibir este mensaje de error, el servicio para la instancia de host de BizTalk se detiene.</span><span class="sxs-lookup"><span data-stu-id="c448d-138">After you receive this error message, the service for the BizTalk host instance is stopped.</span></span> <span data-ttu-id="c448d-139">Sin embargo, la herramienta SC puede emplear dos o más minutos para cerrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c448d-139">However, the SC tool may need two minutes or more to shut down the service.</span></span>  
  
 <span data-ttu-id="c448d-140">Este problema se produce cuando la ubicación de recepción de Microsoft Message Queue Server está habilitada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c448d-140">This problem occurs when a Microsoft Message Queuing receive location is enabled in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c448d-141">Además, puede registrarse un mensaje de error parecido al siguiente en el registro del sistema:</span><span class="sxs-lookup"><span data-stu-id="c448d-141">Additionally, an error message that resembles the following may be logged in the System log:</span></span>  
  
 <span data-ttu-id="c448d-142">**Tipo de evento: Error**</span><span class="sxs-lookup"><span data-stu-id="c448d-142">**Event Type: Error**</span></span>  
  
 <span data-ttu-id="c448d-143">**Origen del evento: Administrador de Control de servicio**</span><span class="sxs-lookup"><span data-stu-id="c448d-143">**Event Source: Service Control Manager**</span></span>  
  
 <span data-ttu-id="c448d-144">**Categoría de eventos: ninguno**</span><span class="sxs-lookup"><span data-stu-id="c448d-144">**Event Category: None**</span></span>  
  
 <span data-ttu-id="c448d-145">**Id. de evento: 7011**</span><span class="sxs-lookup"><span data-stu-id="c448d-145">**Event ID: 7011**</span></span>  
  
 <span data-ttu-id="c448d-146">**Descripción:**</span><span class="sxs-lookup"><span data-stu-id="c448d-146">**Description:**</span></span>  
  
 <span data-ttu-id="c448d-147">**Tiempo de espera (30000 milisegundos) esperando una respuesta de transacción del servicio BTSSvc$ BizTalkServerApplication.**</span><span class="sxs-lookup"><span data-stu-id="c448d-147">**Timeout (30000 milliseconds) waiting for a transaction response from the BTSSvc$BizTalkServerApplication service.**</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c448d-148">Solución</span><span class="sxs-lookup"><span data-stu-id="c448d-148">Resolution</span></span>  
 <span data-ttu-id="c448d-149">Ahora está disponible una revisión compatible de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c448d-149">A supported hotfix is now available from Microsoft.</span></span> <span data-ttu-id="c448d-150">Sin embargo, esta revisión está pensada para corregir únicamente el problema que se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c448d-150">However, this hotfix is intended to correct only the problem that is described in this article.</span></span> <span data-ttu-id="c448d-151">Aplique esta revisión solo a los sistemas que están experimentando este problema específico.</span><span class="sxs-lookup"><span data-stu-id="c448d-151">Apply this hotfix only to systems that are experiencing this specific problem.</span></span> <span data-ttu-id="c448d-152">Es posible que se realicen más pruebas para esta revisión.</span><span class="sxs-lookup"><span data-stu-id="c448d-152">This hotfix might receive additional testing.</span></span> <span data-ttu-id="c448d-153">Por lo tanto, si no se ve gravemente afectado por este problema, se recomienda esperar hasta el siguiente Service Pack que contenga esta revisión.</span><span class="sxs-lookup"><span data-stu-id="c448d-153">Therefore, if you are not severely affected by this problem, we recommend that you wait for the next service pack that contains this hotfix.</span></span>  
  
 <span data-ttu-id="c448d-154">Para resolver este problema, envíe una petición a los servicios de atención al cliente en línea de Microsoft para obtener la revisión.</span><span class="sxs-lookup"><span data-stu-id="c448d-154">To resolve this problem, submit a request to Microsoft Online Customer Services to obtain the hotfix.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c448d-155">Si se producen más problemas o es necesario resolver algún problema, es aconsejable crear una petición de servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="c448d-155">If additional issues occur or any troubleshooting is required, you might have to create a separate service request.</span></span> <span data-ttu-id="c448d-156">Se aplicarán los costes de soporte normales a otras cuestiones y problemas de soporte que no se cualifiquen para esta revisión específica.</span><span class="sxs-lookup"><span data-stu-id="c448d-156">The usual support costs will apply to additional support questions and issues that do not qualify for this specific hotfix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c448d-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="c448d-157">See Also</span></span>  
 [<span data-ttu-id="c448d-158">Solucionar problemas del adaptador MSMQ</span><span class="sxs-lookup"><span data-stu-id="c448d-158">Troubleshooting the MSMQ Adapter</span></span>](../core/troubleshooting-the-msmq-adapter.md)