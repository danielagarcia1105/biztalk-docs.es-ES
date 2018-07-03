---
title: Esquemas de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f749a06c694007008f3d8138b2b087b77b2c4f03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996117"
---
# <a name="swift-schemas"></a><span data-ttu-id="3fca3-102">Esquemas de SWIFT</span><span class="sxs-lookup"><span data-stu-id="3fca3-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="3fca3-103"> envía y recibe mensajes de (FIN) de financieros SWIFT como archivos sin formato individuales a través de la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3fca3-103"> sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="3fca3-104">Cada mensaje individual se compone de un conjunto de bloques de encabezado, un bloque de texto que se compone de un conjunto predefinido de etiquetado campos y subcampos posicionales u ordenados y un conjunto de finalizadores dentro de un bloque de finalizador.</span><span class="sxs-lookup"><span data-stu-id="3fca3-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="3fca3-105">El contenido del bloque de texto varía según el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fca3-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="3fca3-106">También hay muchas aplicaciones, que se intercambian los lotes de mensajes de (FIN) financieros SWIFT: un conjunto de mensajes contenidos en un único archivo.</span><span class="sxs-lookup"><span data-stu-id="3fca3-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="3fca3-107">El archivo, es posible que se entrega localmente o se transmita a través de FileAct (a través de la red IP SWIFT: SIPN), o a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="3fca3-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="3fca3-108">Para simplificar la manipulación de los datos asociados con estos mensajes, independientemente de si están por lotes o individualmente, envía Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] proporciona un esquema XSD que define cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fca3-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="3fca3-109">Este esquema promueve al tipo de mensaje para que los mensajes puedan asocia automáticamente con el esquema apropiado y se transforma automáticamente entre la representación de archivo sin formato externo, utilizada por la red SWIFT, a y desde XML.</span><span class="sxs-lookup"><span data-stu-id="3fca3-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="3fca3-110">El esquema incluye todos los bloques que se incluyen los encabezados de texto y finalizadores.</span><span class="sxs-lookup"><span data-stu-id="3fca3-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="3fca3-111">Este esquema es un intercambio, porque es lo suficientemente completa para transmitir mensajes a través de la red SWIFT mediante los protocolos de nivel de mensaje FIN y para que contenga toda la información asociada con un mensaje recibido a través de la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="3fca3-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="3fca3-112">El esquema para cada tipo de mensaje define el formato general y el contexto de ese tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3fca3-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="3fca3-113">A4SWIFT define cada bloque.</span><span class="sxs-lookup"><span data-stu-id="3fca3-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="3fca3-114">Dentro de cada bloque, se distribuyen los campos y subcampos. Según corresponda, se crean los campos y subcampos a partir de tipos comunes de bases o complejos, definidos en esquemas distintos.</span><span class="sxs-lookup"><span data-stu-id="3fca3-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="3fca3-115">Validación de nivel de esquema que incluye el formato, juego de caracteres, valor establecido, intervalo, obligatorias y opcionales, la repetibilidad, posición y longitud, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="3fca3-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="3fca3-116">Las reglas de negocios realizan validaciones de campos cruzados y otras comprobaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="3fca3-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="3fca3-117">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="3fca3-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="3fca3-118">Presentación de mensajes de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fca3-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="3fca3-119">Presentación de esquemas de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fca3-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="3fca3-120">Encabezados de SWIFT</span><span class="sxs-lookup"><span data-stu-id="3fca3-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="3fca3-121">Texto de SWIFT</span><span class="sxs-lookup"><span data-stu-id="3fca3-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="3fca3-122">Finalizadores SWIFT</span><span class="sxs-lookup"><span data-stu-id="3fca3-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="3fca3-123">Actualización de los estándares de mensaje SWIFT</span><span class="sxs-lookup"><span data-stu-id="3fca3-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)