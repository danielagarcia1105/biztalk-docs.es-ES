---
title: Configuración de conciliación de respuestas de FIN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f2260c8e6096e2bef926fea45aaf778f4bdfa3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997909"
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="73d1b-102">Configuración de conciliación de respuestas de FIN</span><span class="sxs-lookup"><span data-stu-id="73d1b-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="73d1b-103">Debe realizar los pasos en las secciones siguientes para configurar Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] característica de conciliación de respuesta de FIN (FRR), tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="73d1b-103">You must perform the steps in the following sections to configure the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="73d1b-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span><span class="sxs-lookup"><span data-stu-id="73d1b-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span></span>  
  
 <span data-ttu-id="73d1b-105">En el Asistente para instalación de A4SWIFT, puede elegir instalar reparación de mensajes y nuevo envío y FRR, o reparación de mensajes y nuevo envío sin FRR o FRR sin reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="73d1b-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="73d1b-106">Como resultado, las instrucciones de esta sección no suponen que está instalando y configurando la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="73d1b-106">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="73d1b-107">Sin embargo,, suponga que ha realizado los pasos descritos en la [configurar el tiempo de ejecución de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span><span class="sxs-lookup"><span data-stu-id="73d1b-107">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="73d1b-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="73d1b-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="73d1b-109">Enlace e inicio de la orquestación de FRR</span><span class="sxs-lookup"><span data-stu-id="73d1b-109">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="73d1b-110">Creación de la canalización de recepción de FRR</span><span class="sxs-lookup"><span data-stu-id="73d1b-110">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="73d1b-111">Creación de la ubicación de recepción de FRR para recibir de la aplicación back-end</span><span class="sxs-lookup"><span data-stu-id="73d1b-111">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="73d1b-112">Creación de la ubicación de recepción de FRR para recibir de SWIFT</span><span class="sxs-lookup"><span data-stu-id="73d1b-112">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="73d1b-113">Creación de la canalización de envío de FRR</span><span class="sxs-lookup"><span data-stu-id="73d1b-113">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="73d1b-114">Creación del puerto de envío de FRR para enviar a SWIFT</span><span class="sxs-lookup"><span data-stu-id="73d1b-114">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="73d1b-115">Creación de los puertos de envío de FRR para enviar a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="73d1b-115">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)