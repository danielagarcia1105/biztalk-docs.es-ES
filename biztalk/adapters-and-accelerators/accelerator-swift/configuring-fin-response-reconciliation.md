---
title: "Configuración de conciliación de respuesta FIN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="f6bc0-102">Configuración de conciliación de respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="f6bc0-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="f6bc0-103">Debe realizar los pasos en las secciones siguientes para configurar el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] característica Conciliación de respuesta de FIN (FRR), tal como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-103">You must perform the steps in the following sections to configure the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 <span data-ttu-id="f6bc0-104">En el Asistente para la instalación de A4SWIFT, puede elegir instalar reparación de mensajes y nuevo envío y FRR, o reparación de mensajes y nuevo envío sin FRR o FRR sin reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-104">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="f6bc0-105">Como resultado, las instrucciones de esta sección no se da por supuesto que está instalando y configurando la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-105">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="f6bc0-106">, Sin embargo, se da por supuesto que ha llevado a cabo los pasos descritos en la [configurar el tiempo de ejecución de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span><span class="sxs-lookup"><span data-stu-id="f6bc0-106">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="f6bc0-107">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="f6bc0-107">This section contains:</span></span>  
  
-   [<span data-ttu-id="f6bc0-108">Enlazar e iniciar la orquestación FRR</span><span class="sxs-lookup"><span data-stu-id="f6bc0-108">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="f6bc0-109">Crear el FRR la canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="f6bc0-109">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="f6bc0-110">Crear la FRR ubicación de recepción para recibir de la aplicación de Back-End</span><span class="sxs-lookup"><span data-stu-id="f6bc0-110">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="f6bc0-111">Crear la FRR ubicación de recepción para la recepción de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-111">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="f6bc0-112">Crear la canalización de envío FRR</span><span class="sxs-lookup"><span data-stu-id="f6bc0-112">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="f6bc0-113">Crear el puerto de envío FRR para enviar para SWIFT</span><span class="sxs-lookup"><span data-stu-id="f6bc0-113">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="f6bc0-114">Creación de los puertos de envío FRR para enviar a los controladores personalizados</span><span class="sxs-lookup"><span data-stu-id="f6bc0-114">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)