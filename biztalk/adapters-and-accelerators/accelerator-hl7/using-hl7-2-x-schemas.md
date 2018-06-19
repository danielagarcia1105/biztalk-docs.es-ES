---
title: Utilizar esquemas de HL7 2.X | Documentos de Microsoft
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
ms.openlocfilehash: 934ca60bb3d89e08c9e803813f3548f196c3d56d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206780"
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="24460-102">Utilizar esquemas 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="24460-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="24460-103">Esta sección describen las versiones 2.X del nivel de mantenimiento siete (HL7) estándar admitidos por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24460-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24460-104">Que necesite actualizar los esquemas que se instala con BTAHL7 para que coincida con el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="24460-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="24460-105">Para ello, consulte [resolver errores de base de datos](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="24460-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24460-106">El motor de BTAHL7 no puede procesar instancias de mensajes que cumplen los esquemas de HL7 que tienen una estructura de esquema ambigua.</span><span class="sxs-lookup"><span data-stu-id="24460-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="24460-107">Una estructura de esquema ambigua es aquella que no se ha definido totalmente el estándar HL7.</span><span class="sxs-lookup"><span data-stu-id="24460-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="24460-108">Estos esquemas incluyen los tipos de mensaje CSU y SUR.</span><span class="sxs-lookup"><span data-stu-id="24460-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24460-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24460-109">In This Section</span></span>  
  
-   [<span data-ttu-id="24460-110">Versiones 2.X HL7</span><span class="sxs-lookup"><span data-stu-id="24460-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="24460-111">Eventos y las subcarpetas de HL7 2.X</span><span class="sxs-lookup"><span data-stu-id="24460-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="24460-112">Archivos de esquema HL7 2.X comunes</span><span class="sxs-lookup"><span data-stu-id="24460-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="24460-113">Extender HL7 2.X esquemas con objetos de Z</span><span class="sxs-lookup"><span data-stu-id="24460-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="24460-114">Resolver errores de base de datos</span><span class="sxs-lookup"><span data-stu-id="24460-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="24460-115">'X' y 'Y' opcionalidad</span><span class="sxs-lookup"><span data-stu-id="24460-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="24460-116">Segmentos de campo repetible</span><span class="sxs-lookup"><span data-stu-id="24460-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)