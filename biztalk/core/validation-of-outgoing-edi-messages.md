---
title: "Validación de mensajes EDI salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-outgoing-edi-messages"></a><span data-ttu-id="70e96-102">Validación de mensajes EDI salientes</span><span class="sxs-lookup"><span data-stu-id="70e96-102">Validation of Outgoing EDI Messages</span></span>
<span data-ttu-id="70e96-103">Cuando la canalización de envío EDI procesa un mensaje que se va a enviar, se llevan a cabo una serie de validaciones en los datos del sobre y del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70e96-103">When the EDI send pipeline processes a message to be sent, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="70e96-104">Siempre se llevan a cabo algunos de estos procesos. Otros sólo se realizan si usted los habilita.</span><span class="sxs-lookup"><span data-stu-id="70e96-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="70e96-105">Entre estas validaciones, se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="70e96-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="70e96-106">Validación de esquema de los elementos de datos de conjuntos de transacciones con respecto al esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="70e96-106">Schema validation of the transaction-set data elements against the message schema.</span></span> <span data-ttu-id="70e96-107">Esta validación siempre se lleva a cabo.</span><span class="sxs-lookup"><span data-stu-id="70e96-107">This is always performed.</span></span>  
  
-   <span data-ttu-id="70e96-108">Validación de campos cruzados en los elementos de datos del conjunto de transacciones (sólo mensajes con codificación X12).</span><span class="sxs-lookup"><span data-stu-id="70e96-108">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="70e96-109">Esta validación se realiza si se habilita en el esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="70e96-109">This is performed if it is enabled in the message schema.</span></span>  
  
-   <span data-ttu-id="70e96-110">Validación EDI realizada en elementos de datos de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="70e96-110">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="70e96-111">Esto se lleva a cabo si se habilita en las propiedades de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="70e96-111">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="70e96-112">Validación extendida realizada en elementos de datos de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="70e96-112">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="70e96-113">Esto se lleva a cabo si se habilita en las propiedades de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="70e96-113">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="70e96-114">Validación de los conjuntos de transacciones en un único grupo basado en el conjunto de transacciones; asignación de grupo, según los estándares X12.</span><span class="sxs-lookup"><span data-stu-id="70e96-114">Validation of the transaction sets within a single group based on the transaction set – group mapping, according to X12 standards.</span></span> <span data-ttu-id="70e96-115">Esto se realiza solo cuando la **opción de procesamiento por lotes de entrada** propiedad está establecida en **conservar intercambio: suspender intercambio en caso de Error** o **conservar intercambio: Suspender transacción Establece en caso de Error**.</span><span class="sxs-lookup"><span data-stu-id="70e96-115">This is performed only when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e96-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="70e96-116">See Also</span></span>  
 <span data-ttu-id="70e96-117">[Validación estructural de EDI](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="70e96-117">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="70e96-118">[Validación de propiedades de acuerdo](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="70e96-118">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="70e96-119">[Validación de tipo (elemento de datos) de EDI](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="70e96-119">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="70e96-120">[Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="70e96-120">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="70e96-121">[Validación de esquemas](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="70e96-121">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="70e96-122">Campo de segmento validación cruzada</span><span class="sxs-lookup"><span data-stu-id="70e96-122">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)