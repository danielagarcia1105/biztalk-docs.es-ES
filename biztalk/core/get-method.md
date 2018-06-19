---
title: Get (método) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Get method
ms.assetid: 0e621077-f0ef-495c-ba6b-0c6154f48113
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56b060cc261f707a4aa7b0d6a496a62707c4dca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246524"
---
# <a name="get-method"></a><span data-ttu-id="ad801-102">Método Get</span><span class="sxs-lookup"><span data-stu-id="ad801-102">Get Method</span></span>
<span data-ttu-id="ad801-103">Usar para recuperar propiedades basándose en los parámetros de clave de entrada (clave1, clave2...</span><span class="sxs-lookup"><span data-stu-id="ad801-103">Used to retrieve properties based on the input key parameters (key1, key2, …</span></span> <span data-ttu-id="ad801-104">claven).</span><span class="sxs-lookup"><span data-stu-id="ad801-104">keyn).</span></span> <span data-ttu-id="ad801-105">El parámetro de salida es una estructura que contiene las propiedades del registro que coincide con los parámetros de clave.</span><span class="sxs-lookup"><span data-stu-id="ad801-105">The output parameter is a structure containing the properties of the record that matches the key parameters.</span></span> <span data-ttu-id="ad801-106">Si la interfaz de componente tiene solo una instancia (es decir, no hay ninguna clave), la función Get no contiene ningún parámetro de clave.</span><span class="sxs-lookup"><span data-stu-id="ad801-106">If the component interface has only one instance (that is, there is no key), the Get function does not contain any key parameter.</span></span> <span data-ttu-id="ad801-107">Consulte también [método Find](../core/find-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad801-107">Also see [Find Method](../core/find-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad801-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad801-108">Syntax</span></span>  
  
```  
Get (key1, key2, ... keyn, properties)  
Get (key1, key2, ... keyn, getHistoryItems, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad801-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad801-109">Parameters</span></span>  
  
|<span data-ttu-id="ad801-110">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ad801-110">Parameter</span></span>|<span data-ttu-id="ad801-111">Description</span><span class="sxs-lookup"><span data-stu-id="ad801-111">Description</span></span>|  
|---------------|-----------------|  
|`key`|<span data-ttu-id="ad801-112">Conjunto de parámetros que debe existir en la base de datos del servidor; de lo contrario, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="ad801-112">A set of parameters that must exist in the server database; otherwise an error occurs.</span></span> <span data-ttu-id="ad801-113">Estas claves corresponden al conjunto de Get Keys definido para la interfaz de componentes concreta.</span><span class="sxs-lookup"><span data-stu-id="ad801-113">These keys correspond to the set of Get Keys as defined for the particular Component Interface.</span></span>|  
|`properties`|<span data-ttu-id="ad801-114">Contiene una estructura completa de las propiedades de la interfaz de componentes, que se devuelve al completarse la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad801-114">Contains a complete structure of the component interface properties, which is returned upon completion of the call.</span></span>|  
|`getHistoryItems`|<span data-ttu-id="ad801-115">Valor booleano.</span><span class="sxs-lookup"><span data-stu-id="ad801-115">A Boolean value.</span></span> <span data-ttu-id="ad801-116">Si las propiedades de la interfaz de componentes contienen elementos con fecha de vigencia por debajo del nivel 0 (es decir, un campo de claves con el nombre EFFDT), es obligatorio el parámetro adicional `getHistoryItems`.</span><span class="sxs-lookup"><span data-stu-id="ad801-116">If the properties of the component interface contain effective-dated items below level 0 (that is, a key field with a name of EFFDT) the `getHistoryItems` additional parameter is required.</span></span><br /><br /> <span data-ttu-id="ad801-117">Si el valor es:</span><span class="sxs-lookup"><span data-stu-id="ad801-117">If the value is:</span></span><br /><br /> <span data-ttu-id="ad801-118">-True: todos los elementos con fecha de vigencia se devuelven como una secuencia (que puede estar insertada en cualquier nivel).</span><span class="sxs-lookup"><span data-stu-id="ad801-118">-   True—All effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="ad801-119">Entre ellos se incluyen todos los elementos con fecha de vigencia pasada, el elemento con fecha de vigencia actual y todos los elementos con fecha de vigencia futura</span><span class="sxs-lookup"><span data-stu-id="ad801-119">These include all past effective dated items, the current effective dated item, as well as all future effective dated items</span></span><br /><span data-ttu-id="ad801-120">-False, se devuelven solo la actual y todos los elementos con fecha de vigencia futuros.</span><span class="sxs-lookup"><span data-stu-id="ad801-120">-   False—Only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="ad801-121">Si se van a realizar otras llamadas para actualizar en la misma instancia, el parámetro `getHistoryItems` debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="ad801-121">If subsequent calls to update on the same instance will be made, then `getHistoryItems` should be set to False.</span></span>|  
  
### <a name="remarks"></a><span data-ttu-id="ad801-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad801-122">Remarks</span></span>  
 <span data-ttu-id="ad801-123">Si las propiedades de la interfaz de componentes contienen elementos con fecha de vigencia por debajo del nivel 0 (es decir, un campo de clave con el nombre EFFDT), es obligatorio el parámetro adicional `getHistoryItems`.</span><span class="sxs-lookup"><span data-stu-id="ad801-123">If the properties of the component interface contain effective dated items below level 0 (that is, a key field with a name of EFFDT), an additional parameter, `getHistoryItems`, is required.</span></span> <span data-ttu-id="ad801-124">Este parámetro es de tipo booleano.</span><span class="sxs-lookup"><span data-stu-id="ad801-124">This parameter is of type Boolean.</span></span> <span data-ttu-id="ad801-125">Si se establece en True, todos los elementos con fecha de vigencia se devuelven como secuencia (que puede estar insertada en cualquier nivel).</span><span class="sxs-lookup"><span data-stu-id="ad801-125">If it is set to True, all effective dated items are returned as a sequence (which could be embedded in any level).</span></span> <span data-ttu-id="ad801-126">Entre ellos se incluyen todos los elementos con fecha de vigencia pasada, el elemento con fecha de vigencia actual y todos los elementos con fecha de vigencia futura.</span><span class="sxs-lookup"><span data-stu-id="ad801-126">These include all past effective dated items, the current effective dated item, as well as all future effective dated items.</span></span> <span data-ttu-id="ad801-127">Si el parámetro `getHistoryItems` se establece en False, solamente se devolverán el elemento con fecha de vigencia actual y todos los futuros.</span><span class="sxs-lookup"><span data-stu-id="ad801-127">If the `getHistoryItems` parameter is set to False, only the current and all future effective dated items are returned.</span></span> <span data-ttu-id="ad801-128">Si deben realizarse otras llamadas para actualizar en la misma instancia, el parámetro `getHistoryItems` debe establecerse en False.</span><span class="sxs-lookup"><span data-stu-id="ad801-128">If subsequent calls to update on the same instance are to be made, then `getHistoryItems` should be set to False.</span></span> <span data-ttu-id="ad801-129">Vea también [método UpdateEx](../core/updateex-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad801-129">See also [UpdateEx Method](../core/updateex-method.md).</span></span>  
  
 <span data-ttu-id="ad801-130">Si la interfaz de componentes no tiene clave, como sucede si solo puede existir una instancia, el método `Get()` tiene el formato:</span><span class="sxs-lookup"><span data-stu-id="ad801-130">If the component interface does not have a key, as in the case where only one instance can exist, then the `Get()` method has the form:</span></span>  
  
```  
Get(properties)  
```  
  
 <span data-ttu-id="ad801-131">Para obtener más información sobre los elementos con fecha de vigencia, vea la documentación de PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ad801-131">For more information on effective dated items, see the PeopleSoft Enterprise documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad801-132">Se proporciona el método `Get()` del Adaptador de BizTalk para PeopleSoft Enterprise si se habilita la función `Get` de PeopleSoft en la interfaz de componentes.</span><span class="sxs-lookup"><span data-stu-id="ad801-132">The BizTalk Adapter for PeopleSoft Enterprise `Get()` method is provided if the PeopleSoft `Get` function in the component interface is enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad801-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad801-133">See Also</span></span>  
 [<span data-ttu-id="ad801-134">Apéndice A: métodos de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="ad801-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)