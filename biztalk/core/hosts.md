---
title: Hosts | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790c839685e71dd1a88b637e5ca7811d62809cc0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980021"
---
# <a name="hosts"></a><span data-ttu-id="8226a-102">Hosts</span><span class="sxs-lookup"><span data-stu-id="8226a-102">Hosts</span></span>
<span data-ttu-id="8226a-103">El objeto de host de BizTalk representa un conjunto lógico que puede contener (o no) procesos en tiempo de ejecución y en el que se pueden implementar servicios, canalizaciones y otros artefactos.</span><span class="sxs-lookup"><span data-stu-id="8226a-103">The BizTalk Host object represents a logical set of zero or more runtime processes in which you can deploy services, pipelines, and other artifacts.</span></span> <span data-ttu-id="8226a-104">Además, representa un conjunto de instancias de hosts que puede estar vacío y en el que se ejecutan físicamente los elementos implementados.</span><span class="sxs-lookup"><span data-stu-id="8226a-104">The Host object also represents a collection of runtime instances (zero or more) where the deployed items physically run.</span></span>  
  
 <span data-ttu-id="8226a-105">Una vez creado un host (contenedor lógico), puede agregar servidores físicos BizTalk (instancias de host) al host.</span><span class="sxs-lookup"><span data-stu-id="8226a-105">After you create a host (a logical container), you can add physical BizTalk servers (host instances) to the host.</span></span> <span data-ttu-id="8226a-106">Los servidores BizTalk no se pueden agregar más de una vez en el mismo host.</span><span class="sxs-lookup"><span data-stu-id="8226a-106">You cannot add a BizTalk server to the same host more than once.</span></span> <span data-ttu-id="8226a-107">No obstante, una instancia de host se puede agregar a varios hosts.</span><span class="sxs-lookup"><span data-stu-id="8226a-107">A single host instance can be added to multiple hosts.</span></span>  
  
 <span data-ttu-id="8226a-108">Los elementos, como controladores de adaptador, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones, incluidos en BizTalk hosts pueden realizar las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="8226a-108">Items—such as adapter handlers, receive locations (including pipelines), and orchestrations—contained in BizTalk hosts can perform the following functions:</span></span>  
  
