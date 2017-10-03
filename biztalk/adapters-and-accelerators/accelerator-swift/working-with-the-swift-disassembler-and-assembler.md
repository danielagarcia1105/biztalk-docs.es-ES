---
title: Trabajar con el Desensamblador SWIFT y de ensamblador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, assembler
- developing, disassembler
- assembler, developing
- disassembler, developing
ms.assetid: cc88ed4c-baed-4efa-b54f-9fe079df9ba4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ae6acb6239821362ad5f488e9b95b9ffcc43d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-the-swift-disassembler-and-assembler"></a><span data-ttu-id="a0c0c-102">Trabajar con el Desensamblador SWIFT y de ensamblador</span><span class="sxs-lookup"><span data-stu-id="a0c0c-102">Working with the SWIFT Disassembler and Assembler</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="a0c0c-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona componentes de canalización personalizados, el Desensamblador SWIFT y SWIFT ensamblador que tienen características diseñadas específicamente para procesar los mensajes de archivo sin formato SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a0c0c-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides custom pipeline components, the SWIFT disassembler, and SWIFT assembler that have features designed specifically for processing SWIFT flat-file messages.</span></span> <span data-ttu-id="a0c0c-104">El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enviar y recibir los componentes de canalización de uso la A4SWIFT de canalizaciones para llevar a cabo tareas específicas durante las etapas que se definen de entrada (recepción) y el procesamiento de salida (envío).</span><span class="sxs-lookup"><span data-stu-id="a0c0c-104">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send and receive pipelines use the A4SWIFT pipeline components to perform specific tasks during defined stages of inbound (receive) and outbound (send) processing.</span></span> <span data-ttu-id="a0c0c-105">Para obtener más información sobre el procesamiento de mensajes, canalizaciones y componentes de canalización, consulte [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="a0c0c-105">For further details about message processing, pipelines, and pipeline components, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="a0c0c-106">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="a0c0c-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="a0c0c-107">Desensamblador SWIFT y la funcionalidad de ensamblador</span><span class="sxs-lookup"><span data-stu-id="a0c0c-107">SWIFT Disassembler and Assembler Functionality</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-and-assembler-functionality.md)  
  
-   [<span data-ttu-id="a0c0c-108">Agregar el SWIFT Desensamblador o ensamblador a una canalización</span><span class="sxs-lookup"><span data-stu-id="a0c0c-108">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-the-swift-disassembler-or-assembler-to-a-pipeline.md)  
  
-   [<span data-ttu-id="a0c0c-109">Configurar el Desensamblador SWIFT o ensamblador</span><span class="sxs-lookup"><span data-stu-id="a0c0c-109">Configuring the SWIFT Disassembler or Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler-or-assembler.md)  
  
-   [<span data-ttu-id="a0c0c-110">Detección de tipo de mensaje dinámico y la resolución de esquemas</span><span class="sxs-lookup"><span data-stu-id="a0c0c-110">Dynamic Message Type Discovery and Schema Resolution</span></span>](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)  
  
-   [<span data-ttu-id="a0c0c-111">Crear esquemas de encabezado personalizado para la detección del tipo de mensaje dinámico</span><span class="sxs-lookup"><span data-stu-id="a0c0c-111">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-custom-header-schemas-for-dynamic-message-type-discovery.md)  
  
-   [<span data-ttu-id="a0c0c-112">Desensamblado de lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="a0c0c-112">Disassembling Inbound Batches</span></span>](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)