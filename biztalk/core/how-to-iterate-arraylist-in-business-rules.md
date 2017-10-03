---
title: "Cómo recorrer en iteración ArrayList en reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95896b63e5bb982a4778b05970900c989ebc66b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a><span data-ttu-id="dcd75-102">Cómo recorrer en iteración ArrayList en reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="dcd75-102">How to Iterate ArrayList in Business Rules</span></span>
<span data-ttu-id="dcd75-103">Esta sección proporciona un ejemplo de cómo recorrer en iteración los miembros de un **ArrayList** en reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="dcd75-103">This section provides an example of iterating through members of an **ArrayList** in business rules.</span></span>  
  
 <span data-ttu-id="dcd75-104">Suponga que tiene un **ArrayList** con una colección de **MyClass** objetos.</span><span class="sxs-lookup"><span data-stu-id="dcd75-104">Assume you have an **ArrayList** with a collection of **MyClass** objects.</span></span> <span data-ttu-id="dcd75-105">Las reglas de negocio tendrían el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="dcd75-105">Your business rules would look like the following.</span></span>  
  
## <a name="rule-a"></a><span data-ttu-id="dcd75-106">Regla A</span><span class="sxs-lookup"><span data-stu-id="dcd75-106">Rule A</span></span>  
 <span data-ttu-id="dcd75-107">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="dcd75-107">IF 1==1</span></span>  
  
 <span data-ttu-id="dcd75-108">THEN Assert (ArrayList.GetEnumerator)</span><span class="sxs-lookup"><span data-stu-id="dcd75-108">THEN Assert (ArrayList.GetEnumerator)</span></span>  
  
 <span data-ttu-id="dcd75-109">Un **IEnumerator** tipo se impone en la memoria de trabajo, porque la condición de regla (1 == 1) siempre se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="dcd75-109">An **IEnumerator** type is asserted into the working memory, because the rule condition (1==1) always evaluates to true.</span></span>  
  
## <a name="rule-b"></a><span data-ttu-id="dcd75-110">Regla B</span><span class="sxs-lookup"><span data-stu-id="dcd75-110">Rule B</span></span>  
 <span data-ttu-id="dcd75-111">IF IEnumerator.MoveNext</span><span class="sxs-lookup"><span data-stu-id="dcd75-111">IF IEnumerator.MoveNext</span></span>  
  
 <span data-ttu-id="dcd75-112">THEN    Assert (IEnumerator.get_Current)</span><span class="sxs-lookup"><span data-stu-id="dcd75-112">THEN    Assert (IEnumerator.get_Current)</span></span>  
  
 <span data-ttu-id="dcd75-113">Update (IEnumerator)</span><span class="sxs-lookup"><span data-stu-id="dcd75-113">Update (IEnumerator)</span></span>  
  
 <span data-ttu-id="dcd75-114">Como la regla recorre en iteración la **ArrayList**, cada **MyClass** objeto en la colección se agrega a la memoria de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dcd75-114">As the rule iterates through the **ArrayList**, each **MyClass** object in the collection is asserted into the working memory.</span></span>  
  
## <a name="rule-c"></a><span data-ttu-id="dcd75-115">Regla C</span><span class="sxs-lookup"><span data-stu-id="dcd75-115">Rule C</span></span>  
 <span data-ttu-id="dcd75-116">IF MyClass.MyProperty==2</span><span class="sxs-lookup"><span data-stu-id="dcd75-116">IF MyClass.MyProperty==2</span></span>  
  
 <span data-ttu-id="dcd75-117">A continuación, \<hacer algo... ></span><span class="sxs-lookup"><span data-stu-id="dcd75-117">THEN \<Do Something...></span></span>  
  
 <span data-ttu-id="dcd75-118">Esta regla ejecuta una acción (o acciones) cuando el valor de propiedad del objeto coincide con la condición.</span><span class="sxs-lookup"><span data-stu-id="dcd75-118">This rule executes action(s) when the property value of the object is matched in the condition.</span></span>