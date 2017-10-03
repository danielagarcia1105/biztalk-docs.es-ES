---
title: "Inicio de sesión único: Evento 10854 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f9e9e761689b2ed21ec37acdbb8a63f1f88070
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10854"></a><span data-ttu-id="0cc84-102">Inicio de sesión único: Evento 10854</span><span class="sxs-lookup"><span data-stu-id="0cc84-102">Single Sign-On: Event 10854</span></span>
## <a name="details"></a><span data-ttu-id="0cc84-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0cc84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0cc84-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0cc84-104">Product Name</span></span>|<span data-ttu-id="0cc84-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0cc84-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0cc84-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0cc84-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0cc84-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0cc84-107">Event ID</span></span>|<span data-ttu-id="0cc84-108">10854</span><span class="sxs-lookup"><span data-stu-id="0cc84-108">10854</span></span>|  
|<span data-ttu-id="0cc84-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0cc84-109">Event Source</span></span>|<span data-ttu-id="0cc84-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0cc84-110">ENTSSO</span></span>|  
|<span data-ttu-id="0cc84-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0cc84-111">Component</span></span>|<span data-ttu-id="0cc84-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0cc84-112">N/A</span></span>|  
|<span data-ttu-id="0cc84-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0cc84-113">Symbolic Name</span></span>|<span data-ttu-id="0cc84-114">ENTSSO_E_INVALID_STRING_FORMAT</span><span class="sxs-lookup"><span data-stu-id="0cc84-114">ENTSSO_E_INVALID_STRING_FORMAT</span></span>|  
|<span data-ttu-id="0cc84-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0cc84-115">Message Text</span></span>|<span data-ttu-id="0cc84-116">Formato de cadena incorrecto para esta función.</span><span class="sxs-lookup"><span data-stu-id="0cc84-116">The string format is incorrect for this function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0cc84-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0cc84-117">Explanation</span></span>  
 <span data-ttu-id="0cc84-118">Formato de cadena incorrecto para esta función.</span><span class="sxs-lookup"><span data-stu-id="0cc84-118">The string format is incorrect for this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0cc84-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0cc84-119">User Action</span></span>  
 <span data-ttu-id="0cc84-120">A continuación se describe el formato adecuado para cadenas de contraseña:</span><span class="sxs-lookup"><span data-stu-id="0cc84-120">Proper formatting for password strings is described below:</span></span>  
  
 <span data-ttu-id="0cc84-121">Propiedad de tipo VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="0cc84-121">VT_BSTR type property</span></span>  
  
 <span data-ttu-id="0cc84-122">El delimitador es / (barra diagonal)</span><span class="sxs-lookup"><span data-stu-id="0cc84-122">The delimiter is / (slash)</span></span>  
  
 <span data-ttu-id="0cc84-123">dc = caso predeterminado (ninguna operación - no hacer nada)</span><span class="sxs-lookup"><span data-stu-id="0cc84-123">dc = default case (no operation - do nothing)</span></span>  
  
 <span data-ttu-id="0cc84-124">Ejemplo: dc /</span><span class="sxs-lookup"><span data-stu-id="0cc84-124">Example: dc/</span></span>  
  
 <span data-ttu-id="0cc84-125">(ningún cambio: de 'Cat' a 'Cat')</span><span class="sxs-lookup"><span data-stu-id="0cc84-125">(no change - 'Cat' to 'Cat')</span></span>  
  
 <span data-ttu-id="0cc84-126">uc = mayúsculas</span><span class="sxs-lookup"><span data-stu-id="0cc84-126">uc = upper case</span></span>  
  
 <span data-ttu-id="0cc84-127">Ejemplo: uc /</span><span class="sxs-lookup"><span data-stu-id="0cc84-127">Example: uc/</span></span>  
  
 <span data-ttu-id="0cc84-128">(cambiar contraseña a mayúsculas: de 'Cat' a 'CAT')</span><span class="sxs-lookup"><span data-stu-id="0cc84-128">(change password to upper case - 'Cat' to 'CAT')</span></span>  
  
 <span data-ttu-id="0cc84-129">lc = minúsculas</span><span class="sxs-lookup"><span data-stu-id="0cc84-129">lc = lower case</span></span>  
  
 <span data-ttu-id="0cc84-130">Ejemplo: lc /</span><span class="sxs-lookup"><span data-stu-id="0cc84-130">Example: lc/</span></span>  
  
 <span data-ttu-id="0cc84-131">(cambiar contraseña a minúsculas: de 'Cat' a 'cat')</span><span class="sxs-lookup"><span data-stu-id="0cc84-131">(change password to lower case - 'Cat' to 'cat')</span></span>  
  
 <span data-ttu-id="0cc84-132">rc = quitar caracteres - seguido de recuento seguido de caracteres</span><span class="sxs-lookup"><span data-stu-id="0cc84-132">rc = remove chars - followed by count followed by chars</span></span>  
  
 <span data-ttu-id="0cc84-133">Ejemplo: rc/2 / #@/</span><span class="sxs-lookup"><span data-stu-id="0cc84-133">Example: rc/2/#@/</span></span>  
  
 <span data-ttu-id="0cc84-134">(quite los caracteres '#' y ' @' de la contraseña: 'C@t#' a 'Ct')</span><span class="sxs-lookup"><span data-stu-id="0cc84-134">(remove the characters '#' and '@' from the password - 'C@t#' to 'Ct')</span></span>  
  
 <span data-ttu-id="0cc84-135">sc = caracteres sustitutos - seguido de recuento seguido de caracteres por reemplazar seguido de caracteres sustitutos</span><span class="sxs-lookup"><span data-stu-id="0cc84-135">sc = substitute chars - followed by count followed by chars to replace followed by substitute chars</span></span>  
  
 <span data-ttu-id="0cc84-136">Ejemplo: sc/3/abc/def /</span><span class="sxs-lookup"><span data-stu-id="0cc84-136">Example: sc/3/abc/def/</span></span>  
  
 <span data-ttu-id="0cc84-137">(quitar los caracteres 'a', 'b' y 'c' de la contraseña y reemplazarlos por 'd', 'e' y 'f', respectivamente)</span><span class="sxs-lookup"><span data-stu-id="0cc84-137">(remove the characters 'a', 'b' and 'c' from the password and replace with 'd', 'e' and 'f' respectively)</span></span>  
  
 <span data-ttu-id="0cc84-138">(de 'Cat' a 'Cdt')</span><span class="sxs-lookup"><span data-stu-id="0cc84-138">('Cat' to 'Cdt')</span></span>  
  
 <span data-ttu-id="0cc84-139">ps = completar desde el principio - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador</span><span class="sxs-lookup"><span data-stu-id="0cc84-139">ps = pad from start - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="0cc84-140">Ejemplo: ps/8 / #/</span><span class="sxs-lookup"><span data-stu-id="0cc84-140">Example: ps/8/#/</span></span>  
  
 <span data-ttu-id="0cc84-141">(si la contraseña no tiene 8 caracteres como mínimo, completar desde el principio con el carácter '#' hasta que haya 8 caracteres en total)</span><span class="sxs-lookup"><span data-stu-id="0cc84-141">(if the password is not at least 8 chars in length then pad from the start with the character '#' until there are 8 chars total)</span></span>  
  
 <span data-ttu-id="0cc84-142">(de 'Cat' a '#####Cat')</span><span class="sxs-lookup"><span data-stu-id="0cc84-142">('Cat' to '#####Cat')</span></span>  
  
 <span data-ttu-id="0cc84-143">pe = completar desde el final - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador</span><span class="sxs-lookup"><span data-stu-id="0cc84-143">pe = pad from end - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="0cc84-144">Ejemplo: pe/10 / $/</span><span class="sxs-lookup"><span data-stu-id="0cc84-144">Example: pe/10/$/</span></span>  
  
 <span data-ttu-id="0cc84-145">(si la contraseña no tiene 10 caracteres como mínimo, completar desde el final con el carácter '$' hasta que haya 10 caracteres en total)</span><span class="sxs-lookup"><span data-stu-id="0cc84-145">(if the password is not at least 10 chars in length then pad to the end with the character '$' until there are 10 chars total)</span></span>  
  
 <span data-ttu-id="0cc84-146">(de 'Cat' a 'Cat$$$$$$$')</span><span class="sxs-lookup"><span data-stu-id="0cc84-146">('Cat' to 'Cat$$$$$$$')</span></span>  
  
 <span data-ttu-id="0cc84-147">tr = truncar - límite de longitud de cadena - seguido de recuento</span><span class="sxs-lookup"><span data-stu-id="0cc84-147">tr = truncate - limit length of string - followed by count</span></span>  
  
 <span data-ttu-id="0cc84-148">Ejemplo: tr/11 /</span><span class="sxs-lookup"><span data-stu-id="0cc84-148">Example: tr/11/</span></span>  
  
 <span data-ttu-id="0cc84-149">(de 'Cat123456789' a 'Cat12345678');</span><span class="sxs-lookup"><span data-stu-id="0cc84-149">('Cat123456789' to 'Cat12345678');</span></span>  
  
 <span data-ttu-id="0cc84-150">Los token se procesan en su orden en la cadena.</span><span class="sxs-lookup"><span data-stu-id="0cc84-150">The tokens are processed in their order in the string.</span></span>  
  
 <span data-ttu-id="0cc84-151">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0cc84-151">Example:</span></span>  
  
 <span data-ttu-id="0cc84-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span><span class="sxs-lookup"><span data-stu-id="0cc84-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span></span>