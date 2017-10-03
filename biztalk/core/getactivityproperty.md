---
title: GetActivityProperty | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55f0d24da85088fb8f13693c8c71d32bee1bef7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityproperty"></a><span data-ttu-id="59ad2-102">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="59ad2-102">GetActivityProperty</span></span>
<span data-ttu-id="59ad2-103">Inserta la propiedad extraída de la actividad relacionada con el evento de seguimiento en la pila.</span><span class="sxs-lookup"><span data-stu-id="59ad2-103">Pushes the extracted property from the activity related to the tracking event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ad2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59ad2-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59ad2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59ad2-105">Parameters</span></span>  
 <span data-ttu-id="59ad2-106">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="59ad2-106">Name of the property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59ad2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59ad2-107">Return Value</span></span>  
 <span data-ttu-id="59ad2-108">Cadena que contiene el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="59ad2-108">String containing the value of the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59ad2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59ad2-109">Remarks</span></span>  
 <span data-ttu-id="59ad2-110">Puede utilizar la notación con punto para la calificación del nombre de propiedad que desee recuperar.</span><span class="sxs-lookup"><span data-stu-id="59ad2-110">You can use dotted-notation for qualifying the property name you want to retrieve.</span></span> <span data-ttu-id="59ad2-111">Esto le proporcionará acceso a objetos dentro de otros objetos expuestos mediante las propiedades.</span><span class="sxs-lookup"><span data-stu-id="59ad2-111">This will provide you access to objects inside of other objects exposed through properties.</span></span> <span data-ttu-id="59ad2-112">Por ejemplo, para obtener acceso a la propiedad de ciudad de una instancia de dirección de un pedido de compra, utilice “purchaseOrder.Address.City”.</span><span class="sxs-lookup"><span data-stu-id="59ad2-112">For example, to access the City property of an Address instance of a purchase order, use "purchaseOrder.Address.City".</span></span>  
  
 <span data-ttu-id="59ad2-113">Los nombres de propiedades distinguen primero entre mayúsculas y minúsculas; después no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="59ad2-113">Property names are case-sensitive first, and then case-insensitive.</span></span> <span data-ttu-id="59ad2-114">Esto es importante cuando tiene dos o más propiedades de actividad que varían sólo en las mayúsculas y minúsculas en la aplicación WF.</span><span class="sxs-lookup"><span data-stu-id="59ad2-114">This is important when you have two or more activity properties that vary only by case in your WF application.</span></span> <span data-ttu-id="59ad2-115">Por ejemplo, si la aplicación de flujo de trabajo tiene las propiedades “myWorkflow” y “MyWorkflow” definidas y estuvo buscando “MyWorkflow”, coincidiría con la segunda propiedad gracias a la coincidencia que distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59ad2-115">For example, if your workflow application has the properties "myWorkflow" and "MyWorkflow" defined and you were looking for "MyWorkflow", it would match on the second property through a case-sensitive match.</span></span> <span data-ttu-id="59ad2-116">Si especifica “MYWORKFLOW”, coincidiría con “myWorkflow” gracias a la coincidencia que no distingue entre mayúsculas y minúsculas después de que se produzca un error en el intento de coincidencia que distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59ad2-116">If you specify "MYWORKFLOW", it would match "myWorkflow" through a case-insensitive match after a case-sensitive match attempt fails.</span></span>  
  
 <span data-ttu-id="59ad2-117">Por ejemplo, si tiene dos propiedades de la actividad que varían sólo por mayúsculas: "myProperty" y "MyProperty".</span><span class="sxs-lookup"><span data-stu-id="59ad2-117">For example, if you have two activity properties that vary only by case: "myProperty" and "MyProperty".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59ad2-118">Los valores de propiedad NULL crearán una excepción NullReferenceException que se devuelve a la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="59ad2-118">NULL property values will result in a NullReferenceException being thrown back to the workflow instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ad2-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59ad2-119">Example</span></span>  
 <span data-ttu-id="59ad2-120">En el siguiente ejemplo, se utiliza una expresión de actualización para que persista la propiedad de actividad “MyProperty” utilizando `GetActivityProperty`.</span><span class="sxs-lookup"><span data-stu-id="59ad2-120">In the following sample, an update expression is used to persist the activity property "MyProperty" by using `GetActivityProperty`.</span></span>  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```