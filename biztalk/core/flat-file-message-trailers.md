---
title: Finalizadores de mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-message-trailers"></a><span data-ttu-id="719b7-102">Finalizadores de los mensajes de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="719b7-102">Flat File Message Trailers</span></span>
<span data-ttu-id="719b7-103">Como con encabezados de mensaje de instancia de archivo sin formato, el análisis del finalizador de mensaje de instancia de archivo sin formato opcional el Desensamblador de archivos sin formato se controla mediante el esquema de archivo sin formato que se ha configurado en el **esquema de finalizador** tiempo de diseño propiedad del desensamblador de archivos sin formato o **XMLNORM. TrailerSpecName** propiedad de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="719b7-103">As with flat file instance message headers, the parsing of the optional flat file instance message trailer by the flat file disassembler is controlled by the flat file schema that you have configured in the **Trailer schema** design-time property of the flat file disassembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="719b7-104">Si no ha especificado un esquema con uno de estos dos métodos, el desensamblador de archivos sin formato considerará que el mensaje de instancia de archivo sin formato no contiene un finalizador.</span><span class="sxs-lookup"><span data-stu-id="719b7-104">If you have not specified a schema using one of these two methods, the flat file disassembler will assume that the flat file instance message does not contain a trailer.</span></span>  
  
 <span data-ttu-id="719b7-105">A diferencia de los encabezados de los mensajes de instancia de archivo sin formato, los finalizadores de los mensajes de instancia de archivo sin formato no se pueden guardar ni restaurar como una única unidad ni pueden usar la promoción de propiedades para copiar elementos individuales de datos al contexto del mensaje asociado con el cuerpo del mensaje de instancia de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="719b7-105">Unlike with flat file instance message headers, flat file instance message trailers can neither be saved and restored as a single unit, nor can they use property promotion to copy individual items of data to the message context associated with the flat file instance message body.</span></span> <span data-ttu-id="719b7-106">Sin embargo, puede agregarse un finalizador a un mensaje de instancia de archivo sin formato especificando el esquema apropiado en el **esquema de finalizador** propiedad en tiempo de diseño del ensamblador de archivo sin formato o **XMLNORM. TrailerSpecName** propiedad de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="719b7-106">However, a trailer can be added to an outbound flat file instance message by specifying the appropriate schema in the **Trailer schema** design-time property of the flat file assembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="719b7-107">Los datos que constituyen la parte variable del finalizador se pueden especificar mediante la degradación de propiedades desde el contexto del mensaje del cuerpo del mensaje de instancia de archivo sin formato o mediante la especificación de valores predeterminados o fijos en el esquema correspondiente.</span><span class="sxs-lookup"><span data-stu-id="719b7-107">The data that constitutes the variable portion of the trailer can be specified using property demotion from the message context of the flat file instance message body, or by specifying default or fixed values in the corresponding schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="719b7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="719b7-108">See Also</span></span>  
 <span data-ttu-id="719b7-109">[Encabezados de mensaje de archivo sin formato](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="719b7-109">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="719b7-110">[Cuerpos de mensaje de archivo sin formato](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="719b7-110">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="719b7-111">[Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="719b7-111">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="719b7-112">Cómo crear esquemas para mensajes de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="719b7-112">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)