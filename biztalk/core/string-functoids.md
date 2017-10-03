---
title: Functoids de cadena | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06bcb1d42a5e72a57765d17c18a48b6f4808d412
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="string-functoids"></a><span data-ttu-id="751b2-102">Functoids de cadena</span><span class="sxs-lookup"><span data-stu-id="751b2-102">String Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="751b2-103">Información general</span><span class="sxs-lookup"><span data-stu-id="751b2-103">Overview</span></span>
<span data-ttu-id="751b2-104">**Cadena** functoids se utilizan para manipular las cadenas de forma estándar, como conversiones a mayúsculas o minúsculas, concatenación de cadenas, determinación de longitud de cadena, recorte, de espacio en blanco y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="751b2-104">**String** functoids are used to manipulate strings in standard ways such as conversions to all uppercase or all lowercase, string concatenation, determination of string length, white space trimming, and so on.</span></span>  
  
 <span data-ttu-id="751b2-105">Los functoids **mayúsculas**, **minúsculas**, **tamaño**, **recorte derecho de cadena**, y **recorte izquierdo de cadena** acepta un solo parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="751b2-105">The functoids **Uppercase**, **Lowercase**, **Size**, **String Right Trim**, and **String Left Trim** accept only one input parameter.</span></span> <span data-ttu-id="751b2-106">Los functoids **búsqueda de cadenas**, **cadena izquierda**, y **cadena derecha** aceptan dos parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="751b2-106">The functoids **String Find**, **String Left**, and **String Right** accept two input parameters.</span></span> <span data-ttu-id="751b2-107">El **extracción de cadenas** functoid acepta tres entradas, mientras que la **concatenación de cadenas** functoid acepta parámetros de entrada entre 1 y 100.</span><span class="sxs-lookup"><span data-stu-id="751b2-107">The **String Extract** functoid accepts three inputs, whereas the **String Concatenate** functoid accepts input parameters between 1 and 100.</span></span>  
  
 <span data-ttu-id="751b2-108">Dos **cadena** functoids hacen referencia a la posición numérica de un carácter en una cadena: **extracción de cadenas** y **búsqueda de cadenas**.</span><span class="sxs-lookup"><span data-stu-id="751b2-108">Two **String** functoids refer to the numeric position of a character in a string: **String Extract** and **String Find**.</span></span> <span data-ttu-id="751b2-109">Estos functoids empiezan a contar posiciones de caracteres en 1, no en 0.</span><span class="sxs-lookup"><span data-stu-id="751b2-109">These functoids begin counting character positions at 1, not 0.</span></span>  
  
 <span data-ttu-id="751b2-110">Los dos functoids de recorte de cadena **recorte izquierdo de cadena** y **recorte derecho de cadena**, quitar todos los caracteres de espacio en blanco (espacios, tabuladores y así sucesivamente) de la izquierda o la derecha (como puede ser el caso) de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="751b2-110">The two string trimming functoids, **String Left Trim** and **String Right Trim**, remove all white space characters (spaces, tabs, and so on) from the left  or right (as the case may be) of the specified string.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="751b2-111">Functoids disponibles</span><span class="sxs-lookup"><span data-stu-id="751b2-111">Available functoids</span></span> 
 <span data-ttu-id="751b2-112">El **cadena** functoids son:</span><span class="sxs-lookup"><span data-stu-id="751b2-112">The **String** functoids are:</span></span> 

* <span data-ttu-id="751b2-113">Minúsculas</span><span class="sxs-lookup"><span data-stu-id="751b2-113">Lowercase</span></span>
* <span data-ttu-id="751b2-114">Tamaño</span><span class="sxs-lookup"><span data-stu-id="751b2-114">Size</span></span>
* <span data-ttu-id="751b2-115">Concatenación de cadenas</span><span class="sxs-lookup"><span data-stu-id="751b2-115">String Concatenate</span></span>
* <span data-ttu-id="751b2-116">Extracción de cadenas</span><span class="sxs-lookup"><span data-stu-id="751b2-116">String Extract</span></span>
* <span data-ttu-id="751b2-117">Búsqueda de cadenas</span><span class="sxs-lookup"><span data-stu-id="751b2-117">String Find</span></span>
* <span data-ttu-id="751b2-118">Cadena izquierda</span><span class="sxs-lookup"><span data-stu-id="751b2-118">String Left</span></span>
* <span data-ttu-id="751b2-119">Recorte izquierdo de cadena</span><span class="sxs-lookup"><span data-stu-id="751b2-119">String Left Trim</span></span>
* <span data-ttu-id="751b2-120">Cadena derecha</span><span class="sxs-lookup"><span data-stu-id="751b2-120">String Right</span></span>
* <span data-ttu-id="751b2-121">Recorte derecho de cadena</span><span class="sxs-lookup"><span data-stu-id="751b2-121">String Right Trim</span></span>
* <span data-ttu-id="751b2-122">Mayúsculas</span><span class="sxs-lookup"><span data-stu-id="751b2-122">Uppercase</span></span>

<span data-ttu-id="751b2-123">Obtener más detalles sobre estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="751b2-123">More details on these functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="751b2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="751b2-124">See Also</span></span>  
-  [<span data-ttu-id="751b2-125">Cómo agregar Functoids básicos a un mapa</span><span class="sxs-lookup"><span data-stu-id="751b2-125">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="751b2-126">**Referencia a Functoids de cadena**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="751b2-126">**String Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>