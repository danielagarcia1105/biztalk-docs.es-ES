---
title: Ejemplo de escenario basado en concentrador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- hub-and-spoke systems
- supply chains, hub-and-spoke systems
- examples, supply chains
- trading partners, supply chains
ms.assetid: ee92c24d-a281-4950-a61e-9cb3bd08d291
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b417398786e602379d16d6734a5ed366b9d6f2ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210420"
---
# <a name="sample-hub-based-scenario"></a><span data-ttu-id="46e0c-102">Escenario de ejemplo basado en concentrador</span><span class="sxs-lookup"><span data-stu-id="46e0c-102">Sample Hub-Based Scenario</span></span>
<span data-ttu-id="46e0c-103">En muchos escenarios de cadena de suministro, una empresa trabajará con cada uno de sus socios comerciales para establecer una conexión de RosettaNet Implementation Framework (RNIF).</span><span class="sxs-lookup"><span data-stu-id="46e0c-103">In many supply-chain scenarios, a company will work with each of their trading partners to institute a RosettaNet Implementation Framework (RNIF) connection.</span></span> <span data-ttu-id="46e0c-104">Se trata de un método eficaz para estandarizar las comunicaciones en toda la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="46e0c-104">This is an effective way to standardize communications throughout the supply chain.</span></span> <span data-ttu-id="46e0c-105">Este escenario se describe en [escenario de cadena de suministro de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="46e0c-105">This scenario is described in [Sample Supply Chain Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md).</span></span>  
  
 <span data-ttu-id="46e0c-106">Otra manera de automatizar las transacciones en toda la cadena de suministro consiste en que la empresa contrate a otra organización para configurar y administrar el sistema integrado.</span><span class="sxs-lookup"><span data-stu-id="46e0c-106">Another way to automate transactions throughout the supply chain is for the company to contract with another company to set up and manage the integrated system.</span></span> <span data-ttu-id="46e0c-107">Este es un escenario basado en concentrador.</span><span class="sxs-lookup"><span data-stu-id="46e0c-107">This is a hub-based scenario.</span></span>  
  
## <a name="how-a-hub-based-system-works"></a><span data-ttu-id="46e0c-108">Cómo funciona un sistema basado en concentrador</span><span class="sxs-lookup"><span data-stu-id="46e0c-108">How a Hub-Based System Works</span></span>  
 <span data-ttu-id="46e0c-109">En un sistema basado en concentrador, la empresa que contrata un sistema integrado se conecta a la empresa de concentrador mediante una conexión RNIF.</span><span class="sxs-lookup"><span data-stu-id="46e0c-109">In a hub-based system, the company contracting for an integrated system connects to the hub company using an RNIF connection.</span></span> <span data-ttu-id="46e0c-110">A continuación, el concentrador se conecta a todos los socios comerciales de la empresa usando el tipo de conexión electrónica que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="46e0c-110">The hub then connects to all the company's trading partners using whatever type of electronic connection is required.</span></span> <span data-ttu-id="46e0c-111">La empresa de concentrador proporciona opciones de conexión a todos los socios comerciales: Conexiones RNIF, EDI, archivo plano, aplicaciones web o conexiones no compatibles de propietario.</span><span class="sxs-lookup"><span data-stu-id="46e0c-111">The hub company provides all the trading partners with connection options: RNIF connections, EDI, flat file, Web applications, or non-compliant, proprietary connections.</span></span> <span data-ttu-id="46e0c-112">La administración del sistema de comunicaciones es asunto de la empresa de concentrador.</span><span class="sxs-lookup"><span data-stu-id="46e0c-112">Managing the communications system is the hub company's business.</span></span> <span data-ttu-id="46e0c-113">La ilustración siguiente muestra el funcionamiento de este sistema.</span><span class="sxs-lookup"><span data-stu-id="46e0c-113">The following figure shows how such a system might work.</span></span>  
  
 <span data-ttu-id="46e0c-114">![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span><span class="sxs-lookup"><span data-stu-id="46e0c-114">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span></span>  
  
 <span data-ttu-id="46e0c-115">Un sistema basado en concentrador tiene muchas ventajas:</span><span class="sxs-lookup"><span data-stu-id="46e0c-115">A hub-based system has many advantages:</span></span>  
  
-   <span data-ttu-id="46e0c-116">La empresa contratante no tiene que preocuparse por la complejidad de la cadena de suministro, ya que se encarga de ello la empresa de concentrador.</span><span class="sxs-lookup"><span data-stu-id="46e0c-116">The contracting company does not have to deal with the complexity of the supply chain; the hub company handles it.</span></span>  
  
-   <span data-ttu-id="46e0c-117">La empresa contratante no tiene que mantener o actualizar el sistema y no es responsable del tiempo de inactividad; la empresa de concentrador se responsabiliza del mantenimiento del sistema y del tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="46e0c-117">The contracting company does not have to maintain or upgrade the system, and it is not responsible for downtime; the hub company is responsible for system maintenance and downtime.</span></span>  
  
-   <span data-ttu-id="46e0c-118">La empresa contratante se beneficia de las ventajas de un sistema compatible con RosettaNet, lo que incluye la estandarización, la automatización, el ahorro de costos y la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="46e0c-118">The contracting company gains the advantages of a RosettaNet-compliant system, including standardization, automation, cost savings, and visibility.</span></span>  
  
-   <span data-ttu-id="46e0c-119">La empresa contratante automatiza por completo su cadena de suministro con diversas conexiones electrónicas que ofrecen a todos los socios comerciales una selección de conexiones.</span><span class="sxs-lookup"><span data-stu-id="46e0c-119">The contracting company has fully automated their supply chain with a variety of electronic connections that give the full array of trading partners a choice of connections.</span></span> <span data-ttu-id="46e0c-120">La empresa contratante no necesita tener conocimientos tecnológicos en diversas opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="46e0c-120">The contracting company does not have to maintain technological expertise in a variety of connection options.</span></span>  
  
-   <span data-ttu-id="46e0c-121">Un socio comercial puede seguir usando una conexión de propietario, siempre y cuando lo admita la empresa de concentrador.</span><span class="sxs-lookup"><span data-stu-id="46e0c-121">A trading partner can continue to use a proprietary connection, as long as the hub company supports it.</span></span>  
  
-   <span data-ttu-id="46e0c-122">El sistema es flexible.</span><span class="sxs-lookup"><span data-stu-id="46e0c-122">The system is flexible.</span></span> <span data-ttu-id="46e0c-123">No es necesario que los socios comerciales adopten un sistema compatible con RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="46e0c-123">Trading partners do not have to adopt a RosettaNet-compliant system.</span></span> <span data-ttu-id="46e0c-124">Sin embargo, si lo hacen, podrán beneficiarse de dicho sistema.</span><span class="sxs-lookup"><span data-stu-id="46e0c-124">However, if they do so, they will gain the benefits from such a system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e0c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="46e0c-125">See Also</span></span>  
 <span data-ttu-id="46e0c-126">[Cómo BizTalk Server resuelve la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span><span class="sxs-lookup"><span data-stu-id="46e0c-126">[How BizTalk Server Solves the Business Need](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span></span>  
 <span data-ttu-id="46e0c-127">[La necesidad de integración de socios comerciales](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span><span class="sxs-lookup"><span data-stu-id="46e0c-127">[The Need for Trading Partner Integration](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span></span>  
 <span data-ttu-id="46e0c-128">[El desafío de la cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span><span class="sxs-lookup"><span data-stu-id="46e0c-128">[The Supply Chain Challenge](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span></span>  
 <span data-ttu-id="46e0c-129">[La solución de la cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span><span class="sxs-lookup"><span data-stu-id="46e0c-129">[The Supply Chain Solution](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span></span>  
 [<span data-ttu-id="46e0c-130">Escenario de cadena de suministro de ejemplo</span><span class="sxs-lookup"><span data-stu-id="46e0c-130">Sample Supply Chain Scenario</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)