---
title: Las personalizaciones no declaradas | Documentos de Microsoft
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
ms.openlocfilehash: 77f688e4cf6a4bbb55243d9f5f6f60e144bad862
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206492"
---
# <a name="undeclared-customizations"></a><span data-ttu-id="ec0de-102">Personalizaciones no declaradas</span><span class="sxs-lookup"><span data-stu-id="ec0de-102">Undeclared Customizations</span></span>
<span data-ttu-id="ec0de-103">Puede agregar datos a un mensaje sin tener que definir el formato o la naturaleza de los datos.</span><span class="sxs-lookup"><span data-stu-id="ec0de-103">You can add data to a message without defining the format or nature of the data.</span></span> <span data-ttu-id="ec0de-104">La forma de hacerlo es mediante el uso de los segmentos de Z no declarados.</span><span class="sxs-lookup"><span data-stu-id="ec0de-104">You do so by using undeclared Z segments.</span></span> <span data-ttu-id="ec0de-105">Segmentos de Z no declarados son instancias inesperados al final de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec0de-105">Undeclared Z segments are unexpected instances at the end of a message.</span></span> <span data-ttu-id="ec0de-106">El validador de analizador/XML no valida el segmento.</span><span class="sxs-lookup"><span data-stu-id="ec0de-106">The parser/XML validator does not validate the segment.</span></span> <span data-ttu-id="ec0de-107">No se define ningún esquema.</span><span class="sxs-lookup"><span data-stu-id="ec0de-107">It is not defined by any schema.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="ec0de-108">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) trata el segmento como un objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="ec0de-108"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) treats the segment as a binary large object (BLOB).</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="ec0de-109">no declarados segmentar datos de Z a través de se pasa como la tercera parte de un mensaje de tres partes.</span><span class="sxs-lookup"><span data-stu-id="ec0de-109"> passes undeclared Z segment data through as the third part of a three-part message.</span></span> <span data-ttu-id="ec0de-110">Las tres partes son el encabezado, el cuerpo y el segmento de Z no declarado, también denominado elemento Z.</span><span class="sxs-lookup"><span data-stu-id="ec0de-110">The three parts are the header, the body, and the undeclared Z segment, also called the Z part.</span></span> <span data-ttu-id="ec0de-111">Un segmento identificador que comienza con la letra "Z", por ejemplo, "ZPD" para obtener información de datos demográficos de los pacientes personalizado, identifica la parte de Z.</span><span class="sxs-lookup"><span data-stu-id="ec0de-111">A segment ID beginning with the letter "Z", for instance, "ZPD" for custom patient demographics information, identifies the Z part.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0de-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec0de-112">See Also</span></span>  
 <span data-ttu-id="ec0de-113">[Personalizaciones declaradas](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="ec0de-113">[Declared Customizations](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span></span>  
 <span data-ttu-id="ec0de-114">[Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ec0de-114">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="ec0de-115">[Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ec0de-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="ec0de-116">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="ec0de-116">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="ec0de-117">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="ec0de-117">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)