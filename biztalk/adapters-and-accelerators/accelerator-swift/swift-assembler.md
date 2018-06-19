---
title: Ensamblador SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214436"
---
# <a name="swift-assembler"></a><span data-ttu-id="072d1-102">Ensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="072d1-102">SWIFT Assembler</span></span>
<span data-ttu-id="072d1-103">Una canalización de envío saliente procesa todos los mensajes transmitidos por un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (que se envían a través de un puerto de envío).</span><span class="sxs-lookup"><span data-stu-id="072d1-103">An outbound send pipeline processes all messages transmitted by an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (sent through a send port).</span></span>  
  
 <span data-ttu-id="072d1-104">Fases de ejecución lógico relacionados con el procesamiento de salida son las canalizaciones de envío de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="072d1-104">Logical execution stages related to outbound processing make up the BizTalk send pipelines.</span></span> <span data-ttu-id="072d1-105">Un componente de canalización de servicios o que implemente cada fase.</span><span class="sxs-lookup"><span data-stu-id="072d1-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="072d1-106">En concreto, el ensamblador de servicios de la fase de ensamblado en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="072d1-106">In particular, the assembler services the assemble stage in the receive pipeline.</span></span> <span data-ttu-id="072d1-107">A4SWIFT proporciona funcionalidad en un componente de ensamblador personalizados de procesamiento de mensajes salientes de SWIFT específica.</span><span class="sxs-lookup"><span data-stu-id="072d1-107">A4SWIFT provides SWIFT-specific outbound message processing functionality in a custom assembler component.</span></span>  
  
 <span data-ttu-id="072d1-108">El ensamblador de SWIFT, un ensamblador de archivos sin formato personalizado, proporciona funcionalidad para procesar los mensajes salientes de SWIFT y realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="072d1-108">The SWIFT assembler, a custom flat file assembler, provides functionality for processing outbound SWIFT messages, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="072d1-109">Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento</span><span class="sxs-lookup"><span data-stu-id="072d1-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="072d1-110">Serializa el XML analizado en archivos planos SWIFT</span><span class="sxs-lookup"><span data-stu-id="072d1-110">Serializes parsed XML into SWIFT flat files</span></span>  
  
 <span data-ttu-id="072d1-111">En la siguiente ilustración se muestra los datos de ensamblador SWIFT flujo.</span><span class="sxs-lookup"><span data-stu-id="072d1-111">The following figure shows the SWIFT assembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 <span data-ttu-id="072d1-112">Para obtener más información acerca de cómo el ensamblador SWIFT, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="072d1-112">For more information about the SWIFT assembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072d1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="072d1-113">See Also</span></span>  
 [<span data-ttu-id="072d1-114">Acelerador de BizTalk para SWIFT en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="072d1-114">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)