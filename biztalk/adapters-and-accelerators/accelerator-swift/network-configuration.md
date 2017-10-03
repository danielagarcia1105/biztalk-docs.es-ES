---
title: "Configuración de red | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="network-configuration"></a><span data-ttu-id="851b3-102">Configuración de red</span><span class="sxs-lookup"><span data-stu-id="851b3-102">Network Configuration</span></span>
<span data-ttu-id="851b3-103">Esta sección proporciona instrucciones para configurar la red en su implementación.</span><span class="sxs-lookup"><span data-stu-id="851b3-103">This section provides prescriptive guidance for configuring the network in your deployment.</span></span> <span data-ttu-id="851b3-104">Para obtener más información, consulte [preparar para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="851b3-104">For more information, see [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span>  
  
 <span data-ttu-id="851b3-105">Definir redes de área local virtuales (VLAN) en el conmutador y, a continuación, conecte los cables adecuados.</span><span class="sxs-lookup"><span data-stu-id="851b3-105">You define virtual local area networks (VLANs) in the switch and then connect the appropriate cables.</span></span> <span data-ttu-id="851b3-106">Al definir las VLAN, designa puertos en el conmutador para cada segmento de red o la capa.</span><span class="sxs-lookup"><span data-stu-id="851b3-106">By defining the VLANs, you are designating ports on the switch for each network segment or tier.</span></span> <span data-ttu-id="851b3-107">Debe crear una VLAN para cada uno de los siguientes entornos:</span><span class="sxs-lookup"><span data-stu-id="851b3-107">You must create a VLAN for each of the following environments:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="851b3-108">nivel de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="851b3-108"> receive and send tier</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="851b3-109">nivel de orquestación y base de datos</span><span class="sxs-lookup"><span data-stu-id="851b3-109"> orchestration and database tier</span></span>  
  
-   <span data-ttu-id="851b3-110">Red corporativa</span><span class="sxs-lookup"><span data-stu-id="851b3-110">Corporate network</span></span>  
  
 <span data-ttu-id="851b3-111">Después de definir las VLAN, puede conectar los cables de red de los servidores a los puertos correspondientes en el conmutador.</span><span class="sxs-lookup"><span data-stu-id="851b3-111">After you have defined the VLANs, you can connect the network cables from the servers to the appropriate ports on the switch.</span></span>  
  
 <span data-ttu-id="851b3-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="851b3-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="851b3-113">Diagrama físico</span><span class="sxs-lookup"><span data-stu-id="851b3-113">Physical Diagram</span></span>](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [<span data-ttu-id="851b3-114">Equilibrio de carga de red</span><span class="sxs-lookup"><span data-stu-id="851b3-114">Network Load Balancing</span></span>](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)