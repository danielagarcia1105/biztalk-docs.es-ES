---
title: Tipos de datos | Documentos de Microsoft
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
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204948"
---
# <a name="data-types"></a><span data-ttu-id="eda37-102">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="eda37-102">Data Types</span></span>
<span data-ttu-id="eda37-103">La especificación de tipo de datos es una herramienta importante para crear particiones de la complejidad del estándar HL7 y es fundamental para entender el contenido de datos de un campo de HL7.</span><span class="sxs-lookup"><span data-stu-id="eda37-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="eda37-104">Algunos tipos de datos son sencillos y contienen solo un componente, y algunos contienen muchos componentes y subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="eda37-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="eda37-105">Por ejemplo, PID.5 Patient Name tiene el tipo de datos XPN en la versión 2.4.</span><span class="sxs-lookup"><span data-stu-id="eda37-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="eda37-106">Este tipo de datos admite las subdivisiones comunes de un nombre de idioma inglés, por ejemplo, apellido, nombre, segundo nombre, así como sufijo, prefijo, el código de tipo de nombre e intervalo de validez (fecha) de nombre.</span><span class="sxs-lookup"><span data-stu-id="eda37-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="eda37-107">En versiones nuevas de HL7, puede agregar pero no quitar tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="eda37-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="eda37-108">Si agrega contenido a un tipo de datos, mediante la adición de nuevos componentes o subcomponentes, solo puede agregarlos al final de la estructura en la que están anidados.</span><span class="sxs-lookup"><span data-stu-id="eda37-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="eda37-109">En algunos casos, la organización de HL7 combinado existente tipos de datos para formar otros nuevos.</span><span class="sxs-lookup"><span data-stu-id="eda37-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="eda37-110">Esto causaba la necesidad de admitir elementos que anteriormente estaban subcomponentes dentro de los tipos de datos original.</span><span class="sxs-lookup"><span data-stu-id="eda37-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="eda37-111">Las siguientes funciones de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compatible con estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="eda37-111">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="eda37-112">admite tipos de datos estándar para todas las versiones de HL7 desde V2.1 en.</span><span class="sxs-lookup"><span data-stu-id="eda37-112"> supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
-   <span data-ttu-id="eda37-113">Puede restringir los tipos de datos donde corresponda al desarrollar interfaces.</span><span class="sxs-lookup"><span data-stu-id="eda37-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eda37-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eda37-114">In This Section</span></span>  
  
-   [<span data-ttu-id="eda37-115">Id. de tipo de datos de HL7 2.1</span><span class="sxs-lookup"><span data-stu-id="eda37-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)