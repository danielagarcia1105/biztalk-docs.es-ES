---
title: 'De sesión único: Evento 10854 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f89ef2727933e72de1e9d759bd91dc507a0954
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994410"
---
# <a name="single-sign-on-event-10854"></a><span data-ttu-id="891d9-102">De sesión único: Evento 10854</span><span class="sxs-lookup"><span data-stu-id="891d9-102">Single Sign-On: Event 10854</span></span>
## <a name="details"></a><span data-ttu-id="891d9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="891d9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="891d9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="891d9-104">Product Name</span></span>   |                 <span data-ttu-id="891d9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="891d9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="891d9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="891d9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="891d9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="891d9-107">Event ID</span></span>     |                           <span data-ttu-id="891d9-108">10854</span><span class="sxs-lookup"><span data-stu-id="891d9-108">10854</span></span>                            |
|  <span data-ttu-id="891d9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="891d9-109">Event Source</span></span>   |                           <span data-ttu-id="891d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="891d9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="891d9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="891d9-111">Component</span></span>    |                            <span data-ttu-id="891d9-112">N/D</span><span class="sxs-lookup"><span data-stu-id="891d9-112">N/A</span></span>                             |
|  <span data-ttu-id="891d9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="891d9-113">Symbolic Name</span></span>  |               <span data-ttu-id="891d9-114">ENTSSO_E_INVALID_STRING_FORMAT</span><span class="sxs-lookup"><span data-stu-id="891d9-114">ENTSSO_E_INVALID_STRING_FORMAT</span></span>               |
|  <span data-ttu-id="891d9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="891d9-115">Message Text</span></span>   |     <span data-ttu-id="891d9-116">Formato de cadena incorrecto para esta función.</span><span class="sxs-lookup"><span data-stu-id="891d9-116">The string format is incorrect for this function.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="891d9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="891d9-117">Explanation</span></span>  
 <span data-ttu-id="891d9-118">Formato de cadena incorrecto para esta función.</span><span class="sxs-lookup"><span data-stu-id="891d9-118">The string format is incorrect for this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="891d9-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="891d9-119">User Action</span></span>  
 <span data-ttu-id="891d9-120">A continuación se describe el formato adecuado para cadenas de contraseña:</span><span class="sxs-lookup"><span data-stu-id="891d9-120">Proper formatting for password strings is described below:</span></span>  
  
 <span data-ttu-id="891d9-121">Propiedad de tipo VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="891d9-121">VT_BSTR type property</span></span>  
  
 <span data-ttu-id="891d9-122">El delimitador es / (barra diagonal)</span><span class="sxs-lookup"><span data-stu-id="891d9-122">The delimiter is / (slash)</span></span>  
  
 <span data-ttu-id="891d9-123">dc = caso predeterminado (ninguna operación - no hacer nada)</span><span class="sxs-lookup"><span data-stu-id="891d9-123">dc = default case (no operation - do nothing)</span></span>  
  
 <span data-ttu-id="891d9-124">Ejemplo: dc /</span><span class="sxs-lookup"><span data-stu-id="891d9-124">Example: dc/</span></span>  
  
 <span data-ttu-id="891d9-125">(ningún cambio: de 'Cat' a 'Cat')</span><span class="sxs-lookup"><span data-stu-id="891d9-125">(no change - 'Cat' to 'Cat')</span></span>  
  
 <span data-ttu-id="891d9-126">uc = mayúsculas</span><span class="sxs-lookup"><span data-stu-id="891d9-126">uc = upper case</span></span>  
  
 <span data-ttu-id="891d9-127">Ejemplo: comunicaciones unificadas /</span><span class="sxs-lookup"><span data-stu-id="891d9-127">Example: uc/</span></span>  
  
 <span data-ttu-id="891d9-128">(cambiar contraseña a mayúsculas: de 'Cat' a 'CAT')</span><span class="sxs-lookup"><span data-stu-id="891d9-128">(change password to upper case - 'Cat' to 'CAT')</span></span>  
  
 <span data-ttu-id="891d9-129">lc = minúsculas</span><span class="sxs-lookup"><span data-stu-id="891d9-129">lc = lower case</span></span>  
  
 <span data-ttu-id="891d9-130">Ejemplo: lc /</span><span class="sxs-lookup"><span data-stu-id="891d9-130">Example: lc/</span></span>  
  
 <span data-ttu-id="891d9-131">(cambiar contraseña a minúsculas: de 'Cat' a 'cat')</span><span class="sxs-lookup"><span data-stu-id="891d9-131">(change password to lower case - 'Cat' to 'cat')</span></span>  
  
 <span data-ttu-id="891d9-132">rc = quitar caracteres - seguido de recuento seguido de caracteres</span><span class="sxs-lookup"><span data-stu-id="891d9-132">rc = remove chars - followed by count followed by chars</span></span>  
  
 <span data-ttu-id="891d9-133">Ejemplo: rc/2 / #@/</span><span class="sxs-lookup"><span data-stu-id="891d9-133">Example: rc/2/#@/</span></span>  
  
 <span data-ttu-id="891d9-134">(quite los caracteres '#' y ' @' de la contraseña: 'C@t#' a 'Ct')</span><span class="sxs-lookup"><span data-stu-id="891d9-134">(remove the characters '#' and '@' from the password - 'C@t#' to 'Ct')</span></span>  
  
 <span data-ttu-id="891d9-135">sc = caracteres sustitutos - seguido de recuento seguido de caracteres por reemplazar seguido de caracteres sustitutos</span><span class="sxs-lookup"><span data-stu-id="891d9-135">sc = substitute chars - followed by count followed by chars to replace followed by substitute chars</span></span>  
  
 <span data-ttu-id="891d9-136">Ejemplo: sc/3/abc/def /</span><span class="sxs-lookup"><span data-stu-id="891d9-136">Example: sc/3/abc/def/</span></span>  
  
 <span data-ttu-id="891d9-137">(quitar los caracteres 'a', 'b' y 'c' de la contraseña y reemplazarlos por 'd', 'e' y 'f', respectivamente)</span><span class="sxs-lookup"><span data-stu-id="891d9-137">(remove the characters 'a', 'b' and 'c' from the password and replace with 'd', 'e' and 'f' respectively)</span></span>  
  
 <span data-ttu-id="891d9-138">(de 'Cat' a 'Cdt')</span><span class="sxs-lookup"><span data-stu-id="891d9-138">('Cat' to 'Cdt')</span></span>  
  
 <span data-ttu-id="891d9-139">ps = completar desde el principio - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador</span><span class="sxs-lookup"><span data-stu-id="891d9-139">ps = pad from start - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="891d9-140">Ejemplo: ps/8 / #/</span><span class="sxs-lookup"><span data-stu-id="891d9-140">Example: ps/8/#/</span></span>  
  
 <span data-ttu-id="891d9-141">(si la contraseña no tiene 8 caracteres como mínimo, completar desde el principio con el carácter '#' hasta que haya 8 caracteres en total)</span><span class="sxs-lookup"><span data-stu-id="891d9-141">(if the password is not at least 8 chars in length then pad from the start with the character '#' until there are 8 chars total)</span></span>  
  
 <span data-ttu-id="891d9-142">(de 'Cat' a '#####Cat')</span><span class="sxs-lookup"><span data-stu-id="891d9-142">('Cat' to '#####Cat')</span></span>  
  
 <span data-ttu-id="891d9-143">pe = completar desde el final - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador</span><span class="sxs-lookup"><span data-stu-id="891d9-143">pe = pad from end - followed by count (min password length) followed by single pad char</span></span>  
  
 <span data-ttu-id="891d9-144">Ejemplo: pe/10 / $/</span><span class="sxs-lookup"><span data-stu-id="891d9-144">Example: pe/10/$/</span></span>  
  
 <span data-ttu-id="891d9-145">(si la contraseña no tiene 10 caracteres como mínimo, completar desde el final con el carácter '$' hasta que haya 10 caracteres en total)</span><span class="sxs-lookup"><span data-stu-id="891d9-145">(if the password is not at least 10 chars in length then pad to the end with the character '$' until there are 10 chars total)</span></span>  
  
 <span data-ttu-id="891d9-146">(de 'Cat' a 'Cat$$$$$$$')</span><span class="sxs-lookup"><span data-stu-id="891d9-146">('Cat' to 'Cat$$$$$$$')</span></span>  
  
 <span data-ttu-id="891d9-147">tr = truncar - límite de longitud de cadena - seguido de recuento</span><span class="sxs-lookup"><span data-stu-id="891d9-147">tr = truncate - limit length of string - followed by count</span></span>  
  
 <span data-ttu-id="891d9-148">Ejemplo: tr/11 /</span><span class="sxs-lookup"><span data-stu-id="891d9-148">Example: tr/11/</span></span>  
  
 <span data-ttu-id="891d9-149">(de 'Cat123456789' a 'Cat12345678');</span><span class="sxs-lookup"><span data-stu-id="891d9-149">('Cat123456789' to 'Cat12345678');</span></span>  
  
 <span data-ttu-id="891d9-150">Los token se procesan en su orden en la cadena.</span><span class="sxs-lookup"><span data-stu-id="891d9-150">The tokens are processed in their order in the string.</span></span>  
  
 <span data-ttu-id="891d9-151">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="891d9-151">Example:</span></span>  
  
 <span data-ttu-id="891d9-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span><span class="sxs-lookup"><span data-stu-id="891d9-152">uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/</span></span>