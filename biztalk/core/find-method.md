---
title: Find (método) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245972"
---
# <a name="find-method"></a><span data-ttu-id="9cf27-102">Find (método)</span><span class="sxs-lookup"><span data-stu-id="9cf27-102">Find Method</span></span>
<span data-ttu-id="9cf27-103">Se usa para devolver una lista de claves que satisfacen las claves de búsqueda parciales proporcionada.</span><span class="sxs-lookup"><span data-stu-id="9cf27-103">Used to return a list of keys that satisfy the supplied partial search keys.</span></span> <span data-ttu-id="9cf27-104">Tenga en cuenta que, para una interfaz de componente que solo tiene una instancia, es decir, que no existe clave, no se genera la función `Find()`.</span><span class="sxs-lookup"><span data-stu-id="9cf27-104">Note that for a component interface that has only one instance, that is, there is no key, the `Find()` function is not generated.</span></span> <span data-ttu-id="9cf27-105">Vea también [Get (método)](../core/get-method.md).</span><span class="sxs-lookup"><span data-stu-id="9cf27-105">See also [Get Method](../core/get-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf27-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cf27-106">Syntax</span></span>  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cf27-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cf27-107">Parameters</span></span>  
  
|<span data-ttu-id="9cf27-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9cf27-108">Parameter</span></span>|<span data-ttu-id="9cf27-109">Description</span><span class="sxs-lookup"><span data-stu-id="9cf27-109">Description</span></span>|  
|---------------|-----------------|  
|`partialKey`|<span data-ttu-id="9cf27-110">Una estructura donde las claves individuales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="9cf27-110">A structure where the individual keys are optional.</span></span>|  
|`keyList`|<span data-ttu-id="9cf27-111">Lista de claves que coincide con `partialKey`.</span><span class="sxs-lookup"><span data-stu-id="9cf27-111">A list of keys that matches the `partialKey`.</span></span> <span data-ttu-id="9cf27-112">Es un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="9cf27-112">It is an output parameter.</span></span><br /><br /> <span data-ttu-id="9cf27-113">Las claves corresponden con el conjunto de claves Buscar definido para la interfaz de componentes concreta.</span><span class="sxs-lookup"><span data-stu-id="9cf27-113">The keys correspond to the set of Find Keys as defined for the particular component interface.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf27-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9cf27-114">Remarks</span></span>  
 <span data-ttu-id="9cf27-115">Si especifica las claves parciales, se puede usar la misma búsqueda con comodín disponible desde la función interna de PeopleSoft `Find()`.</span><span class="sxs-lookup"><span data-stu-id="9cf27-115">When you specify the partial keys, it is possible to use the same wildcard search available from the PeopleSoft internal `Find()` function.</span></span> <span data-ttu-id="9cf27-116">Por ejemplo, la clave parcial de CUENTA "11" devuelve todas las claves de CUENTA que comienzan por "11", mientras que "%40" devuelve todas las claves de CUENTA que contienen "40" en cualquier lugar de la clave.</span><span class="sxs-lookup"><span data-stu-id="9cf27-116">For example, the partial ACCOUNT key of "11" returns all ACCOUNT keys that start with "11", whereas "%40" returns all ACCOUNT keys that contain "40" anywhere within the key.</span></span> <span data-ttu-id="9cf27-117">La clave parcial "_4_4" devuelve todas las claves de CUENTA que tengan el carácter "4" en las posiciones 2 y 4.</span><span class="sxs-lookup"><span data-stu-id="9cf27-117">A partial key "_4_4" returns all ACCOUNT keys with the character "4" in the 2nd and 4th positions.</span></span>  
  
 <span data-ttu-id="9cf27-118">Nota: Con la implementación actual de PeopleSoft Server, si más de 300 elementos coinciden con los criterios de búsqueda, la llamada produce un error.</span><span class="sxs-lookup"><span data-stu-id="9cf27-118">Note: With the current implementation of the PeopleSoft Server, if more than 300 items match the search criteria, the call fails.</span></span> <span data-ttu-id="9cf27-119">Esto es una restricción del servidor PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="9cf27-119">This is a restriction of the PeopleSoft server.</span></span> <span data-ttu-id="9cf27-120">Se proporciona el método `Find()` del adaptador de Microsoft BizTalk para PeopleSoft Enterprise si la función `Find` de PeopleSoft está habilitada en la interfaz de componentes y las claves Obtener están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cf27-120">The Microsoft BizTalk Adapter for PeopleSoft Enterprise `Find()` method is provided if the PeopleSoft `Find` function in the component interface is enabled and Get keys are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf27-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cf27-121">See Also</span></span>  
 [<span data-ttu-id="9cf27-122">Apéndice A: métodos de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="9cf27-122">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)