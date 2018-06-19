---
title: Consideraciones al crear planos esquemas de mensaje de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52271b17-4f0b-4286-a462-cd5951ae49aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d0cbe19b85fc65c492f1e0ae377da94dad75baf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237900"
---
# <a name="considerations-when-creating-flat-file-message-schemas"></a><span data-ttu-id="b5a95-102">Consideraciones al crear sin formato de archivo esquemas de mensaje</span><span class="sxs-lookup"><span data-stu-id="b5a95-102">Considerations When Creating Flat File Message Schemas</span></span>
<span data-ttu-id="b5a95-103">Es necesario tener en cuenta una serie de cuestiones al trabajar con esquemas de mensajes de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="b5a95-103">There are a number of considerations when working with flat file message schemas.</span></span> <span data-ttu-id="b5a95-104">Esto incluye consideraciones aplicables a todos los esquemas de archivo sin formato, así como consideraciones que se aplican de forma específica a los registros posicionales, los registros delimitados, los campos posicionales o los campos delimitados.</span><span class="sxs-lookup"><span data-stu-id="b5a95-104">This includes considerations that apply to all flat file schemas, as well as considerations that apply specifically to positional records, delimited records, positional fields, or delimited fields.</span></span> <span data-ttu-id="b5a95-105">También existen consideraciones acerca de cómo interpretar de otro modo los caracteres especiales para que se consideren como datos normales.</span><span class="sxs-lookup"><span data-stu-id="b5a95-105">There are also considerations about how to interpret otherwise special characters as regular data.</span></span> <span data-ttu-id="b5a95-106">Esta sección proporciona información acerca de estas consideraciones.</span><span class="sxs-lookup"><span data-stu-id="b5a95-106">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5a95-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b5a95-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b5a95-108">Especificación de la página de código para esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="b5a95-108">Code Page Specification for Flat File Schemas</span></span>](../core/code-page-specification-for-flat-file-schemas.md)  
  
-   [<span data-ttu-id="b5a95-109">Caso de control en esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="b5a95-109">Case Handling in Flat File Schemas</span></span>](../core/case-handling-in-flat-file-schemas.md)  
  
-   [<span data-ttu-id="b5a95-110">Intervalos de caracteres restringidos</span><span class="sxs-lookup"><span data-stu-id="b5a95-110">Restricted Character Ranges</span></span>](../core/restricted-character-ranges.md)  
  
-   [<span data-ttu-id="b5a95-111">Registros delimitados y posicionales anidados</span><span class="sxs-lookup"><span data-stu-id="b5a95-111">Nested Positional and Delimited Records</span></span>](../core/nested-positional-and-delimited-records.md)  
  
-   [<span data-ttu-id="b5a95-112">Consideraciones del registro posicional</span><span class="sxs-lookup"><span data-stu-id="b5a95-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)  
  
-   [<span data-ttu-id="b5a95-113">Consideraciones de registro delimitadas</span><span class="sxs-lookup"><span data-stu-id="b5a95-113">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)  
  
-   [<span data-ttu-id="b5a95-114">Consideraciones de campo</span><span class="sxs-lookup"><span data-stu-id="b5a95-114">Field Considerations</span></span>](../core/field-considerations.md)  
  
-   [<span data-ttu-id="b5a95-115">Formas de interpretar los caracteres especiales como parte de un valor de campo</span><span class="sxs-lookup"><span data-stu-id="b5a95-115">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)