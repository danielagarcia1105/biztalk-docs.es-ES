---
title: Tipos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7b8d75be35be01e9c961d6bd054dcaed6d3aee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984677"
---
# <a name="data-types"></a><span data-ttu-id="4e5ba-102">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4e5ba-102">Data Types</span></span>
<span data-ttu-id="4e5ba-103">La especificación de tipo de datos es una herramienta importante para la partición de la complejidad del estándar HL7 y es fundamental para entender el contenido de datos de un campo de HL7.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="4e5ba-104">Algunos tipos de datos son simples y contienen solo un componente, y algunos contienen muchos componentes y subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="4e5ba-105">Por ejemplo, nombre de paciente PID.5 tiene el tipo de datos XPN en la versión 2.4.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="4e5ba-106">Este tipo de datos es compatible con las subdivisiones comunes de un nombre de idioma inglés, por ejemplo, apellido, nombre, segundo nombre, así como sufijo, prefijo, el código de tipo de nombre e intervalo de validez (fecha) de nombre.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="4e5ba-107">En nuevas versiones de HL7, puede agregar, pero no quitar tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="4e5ba-108">Si agrega contenido a un tipo de datos mediante la adición de nuevos componentes o subcomponentes, solo se puede agregar al final de la estructura en la que están anidados.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="4e5ba-109">En algunos casos, la organización de HL7 combina existentes de los tipos de datos para formar otros nuevos.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="4e5ba-110">Esto se llevó a la necesidad de admitir los elementos que estaban anteriormente subcomponentes dentro de los tipos de datos original.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="4e5ba-111">Las siguientes funciones del Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) admiten estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="4e5ba-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="4e5ba-112"> admite los tipos de datos estándar para todas las versiones de HL7 desde V2.1 en.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-112"> supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
- <span data-ttu-id="4e5ba-113">Puede restringir los tipos de datos cuando sea apropiado al desarrollar interfaces.</span><span class="sxs-lookup"><span data-stu-id="4e5ba-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e5ba-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4e5ba-114">In This Section</span></span>  
  
-   [<span data-ttu-id="4e5ba-115">Id. de tipo de datos en HL7 2.1</span><span class="sxs-lookup"><span data-stu-id="4e5ba-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)