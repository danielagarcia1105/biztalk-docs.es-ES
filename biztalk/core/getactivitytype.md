---
title: GetActivityType | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67e6f31331907e20e810c11e82002fb08b89abe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246420"
---
# <a name="getactivitytype"></a><span data-ttu-id="a96e6-102">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="a96e6-102">GetActivityType</span></span>
<span data-ttu-id="a96e6-103">Inserta el nombre del tipo de actividad actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="a96e6-103">Pushes the name of the current activity type onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a96e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a96e6-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a96e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a96e6-105">Parameters</span></span>  
 <span data-ttu-id="a96e6-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a96e6-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="a96e6-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="a96e6-107">Pushed Value</span></span>  
 <span data-ttu-id="a96e6-108">Cadena que contiene el tipo de actividad actual en un formato de nombre de clase cualificado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a96e6-108">String containing the current activity type in assembly-qualified class name format.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a96e6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a96e6-109">Remarks</span></span>  
 <span data-ttu-id="a96e6-110">La operación `GetActivityType` recupera el tipo de actividad actual y lo coloca en la pila del formato de nombre de clase cualificado del ensamblado:</span><span class="sxs-lookup"><span data-stu-id="a96e6-110">The `GetActivityType` operation retrieves the current activity type and places it on the stack in assembly-qualified class name format:</span></span>  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 <span data-ttu-id="a96e6-111">Al realizar la comparación, puede especificar la mayor parte del tipo necesario para satisfacer los requisitos de búsqueda específicos.</span><span class="sxs-lookup"><span data-stu-id="a96e6-111">When comparing, you can specify as much of the type as necessary to satisfy your specific search needs.</span></span> <span data-ttu-id="a96e6-112">Por ejemplo, se podría comparar el resultado de GetActivityType con la constante:</span><span class="sxs-lookup"><span data-stu-id="a96e6-112">For example, you might compare the result of GetActivityType with the constant:</span></span>  
  
 <span data-ttu-id="a96e6-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span><span class="sxs-lookup"><span data-stu-id="a96e6-113">TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0</span></span>  
  
 <span data-ttu-id="a96e6-114">Es menos restrictivo que el formato de nombre de clase cualificado del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a96e6-114">This is less restrictive than the assembly-qualified class name format.</span></span>  
  
## <a name="special-filter-behavior"></a><span data-ttu-id="a96e6-115">Comportamiento de filtro especial</span><span class="sxs-lookup"><span data-stu-id="a96e6-115">Special Filter Behavior</span></span>  
 <span data-ttu-id="a96e6-116">Cuando se realiza esta operación dentro de un filtro, también se buscan coincidencias de las actividades derivadas.</span><span class="sxs-lookup"><span data-stu-id="a96e6-116">When this operation is performed inside of a filter, derived activities are always matched as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a96e6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a96e6-117">Example</span></span>  
 <span data-ttu-id="a96e6-118">El siguiente ejemplo contiene un filtro de evento que se evaluará como `true` para las instancias de `System.Workflow.ComponentModel.Activity` y para cualquier instancia de las clases que se deriven de `System.Workflow.ComponentModel.Activity`.</span><span class="sxs-lookup"><span data-stu-id="a96e6-118">The following sample contains an event filter expression that will evaluate to `true` for `System.Workflow.ComponentModel.Activity` instances and any instances from classes that derive from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```