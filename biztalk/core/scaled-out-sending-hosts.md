---
title: Hosts de envío escalado horizontalmente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50659e267731caafe4bad6dabe89944cb16c0c98
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007749"
---
# <a name="scaled-out-sending-hosts"></a><span data-ttu-id="1b6a5-102">Hosts de envío escalados horizontalmente</span><span class="sxs-lookup"><span data-stu-id="1b6a5-102">Scaled-Out Sending Hosts</span></span>
<span data-ttu-id="1b6a5-103">Un host de envío de escala horizontal asegura de que la funcionalidad de envío [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-103">A scaled-out sending host makes sure that the sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is highly available.</span></span> <span data-ttu-id="1b6a5-104">Si agrega varios equipos a un host para el envío de mensajes, puede ejecutar varias instancias de host de envío para obtener redundancia y alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-104">If you add multiple computers to a host for sending messages, you can run multiple sending host instances for redundancy and high availability.</span></span>  
  
 <span data-ttu-id="1b6a5-105">La siguiente ilustración muestra un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación que proporciona alta disponibilidad para el host de envío gracias a dos equipos que ejecutan instancias de host de envío.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-105">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the sending host by having two computers that are running instances of the sending host.</span></span> <span data-ttu-id="1b6a5-106">Tenga en cuenta que, en esta ilustración, los hosts de procesamiento y recepción no tienen una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-106">Note that in this figure the receiving and processing hosts are not highly available.</span></span>  
  
 <span data-ttu-id="1b6a5-107">![Escala &#45; Out Host de envío](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span><span class="sxs-lookup"><span data-stu-id="1b6a5-107">![Scaled&#45;Out Sending Host](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span></span>  
  
## <a name="high-availability-for-sending-hosts"></a><span data-ttu-id="1b6a5-108">Alta disponibilidad de los hosts de envío</span><span class="sxs-lookup"><span data-stu-id="1b6a5-108">High Availability for Sending Hosts</span></span>  
 <span data-ttu-id="1b6a5-109">Enviando la funcionalidad en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es similar a la funcionalidad de procesamiento en el sentido de que ninguna de estas actividades requiere ninguna asociación entre el host y los datos.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-109">Sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is similar to processing functionality in the sense that neither of these activities requires any association between host and data.</span></span> <span data-ttu-id="1b6a5-110">Igual que cualquier instancia de host de procesamiento puede recuperar mensajes de la base de datos de cuadros de mensajes y procesarlos, cualquier instancia de host de envío puede recuperar mensajes de la base de datos de cuadros de mensajes y enviarlos.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-110">Just as any processing host instance can retrieve messages from the MessageBox database and process them, any sending host instance can retrieve messages from the MessageBox database and send them.</span></span> <span data-ttu-id="1b6a5-111">Por tanto, proporcionar alta disponibilidad a los host de envío significa que utiliza las mismas técnicas que para proporcionar alta disponibilidad a los hosts de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-111">Therefore, providing high availability for the sending hosts means that you use the same techniques as for providing high availability for the processing hosts.</span></span>  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a><span data-ttu-id="1b6a5-112">Escala de los adaptadores de envío de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1b6a5-112">Scaling the BizTalk Server Send Adapters</span></span>  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a><span data-ttu-id="1b6a5-113">Alta disponibilidad para el adaptador de envío MSMQ</span><span class="sxs-lookup"><span data-stu-id="1b6a5-113">High Availability for the MSMQ Send Adapter</span></span>  
 <span data-ttu-id="1b6a5-114">Para proporcionar alta disponibilidad al adaptador de envío MSMQ, debe agrupar el servicio MSMQ, agrupar un host de BizTalk en el mismo grupo que el servicio MSMQ agrupado y configurar el controlador de envío MSMQ para ejecutarse en este host de BizTalk agrupado.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-114">To provide high availability for the MSMQ send adapter you should cluster the MSMQ service, cluster a BizTalk host in the same group as the clustered MSMQ service, and configure the MSMQ send handler to run in this clustered BizTalk host.</span></span> <span data-ttu-id="1b6a5-115">Esto se debe hacer para garantizar la coherencia de los envíos transaccionales iniciados por el adaptador MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-115">This should be done to ensure the consistency of transactional sends initiated by the MSMQ adapter.</span></span> <span data-ttu-id="1b6a5-116">Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span><span class="sxs-lookup"><span data-stu-id="1b6a5-116">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a><span data-ttu-id="1b6a5-117">Alta disponibilidad para el adaptador de envío de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="1b6a5-117">High Availability for the Windows SharePoint Services Send Adapter</span></span>  
 <span data-ttu-id="1b6a5-118">Para proporcionar alta disponibilidad al adaptador de envío de Windows SharePoint Services, agregue varios equipos al host de envío con el puerto de envío de cada equipo host haciendo referencia a la misma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-118">To provide high availability for the Windows SharePoint Services send adapter, add multiple computers to the send host with the send port on each host computer referencing the same document library.</span></span> <span data-ttu-id="1b6a5-119">El adaptador de Windows SharePoint Services envía mensajes a SharePoint mediante una llamada al servicio web de Windows SharePoint Services instalado por BizTalk en el equipo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-119">The Windows SharePoint Services adapter sends messages to SharePoint by calling into the Windows SharePoint Services web service installed by BizTalk on the SharePoint machine.</span></span> <span data-ttu-id="1b6a5-120">BizTalk Server proporciona alta disponibilidad para el adaptador de envío de SharePoint al permitir que se ejecuta el mismo envío puertos en varias instancias de host que envían mensajes a la misma dirección URL de HTTP que apunte a una instalación de NLB de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1b6a5-120">BizTalk Server provides high availability for the SharePoint send adapter by letting you run the same send ports on multiple host instances that push messages to the same HTTP URL pointing to a SharePoint NLB installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6a5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b6a5-121">See Also</span></span>  
 <span data-ttu-id="1b6a5-122">[Proporcionar alta disponibilidad de Hosts de BizTalk](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="1b6a5-122">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="1b6a5-123">Consideraciones para ejecutar controladores de adaptador en un host agrupado</span><span class="sxs-lookup"><span data-stu-id="1b6a5-123">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)