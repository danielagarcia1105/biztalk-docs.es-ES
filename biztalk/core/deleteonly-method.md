---
title: Método DeleteOnly | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DeleteOnly method
ms.assetid: 99e1d7af-1450-439b-882f-de677e593bee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42366a273fd65348daa9364a39c57c3fec3dff90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983453"
---
# <a name="deleteonly-method"></a><span data-ttu-id="680cd-102">Método DeleteOnly</span><span class="sxs-lookup"><span data-stu-id="680cd-102">DeleteOnly Method</span></span>
<span data-ttu-id="680cd-103">Permite eliminar elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="680cd-103">Allows you to delete items in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="680cd-104">Syntax</span></span>  
  
```  
DeleteOnly(key1, key2, ..., keyn, correctionMode, interactiveMode,  
    properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="680cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="680cd-105">Parameters</span></span>  
  
|<span data-ttu-id="680cd-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="680cd-106">Parameter</span></span>|<span data-ttu-id="680cd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="680cd-107">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="680cd-108">Es un conjunto de parámetros que se debe proporcionar.</span><span class="sxs-lookup"><span data-stu-id="680cd-108">Is a set of parameters that must be supplied.</span></span> <span data-ttu-id="680cd-109">Este conjunto de claves debe existir en la base de datos del servidor o se produce un error.</span><span class="sxs-lookup"><span data-stu-id="680cd-109">This set of keys must exist in the server database, or an error occurs.</span></span> <span data-ttu-id="680cd-110">Estas claves corresponden al conjunto de Obtener claves definido para la interfaz de componentes concreta.</span><span class="sxs-lookup"><span data-stu-id="680cd-110">These keys correspond to the set of Get Keys as defined for the particular component interface.</span></span>|  
|`correctionMode`|<span data-ttu-id="680cd-111">Una marca booleana.</span><span class="sxs-lookup"><span data-stu-id="680cd-111">A Boolean flag.</span></span> <span data-ttu-id="680cd-112">Cuando se establece en true, permite la eliminación de elementos con fecha de vigencia pasada, de una colección.</span><span class="sxs-lookup"><span data-stu-id="680cd-112">When set to true, allows deletion of past effective-dated items in a collection.</span></span> <span data-ttu-id="680cd-113">Específicamente, permite la eliminación de elementos que tienen un valor de EFFDT anterior a la fecha de vigencia actual.</span><span class="sxs-lookup"><span data-stu-id="680cd-113">Specifically, it allows the deletion of items that have EFFDT prior to the current effective date.</span></span> <span data-ttu-id="680cd-114">Sin esta marca establecida en TRUE, cualquier modificación a estos elementos origina la devolución de un error desde el servidor PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="680cd-114">Without this flag set to TRUE, any modification to these items results in an error returned from PeopleSoft server.</span></span> <span data-ttu-id="680cd-115">**Nota:** el `correctionMode` argumento solo se expone para las interfaces de componente que contienen elementos con fecha efectiva.</span><span class="sxs-lookup"><span data-stu-id="680cd-115">**Note:**  The `correctionMode` argument is only exposed for those component interfaces that contain effective-dated items.</span></span> <span data-ttu-id="680cd-116">De lo contrario, no aparece como parte del argumento.</span><span class="sxs-lookup"><span data-stu-id="680cd-116">Otherwise it is not shown as part of the argument.</span></span>|  
|`interactiveMode`|<span data-ttu-id="680cd-117">Se usa para el control de errores.</span><span class="sxs-lookup"><span data-stu-id="680cd-117">Used for error handling.</span></span><br /><br /> <span data-ttu-id="680cd-118">Cuando se obtiene acceso a las propiedades de una interfaz de componentes, BizTalk Adapter para PeopleSoft Enterprise usa las API proporcionadas por PeopleSoft, que leen y escriben campos individuales de la interfaz de componentes; sin embargo, estos cambios no se propagan al servidor PeopleSoft uno a uno.</span><span class="sxs-lookup"><span data-stu-id="680cd-118">When accessing properties in a component interface, the BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="680cd-119">En su lugar, psjoa.jar (con el que el adaptador de BizTalk para PeopleSoft Enterprise interactúa) empaqueta todos los cambios y envía los cambios al servidor en un solo paquete.</span><span class="sxs-lookup"><span data-stu-id="680cd-119">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span> <span data-ttu-id="680cd-120">Si alguna de las actualizaciones individuales produce un error, se devuelve un error genérico, que no ubica el error real.</span><span class="sxs-lookup"><span data-stu-id="680cd-120">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="680cd-121">Con el modo interactivo establecido en TRUE, cada actualización de campo se envía al servidor individualmente.</span><span class="sxs-lookup"><span data-stu-id="680cd-121">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="680cd-122">Esto tiene un impacto sustancial en el rendimiento, pero proporciona información del error específico si se genera un error en la actualización (por ejemplo, si se usa un valor no válido para configurar un campo).</span><span class="sxs-lookup"><span data-stu-id="680cd-122">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="680cd-123">El parámetro `interactiveMode` proporciona el rendimiento máximo y el informe de errores en el nivel de actualizaciones de campo.</span><span class="sxs-lookup"><span data-stu-id="680cd-123">The `interactiveMode` parameter provides maximum performance and provides error reporting at the field-update level.</span></span> <span data-ttu-id="680cd-124">Para usar correctamente esta característica, se recomienda que realice llamadas normales con `interactiveMode` definido en FALSE.</span><span class="sxs-lookup"><span data-stu-id="680cd-124">To use this feature properly, it is recommended that you make normal calls with `interactiveMode` set to FALSE.</span></span> <span data-ttu-id="680cd-125">No debe haber ningún impacto en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="680cd-125">There should be no impact on performance.</span></span> <span data-ttu-id="680cd-126">Si se devuelve un error, se puede recuperar la misma llamada con la marca de interactiveMode establecida en TRUE.</span><span class="sxs-lookup"><span data-stu-id="680cd-126">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="680cd-127">Cuando se produce un error en la llamada, el servidor devuelve un mensaje de error más preciso.</span><span class="sxs-lookup"><span data-stu-id="680cd-127">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="680cd-128">Contiene un subconjunto de la estructura que existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="680cd-128">Contains a subset of the structure that exists on the server.</span></span> <span data-ttu-id="680cd-129">Todos los elementos que son hojas se eliminan.</span><span class="sxs-lookup"><span data-stu-id="680cd-129">All items that are leaves are deleted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="680cd-130">Notas</span><span class="sxs-lookup"><span data-stu-id="680cd-130">Remarks</span></span>  
 <span data-ttu-id="680cd-131">Las propiedades tienen el mismo tipo de datos que los métodos `CreateEx` o `UpdateEx` de esta interfaz de componentes; sin embargo, únicamente los valores de clave son importantes.</span><span class="sxs-lookup"><span data-stu-id="680cd-131">The properties have the same data type as the `CreateEx` or `UpdateEx` methods of this component interface; however, only the key values are important.</span></span> <span data-ttu-id="680cd-132">Se omiten los valores que no son claves.</span><span class="sxs-lookup"><span data-stu-id="680cd-132">The non-key values are ignored.</span></span> <span data-ttu-id="680cd-133">Los valores de clave deben coincidir con los del servidor, de lo contrario se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="680cd-133">The key values must match those on the server, otherwise an exception is raised.</span></span>  
  
 <span data-ttu-id="680cd-134">A continuación, se muestra el uso de los valores de clave.</span><span class="sxs-lookup"><span data-stu-id="680cd-134">The following demonstrates the use of the key values.</span></span> <span data-ttu-id="680cd-135">Si una colección contiene los elementos:</span><span class="sxs-lookup"><span data-stu-id="680cd-135">If a collection contains the items:</span></span>  
  
- <span data-ttu-id="680cd-136">item0</span><span class="sxs-lookup"><span data-stu-id="680cd-136">item0</span></span>  
  
- <span data-ttu-id="680cd-137">item1</span><span class="sxs-lookup"><span data-stu-id="680cd-137">item1</span></span>  
  
- <span data-ttu-id="680cd-138">Item2</span><span class="sxs-lookup"><span data-stu-id="680cd-138">item2</span></span>  
  
- <span data-ttu-id="680cd-139">Item3</span><span class="sxs-lookup"><span data-stu-id="680cd-139">item3</span></span>  
  
  <span data-ttu-id="680cd-140">Puede eliminar item1 e item3 proporcionando las claves de item1 e item3 en las propiedades:</span><span class="sxs-lookup"><span data-stu-id="680cd-140">You can delete item1 and item3 by providing the keys of item1 and item3 in the properties:</span></span>  
  
- <span data-ttu-id="680cd-141">item1</span><span class="sxs-lookup"><span data-stu-id="680cd-141">item1</span></span>  
  
- <span data-ttu-id="680cd-142">Item3</span><span class="sxs-lookup"><span data-stu-id="680cd-142">item3</span></span>  
  
  <span data-ttu-id="680cd-143">Después de la llamada, el servidor tiene los elementos restantes de la colección:</span><span class="sxs-lookup"><span data-stu-id="680cd-143">After the call, the server has the remaining items in the collection:</span></span>  
  
- <span data-ttu-id="680cd-144">item0</span><span class="sxs-lookup"><span data-stu-id="680cd-144">item0</span></span>  
  
- <span data-ttu-id="680cd-145">Item2</span><span class="sxs-lookup"><span data-stu-id="680cd-145">item2</span></span>  
  
  <span data-ttu-id="680cd-146">El segundo ejemplo muestra los elementos que contienen otras colecciones:</span><span class="sxs-lookup"><span data-stu-id="680cd-146">The second example shows the items containing other collections:</span></span>  
  
- <span data-ttu-id="680cd-147">item0</span><span class="sxs-lookup"><span data-stu-id="680cd-147">item0</span></span>  
  
  -   <span data-ttu-id="680cd-148">item0a</span><span class="sxs-lookup"><span data-stu-id="680cd-148">item0a</span></span>  
  
- <span data-ttu-id="680cd-149">item1</span><span class="sxs-lookup"><span data-stu-id="680cd-149">item1</span></span>  
  
  -   <span data-ttu-id="680cd-150">item1a</span><span class="sxs-lookup"><span data-stu-id="680cd-150">item1a</span></span>  
  
  -   <span data-ttu-id="680cd-151">item1b</span><span class="sxs-lookup"><span data-stu-id="680cd-151">item1b</span></span>  
  
  -   <span data-ttu-id="680cd-152">item1c</span><span class="sxs-lookup"><span data-stu-id="680cd-152">item1c</span></span>  
  
- <span data-ttu-id="680cd-153">Item2</span><span class="sxs-lookup"><span data-stu-id="680cd-153">item2</span></span>  
  
  -   <span data-ttu-id="680cd-154">item2a</span><span class="sxs-lookup"><span data-stu-id="680cd-154">item2a</span></span>  
  
  -   <span data-ttu-id="680cd-155">item2b</span><span class="sxs-lookup"><span data-stu-id="680cd-155">item2b</span></span>  
  
  <span data-ttu-id="680cd-156">Puede eliminar item1b y todos los item2 proporcionando las claves a item1b e item2:</span><span class="sxs-lookup"><span data-stu-id="680cd-156">You can delete item1b and all of item2 by giving the keys to item1b and item2:</span></span>  
  
- <span data-ttu-id="680cd-157">item1</span><span class="sxs-lookup"><span data-stu-id="680cd-157">item1</span></span>  
  
  -   <span data-ttu-id="680cd-158">item1b</span><span class="sxs-lookup"><span data-stu-id="680cd-158">item1b</span></span>  
  
- <span data-ttu-id="680cd-159">Item2</span><span class="sxs-lookup"><span data-stu-id="680cd-159">item2</span></span>  
  
  <span data-ttu-id="680cd-160">Si suministra una subcolección vacía para item2, lo convierte en hoja y se elimina toda la subramificación.</span><span class="sxs-lookup"><span data-stu-id="680cd-160">By providing an empty sub-collection for item2, you turn it into a leaf and that entire sub-branch is deleted.</span></span> <span data-ttu-id="680cd-161">Después de la llamada, el servidor tiene los elementos restantes:</span><span class="sxs-lookup"><span data-stu-id="680cd-161">After the call, the server has the remaining items:</span></span>  
  
- <span data-ttu-id="680cd-162">item0</span><span class="sxs-lookup"><span data-stu-id="680cd-162">item0</span></span>  
  
  -   <span data-ttu-id="680cd-163">item0a</span><span class="sxs-lookup"><span data-stu-id="680cd-163">item0a</span></span>  
  
- <span data-ttu-id="680cd-164">item1</span><span class="sxs-lookup"><span data-stu-id="680cd-164">item1</span></span>  
  
  -   <span data-ttu-id="680cd-165">item1a</span><span class="sxs-lookup"><span data-stu-id="680cd-165">item1a</span></span>  
  
  -   <span data-ttu-id="680cd-166">item1c</span><span class="sxs-lookup"><span data-stu-id="680cd-166">item1c</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680cd-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="680cd-167">See Also</span></span>  
 [<span data-ttu-id="680cd-168">Apéndice A: Métodos de interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="680cd-168">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)