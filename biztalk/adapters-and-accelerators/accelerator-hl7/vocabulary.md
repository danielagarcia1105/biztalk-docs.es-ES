---
title: Vocabulario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e72b51e327581c0a17f18582b0511218b556a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979037"
---
# <a name="vocabulary"></a><span data-ttu-id="01490-102">Vocabulario</span><span class="sxs-lookup"><span data-stu-id="01490-102">Vocabulary</span></span>
<span data-ttu-id="01490-103">HL7 versión 2 proporciona compatibilidad para vocabularios para elementos codificados, pero en su mayor parte, proporciona una estructura que transmite códigos procedentes de los sistemas locales de codificación.</span><span class="sxs-lookup"><span data-stu-id="01490-103">HL7 Version 2 provides some support for vocabularies for coded elements, but for the most part, provides a structure that transmits codes drawn from local coding systems.</span></span>  
  
 <span data-ttu-id="01490-104">De HL7 versión 2, una tabla de segmentos vincula todos los campos codificados.</span><span class="sxs-lookup"><span data-stu-id="01490-104">In HL7 Version 2, a segment table links all coded fields.</span></span> <span data-ttu-id="01490-105">La tabla segmento incluye el identificador de la tabla que usa el campo.</span><span class="sxs-lookup"><span data-stu-id="01490-105">The segment table includes the identifier of the table that the field uses.</span></span> <span data-ttu-id="01490-106">Hay tres tipos de tablas: HL7 definido, definido externamente y definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="01490-106">There are three types of tables: HL7 defined, externally defined, and user-defined.</span></span> <span data-ttu-id="01490-107">En algunos casos, el estándar proporciona los valores de ejemplo para una tabla definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="01490-107">In some cases, the standard supplies example values for a user-defined table.</span></span> <span data-ttu-id="01490-108">Debe tratar estos según el estándar HL7 ha etiquetado en ellos.</span><span class="sxs-lookup"><span data-stu-id="01490-108">You should treat these as the HL7 standard has labeled them.</span></span>  
  
 <span data-ttu-id="01490-109">En las nuevas versiones, no se puede quitar los códigos de las tablas de HL7 definido, pero puede agregar nuevos códigos.</span><span class="sxs-lookup"><span data-stu-id="01490-109">In new versions, you cannot remove codes from HL7 defined tables, but you can add new codes.</span></span> <span data-ttu-id="01490-110">Puede cambiar las tablas definidas por el usuario a voluntad.</span><span class="sxs-lookup"><span data-stu-id="01490-110">You can change user-defined tables at will.</span></span>  
  
 <span data-ttu-id="01490-111">Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="01490-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="01490-112">Puede usar todas las tablas de HL7 definido.</span><span class="sxs-lookup"><span data-stu-id="01490-112">You can use all of the HL7 defined tables.</span></span>  
  
-   <span data-ttu-id="01490-113">Puede importar y conjuntos de código como ICD9 y LOINC define el uso externamente.</span><span class="sxs-lookup"><span data-stu-id="01490-113">You can import and use externally defined code sets such as ICD9 and LOINC.</span></span>  
  
-   <span data-ttu-id="01490-114">Puede proporcionar los valores para las tablas definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="01490-114">You can provide the values for user-defined tables.</span></span>  
  
-   <span data-ttu-id="01490-115">En casos donde los sistemas son compatibles con diferentes conjuntos de códigos, puede configurar las asignaciones que permiten conjuntos dispares de código interoperar.</span><span class="sxs-lookup"><span data-stu-id="01490-115">In cases where systems are supporting different sets of codes, you can set up mappings that allow disparate code sets to interoperate.</span></span> <span data-ttu-id="01490-116">Si es necesario, puede definir varias instancias de una sola tabla definido por el usuario que acompañan a la asignación intermedia.</span><span class="sxs-lookup"><span data-stu-id="01490-116">If necessary, you can define multiple instances of a single user-defined table to go along with the intermediary mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01490-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="01490-117">See Also</span></span>  
 <span data-ttu-id="01490-118">[Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="01490-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="01490-119">[Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="01490-119">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="01490-120">Uso de esquemas HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="01490-120">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)