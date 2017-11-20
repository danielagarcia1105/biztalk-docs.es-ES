---
title: Constante | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="constant"></a><span data-ttu-id="3e164-102">Constante</span><span class="sxs-lookup"><span data-stu-id="3e164-102">Constant</span></span>
<span data-ttu-id="3e164-103">Inserta un valor único y constante en la pila.</span><span class="sxs-lookup"><span data-stu-id="3e164-103">Pushes a single constant value onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e164-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e164-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e164-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e164-105">Parameters</span></span>  
 <span data-ttu-id="3e164-106">Valor constante.</span><span class="sxs-lookup"><span data-stu-id="3e164-106">Constant value.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="3e164-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="3e164-107">Pushed Value</span></span>  
 <span data-ttu-id="3e164-108">Cadena que contiene el valor constante.</span><span class="sxs-lookup"><span data-stu-id="3e164-108">String containing the constant value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e164-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e164-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e164-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e164-110">Example</span></span>  
 <span data-ttu-id="3e164-111">La siguiente expresión de filtro de ejemplo utiliza la **constante** operación para insertar un valor que se usará en un **es igual a** operación para asegurarse de que el nombre de la actividad actual sea "FoodAndDrinksPolicy".</span><span class="sxs-lookup"><span data-stu-id="3e164-111">The following sample filter expression uses the **Constant** operation to push a value that will then be used in an **Equals** operation to ensure that the current activity name is "FoodAndDrinksPolicy".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="3e164-112">Se trata de un patrón de uso común para la **constante** operación.</span><span class="sxs-lookup"><span data-stu-id="3e164-112">This is a common usage pattern for the **Constant** operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e164-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e164-113">See Also</span></span>  
 [<span data-ttu-id="3e164-114">Operaciones de interceptor</span><span class="sxs-lookup"><span data-stu-id="3e164-114">Interceptor Operations</span></span>](../core/interceptor-operations.md)