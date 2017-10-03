---
title: Hosts de procesamiento escalado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ee36777a5c64713fd31e86fe6ef2a1886b3348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-processing-hosts"></a><span data-ttu-id="61931-102">Hosts de procesamiento escalados horizontalmente</span><span class="sxs-lookup"><span data-stu-id="61931-102">Scaled-Out Processing Hosts</span></span>
<span data-ttu-id="61931-103">Un host de procesamiento escalado horizontalmente mejora el rendimiento y proporciona alta disponibilidad aislando la funcionalidad de orquestación en dos o más equipos host.</span><span class="sxs-lookup"><span data-stu-id="61931-103">A scaled-out processing host improves performance and provides high availability by isolating orchestration functionality onto two or more separate host computers.</span></span> <span data-ttu-id="61931-104">Este aislamiento permite agregar varios equipos a un host de procesamiento para obtener redundancia.</span><span class="sxs-lookup"><span data-stu-id="61931-104">This isolation lets you add multiple computers to a processing host for redundancy.</span></span> <span data-ttu-id="61931-105">Un host de procesamiento en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecuta uno o más host instancias que coordenadas procesos empresariales distintos y crea una instancia de objetos de programación para orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="61931-105">A processing host in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runs one or more host instances that coordinate various business processes and creates an instance of programmatic objects for orchestrations.</span></span>  
  
 <span data-ttu-id="61931-106">La siguiente ilustración muestra una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que proporciona alta disponibilidad para el host de procesamiento a través de dos equipos que ejecutan instancias del host de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="61931-106">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the processing host by having two computers that are running instances of the processing host.</span></span> <span data-ttu-id="61931-107">Tenga en cuenta que, en esta ilustración, los hosts de envío y recepción no tienen una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="61931-107">Note that in this figure the receiving and sending hosts are not highly available.</span></span>  
  
 <span data-ttu-id="61931-108">![Host de procesamiento ampliado](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span><span class="sxs-lookup"><span data-stu-id="61931-108">![Scaled Out Processing Host](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span></span>  
  
 <span data-ttu-id="61931-109">En esta configuración, el trabajo de procesamiento de orquestaciones tiene una carga equilibrada entre dos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos que tienen instancias del host de procesamiento y ejecutan independientemente entre sí.</span><span class="sxs-lookup"><span data-stu-id="61931-109">In this configuration, the work for processing orchestrations is load balanced between two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers that have instances of the processing host and run independently of each other.</span></span> <span data-ttu-id="61931-110">Si un equipo encuentra errores o deja de funcionar, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza automáticamente la instancia de host en el otro equipo para procesar las orquestaciones restantes.</span><span class="sxs-lookup"><span data-stu-id="61931-110">If one computer encounters errors or fails, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically uses the host instance on the other computer to process remaining orchestrations.</span></span>  
  
## <a name="maintaining-orchestration-state"></a><span data-ttu-id="61931-111">Mantener el estado de las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="61931-111">Maintaining Orchestration State</span></span>  
 <span data-ttu-id="61931-112">BizTalk Server mantiene el estado de la orquestación forma centralizada en Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]y no de forma local en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="61931-112">BizTalk Server maintains orchestration state centrally in Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and not locally on each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="61931-113">Al guardar el estado en la base de datos de cuadro de mensajes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supera la limitación de basarse en una instancia de host único procesamiento para procesar la orquestación y permite que cualquier instancia de host de procesamiento procese la orquestación.</span><span class="sxs-lookup"><span data-stu-id="61931-113">By persisting the state in the MessageBox database, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] overcomes the limitation of relying on a single processing host instance to process the orchestration, and lets any processing host instance process the orchestration.</span></span> <span data-ttu-id="61931-114">Si se produce un error mientras [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa una orquestación, otra instancia del mismo host de procesamiento puede completar la orquestación desde el último estado persistente.</span><span class="sxs-lookup"><span data-stu-id="61931-114">If an error occurs while [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes an orchestration, another instance of the same processing host can complete the orchestration from the last persisted state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61931-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="61931-115">See Also</span></span>  
 [<span data-ttu-id="61931-116">Proporcionar alta disponibilidad a hosts de BizTalk</span><span class="sxs-lookup"><span data-stu-id="61931-116">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)