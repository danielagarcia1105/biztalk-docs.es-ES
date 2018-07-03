---
title: Funcionalidad de ensamblador y desensamblador de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9a01480c5d308ffa882b2457e26548f4b5e43b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992861"
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="73a39-102">Funcionalidad de ensamblador y desensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="73a39-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="73a39-103">El Desensamblador de SWIFT puede realizar las tareas siguientes cuando se invoca en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de recepción:</span><span class="sxs-lookup"><span data-stu-id="73a39-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
- <span data-ttu-id="73a39-104">Detectar el tipo de mensaje y resolver el esquema de documento de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="73a39-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="73a39-105">Esto permite que un único puerto de recepción y canalización para controlar varios tipos de mensaje SWIFT.</span><span class="sxs-lookup"><span data-stu-id="73a39-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="73a39-106">Analizar un archivo plano SWIFT en XML.</span><span class="sxs-lookup"><span data-stu-id="73a39-106">Parse a SWIFT flat file into XML.</span></span>  
  
- <span data-ttu-id="73a39-107">Invoque el lector para realizar la validación de XML (esquema), como la comprobación de validez del tipo de datos, el formato de datos o la conformidad de longitud de la validación de XML.</span><span class="sxs-lookup"><span data-stu-id="73a39-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
- <span data-ttu-id="73a39-108">Invocar el motor de reglas de negocios (BRE) para realizar la validación del BRE, como la comprobación de conformidad con las reglas de red SWIFT o realizar otra validación compleja que no implementa el esquema.</span><span class="sxs-lookup"><span data-stu-id="73a39-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
- <span data-ttu-id="73a39-109">Publicar un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado XML (con información sobre los errores detectados durante el análisis o validación).</span><span class="sxs-lookup"><span data-stu-id="73a39-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="73a39-110">Si el Desensamblador encuentra errores irrecuperables durante el análisis, el Desensamblador publicará el mensaje en la base de datos de cuadro de mensajes en formato de archivo sin formato nativo en lugar de XML.</span><span class="sxs-lookup"><span data-stu-id="73a39-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
- <span data-ttu-id="73a39-111">Procesar lotes entrantes, como sigue:</span><span class="sxs-lookup"><span data-stu-id="73a39-111">Process inbound batches, as follows:</span></span>  
  
  -   <span data-ttu-id="73a39-112">Analizar y conservar los sobres por lotes (encabezado de lote, el finalizador de lote)</span><span class="sxs-lookup"><span data-stu-id="73a39-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
  -   <span data-ttu-id="73a39-113">Analizar y conservar los sobres de mensajes (encabezado del mensaje, el finalizador de mensaje)</span><span class="sxs-lookup"><span data-stu-id="73a39-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
  -   <span data-ttu-id="73a39-114">Analizar y validar los mensajes del lote de SWIFT individualmente</span><span class="sxs-lookup"><span data-stu-id="73a39-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
  -   <span data-ttu-id="73a39-115">Publicar los mensajes de SWIFT para la base de datos de cuadro de mensajes individualmente</span><span class="sxs-lookup"><span data-stu-id="73a39-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
  -   <span data-ttu-id="73a39-116">Publicar todo el lote de entrada en la base de datos de cuadro de mensajes como un solo mensaje (una copia exacta de entrada)</span><span class="sxs-lookup"><span data-stu-id="73a39-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
  -   <span data-ttu-id="73a39-117">Promocionar propiedades de contexto relacionado con el lote de ordenación o poner en correlación los mensajes que se origina en el mismo lote</span><span class="sxs-lookup"><span data-stu-id="73a39-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
  <span data-ttu-id="73a39-118">El ensamblador de SWIFT puede realizar las tareas siguientes cuando se invoca en una canalización de envío de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="73a39-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
- <span data-ttu-id="73a39-119">Detectar el tipo de mensaje y resolver el esquema de documento de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="73a39-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="73a39-120">Esto permite a un puerto de envío único y la canalización para controlar varios SWIFT tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="73a39-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="73a39-121">Serializar XML analizado en un archivo plano SWIFT.</span><span class="sxs-lookup"><span data-stu-id="73a39-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a39-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a39-122">See Also</span></span>  
 [<span data-ttu-id="73a39-123">Trabajar con el desensamblador y el ensamblador de SWIFT</span><span class="sxs-lookup"><span data-stu-id="73a39-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)