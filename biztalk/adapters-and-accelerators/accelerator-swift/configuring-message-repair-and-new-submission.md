---
title: Configuración de reparación de mensajes y nuevo envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, configuring
- A4SWIFT, Message Repair and New Submission
- configuring, Message Repair and New Submission
ms.assetid: e3e5e865-109c-469e-8b5b-c2675583d5a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2cdbad69b017a3927d3912de42053072d061b6
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848972"
---
# <a name="configuring-message-repair-and-new-submission"></a><span data-ttu-id="8526d-102">Configuración de reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="8526d-102">Configuring Message Repair and New Submission</span></span>
<span data-ttu-id="8526d-103">Debe realizar los pasos en las secciones siguientes para configurar la característica de reparación de mensajes y nuevo envío de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], tal y como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="8526d-103">You must perform the steps in the following sections to configure the Message Repair and New Submission feature of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], as shown in the following figure.</span></span>  
  
 <span data-ttu-id="8526d-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span><span class="sxs-lookup"><span data-stu-id="8526d-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span></span>  
  
 <span data-ttu-id="8526d-105">En el Asistente para la instalación de A4SWIFT, puede elegir instalar reparación de mensajes y nuevo envío y conciliación de respuesta de FIN (FRR), o reparación de mensajes y nuevo envío sin FRR o FRR sin reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="8526d-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FIN Response Reconciliation (FRR), or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="8526d-106">Como resultado, las instrucciones de esta sección no se da por supuesto que está instalando y configurando FRR.</span><span class="sxs-lookup"><span data-stu-id="8526d-106">As a result, the instructions in this section do not assume that you are installing and configuring FRR.</span></span> <span data-ttu-id="8526d-107">, Sin embargo, se da por supuesto que ha llevado a cabo los pasos descritos en la [Guía de configuración de componentes de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) sección.</span><span class="sxs-lookup"><span data-stu-id="8526d-107">They do, however, assume that you have performed the steps in the [A4SWIFT Component Configuration Guide](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) section.</span></span>  
  
 <span data-ttu-id="8526d-108">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="8526d-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="8526d-109">Instalación de certificados</span><span class="sxs-lookup"><span data-stu-id="8526d-109">Installing Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)  
  
-   [<span data-ttu-id="8526d-110">Configuración de las propiedades de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="8526d-110">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)  
  
-   [<span data-ttu-id="8526d-111">Agregar usuarios de A4SWIFT y actualizar grupos de Windows</span><span class="sxs-lookup"><span data-stu-id="8526d-111">Adding A4SWIFT Users and Updating Windows Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-a4swift-users-and-updating-windows-groups.md)  
  
-   [<span data-ttu-id="8526d-112">Agregar funciones y departamentos</span><span class="sxs-lookup"><span data-stu-id="8526d-112">Adding Roles and Departments</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-roles-and-departments.md)  
  
-   [<span data-ttu-id="8526d-113">Implementación de esquemas de sobres de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="8526d-113">Deploying A4SWIFT Envelope Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-envelope-schemas.md)  
  
-   [<span data-ttu-id="8526d-114">Publicar plantillas de formulario de InfoPath</span><span class="sxs-lookup"><span data-stu-id="8526d-114">Publishing InfoPath Form Templates</span></span>](http://msdn.microsoft.com/2947e1ad-8c44-4cdb-bbde-7683e186b41b)