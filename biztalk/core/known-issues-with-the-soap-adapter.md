---
title: Problemas conocidos con el adaptador de SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 671510c6901fc399580ab73018e67eadc86f7212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262852"
---
# <a name="known-issues-with-the-soap-adapter"></a><span data-ttu-id="555e8-102">Problemas conocidos del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="555e8-102">Known Issues with the SOAP Adapter</span></span>
<span data-ttu-id="555e8-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="555e8-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="555e8-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="555e8-104">Known Issues</span></span>  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a><span data-ttu-id="555e8-105">Se produce un rendimiento muy bajo del adaptador de SOAP o éste genera errores de carga</span><span class="sxs-lookup"><span data-stu-id="555e8-105">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="555e8-106">Problema</span><span class="sxs-lookup"><span data-stu-id="555e8-106">Problem</span></span>  
 <span data-ttu-id="555e8-107">Se produce un rendimiento muy bajo del adaptador de SOAP o éste genera errores de carga</span><span class="sxs-lookup"><span data-stu-id="555e8-107">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="555e8-108">Causa</span><span class="sxs-lookup"><span data-stu-id="555e8-108">Cause</span></span>  
 <span data-ttu-id="555e8-109">Este problema se debe a que las opciones de configuración predeterminadas para el adaptador de SOAP o los componentes de dependencia que afectan al adaptador de SOAP no se optimizan para el rendimiento de la carga.</span><span class="sxs-lookup"><span data-stu-id="555e8-109">This problem occurs because the default configuration options for the SOAP adapter or for dependency components that affect the SOAP adapter are not tuned for performance under load.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="555e8-110">Solución</span><span class="sxs-lookup"><span data-stu-id="555e8-110">Resolution</span></span>  
 <span data-ttu-id="555e8-111">Para resolver este problema, modifique las opciones de configuración del adaptador de SOAP o de los componentes de dependencia descritos en el tema [parámetros de configuración que afectan al rendimiento del adaptador](../core/configuration-parameters-that-affect-adapter-performance.md).</span><span class="sxs-lookup"><span data-stu-id="555e8-111">To resolve this problem modify the configuration options for the SOAP adapter or for the dependency components described in the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a><span data-ttu-id="555e8-112">Los componentes de canalización del codificador y del descodificador de MIME/SMIME no pueden codificar ni descodificar los datos procesados por el adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="555e8-112">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="555e8-113">Problema</span><span class="sxs-lookup"><span data-stu-id="555e8-113">Problem</span></span>  
 <span data-ttu-id="555e8-114">Los componentes de canalización del codificador y del descodificador de MIME/SMIME no pueden codificar ni descodificar los datos procesados por el adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="555e8-114">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="555e8-115">Causa</span><span class="sxs-lookup"><span data-stu-id="555e8-115">Cause</span></span>  
 <span data-ttu-id="555e8-116">Este problema se produce porque el adaptador de SOAP ensambla y desensambla los mensajes SOAP en la fase de adaptador del proceso.</span><span class="sxs-lookup"><span data-stu-id="555e8-116">This problem occurs because the SOAP adapter assembles and disassembles the SOAP messages in the adapter stage of the process.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="555e8-117">Solución</span><span class="sxs-lookup"><span data-stu-id="555e8-117">Resolution</span></span>  
 <span data-ttu-id="555e8-118">Para solucionar este problema, use la opción Utilizar SSL para garantizar la comunicación segura para codificar mensajes procesados por el adaptador de SOAP.</span><span class="sxs-lookup"><span data-stu-id="555e8-118">To resolve this problem, Use Secure Sockets Layer (SSL) to secure communications to encode messages processed by the SOAP adapter.</span></span> <span data-ttu-id="555e8-119">En el lado de envío, use la **huella digital del certificado de cliente** propiedad en la página de propiedades del adaptador SOAP para lograr esto.</span><span class="sxs-lookup"><span data-stu-id="555e8-119">On the send side, use the **Client Certificate Thumbprint** property in the SOAP adapter properties page to achieve this.</span></span> <span data-ttu-id="555e8-120">En el caso de la recepción, debe configurar el directorio virtual que aloja los servicios Web de BizTalk para las comunicaciones seguras de SSL.</span><span class="sxs-lookup"><span data-stu-id="555e8-120">On the receive side, you must configure the virtual directory that hosts the BizTalk Web Service for SSL secure communications.</span></span>  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a><span data-ttu-id="555e8-121">El AppDomain predeterminado que aloja el adaptador de SOAP se descarga, lo que causa un bloqueo del proceso de host.</span><span class="sxs-lookup"><span data-stu-id="555e8-121">The default AppDomain hosting the SOAP adapter gets unloaded causing the host process to hang</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="555e8-122">Problema</span><span class="sxs-lookup"><span data-stu-id="555e8-122">Problem</span></span>  
 <span data-ttu-id="555e8-123">El proceso que aloja el adaptador de SOAP se bloquea, lo que hace que el resto de servicios Web del proceso se bloqueen.</span><span class="sxs-lookup"><span data-stu-id="555e8-123">The process hosting the SOAP adapter hangs, causing all other Web services in the process to hang.</span></span> <span data-ttu-id="555e8-124">Esto puede ocasionar el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="555e8-124">This may result in the following error:</span></span>  
  
 <span data-ttu-id="555e8-125">Se produjo un error al ejecutar la canalización: "Desconocido" origen: "desconocido"recibir puerto: TwoWayLatencyLoopBack_RxPort"URI:" / /twowaylatencyrxsoap/twowaylatencyws.asmx "razón: intentado tener acceso a un dominio de aplicación descargado.</span><span class="sxs-lookup"><span data-stu-id="555e8-125">There was a failure executing the response(send) pipeline: "Unknown " Source: "Unknown " Receive Port: TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason: Attempted to access an unloaded AppDomain.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="555e8-126">Causa</span><span class="sxs-lookup"><span data-stu-id="555e8-126">Cause</span></span>  
 <span data-ttu-id="555e8-127">El adaptador de SOAP se ejecuta en el espacio de proceso de IIS.</span><span class="sxs-lookup"><span data-stu-id="555e8-127">The SOAP adapter runs in the IIS process space.</span></span> <span data-ttu-id="555e8-128">Si existe más de un servicio Web en el AppPool de IIS, todos los servicios Web terminan teniendo su propio AppDomain.</span><span class="sxs-lookup"><span data-stu-id="555e8-128">If more than one Web service exists in the IIS AppPool, then every Web service ends up having its own AppDomain.</span></span>  
  
 <span data-ttu-id="555e8-129">De forma predeterminada, todos los objetos de motor de mensajería se crean en el primer AppDomain (es decir,.</span><span class="sxs-lookup"><span data-stu-id="555e8-129">By default all messaging engine objects are created in the first AppDomain (that is,.</span></span> <span data-ttu-id="555e8-130">el AppDomain que corresponde al primer servicio Web).</span><span class="sxs-lookup"><span data-stu-id="555e8-130">the AppDomain corresponding to the first Web service).</span></span> <span data-ttu-id="555e8-131">Si por alguna razón el primer servicio Web está inactivo durante un período de tiempo prologado, IIS descarga el primer AppDomain.</span><span class="sxs-lookup"><span data-stu-id="555e8-131">If the first Web service is inactive for an extended period of time for any reason, IIS unloads the first AppDomain.</span></span> <span data-ttu-id="555e8-132">Cuando esto ocurre, todos los servicios del proceso de alojamiento dejan de poder usarse.</span><span class="sxs-lookup"><span data-stu-id="555e8-132">When this happens, all services in the hosting process become unusable.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="555e8-133">Solución</span><span class="sxs-lookup"><span data-stu-id="555e8-133">Resolution</span></span>  
 <span data-ttu-id="555e8-134">Para impedir que AppDomain se descargue, siga el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="555e8-134">To prevent the AppDomain from being unloaded, follow the procedure below:</span></span>  
  
