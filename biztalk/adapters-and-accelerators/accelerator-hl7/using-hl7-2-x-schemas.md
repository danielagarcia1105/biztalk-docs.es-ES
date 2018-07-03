---
title: Uso de esquemas de HL7 2.X | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas
- HL7, 2.X schemas
- schemas, 2.X schemas
ms.assetid: 7f2d7dd4-76f1-463e-b579-9839a74b9631
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155710a421eaaf98f551729a00d724cd9a29ce3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979565"
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="cd8f4-102">Uso de esquemas de HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="cd8f4-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="cd8f4-103">Esta sección describen las versiones 2.X del estándar de siete de nivel de mantenimiento (HL7) compatible con Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd8f4-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd8f4-104">Es posible que deba actualizar los esquemas se instalan con BTAHL7 para cumplir con el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="cd8f4-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="cd8f4-105">Para ello, consulte [resolver errores de base de datos](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="cd8f4-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd8f4-106">El motor de BTAHL7 no puede procesar instancias de mensaje que se ajuste a los esquemas de HL7 que tienen una estructura de esquema ambiguo.</span><span class="sxs-lookup"><span data-stu-id="cd8f4-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="cd8f4-107">Una estructura de esquema ambigua es aquella que no se ha definido totalmente el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="cd8f4-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="cd8f4-108">Estos esquemas incluyen para los tipos de mensaje CSU y SUR.</span><span class="sxs-lookup"><span data-stu-id="cd8f4-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd8f4-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cd8f4-109">In This Section</span></span>  
  
-   [<span data-ttu-id="cd8f4-110">Versiones de HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="cd8f4-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="cd8f4-111">Subcarpetas y eventos de HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="cd8f4-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="cd8f4-112">Archivos de esquema comunes de HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="cd8f4-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="cd8f4-113">Ampliar esquemas de HL7 2.X con objetos de Z</span><span class="sxs-lookup"><span data-stu-id="cd8f4-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="cd8f4-114">Resolución de errores de base de datos</span><span class="sxs-lookup"><span data-stu-id="cd8f4-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="cd8f4-115">Opcionalidad “X” e “Y”</span><span class="sxs-lookup"><span data-stu-id="cd8f4-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="cd8f4-116">Segmentos de campo repetibles</span><span class="sxs-lookup"><span data-stu-id="cd8f4-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)