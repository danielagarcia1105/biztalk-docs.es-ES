---
title: Trabajar con el Desensamblador de SWIFT y ensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, assembler
- developing, disassembler
- assembler, developing
- disassembler, developing
ms.assetid: cc88ed4c-baed-4efa-b54f-9fe079df9ba4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1942e6648311c65acc2bb1cd91406904906cc8f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005741"
---
# <a name="working-with-the-swift-disassembler-and-assembler"></a><span data-ttu-id="8518e-102">Trabajar con el Desensamblador de SWIFT y ensamblador</span><span class="sxs-lookup"><span data-stu-id="8518e-102">Working with the SWIFT Disassembler and Assembler</span></span>
<span data-ttu-id="8518e-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona componentes de canalización personalizados, el Desensamblador de SWIFT y ensamblador de SWIFT que tienen características diseñadas específicamente para procesar los mensajes de archivo sin formato SWIFT.</span><span class="sxs-lookup"><span data-stu-id="8518e-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides custom pipeline components, the SWIFT disassembler, and SWIFT assembler that have features designed specifically for processing SWIFT flat-file messages.</span></span> <span data-ttu-id="8518e-104">El [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enviar y recibir los componentes de canalización de canalizaciones uso el A4SWIFT para llevar a cabo tareas específicas durante las fases definidas de entrada (recepción) y el procesamiento de salida (enviar).</span><span class="sxs-lookup"><span data-stu-id="8518e-104">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send and receive pipelines use the A4SWIFT pipeline components to perform specific tasks during defined stages of inbound (receive) and outbound (send) processing.</span></span> <span data-ttu-id="8518e-105">Para obtener más información sobre el procesamiento de mensajes, canalizaciones y los componentes de canalización, consulte la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8518e-105">For further details about message processing, pipelines, and pipeline components, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="8518e-106">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="8518e-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="8518e-107">Funcionalidad del desensamblador y el ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="8518e-107">SWIFT Disassembler and Assembler Functionality</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-and-assembler-functionality.md)  
  
-   [<span data-ttu-id="8518e-108">Agregar el desensamblador o ensamblador de SWIFT a una canalización</span><span class="sxs-lookup"><span data-stu-id="8518e-108">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-the-swift-disassembler-or-assembler-to-a-pipeline.md)  
  
-   [<span data-ttu-id="8518e-109">Configuración del desensamblador o ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="8518e-109">Configuring the SWIFT Disassembler or Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler-or-assembler.md)  
  
-   [<span data-ttu-id="8518e-110">Detección de tipos de mensaje dinámicos y resolución de esquemas</span><span class="sxs-lookup"><span data-stu-id="8518e-110">Dynamic Message Type Discovery and Schema Resolution</span></span>](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)  
  
-   [<span data-ttu-id="8518e-111">Creación de esquemas de encabezado personalizado para la detección de tipos de mensaje dinámicos</span><span class="sxs-lookup"><span data-stu-id="8518e-111">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-custom-header-schemas-for-dynamic-message-type-discovery.md)  
  
-   [<span data-ttu-id="8518e-112">Desensamblado de lotes de entrada</span><span class="sxs-lookup"><span data-stu-id="8518e-112">Disassembling Inbound Batches</span></span>](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)