1.  <span data-ttu-id="555e8-135">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server** y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="555e8-135">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server** and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="555e8-136">En **consola de administración de BizTalk Server**, expandir **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **deconfiguracióndeplataforma**y, a continuación, haga clic en **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="555e8-136">In **BizTalk Server Administration Console**, Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Hosts**.</span></span>  
  
3.  <span data-ttu-id="555e8-137">En la lista de Hosts, haga clic en el host necesario y, a continuación, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="555e8-137">From the list of Hosts, right-click the required host, and then click **Settings**.</span></span>  
  
4.  <span data-ttu-id="555e8-138">En el **panel de configuración de BizTalk**, comprobar **dominio de aplicación predeterminado para adaptador aislado** en **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="555e8-138">In the **BizTalk Settings Dashboard**, check **Default application domain for isolated adapter** under **General** tab.</span></span>  
  
 <span data-ttu-id="555e8-139">Al hacerlo, los objetos del motor de mensajería de BizTalk se crean en el AppDomain predeterminado en vez de en los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="555e8-139">When you do this, the BizTalk Messaging Engine objects are created in the default AppDomain instead of in their own AppDomains.</span></span> <span data-ttu-id="555e8-140">Como el AppDomain predeterminado no se descarga nunca, el problema deja de producirse.</span><span class="sxs-lookup"><span data-stu-id="555e8-140">Because the default AppDomain is never unloaded, the problem no longer occurs.</span></span>  
  
