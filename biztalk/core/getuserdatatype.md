---
title: Getuserdatatype (operación) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246468"
---
# <a name="getuserdatatype"></a><span data-ttu-id="67c36-102">GetUserDataType (operación)</span><span class="sxs-lookup"><span data-stu-id="67c36-102">GetUserDataType</span></span>
<span data-ttu-id="67c36-103">Inserta el nombre del tipo de datos del usuario actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="67c36-103">Pushes the name of the current user data type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67c36-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67c36-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67c36-105">Parameters</span></span>  
 <span data-ttu-id="67c36-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="67c36-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="67c36-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="67c36-107">Pushed Value</span></span>  
 <span data-ttu-id="67c36-108">Cadena que contiene el tipo de datos del usuario actual en formato completo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="67c36-108">String containing the current user data type in assembly-qualified format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c36-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67c36-109">Remarks</span></span>  
 <span data-ttu-id="67c36-110">A diferencia de **GetActivityType**, esta operación no utiliza el formato de nombre de clase cualificado del ensamblado; en su lugar, inserta el nombre de tipo:</span><span class="sxs-lookup"><span data-stu-id="67c36-110">Unlike **GetActivityType**, this operation does not use the assembly-qualified class name format; instead, it pushes only the type name:</span></span>  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  <span data-ttu-id="67c36-111">Si usa el formato de nombre de clase completo de ensamblado como constante al comparar valores, siempre se evaluará como `false`.</span><span class="sxs-lookup"><span data-stu-id="67c36-111">If you use the assembly-qualified class name format as a constant when comparing values it will always evaluate to `false`.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="67c36-112">Comportamiento de filtro especial</span><span class="sxs-lookup"><span data-stu-id="67c36-112">Special Filter Behavior</span></span>  
 <span data-ttu-id="67c36-113">Cuando se realiza esta operación dentro de un filtro, también se buscan coincidencias de los tipos de datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="67c36-113">When this operation is performed inside of a filter, derived user data types are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67c36-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c36-114">Example</span></span>  
 <span data-ttu-id="67c36-115">El siguiente ejemplo contiene una expresión de filtro de evento que se evaluará como `true` para las instancias de `MyLibrary.MyObject` y para cualquier instancia de las clases que se deriven de `MyLibrary.MyObject`.</span><span class="sxs-lookup"><span data-stu-id="67c36-115">The following sample contains an event filter expression that will evaluate to `true` for `MyLibrary.MyObject` instances and for any instances from classes that derive from `MyLibrary.MyObject`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyLibrary.MyObject</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```