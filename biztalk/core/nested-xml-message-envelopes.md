---
title: Anidar sobres de mensajes XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263844"
---
# <a name="nested-xml-message-envelopes"></a><span data-ttu-id="92021-102">Sobres de mensajes XML anidados</span><span class="sxs-lookup"><span data-stu-id="92021-102">Nested XML Message Envelopes</span></span>
<span data-ttu-id="92021-103">Los sobres XML se pueden anidar para crear estructuras complejas de documentos.</span><span class="sxs-lookup"><span data-stu-id="92021-103">XML envelopes can be nested to create complex document structures.</span></span> <span data-ttu-id="92021-104">Los sobres XML anidados pueden aparecer de dos formas: flexible y canónica.</span><span class="sxs-lookup"><span data-stu-id="92021-104">Nested XML envelopes can occur in two forms, known as flexible and canonical.</span></span> <span data-ttu-id="92021-105">En el siguiente ejemplo se muestra la forma flexible de documentos con doble cifrado, donde los documentos y los sobres (en negrita) pueden aparecer en el mismo nivel dentro de un sobre envolvente.</span><span class="sxs-lookup"><span data-stu-id="92021-105">The following example shows the flexible form of enveloped documents, in which documents and envelopes (shown in bold type) can appear at the same level within an enclosing envelope.</span></span>  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="92021-106">El siguiente ejemplo muestra un mensaje de instancia similar que se ajusta a la forma canónica de documentos con doble cifrado, donde todos los documentos aparecen en el mismo nivel dentro del sobre más interno.</span><span class="sxs-lookup"><span data-stu-id="92021-106">The following example shows a similar instance message that conforms to the canonical form of enveloped documents, in which all documents appear at the same level within the innermost envelope.</span></span>  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 <span data-ttu-id="92021-107">Para un determinado mensaje de instancia con una de las formas descritas, el desensamblador XML producirá los documentos document1, document2, document3 y document4.</span><span class="sxs-lookup"><span data-stu-id="92021-107">Given an instance message in either of the forms described, the XML disassembler will produce document1, document2, document3, and document4.</span></span> <span data-ttu-id="92021-108">El contexto del mensaje de cada uno de estos documentos incluye las propiedades promocionadas a partir del documento correspondiente, así como las propiedades promocionadas dentro de cada uno de los sobres envolventes.</span><span class="sxs-lookup"><span data-stu-id="92021-108">The message context of each of these documents includes the properties promoted from the corresponding document as well as the properties promoted within each of the enclosing envelopes.</span></span> <span data-ttu-id="92021-109">La tabla siguiente muestra las propiedades promocionadas que se incluirán en el contexto del mensaje de cada documento no incluido, para los ejemplos de forma flexible y canónica, según las promociones de propiedades que se especifiquen en la primera columna para los distintos sobres y documentos.</span><span class="sxs-lookup"><span data-stu-id="92021-109">The following table shows the promoted properties that will be include in the message context of each unwrapped documents for both the flexible and canonical examples, given the property promotions specified in the first column for the various envelopes and documents.</span></span>  
  
|<span data-ttu-id="92021-110">Promociones de propiedades especificadas</span><span class="sxs-lookup"><span data-stu-id="92021-110">Specified property promotions</span></span>|<span data-ttu-id="92021-111">Propiedades del contexto del mensaje para el ejemplo de forma flexible</span><span class="sxs-lookup"><span data-stu-id="92021-111">Resulting message context properties for flexible example</span></span>|<span data-ttu-id="92021-112">Propiedades del contexto del mensaje para el ejemplo de forma canónica</span><span class="sxs-lookup"><span data-stu-id="92021-112">Resulting message context properties for canonical example</span></span>|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|<span data-ttu-id="92021-113">envelope1: p1</span><span class="sxs-lookup"><span data-stu-id="92021-113">envelope1: p1</span></span><br /><br /> <span data-ttu-id="92021-114">envelope2: p3</span><span class="sxs-lookup"><span data-stu-id="92021-114">envelope2: p3</span></span><br /><br /> <span data-ttu-id="92021-115">Document1: p2</span><span class="sxs-lookup"><span data-stu-id="92021-115">document1: p2</span></span><br /><br /> <span data-ttu-id="92021-116">Document2: p4 y p5</span><span class="sxs-lookup"><span data-stu-id="92021-116">document2: p4 and p5</span></span><br /><br /> <span data-ttu-id="92021-117">document3: ninguna promoción</span><span class="sxs-lookup"><span data-stu-id="92021-117">document3: no promotions</span></span><br /><br /> <span data-ttu-id="92021-118">document4: ninguna promoción</span><span class="sxs-lookup"><span data-stu-id="92021-118">document4: no promotions</span></span>|<span data-ttu-id="92021-119">Document1: p1, p2</span><span class="sxs-lookup"><span data-stu-id="92021-119">document1: p1, p2</span></span><br /><br /> <span data-ttu-id="92021-120">Document2: p1, p3, p4, p5</span><span class="sxs-lookup"><span data-stu-id="92021-120">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="92021-121">document3: p1, p3</span><span class="sxs-lookup"><span data-stu-id="92021-121">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="92021-122">document4: p1</span><span class="sxs-lookup"><span data-stu-id="92021-122">document4: p1</span></span>|<span data-ttu-id="92021-123">Document1: p1, p2, p3</span><span class="sxs-lookup"><span data-stu-id="92021-123">document1: p1, p2, p3</span></span><br /><br /> <span data-ttu-id="92021-124">Document2: p1, p3, p4, p5</span><span class="sxs-lookup"><span data-stu-id="92021-124">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="92021-125">document3: p1, p3</span><span class="sxs-lookup"><span data-stu-id="92021-125">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="92021-126">document4: p1, p3</span><span class="sxs-lookup"><span data-stu-id="92021-126">document4: p1, p3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92021-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="92021-127">See Also</span></span>  
 <span data-ttu-id="92021-128">[Sobres de mensajes XML](../core/xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="92021-128">[XML Message Envelopes](../core/xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="92021-129">[Estructura de un mensaje XML](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="92021-129">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="92021-130">Cómo crear esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="92021-130">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)