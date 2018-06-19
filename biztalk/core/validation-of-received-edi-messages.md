---
title: Validación de mensajes EDI recibidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc48b343332ea6b402841ec5ed1f5c9af49b2dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288060"
---
# <a name="validation-of-received-edi-messages"></a><span data-ttu-id="dd45b-102">Validación de mensajes EDI recibidos</span><span class="sxs-lookup"><span data-stu-id="dd45b-102">Validation of Received EDI Messages</span></span>
<span data-ttu-id="dd45b-103">Cuando la canalización de recepción EDI procesa un mensaje entrante, se llevan a cabo una serie de validaciones en los datos del sobre y del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd45b-103">When the EDI receive pipeline processes an incoming message, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="dd45b-104">Siempre se llevan a cabo algunos de estos procesos. Otros sólo se realizan si usted los habilita.</span><span class="sxs-lookup"><span data-stu-id="dd45b-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="dd45b-105">Entre estas validaciones, se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd45b-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="dd45b-106">**Las validaciones que siempre se realizan son**:</span><span class="sxs-lookup"><span data-stu-id="dd45b-106">**The validations that are always performed are**:</span></span>  
  
    -   <span data-ttu-id="dd45b-107">Validación de la estructura del sobre de intercambio.</span><span class="sxs-lookup"><span data-stu-id="dd45b-107">Validation of the structure of the interchange envelope.</span></span>  
  
    -   <span data-ttu-id="dd45b-108">Validación del sobre con respecto al acuerdo entre socios comerciales (o acuerdo de reserva si no se ha definido ningún acuerdo).</span><span class="sxs-lookup"><span data-stu-id="dd45b-108">Validation of the envelope against trading partner agreement (or fallback agreement if no agreement is defined).</span></span>  
  
    -   <span data-ttu-id="dd45b-109">Validación de esquema del sobre con respecto al esquema de control.</span><span class="sxs-lookup"><span data-stu-id="dd45b-109">Schema validation of the envelope against the control schema.</span></span>  
  
    -   <span data-ttu-id="dd45b-110">Validación de esquema de los elementos de datos de conjuntos de transacciones con respecto al esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd45b-110">Schema validation of the transaction-set data elements against the message schema.</span></span>  
  
    -   <span data-ttu-id="dd45b-111">Validación de los tipos de conjuntos de transacciones en un único grupo en función de la asignación conjunto de transacciones-grupo proporcionada por los estándares X12.</span><span class="sxs-lookup"><span data-stu-id="dd45b-111">Validation of the types of transaction sets within a single group based on the transaction set -group mapping provided by X12 standards.</span></span>  
  
-   <span data-ttu-id="dd45b-112">**Las validaciones que se realizan solo si se habilitan son**:</span><span class="sxs-lookup"><span data-stu-id="dd45b-112">**The validations that are performed only if enabled are**:</span></span>  
  
    -   <span data-ttu-id="dd45b-113">Validación EDI realizada en elementos de datos de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="dd45b-113">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="dd45b-114">Esta se lleva a cabo si se habilita en las propiedades de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="dd45b-114">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="dd45b-115">Validación extendida realizada en elementos de datos de conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="dd45b-115">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="dd45b-116">Esta se lleva a cabo si se habilita en las propiedades de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="dd45b-116">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="dd45b-117">Validación de campos cruzados en los elementos de datos del conjunto de transacciones (sólo mensajes con codificación X12).</span><span class="sxs-lookup"><span data-stu-id="dd45b-117">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="dd45b-118">Esta se lleva a cabo si se habilita en el esquema del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd45b-118">This is performed if enabled in the message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd45b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd45b-119">See Also</span></span>  
 <span data-ttu-id="dd45b-120">[Validación estructural de EDI](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="dd45b-120">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="dd45b-121">[Validación de propiedades de acuerdo](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="dd45b-121">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="dd45b-122">[Validación de tipo (elemento de datos) de EDI](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="dd45b-122">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="dd45b-123">[Validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="dd45b-123">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="dd45b-124">[Validación de esquemas](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="dd45b-124">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="dd45b-125">Campo de segmento validación cruzada</span><span class="sxs-lookup"><span data-stu-id="dd45b-125">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)