#### <a name="the-soap-adapter-fails-to-register"></a><span data-ttu-id="555e8-141">Se produce un error al registrar el adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="555e8-141">The SOAP Adapter fails to register</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="555e8-142">Problema</span><span class="sxs-lookup"><span data-stu-id="555e8-142">Problem</span></span>  
 <span data-ttu-id="555e8-143">Cuando BizTalk Server intenta registrar el adaptador de SOAP (o HTTP), puede producirse el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="555e8-143">The following error may occur when BizTalk Server attempts to register the SOAP (or HTTP) adapter.</span></span>  
  
 <span data-ttu-id="555e8-144">"El motor de mensajería no pudo registrar un adaptador "SOAP".</span><span class="sxs-lookup"><span data-stu-id="555e8-144">"The Messaging Engine failed to register an adapter "SOAP".</span></span> <span data-ttu-id="555e8-145">Detalles: "registro de varios tipos de adaptador dentro del mismo proceso no es un escenario admitido.</span><span class="sxs-lookup"><span data-stu-id="555e8-145">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span> <span data-ttu-id="555e8-146">Los adaptadores de recepción HTTP y SOAP, por ejemplo, no pueden coexistir en el mismo proceso".</span><span class="sxs-lookup"><span data-stu-id="555e8-146">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
 <span data-ttu-id="555e8-147">O bien</span><span class="sxs-lookup"><span data-stu-id="555e8-147">Or</span></span>  
  
 <span data-ttu-id="555e8-148">"El motor de mensajería no pudo registrar un adaptador "HTTP".</span><span class="sxs-lookup"><span data-stu-id="555e8-148">"The Messaging Engine failed to register an adapter "HTTP".</span></span> <span data-ttu-id="555e8-149">Detalles: "registro de varios tipos de adaptador dentro del mismo proceso no es un escenario admitido.</span><span class="sxs-lookup"><span data-stu-id="555e8-149">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span>  <span data-ttu-id="555e8-150">Los adaptadores de recepción HTTP y SOAP, por ejemplo, no pueden coexistir en el mismo proceso".</span><span class="sxs-lookup"><span data-stu-id="555e8-150">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="555e8-151">Causa</span><span class="sxs-lookup"><span data-stu-id="555e8-151">Cause</span></span>  
 <span data-ttu-id="555e8-152">Cuando se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, los adaptadores SOAP y HTTP no se pueden ejecutar en el mismo espacio de proceso o grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="555e8-152">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, the SOAP and HTTP adapters cannot execute in the same process space or application pool.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="555e8-153">Solución</span><span class="sxs-lookup"><span data-stu-id="555e8-153">Resolution</span></span>  
 <span data-ttu-id="555e8-154">Si una instalación requiere que se usen adaptadores de SOAP y HTTP en el mismo servidor Web, deberán crearse grupos de aplicaciones separados para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="555e8-154">If an installation requires using both the SOAP and HTTP adapters on the same Web server then separate application pools must be created for each adapter.</span></span>  <span data-ttu-id="555e8-155">Una vez creados, los directorios virtuales de cada adaptador se asignan a un grupo de aplicaciones diferente.</span><span class="sxs-lookup"><span data-stu-id="555e8-155">Once created, the virtual directories for each adapter are each assigned to a different application pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="555e8-156">Este problema no se produce en Windows XP ya que en estos sistemas operativos, los adaptadores SOAP y HTTP se ejecutan en espacios de proceso diferentes en IIS 5.x.</span><span class="sxs-lookup"><span data-stu-id="555e8-156">This problem does not occur under Windows XP since under these operating systems, the SOAP and HTTP adapter run in different process spaces under IIS 5.x.</span></span>  <span data-ttu-id="555e8-157">El adaptador de SOAP se ejecuta como una aplicación ASP.NET en el proceso aspnet_wp.exe.</span><span class="sxs-lookup"><span data-stu-id="555e8-157">The SOAP adapter runs as an ASP.Net application in the aspnet_wp.exe process.</span></span>  <span data-ttu-id="555e8-158">El adaptador de HTTP se ejecuta en el espacio de proceso dedicado de dllhost.exe.</span><span class="sxs-lookup"><span data-stu-id="555e8-158">The HTTP adapter runs in the dedicated process space of dllhost.exe.</span></span>  <span data-ttu-id="555e8-159">Por lo tanto, ambos adaptadores están aislados el uno del otro, lo que les permite ejecutarse en el mismo servidor Web simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="555e8-159">Therefore both adapters are isolated from each other allowing them to run on the same Web server concurrently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="555e8-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="555e8-160">See Also</span></span>  
 [<span data-ttu-id="555e8-161">Solucionar problemas del adaptador SOAP</span><span class="sxs-lookup"><span data-stu-id="555e8-161">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)