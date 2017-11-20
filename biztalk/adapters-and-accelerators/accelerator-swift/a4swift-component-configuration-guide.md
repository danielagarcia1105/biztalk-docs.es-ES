---
title: "Guía de configuración de componentes de A4SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: A4SWIFT, configuration guide
ms.assetid: ff4a3ee7-2fd9-44e7-8aa3-c3d214a6ce68
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 396e28d49b3e6a43e188e8358a045c3c91a627cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-component-configuration-guide"></a><span data-ttu-id="0cc1d-102">Guía de configuración de componentes de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="0cc1d-102">A4SWIFT Component Configuration Guide</span></span>
<span data-ttu-id="0cc1d-103">Esta guía proporciona información acerca de cómo configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cc1d-103">This guide provides information about configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="0cc1d-104">Realice los pasos de esta guía de configuración después de haber instalado A4SWIFT y completar al Asistente para configuración de A4SWIFT (como se describe en la Guía de instalación).</span><span class="sxs-lookup"><span data-stu-id="0cc1d-104">Perform the steps in this configuration guide after you have installed A4SWIFT and completed the A4SWIFT Configuration Wizard (as described in the Installation Guide).</span></span> <span data-ttu-id="0cc1d-105">Esta guía de configuración incluye las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0cc1d-105">This configuration guide includes the following instructions:</span></span>  
  
-   <span data-ttu-id="0cc1d-106">Pasos posteriores a la instalación para configurar el tiempo de ejecución de A4SWIFT para escenarios de mensajería.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-106">Post-installation steps for configuring the A4SWIFT runtime for messaging scenarios.</span></span>  
  
-   <span data-ttu-id="0cc1d-107">Cómo configurar la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-107">How to configure Message Repair and New Submission.</span></span> <span data-ttu-id="0cc1d-108">Para ello, primero se debe configurar manualmente el tiempo de ejecución de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-108">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="0cc1d-109">Esto no requiere que configure conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-109">This does not require that you configure FIN Response Reconciliation.</span></span>  
  
-   <span data-ttu-id="0cc1d-110">Cómo configurar la conciliación de respuesta de FIN.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-110">How to configure FIN Response Reconciliation.</span></span> <span data-ttu-id="0cc1d-111">Para ello, primero se debe configurar manualmente el tiempo de ejecución de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-111">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="0cc1d-112">Esto no requiere que configure la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-112">This does not require that you configure Message Repair and New Submission.</span></span>  
  
 <span data-ttu-id="0cc1d-113">En la siguiente ilustración muestra los componentes de A4SWIFT que se va a configurar.</span><span class="sxs-lookup"><span data-stu-id="0cc1d-113">The following figure shows the A4SWIFT components that you will configure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-component-configuration.gif "A4SWIFT_Component_Configuration")  
  
 <span data-ttu-id="0cc1d-114">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="0cc1d-114">This section contains:</span></span>  
  
-   [<span data-ttu-id="0cc1d-115">Configurar el tiempo de ejecución de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="0cc1d-115">Configuring the A4SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)  
  
-   [<span data-ttu-id="0cc1d-116">Configuración de reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="0cc1d-116">Configuring Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="0cc1d-117">Configuración de conciliación de respuesta FIN</span><span class="sxs-lookup"><span data-stu-id="0cc1d-117">Configuring FIN Response Reconciliation</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)