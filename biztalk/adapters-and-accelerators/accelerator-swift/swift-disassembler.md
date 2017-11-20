---
title: Desensamblador SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler"></a><span data-ttu-id="9ae41-102">Desensamblador SWIFT</span><span class="sxs-lookup"><span data-stu-id="9ae41-102">SWIFT Disassembler</span></span>
<span data-ttu-id="9ae41-103">Una canalización de recepción entrante procesa todos los mensajes enviados a un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (recibida en una ubicación de recepción).</span><span class="sxs-lookup"><span data-stu-id="9ae41-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="9ae41-104">Fases de ejecución lógico relacionados con el procesamiento de entrada componen BizTalk canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="9ae41-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="9ae41-105">Un componente de canalización de servicios o que implemente cada fase.</span><span class="sxs-lookup"><span data-stu-id="9ae41-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="9ae41-106">En concreto, el Desensamblador de servicios de la fase de desensamblado en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="9ae41-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="9ae41-107">A4SWIFT proporciona funcionalidad en un componente de desensamblador personalizado de procesamiento de mensajes de SWIFT específica.</span><span class="sxs-lookup"><span data-stu-id="9ae41-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="9ae41-108">El Desensamblador SWIFT, un desensamblador de archivos sin formato personalizado, proporciona funcionalidad para procesar lotes y los mensajes entrantes de SWIFT y realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="9ae41-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="9ae41-109">Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento</span><span class="sxs-lookup"><span data-stu-id="9ae41-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="9ae41-110">Analiza los archivos planos SWIFT en XML</span><span class="sxs-lookup"><span data-stu-id="9ae41-110">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="9ae41-111">Invoca el lector para realizar la validación XML (esquema) de validación de XML</span><span class="sxs-lookup"><span data-stu-id="9ae41-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="9ae41-112">Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE</span><span class="sxs-lookup"><span data-stu-id="9ae41-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="9ae41-113">Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado de XML</span><span class="sxs-lookup"><span data-stu-id="9ae41-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="9ae41-114">Procesa y desensambla lotes entrantes</span><span class="sxs-lookup"><span data-stu-id="9ae41-114">Processes and disassembles inbound batches</span></span>  
  
 <span data-ttu-id="9ae41-115">En la siguiente ilustración se muestra los datos SWIFT Desensamblador flujo.</span><span class="sxs-lookup"><span data-stu-id="9ae41-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 <span data-ttu-id="9ae41-116">Para obtener más información acerca de cómo el Desensamblador SWIFT, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="9ae41-116">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae41-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ae41-117">See Also</span></span>  
 [<span data-ttu-id="9ae41-118">Acelerador de BizTalk para SWIFT en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9ae41-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)