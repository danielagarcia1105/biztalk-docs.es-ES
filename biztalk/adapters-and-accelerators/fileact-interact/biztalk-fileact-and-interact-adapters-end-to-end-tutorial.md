---
title: BizTalk FileAct e interactuar adaptadores-to-End Tutorial | Microsoft Docs
ms.custom: ''
ms.date: 2015-12-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fbfb10-73e8-4365-a943-bcb9055f4f74
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af083b0e38d372c18bca4496033983cd7f579347
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014805"
---
# <a name="biztalk-fileact-and-interact-adapters-end-to-end-tutorial"></a><span data-ttu-id="270ca-102">BizTalk FileAct e interactuar Tutorial to-End de adaptadores</span><span class="sxs-lookup"><span data-stu-id="270ca-102">BizTalk FileAct and InterAct Adapters End-to-End Tutorial</span></span>
<span data-ttu-id="270ca-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Tutorial de extremo a otro proporciona información específica acerca de cómo puede usar [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para configurar en tiempo real y almacenar y reenviar los escenarios de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="270ca-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-to-End Tutorial provides specific information about how you can use [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to set up real-time and store and forward message exchange scenarios.</span></span>  
  
 <span data-ttu-id="270ca-104">El [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial proporciona cuatro escenarios independientes que incluyen los pasos detallados en el formulario de tutoriales para cada tipo de solución.</span><span class="sxs-lookup"><span data-stu-id="270ca-104">The [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial provides four separate scenarios that include detailed steps in the form of tutorials for each type of solution.</span></span> <span data-ttu-id="270ca-105">Antes de comenzar estos tutoriales, debe conocer los conceptos básicos que rodean a BizTalk Server y estar familiarizado con la documentación de la puerta de enlace de la alianza de SWIFT (SAG).</span><span class="sxs-lookup"><span data-stu-id="270ca-105">Before you begin these tutorials, you should understand the fundamental concepts surrounding BizTalk Server, and be familiar with the SWIFT Alliance Gateway (SAG) documentation.</span></span>  
  
 <span data-ttu-id="270ca-106">El tutorial de extremo a otro de A4SWIFT proporciona los pasos detallados para configurar en tiempo real y escenarios de almacenamiento y reenvío con adaptadores tanto el FileAct e InterAct de A4Swift.</span><span class="sxs-lookup"><span data-stu-id="270ca-106">The A4SWIFT end-to-end tutorial provides you with detailed steps to configure real-time and store-and-forward scenarios with both the FileAct and InterAct adapters for A4Swift.</span></span> <span data-ttu-id="270ca-107">Para cada uno de los escenarios, hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="270ca-107">For each of the scenarios, you will do the following:</span></span>  
  
- <span data-ttu-id="270ca-108">Configurar el adaptador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="270ca-108">Configure the SWIFT adapter</span></span>  
  
- <span data-ttu-id="270ca-109">Configurar el archivo de parámetros de SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="270ca-109">Configure the SWIFTNet paramfile</span></span>  
  
- <span data-ttu-id="270ca-110">Crear puertos de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="270ca-110">Create send ports and receive ports</span></span>  
  
- <span data-ttu-id="270ca-111">El escenario de prueba</span><span class="sxs-lookup"><span data-stu-id="270ca-111">Test the scenario</span></span>  
  
  <span data-ttu-id="270ca-112">En este tutorial, desempeñará los dos roles: remitente y receptor.</span><span class="sxs-lookup"><span data-stu-id="270ca-112">In this tutorial, you will play two roles: Sender and Receiver.</span></span> <span data-ttu-id="270ca-113">Creará puertos de envían de mensajes y recibirán.</span><span class="sxs-lookup"><span data-stu-id="270ca-113">You will create ports that send messages and receive them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="270ca-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="270ca-114">In This Section</span></span>  
  
-   [<span data-ttu-id="270ca-115">Preparación para usar el tutorial</span><span class="sxs-lookup"><span data-stu-id="270ca-115">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)  
  
-   [<span data-ttu-id="270ca-116">Escenario de InterAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="270ca-116">InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="270ca-117">Escenario de almacenamiento y reenvío (inserción) de InterAct</span><span class="sxs-lookup"><span data-stu-id="270ca-117">InterAct Store and Forward (Push) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)  
  
-   [<span data-ttu-id="270ca-118">Escenario de FileAct en tiempo real</span><span class="sxs-lookup"><span data-stu-id="270ca-118">FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="270ca-119">Escenario de almacenamiento y reenvío de FileAct</span><span class="sxs-lookup"><span data-stu-id="270ca-119">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)