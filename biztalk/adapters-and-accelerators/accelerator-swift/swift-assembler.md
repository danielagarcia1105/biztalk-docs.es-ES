---
title: Ensamblador de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 39f89720a36c026fa0e8f02902a8fefb08fcebf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973317"
---
# <a name="swift-assembler"></a><span data-ttu-id="e8020-102">Ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="e8020-102">SWIFT Assembler</span></span>
<span data-ttu-id="e8020-103">Una canalización de envío saliente procesa todos los mensajes transmitidos por un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (que se envían a través de un puerto de envío).</span><span class="sxs-lookup"><span data-stu-id="e8020-103">An outbound send pipeline processes all messages transmitted by an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (sent through a send port).</span></span>  
  
 <span data-ttu-id="e8020-104">Fases de la lógica de ejecución relacionados con el procesamiento de salida son las canalizaciones de envío de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e8020-104">Logical execution stages related to outbound processing make up the BizTalk send pipelines.</span></span> <span data-ttu-id="e8020-105">Un componente de canalización de servicios o implementa cada fase.</span><span class="sxs-lookup"><span data-stu-id="e8020-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="e8020-106">En concreto, el ensamblador de servicios de la fase de ensamblado en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="e8020-106">In particular, the assembler services the assemble stage in the receive pipeline.</span></span> <span data-ttu-id="e8020-107">A4SWIFT proporciona funcionalidad de procesamiento en un componente de ensamblador personalizados de mensaje saliente de SWIFT específicos.</span><span class="sxs-lookup"><span data-stu-id="e8020-107">A4SWIFT provides SWIFT-specific outbound message processing functionality in a custom assembler component.</span></span>  
  
 <span data-ttu-id="e8020-108">El ensamblador de SWIFT, un ensamblador de archivo sin formato personalizado, proporciona funcionalidad para procesar los mensajes salientes de SWIFT y realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="e8020-108">The SWIFT assembler, a custom flat file assembler, provides functionality for processing outbound SWIFT messages, and performs the following functions:</span></span>  
  
- <span data-ttu-id="e8020-109">Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento</span><span class="sxs-lookup"><span data-stu-id="e8020-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="e8020-110">Serializa el XML analizado en archivos planos SWIFT</span><span class="sxs-lookup"><span data-stu-id="e8020-110">Serializes parsed XML into SWIFT flat files</span></span>  
  
  <span data-ttu-id="e8020-111">La siguiente ilustración muestra los datos del ensamblador de SWIFT flujo.</span><span class="sxs-lookup"><span data-stu-id="e8020-111">The following figure shows the SWIFT assembler data flow.</span></span>  
  
  <span data-ttu-id="e8020-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")</span><span class="sxs-lookup"><span data-stu-id="e8020-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")</span></span>  
  
  <span data-ttu-id="e8020-113">Para obtener más información acerca del ensamblador de SWIFT, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="e8020-113">For more information about the SWIFT assembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8020-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8020-114">See Also</span></span>  
 [<span data-ttu-id="e8020-115">Acelerador de BizTalk para el tiempo de ejecución de SWIFT</span><span class="sxs-lookup"><span data-stu-id="e8020-115">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)