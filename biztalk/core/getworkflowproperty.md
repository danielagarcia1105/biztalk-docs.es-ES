---
title: GetWorkflowProperty | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505fc41ce544cdf16e3826116514ba1991ba012e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowproperty"></a><span data-ttu-id="7529e-102">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="7529e-102">GetWorkflowProperty</span></span>
<span data-ttu-id="7529e-103">Inserta la propiedad extraída de la actividad raíz del flujo de trabajo en la pila.</span><span class="sxs-lookup"><span data-stu-id="7529e-103">Pushes the extracted property from the root activity of the workflow onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7529e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7529e-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7529e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7529e-105">Parameters</span></span>  
 <span data-ttu-id="7529e-106">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7529e-106">Name of the property.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="7529e-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="7529e-107">Pushed Value</span></span>  
 <span data-ttu-id="7529e-108">Cadena que contiene el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7529e-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7529e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7529e-109">Remarks</span></span>  
 <span data-ttu-id="7529e-110">Esta operación sólo es válida en las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="7529e-110">This operation is only valid in Updates.</span></span>  
  
 <span data-ttu-id="7529e-111">Puede utilizar la notación con punto para la calificación del nombre de propiedad que desee recuperar.</span><span class="sxs-lookup"><span data-stu-id="7529e-111">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="7529e-112">Esto le proporcionará acceso a objetos dentro de otros objetos expuestos mediante las propiedades.</span><span class="sxs-lookup"><span data-stu-id="7529e-112">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="7529e-113">Por ejemplo, para obtener acceso a la propiedad de ciudad de una instancia de dirección de un pedido de compra, utilice “purchaseOrder.Address.City”.</span><span class="sxs-lookup"><span data-stu-id="7529e-113">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="7529e-114">Los nombres de propiedades distinguen primero entre mayúsculas y minúsculas; después no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="7529e-114">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="7529e-115">Esto es importante cuando tiene dos o más propiedades de actividad que varían sólo en las mayúsculas y minúsculas en la aplicación WF.</span><span class="sxs-lookup"><span data-stu-id="7529e-115">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="7529e-116">Por ejemplo, si la aplicación de flujo de trabajo tiene las propiedades “myWorkflow” y “MyWorkflow” definidas y estuvo buscando “MyWorkflow”, coincidiría con la segunda propiedad gracias a la coincidencia que distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7529e-116">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="7529e-117">Si especifica “MYWORKFLOW”, coincidiría con “myWorkflow” gracias a la coincidencia que distingue entre mayúsculas y minúsculas después de que se produzca un error en el intento de coincidencia que no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7529e-117">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-sensitive match after a case-insensitive match attempt fails.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7529e-118">Los valores de propiedad NULL crearán una excepción NullReferenceException que se devuelve a la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7529e-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7529e-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7529e-119">Example</span></span>  
 <span data-ttu-id="7529e-120">En el siguiente ejemplo, se utiliza una expresión de actualización para que persista la propiedad de flujo de trabajo de ciudad a partir de un pedido de compra utilizando `GetWorkflowProperty`.</span><span class="sxs-lookup"><span data-stu-id="7529e-120">In the following sample, an update expression is used to persist the workflow property "City" from a purchase order by using `GetWorkflowProperty`.</span></span>  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```