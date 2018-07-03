---
title: Configuración de red | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb693b9718b7c92e24f3537bea7ef27267f9a05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967445"
---
# <a name="network-configuration"></a><span data-ttu-id="b4f72-102">Configuración de red</span><span class="sxs-lookup"><span data-stu-id="b4f72-102">Network Configuration</span></span>
<span data-ttu-id="b4f72-103">Esta sección proporciona instrucciones para configurar la red en su implementación.</span><span class="sxs-lookup"><span data-stu-id="b4f72-103">This section provides prescriptive guidance for configuring the network in your deployment.</span></span> <span data-ttu-id="b4f72-104">Para obtener más información, consulte [preparación para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="b4f72-104">For more information, see [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span>  

 <span data-ttu-id="b4f72-105">Definir las redes de área local virtuales (VLAN) en el conmutador y, a continuación, conecte los cables adecuados.</span><span class="sxs-lookup"><span data-stu-id="b4f72-105">You define virtual local area networks (VLANs) in the switch and then connect the appropriate cables.</span></span> <span data-ttu-id="b4f72-106">Al definir las VLAN, que designa los puertos del conmutador para cada nivel o un segmento de red.</span><span class="sxs-lookup"><span data-stu-id="b4f72-106">By defining the VLANs, you are designating ports on the switch for each network segment or tier.</span></span> <span data-ttu-id="b4f72-107">Debe crear una VLAN para cada uno de los siguientes entornos:</span><span class="sxs-lookup"><span data-stu-id="b4f72-107">You must create a VLAN for each of the following environments:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b4f72-108"> nivel de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="b4f72-108"> receive and send tier</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b4f72-109"> nivel de orquestación y de base de datos</span><span class="sxs-lookup"><span data-stu-id="b4f72-109"> orchestration and database tier</span></span>  

- <span data-ttu-id="b4f72-110">Red corporativa</span><span class="sxs-lookup"><span data-stu-id="b4f72-110">Corporate network</span></span>  

  <span data-ttu-id="b4f72-111">Después de haber definido las VLAN, puede conectar los cables de red de los servidores a los puertos correspondientes en el conmutador.</span><span class="sxs-lookup"><span data-stu-id="b4f72-111">After you have defined the VLANs, you can connect the network cables from the servers to the appropriate ports on the switch.</span></span>  

  <span data-ttu-id="b4f72-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="b4f72-112">This section contains:</span></span>  

- [<span data-ttu-id="b4f72-113">Diagrama físico</span><span class="sxs-lookup"><span data-stu-id="b4f72-113">Physical Diagram</span></span>](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  

- [<span data-ttu-id="b4f72-114">Equilibrio de carga de red</span><span class="sxs-lookup"><span data-stu-id="b4f72-114">Network Load Balancing</span></span>](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)
