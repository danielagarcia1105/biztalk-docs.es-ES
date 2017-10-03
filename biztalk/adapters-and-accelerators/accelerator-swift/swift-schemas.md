---
title: Esquemas SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schemas"></a><span data-ttu-id="31a66-102">Esquemas SWIFT</span><span class="sxs-lookup"><span data-stu-id="31a66-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="31a66-103">envía y recibe mensajes de (FIN) de financieros SWIFT distintos archivos planos a través de la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="31a66-103"> sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="31a66-104">Cada mensaje individual se compone de un conjunto de bloques de encabezado, un bloque de texto que se compone de un conjunto predefinido de etiquetado campos y subcampos ordenados o posicionales y un conjunto de finalizadores dentro de un bloque de finalizador.</span><span class="sxs-lookup"><span data-stu-id="31a66-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="31a66-105">El contenido del bloque de texto varía según el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="31a66-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="31a66-106">También hay muchas aplicaciones, que intercambian lotes de mensajes de (FIN) financieros SWIFT: un conjunto de mensajes contenidos en un único archivo.</span><span class="sxs-lookup"><span data-stu-id="31a66-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="31a66-107">El archivo puede entregar localmente o que se transmita a través de FileAct (a través de la red IP de SWIFT: SIPN), o a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="31a66-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="31a66-108">Para simplificar la manipulación de los datos asociados a estos mensajes, independientemente de si se procesan por lotes o envían individualmente, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] proporciona un esquema XSD que define cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="31a66-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="31a66-109">Este esquema promueve al tipo de mensaje para que los mensajes se puedan asociados automáticamente con el esquema apropiado y transforma automáticamente entre la representación de archivo sin formato externo, utilizada por la red SWIFT, a y desde XML.</span><span class="sxs-lookup"><span data-stu-id="31a66-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="31a66-110">El esquema incluye todos los bloques incluidos los encabezados, el texto y finalizadores.</span><span class="sxs-lookup"><span data-stu-id="31a66-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="31a66-111">Este esquema es un esquema de intercambio, porque es lo suficientemente exhaustivos para transmitir mensajes a través de la red SWIFT mediante los protocolos de nivel de mensaje FIN y para que contenga toda la información asociada a un mensaje recibido a través de la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="31a66-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="31a66-112">El esquema para cada tipo de mensaje define el formato global y el contexto de ese tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="31a66-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="31a66-113">A4SWIFT define cada bloque.</span><span class="sxs-lookup"><span data-stu-id="31a66-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="31a66-114">Dentro de cada bloque están dispuestos los campos y subcampos. Según corresponda, se generan los campos y subcampos a partir de tipos comunes de base o complejos, definidos en esquemas distintos.</span><span class="sxs-lookup"><span data-stu-id="31a66-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="31a66-115">Validación de nivel de esquema que incluye el formato, juego de caracteres, valor establecido, intervalo, obligatorias y opcionales, capacidad de repetición, posición y longitud, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="31a66-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="31a66-116">Las reglas de negocios realizan validaciones de campos cruzados y otras comprobaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="31a66-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="31a66-117">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="31a66-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="31a66-118">Presentación de mensajes de ejemplo</span><span class="sxs-lookup"><span data-stu-id="31a66-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="31a66-119">Presentación del esquema de ejemplo</span><span class="sxs-lookup"><span data-stu-id="31a66-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="31a66-120">Encabezados de SWIFT</span><span class="sxs-lookup"><span data-stu-id="31a66-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="31a66-121">Texto SWIFT</span><span class="sxs-lookup"><span data-stu-id="31a66-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="31a66-122">Finalizadores SWIFT</span><span class="sxs-lookup"><span data-stu-id="31a66-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="31a66-123">Actualización de los estándares de mensaje SWIFT</span><span class="sxs-lookup"><span data-stu-id="31a66-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)