---
title: Id. de tipo de datos en HL7 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7251ce1c041ebfd2f523e3304bd253fec22fb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983013"
---
# <a name="data-type-id-in-hl7"></a><span data-ttu-id="71448-102">Identificador de tipo de datos en HL7</span><span class="sxs-lookup"><span data-stu-id="71448-102">Data Type ID in HL7</span></span>
<span data-ttu-id="71448-103">En el caso de HL7 V2.1, el identificador de tipo de datos es un marcador de posición para los tipos de datos sin definir.</span><span class="sxs-lookup"><span data-stu-id="71448-103">In the case of HL7 V2.1, the data type ID is a placeholder for undefined data types.</span></span> <span data-ttu-id="71448-104">Los siguientes son ejemplos de su uso:</span><span class="sxs-lookup"><span data-stu-id="71448-104">The following are examples of its usage:</span></span>  
  
- <span data-ttu-id="71448-105">El tipo de datos en forma de un campo ST es SI (Id. de secuencia).</span><span class="sxs-lookup"><span data-stu-id="71448-105">The data type in the form of an ST field is SI (Sequence ID).</span></span>  
  
- <span data-ttu-id="71448-106">El tipo de datos en forma de un campo NM es campos compuestos.</span><span class="sxs-lookup"><span data-stu-id="71448-106">The data type in the form of an NM field is composite fields.</span></span>  
  
  <span data-ttu-id="71448-107">Los siguientes son ejemplos de tipos de datos compuesto definido específicamente:</span><span class="sxs-lookup"><span data-stu-id="71448-107">The following are examples of specifically defined composite data types:</span></span>  
  
- <span data-ttu-id="71448-108">CK: Identificador compuesto con el dígito de control.</span><span class="sxs-lookup"><span data-stu-id="71448-108">CK: Composite ID with check digit.</span></span> <span data-ttu-id="71448-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71448-109">For example:</span></span>  
  
  ```  
  |128952^6^M11|  
  ```  
  
- <span data-ttu-id="71448-110">CN: Número de identificador compuesto y nombre.</span><span class="sxs-lookup"><span data-stu-id="71448-110">CN: Composite ID number and name.</span></span> <span data-ttu-id="71448-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71448-111">For example:</span></span>  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- <span data-ttu-id="71448-112">CQ: La cantidad compuesta por unidades.</span><span class="sxs-lookup"><span data-stu-id="71448-112">CQ: Composite quantity with units.</span></span> <span data-ttu-id="71448-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71448-113">For example:</span></span>  
  
  ```  
  |123.7^ML|  
  ```  
  
- <span data-ttu-id="71448-114">CE: Elemento codificada.</span><span class="sxs-lookup"><span data-stu-id="71448-114">CE: Coded element.</span></span> <span data-ttu-id="71448-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71448-115">For example:</span></span>  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  <span data-ttu-id="71448-116">Este tipo de datos está localizado y definido por el sitio.</span><span class="sxs-lookup"><span data-stu-id="71448-116">This data type is localized and site-defined.</span></span> <span data-ttu-id="71448-117">Además, HL7 V2.1 no proporciona la cobertura para este tipo de datos en la base de datos de Access de HL7.</span><span class="sxs-lookup"><span data-stu-id="71448-117">Additionally, HL7 V2.1 does not provide the coverage for this data type in the HL7 Access database.</span></span> <span data-ttu-id="71448-118">Para generar los esquemas, el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se da por supuesto que los tipos de datos de HL7 V2.2 son válidos y usa esta información para generar los esquemas.</span><span class="sxs-lookup"><span data-stu-id="71448-118">For generating your schemas, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) assumes that the HL7 V2.2 data types are valid, and uses this information to build the schemas.</span></span> <span data-ttu-id="71448-119">Dependiendo del uso en el esquema, se debe usar un tipo de datos adecuado, lo que significa que el tipo de datos debe reemplazarse por CK, CQ, CE, ST ^ SI y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="71448-119">Depending on the usage in the schema, an appropriate data type must be used, meaning that the data type must be replaced with CK, CQ, CE, ST^SI, and so on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71448-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="71448-120">See Also</span></span>  
 <span data-ttu-id="71448-121">[Tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span><span class="sxs-lookup"><span data-stu-id="71448-121">[Data Types](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span></span>  
 <span data-ttu-id="71448-122">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="71448-122">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="71448-123">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="71448-123">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="71448-124">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="71448-124">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)