---
title: Desensamblador de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25c389e10a48287ef87495b32fe2d69644a8259e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010925"
---
# <a name="swift-disassembler"></a><span data-ttu-id="b7a95-102">Desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="b7a95-102">SWIFT Disassembler</span></span>
<span data-ttu-id="b7a95-103">Una canalización de recepción entrante procesa todos los mensajes enviados a un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (se recibe en una ubicación de recepción).</span><span class="sxs-lookup"><span data-stu-id="b7a95-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="b7a95-104">Canalizaciones de recepción de las fases de la lógica de ejecución relacionados con el procesamiento de entrada se componen de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b7a95-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="b7a95-105">Un componente de canalización de servicios o implementa cada fase.</span><span class="sxs-lookup"><span data-stu-id="b7a95-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="b7a95-106">En concreto, el Desensamblador de servicios de la fase de desensamblado en la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="b7a95-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="b7a95-107">A4SWIFT proporciona la funcionalidad en un componente de desensamblador personalizado de procesamiento de mensajes de SWIFT específicos.</span><span class="sxs-lookup"><span data-stu-id="b7a95-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="b7a95-108">El Desensamblador de SWIFT, un desensamblador de archivos sin formato personalizado, proporciona funcionalidad para el procesamiento de lotes y los mensajes entrantes de SWIFT y realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="b7a95-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
- <span data-ttu-id="b7a95-109">Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento</span><span class="sxs-lookup"><span data-stu-id="b7a95-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="b7a95-110">Analiza archivos planos SWIFT en XML</span><span class="sxs-lookup"><span data-stu-id="b7a95-110">Parses SWIFT flat files into XML</span></span>  
  
- <span data-ttu-id="b7a95-111">Invoca el lector para realizar la validación de XML (esquema) de validación de XML</span><span class="sxs-lookup"><span data-stu-id="b7a95-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
- <span data-ttu-id="b7a95-112">Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE</span><span class="sxs-lookup"><span data-stu-id="b7a95-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
- <span data-ttu-id="b7a95-113">Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado XML</span><span class="sxs-lookup"><span data-stu-id="b7a95-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
- <span data-ttu-id="b7a95-114">Procesa y desensambla los lotes de entrada</span><span class="sxs-lookup"><span data-stu-id="b7a95-114">Processes and disassembles inbound batches</span></span>  
  
  <span data-ttu-id="b7a95-115">La siguiente ilustración muestra los datos de desensamblador de SWIFT flujo.</span><span class="sxs-lookup"><span data-stu-id="b7a95-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
  <span data-ttu-id="b7a95-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span><span class="sxs-lookup"><span data-stu-id="b7a95-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span></span>  
  
  <span data-ttu-id="b7a95-117">Para obtener más información sobre el Desensamblador de SWIFT, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span><span class="sxs-lookup"><span data-stu-id="b7a95-117">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a95-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a95-118">See Also</span></span>  
 [<span data-ttu-id="b7a95-119">Acelerador de BizTalk para el tiempo de ejecución de SWIFT</span><span class="sxs-lookup"><span data-stu-id="b7a95-119">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)