---
title: Desensamblador SWIFT y la funcionalidad de ensamblador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="1e9d9-102">Desensamblador SWIFT y la funcionalidad de ensamblador</span><span class="sxs-lookup"><span data-stu-id="1e9d9-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="1e9d9-103">El Desensamblador SWIFT puede realizar las siguientes tareas cuando se invoca en una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] la canalización de recepción:</span><span class="sxs-lookup"><span data-stu-id="1e9d9-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="1e9d9-104">Dinámicamente el tipo de mensaje de detectar y resolver el esquema de documento.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="1e9d9-105">Esto permite que un único puerto de recepción y canalización para controlar varios tipos de mensaje SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="1e9d9-106">Analizar un archivo plano SWIFT en XML.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-106">Parse a SWIFT flat file into XML.</span></span>  
  
-   <span data-ttu-id="1e9d9-107">Invoque el lector para realizar la validación de XML (esquema), como la comprobación de validez del tipo de datos, el formato de datos o la conformidad de longitud de la validación de XML.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
-   <span data-ttu-id="1e9d9-108">Invocar el motor de reglas de negocios (BRE) para realizar la validación del BRE, como la comprobación de conformidad con las reglas de red SWIFT o realizar otra validación compleja que no implementa el esquema.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
-   <span data-ttu-id="1e9d9-109">Publicar un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y colección de errores serializado de XML (con información sobre los errores detectados durante el análisis o validación).</span><span class="sxs-lookup"><span data-stu-id="1e9d9-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1e9d9-110">Si el Desensamblador encuentra errores irrecuperables durante el análisis, el Desensamblador publicará el mensaje en la base de datos de cuadro de mensajes en formato de archivo sin formato nativo en lugar de XML.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
-   <span data-ttu-id="1e9d9-111">Procesar lotes entrantes, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1e9d9-111">Process inbound batches, as follows:</span></span>  
  
    -   <span data-ttu-id="1e9d9-112">Analizar y conservar los sobres de lote (encabezado de lote, el finalizador de lote)</span><span class="sxs-lookup"><span data-stu-id="1e9d9-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
    -   <span data-ttu-id="1e9d9-113">Analizar y conservar los sobres de mensajes (encabezado del mensaje, el finalizador de mensaje)</span><span class="sxs-lookup"><span data-stu-id="1e9d9-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
    -   <span data-ttu-id="1e9d9-114">Analizar y validar los mensajes en el lote de SWIFT individualmente</span><span class="sxs-lookup"><span data-stu-id="1e9d9-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
    -   <span data-ttu-id="1e9d9-115">Publicar mensajes SWIFT en la base de datos de cuadro de mensajes individualmente</span><span class="sxs-lookup"><span data-stu-id="1e9d9-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
    -   <span data-ttu-id="1e9d9-116">Publicar todo el lote de entrada a la base de datos de cuadro de mensajes como un único mensaje (una copia exacta de entrada)</span><span class="sxs-lookup"><span data-stu-id="1e9d9-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
    -   <span data-ttu-id="1e9d9-117">Promocionar propiedades de contexto relacionadas con el lote de correlación de mensajes que se origina en el mismo lote u ordenación</span><span class="sxs-lookup"><span data-stu-id="1e9d9-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
 <span data-ttu-id="1e9d9-118">El ensamblador de SWIFT puede realizar las siguientes tareas cuando se invoca en una canalización de envío de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="1e9d9-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
-   <span data-ttu-id="1e9d9-119">Dinámicamente el tipo de mensaje de detectar y resolver el esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="1e9d9-120">Esto permite a un puerto de envío único y la canalización para controlar SWIFT varios tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="1e9d9-121">Serializar XML analizado en un archivo plano SWIFT.</span><span class="sxs-lookup"><span data-stu-id="1e9d9-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9d9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e9d9-122">See Also</span></span>  
 [<span data-ttu-id="1e9d9-123">Trabajar con el Desensamblador SWIFT y de ensamblador</span><span class="sxs-lookup"><span data-stu-id="1e9d9-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)