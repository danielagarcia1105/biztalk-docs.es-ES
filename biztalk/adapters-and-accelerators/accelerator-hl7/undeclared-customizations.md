---
title: Personalizaciones no declaradas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a33abb76d49cfa5db640b1d15d9fde420f19c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974229"
---
# <a name="undeclared-customizations"></a><span data-ttu-id="1bf52-102">Personalizaciones no declaradas</span><span class="sxs-lookup"><span data-stu-id="1bf52-102">Undeclared Customizations</span></span>
<span data-ttu-id="1bf52-103">Puede agregar datos a un mensaje sin tener que definir el formato o la naturaleza de los datos.</span><span class="sxs-lookup"><span data-stu-id="1bf52-103">You can add data to a message without defining the format or nature of the data.</span></span> <span data-ttu-id="1bf52-104">Hacerlo mediante el uso de los segmentos de Z no declarados.</span><span class="sxs-lookup"><span data-stu-id="1bf52-104">You do so by using undeclared Z segments.</span></span> <span data-ttu-id="1bf52-105">Segmentos de Z no declarados son instancias inesperadas al final de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="1bf52-105">Undeclared Z segments are unexpected instances at the end of a message.</span></span> <span data-ttu-id="1bf52-106">El validador de XML/analizador no valida el segmento.</span><span class="sxs-lookup"><span data-stu-id="1bf52-106">The parser/XML validator does not validate the segment.</span></span> <span data-ttu-id="1bf52-107">No se define ningún esquema.</span><span class="sxs-lookup"><span data-stu-id="1bf52-107">It is not defined by any schema.</span></span> <span data-ttu-id="1bf52-108">Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) trata el segmento como un objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="1bf52-108">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) treats the segment as a binary large object (BLOB).</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1bf52-109"> pasa los datos de segmentos de Z no declarados a través como la tercera parte de un mensaje de tres partes.</span><span class="sxs-lookup"><span data-stu-id="1bf52-109"> passes undeclared Z segment data through as the third part of a three-part message.</span></span> <span data-ttu-id="1bf52-110">Las tres partes son el encabezado, el cuerpo y el segmento de Z no declarado, que también se denomina parte Z.</span><span class="sxs-lookup"><span data-stu-id="1bf52-110">The three parts are the header, the body, and the undeclared Z segment, also called the Z part.</span></span> <span data-ttu-id="1bf52-111">Un principio de Id. de segmento con la letra "Z", por ejemplo, "ZPD" para obtener información personalizada datos demográficos de los pacientes, identifica la parte de la Z.</span><span class="sxs-lookup"><span data-stu-id="1bf52-111">A segment ID beginning with the letter "Z", for instance, "ZPD" for custom patient demographics information, identifies the Z part.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf52-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bf52-112">See Also</span></span>  
 <span data-ttu-id="1bf52-113">[Personalizaciones declaradas](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="1bf52-113">[Declared Customizations](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span></span>  
 <span data-ttu-id="1bf52-114">[Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="1bf52-114">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="1bf52-115">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="1bf52-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="1bf52-116">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="1bf52-116">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="1bf52-117">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="1bf52-117">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)