---
title: BizTalk FileAct e interactuar adaptadores-to-End Tutorial | Documentos de Microsoft
ms.custom: 
ms.date: 2015-12-10
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73fbfb10-73e8-4365-a943-bcb9055f4f74
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f2908abdb039d531fc0829efa7e019a6d0ca03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-fileact-and-interact-adapters-end-to-end-tutorial"></a><span data-ttu-id="47ae6-102">BizTalk FileAct e interactuar Tutorial de adaptadores-to-End</span><span class="sxs-lookup"><span data-stu-id="47ae6-102">BizTalk FileAct and InterAct Adapters End-to-End Tutorial</span></span>
<span data-ttu-id="47ae6-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] -to-End Tutorial proporciona información específica acerca de cómo puede usar [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para configurar en tiempo real, almacenar y reenviar los escenarios de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="47ae6-103">The Microsoft® [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-to-End Tutorial provides specific information about how you can use [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to set up real-time and store and forward message exchange scenarios.</span></span>  
  
 <span data-ttu-id="47ae6-104">El [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial proporciona cuatro escenarios independientes que incluyen los pasos detallados en el formulario de tutoriales para cada tipo de solución.</span><span class="sxs-lookup"><span data-stu-id="47ae6-104">The [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] End-To-End Tutorial provides four separate scenarios that include detailed steps in the form of tutorials for each type of solution.</span></span> <span data-ttu-id="47ae6-105">Antes de comenzar estos tutoriales, debe comprender los conceptos fundamentales sobre BizTalk Server y estar familiarizado con la documentación de la puerta de enlace de Alliance de SWIFT (SAG).</span><span class="sxs-lookup"><span data-stu-id="47ae6-105">Before you begin these tutorials, you should understand the fundamental concepts surrounding BizTalk Server, and be familiar with the SWIFT Alliance Gateway (SAG) documentation.</span></span>  
  
 <span data-ttu-id="47ae6-106">El tutorial de extremo a extremo de A4SWIFT proporciona instrucciones detalladas para configurar en tiempo real y escenarios de almacenamiento y reenvío con adaptadores tanto el FileAct e InterAct de A4Swift.</span><span class="sxs-lookup"><span data-stu-id="47ae6-106">The A4SWIFT end-to-end tutorial provides you with detailed steps to configure real-time and store-and-forward scenarios with both the FileAct and InterAct adapters for A4Swift.</span></span> <span data-ttu-id="47ae6-107">Para cada uno de los escenarios, hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47ae6-107">For each of the scenarios, you will do the following:</span></span>  
  
-   <span data-ttu-id="47ae6-108">Configure el adaptador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="47ae6-108">Configure the SWIFT adapter</span></span>  
  
-   <span data-ttu-id="47ae6-109">Configurar la paramfile SWIFTNet</span><span class="sxs-lookup"><span data-stu-id="47ae6-109">Configure the SWIFTNet paramfile</span></span>  
  
-   <span data-ttu-id="47ae6-110">Crear puertos de envío y puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="47ae6-110">Create send ports and receive ports</span></span>  
  
-   <span data-ttu-id="47ae6-111">El escenario de prueba</span><span class="sxs-lookup"><span data-stu-id="47ae6-111">Test the scenario</span></span>  
  
 <span data-ttu-id="47ae6-112">En este tutorial, desempeñará dos roles: remitente y receptor.</span><span class="sxs-lookup"><span data-stu-id="47ae6-112">In this tutorial, you will play two roles: Sender and Receiver.</span></span> <span data-ttu-id="47ae6-113">Creará puertos que envían mensajes y recibirán.</span><span class="sxs-lookup"><span data-stu-id="47ae6-113">You will create ports that send messages and receive them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47ae6-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="47ae6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="47ae6-115">Preparando para utilizar el Tutorial</span><span class="sxs-lookup"><span data-stu-id="47ae6-115">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)  
  
-   [<span data-ttu-id="47ae6-116">Interactuar en tiempo real escenario</span><span class="sxs-lookup"><span data-stu-id="47ae6-116">InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="47ae6-117">Interactuar almacén y escenario de reenvío (inserción)</span><span class="sxs-lookup"><span data-stu-id="47ae6-117">InterAct Store and Forward (Push) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)  
  
-   [<span data-ttu-id="47ae6-118">Escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="47ae6-118">FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="47ae6-119">Escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="47ae6-119">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)