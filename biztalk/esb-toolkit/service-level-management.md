---
title: Administración del nivel de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add50343-5470-4db3-a029-c827523e2f2c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b7ba1672660af2a68a5d193729a0a9009173d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294732"
---
# <a name="service-level-management"></a><span data-ttu-id="5b3f8-102">Administración del nivel de servicio</span><span class="sxs-lookup"><span data-stu-id="5b3f8-102">Service Level Management</span></span>
<span data-ttu-id="5b3f8-103">El Administrador de nivel de servicio de SMS de AmberPoint proporciona visibilidad a específicos de problemas de rendimiento y disponibilidad en sistemas basados en SOA de nivel de empresa.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-103">The AmberPoint SMS Service Level Manager provides visibility into specific performance and availability issues within enterprise-level SOA-based systems.</span></span> <span data-ttu-id="5b3f8-104">Instrumenta y realiza un seguimiento de las métricas para cada Microsoft BizTalk Server ubicación de recepción y el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-104">It instruments and tracks the metrics for each Microsoft BizTalk Server receive location and send port.</span></span> <span data-ttu-id="5b3f8-105">Esto proporciona la indicación de estado en tiempo real, además de caracterización de rendimiento en curso de estos componentes.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-105">This provides real-time health and status indication, in addition to ongoing performance characterization of these components.</span></span> <span data-ttu-id="5b3f8-106">La figura 1 muestra la visualización de las métricas asociadas a una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-106">Figure 1 shows the display of the metrics associated with a receive location.</span></span>  
  
 <span data-ttu-id="5b3f8-107">![Ubicación de recepción AmberPoint](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")</span><span class="sxs-lookup"><span data-stu-id="5b3f8-107">![AmberPoint Receive Location](../esb-toolkit/media/ch9-amberpointreceivelocation.gif "Ch9-AmberPointReceiveLocation")</span></span>  
  
 <span data-ttu-id="5b3f8-108">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="5b3f8-109">**Las métricas asociadas a una ubicación de recepción**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-109">**The metrics associated with a receive location**</span></span>  
  
 <span data-ttu-id="5b3f8-110">Análisis en tiempo de ejecución AmberPoint permiten a los usuarios establecer umbrales y enviar alertas cuando un sistema supera un umbral de un evento crítico, incluidos los eventos de advertencias de conformidad, eventos de infracciones de cumplimiento de normas y un retorno posterior al cumplimiento de normas.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-110">AmberPoint run-time analytics allow users to set thresholds and send alerts when a system crosses a critical event threshold, including compliance warnings events, compliance violations events, and a subsequent return to compliance.</span></span> <span data-ttu-id="5b3f8-111">La figura 2 muestra la pantalla donde los usuarios configurar acuerdos de nivel de servicio y ver las alertas generadas para este contrato de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-111">Figure 2 shows the display where users configure service level agreements and view alerts generated for this service level agreement.</span></span>  
  
 <span data-ttu-id="5b3f8-112">![SLA AmberPoint](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span><span class="sxs-lookup"><span data-stu-id="5b3f8-112">![AmberPoint SLA](../esb-toolkit/media/ch9-amberpointsla.gif "Ch9-AmberPointSLA")</span></span>  
  
 <span data-ttu-id="5b3f8-113">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-113">**Figure 2**</span></span>  
  
 <span data-ttu-id="5b3f8-114">**Las pantallas para configurar un contrato de nivel de servicio y ver las alertas**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-114">**The screens to configure a service level agreement and view alerts**</span></span>  
  
 <span data-ttu-id="5b3f8-115">Puede establecer objetivos de rendimiento dentro del Administrador de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-115">You can establish performance targets within the Service Level Manager.</span></span> <span data-ttu-id="5b3f8-116">A continuación, el software realiza un seguimiento de los mensajes individuales, mensajes de un usuario específico o mensajes de grupos de usuarios para medir el rendimiento en estos destinos.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-116">The software then tracks individual messages, messages from a specific user, or messages from groups of users, to measure performance against these targets.</span></span>  
  
 <span data-ttu-id="5b3f8-117">También puede configurar directivas de registro que indique a AmberPoint SMS dinámicamente recopilar e inspeccionar el contexto del mensaje y los datos que pasan a través de BizTalk Server, como se muestra en la figura 3.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-117">You can also configure logging policies that instruct AmberPoint SMS to dynamically collect and inspect message context and data passing through BizTalk Server, as shown in Figure 3.</span></span> <span data-ttu-id="5b3f8-118">A continuación, puede utilizar estos registros para solucionar el problema "sobre la marcha", para el análisis técnico de problemas y para archivar para cumplir con las normas específicas de la industria.</span><span class="sxs-lookup"><span data-stu-id="5b3f8-118">You can then use these logs for "on-the-fly" troubleshooting, for technical analysis of problems, and for archiving to comply with industry-specific regulations.</span></span>  
  
 <span data-ttu-id="5b3f8-119">![Mensajes de servicio de BizTalk](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")</span><span class="sxs-lookup"><span data-stu-id="5b3f8-119">![BizTalk Service Messages](../esb-toolkit/media/ch9-biztalkservicemessages.jpg "Ch9-BizTalkServiceMessages")</span></span>  
  
 <span data-ttu-id="5b3f8-120">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-120">**Figure 3**</span></span>  
  
 <span data-ttu-id="5b3f8-121">**El archivo de registro de mensajes del servicio de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="5b3f8-121">**The log file for BizTalk Server service messages**</span></span>