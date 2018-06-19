---
title: Functoids de conversión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237892"
---
# <a name="conversion-functoids"></a><span data-ttu-id="56451-102">Functoids de conversión</span><span class="sxs-lookup"><span data-stu-id="56451-102">Conversion Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="56451-103">Información general</span><span class="sxs-lookup"><span data-stu-id="56451-103">Overview</span></span>
<span data-ttu-id="56451-104">**Conversión** functoids se utilizan para realizar conversiones entre números y sus equivalentes ASCII y para convertir números de base 10 en su base 8 y 16 equivalentes de base.</span><span class="sxs-lookup"><span data-stu-id="56451-104">**Conversion** functoids are used to convert between numbers and their ASCII equivalents, and to convert base 10 numbers to their base 8 and base 16 equivalents.</span></span>  
  
 <span data-ttu-id="56451-105">Todos los functoids de conversión toman un único parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="56451-105">All of the conversion functoids take a single input parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56451-106">Debido a cambios en el sistema de tipos subyacente, el **conversión** functoids en esta versión del asignador de BizTalk producen resultados ligeramente diferentes de los que se obtenían en las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="56451-106">Due to changes in the underlying type system, the **Conversion** functoids in this version of BizTalk Mapper produce slightly different results than those produced in previous versions.</span></span> <span data-ttu-id="56451-107">Por ejemplo, en versiones anteriores del asignador de BizTalk un valor de entrada de -20 a la **Hexadecimal** functoid daba como resultado 0xffec.</span><span class="sxs-lookup"><span data-stu-id="56451-107">For example, in previous versions of BizTalk Mapper an input value of -20 to the **Hexadecimal** functoid resulted in an output of 0xFFEC.</span></span> <span data-ttu-id="56451-108">En esta versión, el mismo valor de -20 dará como resultado 0xFFFFFFEC.</span><span class="sxs-lookup"><span data-stu-id="56451-108">In this version, the same input value of -20 will result in an output of 0xFFFFFFEC.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="56451-109">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="56451-109">Available functoids</span></span>  
 <span data-ttu-id="56451-110">El **conversión** functoids son:</span><span class="sxs-lookup"><span data-stu-id="56451-110">The **Conversion** functoids are:</span></span> 

* <span data-ttu-id="56451-111">ASCII a carácter</span><span class="sxs-lookup"><span data-stu-id="56451-111">ASCII to Character</span></span>
* <span data-ttu-id="56451-112">Carácter a ASCII</span><span class="sxs-lookup"><span data-stu-id="56451-112">Character to ASCII</span></span>
* <span data-ttu-id="56451-113">Hexadecimal</span><span class="sxs-lookup"><span data-stu-id="56451-113">Hexadecimal</span></span>
* <span data-ttu-id="56451-114">Octal</span><span class="sxs-lookup"><span data-stu-id="56451-114">Octal</span></span>

<span data-ttu-id="56451-115">Se describen estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="56451-115">These functoids are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="56451-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="56451-116">See Also</span></span>  
 [<span data-ttu-id="56451-117">Cómo agregar Functoids básicos a un mapa</span><span class="sxs-lookup"><span data-stu-id="56451-117">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