- <span data-ttu-id="8226a-109">**Recibir**.</span><span class="sxs-lookup"><span data-stu-id="8226a-109">**Receiving**.</span></span> <span data-ttu-id="8226a-110">Estos elementos realizan el procesamiento inicial de los mensajes después de haberlos recogido en una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="8226a-110">These items do the initial processing of messages after they are picked up in a receive location.</span></span> <span data-ttu-id="8226a-111">Cuando un host contiene un elemento de recepción, como una canalización o una ubicación de recepción, actúa como un límite de seguridad y la descodificación y descifrado de mensajes tiene lugar en una canalización del host.</span><span class="sxs-lookup"><span data-stu-id="8226a-111">When a host contains a receiving item, such as a receive location or pipeline, it acts as a security boundary, and the message decoding and decrypting occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="8226a-112">**Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8226a-112">**Sending**.</span></span> <span data-ttu-id="8226a-113">Estos elementos realizan el procesamiento final de los mensajes antes de enviarlos al puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="8226a-113">These items do the final processing of messages before they are sent out to the send port.</span></span> <span data-ttu-id="8226a-114">Cuando un host contiene un elemento de envío, como un puerto de envío o una canalización, el host actúa como un límite de seguridad, y la firma y cifrado de mensajes tiene lugar en una canalización del host.</span><span class="sxs-lookup"><span data-stu-id="8226a-114">When a host contains a sending item, such as a send port or pipeline, the host acts as a security boundary, and the message signing and encryption occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="8226a-115">**Procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="8226a-115">**Processing**.</span></span> <span data-ttu-id="8226a-116">Estos elementos procesan los mensajes en función de las instrucciones de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="8226a-116">These items process messages based on the instructions in an orchestration.</span></span>  
  
  <span data-ttu-id="8226a-117">Un host de BizTalk puede contener elementos que reciben, envían y procesan mensajes.</span><span class="sxs-lookup"><span data-stu-id="8226a-117">One BizTalk Host can contain items that receive, send, and process messages.</span></span> <span data-ttu-id="8226a-118">Se recomienda crear diferentes hosts para cada función con el fin de crear límites de seguridad y facilitar la administración.</span><span class="sxs-lookup"><span data-stu-id="8226a-118">It is recommended that you create different hosts for each function to create security boundaries and facilitate management.</span></span> <span data-ttu-id="8226a-119">En concreto, se recomienda utilizar hosts diferentes para operaciones de procesamiento y recepción o envío, así como separar los elementos que son de confianza de los que no lo son.</span><span class="sxs-lookup"><span data-stu-id="8226a-119">In particular, it is recommended that you use different hosts for processing and for receive/send, and that you separate trusted and non-trusted items.</span></span>  
  
  <span data-ttu-id="8226a-120">La siguiente ilustración muestra la relación entre servidores, hosts e instancias de host.</span><span class="sxs-lookup"><span data-stu-id="8226a-120">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
  <span data-ttu-id="8226a-121">![Hosts, instancias de host y las relaciones de servidor](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="8226a-121">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
  <span data-ttu-id="8226a-122">Relación entre hosts, instancias de host y servidores</span><span class="sxs-lookup"><span data-stu-id="8226a-122">Relationship between hosts, host instances, and servers</span></span>  
  
  <span data-ttu-id="8226a-123">Para obtener más información acerca de las instancias de Host, consulte [instancias de Host](../core/host-instances.md).</span><span class="sxs-lookup"><span data-stu-id="8226a-123">For more information about Host Instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
  <span data-ttu-id="8226a-124">Según la configuración física y el tipo de adaptador que se aloje, hay dos tipos de hosts: hosts y hosts aislados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8226a-124">Based on the physical configuration and type of adapter hosted, there are two types of hosts: in-process hosts and isolated hosts.</span></span>  
  
## <a name="in-process-hosts"></a><span data-ttu-id="8226a-125">Hosts de tipo en curso</span><span class="sxs-lookup"><span data-stu-id="8226a-125">In-process Hosts</span></span>  
 <span data-ttu-id="8226a-126">Los hosts de tipo En curso representan instancias de servicio que un administrador crea, elimina y controla por completo a través del Instrumental de administración de Windows (WMI) y la Consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8226a-126">In-process hosts represent service instances that an administrator creates, deletes, and fully controls with Windows Management Instrumentation (WMI) and the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="8226a-127">Los hosts de tipo En curso cuentan con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="8226a-127">In-process hosts have the following characteristics:</span></span>  
  
- <span data-ttu-id="8226a-128">Las orquestaciones pueden darse de alta en los hosts de tipo En curso.</span><span class="sxs-lookup"><span data-stu-id="8226a-128">You can enlist any orchestration into an in-process host.</span></span>  
  
- <span data-ttu-id="8226a-129">Los hosts de tipo En curso pueden alojar controladores de envío.</span><span class="sxs-lookup"><span data-stu-id="8226a-129">An in-process host can host any send handler.</span></span>  
  
- <span data-ttu-id="8226a-130">Un host de tipo En curso puede alojar cualquiera de los controladores de recepción excepto SOAP y HTTP:</span><span class="sxs-lookup"><span data-stu-id="8226a-130">An in-process host can host any of the receive handlers except for SOAP and HTTP:</span></span>  
  
  -   <span data-ttu-id="8226a-131">FILE</span><span class="sxs-lookup"><span data-stu-id="8226a-131">FILE</span></span>  
  
  -   <span data-ttu-id="8226a-132">FTP</span><span class="sxs-lookup"><span data-stu-id="8226a-132">FTP</span></span>  
  
  -   <span data-ttu-id="8226a-133">MQSeries</span><span class="sxs-lookup"><span data-stu-id="8226a-133">MQSeries</span></span>  
  
  -   <span data-ttu-id="8226a-134">MSMQ</span><span class="sxs-lookup"><span data-stu-id="8226a-134">MSMQ</span></span>  
  
  -   <span data-ttu-id="8226a-135">POP3</span><span class="sxs-lookup"><span data-stu-id="8226a-135">POP3</span></span>  
  
  -   <span data-ttu-id="8226a-136">SQL</span><span class="sxs-lookup"><span data-stu-id="8226a-136">SQL</span></span>  
  
  -   <span data-ttu-id="8226a-137">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="8226a-137">Windows SharePoint Services</span></span>  
  
- <span data-ttu-id="8226a-138">El primer host en proceso se crea en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación es el **host predeterminado** y no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="8226a-138">The first in-process host you create in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is the **default host** and you cannot delete it.</span></span> <span data-ttu-id="8226a-139">El Adaptador de BizTalk para Message Queue Server utiliza el host predeterminado para la configuración del controlador estático.</span><span class="sxs-lookup"><span data-stu-id="8226a-139">The BizTalk Message Queuing adapter uses the default host for static handler configuration.</span></span> <span data-ttu-id="8226a-140">La agregación automática de adaptadores crea puertos de envío y recepción en el host predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8226a-140">Adding an adapter automatically creates receive and send ports for the default host.</span></span>  
  
## <a name="isolated-hosts"></a><span data-ttu-id="8226a-141">Hosts aislados</span><span class="sxs-lookup"><span data-stu-id="8226a-141">Isolated Hosts</span></span>  
 <span data-ttu-id="8226a-142">Los hosts aislados representan instancias de servicio que un programador de soluciones crea, elimina y controla mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8226a-142">Isolated hosts represent service instances that a solutions developer programmatically creates, deletes, and controls.</span></span> <span data-ttu-id="8226a-143">Los administradores usan el WMI y la Consola de administración de BizTalk para configurar estos hosts (por ejemplo, para configurar la cuenta de servicio de host y la autenticación de confianza).</span><span class="sxs-lookup"><span data-stu-id="8226a-143">An administrator uses WMI and the BizTalk Administration Console to configure these hosts (for example, to configure the host service account and authentication trust).</span></span>  
  
 <span data-ttu-id="8226a-144">Los hosts aislados se encargan principalmente de alojar adaptadores que deban ejecutarse fuera del proceso en tiempo de ejecución habitual de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8226a-144">Isolated hosts primarily host adapters that must run outside of the normal BizTalk Server runtime process.</span></span> <span data-ttu-id="8226a-145">Por ejemplo, los hosts aislados se emplean para alojar adaptadores para procesos externos como, por ejemplo, extensiones ISAPI y ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8226a-145">For example, you use isolated hosts to host adapters for external processes such as ISAPI extensions and ASP.NET.</span></span>  
  
 <span data-ttu-id="8226a-146">Los hosts aislados cuentan con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="8226a-146">Isolated hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="8226a-147">Las orquestaciones no pueden darse de alta en un host aislado.</span><span class="sxs-lookup"><span data-stu-id="8226a-147">You cannot enlist orchestrations into an isolated host.</span></span>  
  
-   <span data-ttu-id="8226a-148">Los hosts aislados no pueden alojar controladores de envío.</span><span class="sxs-lookup"><span data-stu-id="8226a-148">An isolated host cannot host send handlers.</span></span>  
  
-   <span data-ttu-id="8226a-149">Los hosts aislados solo pueden alojar controladores de recepción que estén asociados con adaptadores de HTTP/S y SOAP (los adaptadores de tipo aislado).</span><span class="sxs-lookup"><span data-stu-id="8226a-149">An isolated host can host only the receive handlers associated with HTTP/S and SOAP adapters (the isolated-type adapters).</span></span>  
  
-   <span data-ttu-id="8226a-150">Los hosts aislados no pueden alojar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8226a-150">An isolated host cannot host tracking.</span></span>  
  
-   <span data-ttu-id="8226a-151">Un host aislado no puede ser el host predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8226a-151">An isolated host cannot be the default host.</span></span>  
  
-   <span data-ttu-id="8226a-152">El estado de un host aislado siempre es **estado no disponible**.</span><span class="sxs-lookup"><span data-stu-id="8226a-152">The status of an isolated host is always **Status Unavailable**.</span></span> <span data-ttu-id="8226a-153">BizTalk Server no tiene acceso a la información de estado de los procesos externos.</span><span class="sxs-lookup"><span data-stu-id="8226a-153">BizTalk Server does not access the status information for external processes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8226a-154">Las instancias de hosts pueden compartir la misma cuenta de servicio siempre que compartan también la misma configuración de seguridad (autenticación de confianza).</span><span class="sxs-lookup"><span data-stu-id="8226a-154">Host instances can share the same service account as long as they share the same security configuration (authentication trust).</span></span>  
  
## <a name="trusted-and-untrusted-hosts"></a><span data-ttu-id="8226a-155">Hosts de confianza y de no confianza</span><span class="sxs-lookup"><span data-stu-id="8226a-155">Trusted and Untrusted Hosts</span></span>  
 <span data-ttu-id="8226a-156">BizTalk Server permite que un host identificado como con autenticación de confianza indique que el remitente de un mensaje que dicho host está agregando a la cola de la base de datos de cuadro de mensajes es una entidad distinta del host de confianza mismo.</span><span class="sxs-lookup"><span data-stu-id="8226a-156">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="8226a-157">Los fines principales de la autenticación de confianza son permitir que las canalizaciones se resuelvan en un Id. de producto (PID) y pasen éste a servicios de consumo para su uso en la autorización y la resolución de entidades salientes, y permitir la transmisión del Id. de seguridad de Windows del remitente (SSID) a los servicios de consumo para su uso en la autorización de acciones de orquestación.</span><span class="sxs-lookup"><span data-stu-id="8226a-157">The primary purposes of authentication trust are to enable pipelines to resolve to a Product ID (PID) and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8226a-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="8226a-158">See Also</span></span>  
 <span data-ttu-id="8226a-159">[Instancias de host](../core/host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="8226a-159">[Host Instances](../core/host-instances.md) </span></span>  
 [<span data-ttu-id="8226a-160">Administrar hosts de BizTalk e instancias de host</span><span class="sxs-lookup"><span data-stu-id="8226a-160">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)  
 [<span data-ttu-id="8226a-161">Entidades</span><span class="sxs-lookup"><span data-stu-id="8226a-161">Entities</span></span>](../core/entities.md)