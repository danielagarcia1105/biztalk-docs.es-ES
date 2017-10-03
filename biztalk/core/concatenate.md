---
title: Concatenar | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4766f65fb0cbe26c8f3c545c38235d83abb283a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="concatenate"></a><span data-ttu-id="61488-102">Concatenate</span><span class="sxs-lookup"><span data-stu-id="61488-102">Concatenate</span></span>
<span data-ttu-id="61488-103">Quita los dos elementos principales de la pila, los concatena y después inserta el resultado en la pila.</span><span class="sxs-lookup"><span data-stu-id="61488-103">Removes the top two items from the stack, concatenates them, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61488-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61488-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61488-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61488-105">Parameters</span></span>  
 <span data-ttu-id="61488-106">Dos elementos principales en la pila.</span><span class="sxs-lookup"><span data-stu-id="61488-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="61488-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="61488-107">Pushed Value</span></span>  
 <span data-ttu-id="61488-108">Cadena resultado de la operación de concatenación.</span><span class="sxs-lookup"><span data-stu-id="61488-108">String result of the concatenation operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61488-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="61488-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="61488-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61488-110">Example</span></span>  
 <span data-ttu-id="61488-111">En el ejemplo siguiente actualizar expresión, la cadena de constante "iniciar:" se concatena con el valor de la propiedad de contexto "EventTime" y se conservan en la columna de base de datos NewOrderCreateTime.</span><span class="sxs-lookup"><span data-stu-id="61488-111">In the following example update expression, the constant string "Start:" is concatenated with the value of the "EventTime" context property and persisted to the database column NewOrderCreateTime.</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61488-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="61488-112">See Also</span></span>  
 [<span data-ttu-id="61488-113">Operaciones de interceptor</span><span class="sxs-lookup"><span data-stu-id="61488-113">Interceptor Operations</span></span>](../core/interceptor-operations.md)