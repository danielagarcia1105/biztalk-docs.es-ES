---
title: XPath | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289652"
---
# <a name="xpath"></a><span data-ttu-id="916d6-102">XPath</span><span class="sxs-lookup"><span data-stu-id="916d6-102">XPath</span></span>
<span data-ttu-id="916d6-103">Inserta el valor indicado por una instrucción XPath.</span><span class="sxs-lookup"><span data-stu-id="916d6-103">Pushes the value indicated by an XPath statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="916d6-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="916d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="916d6-105">Parameters</span></span>  
 <span data-ttu-id="916d6-106">Instrucción XPath válida.</span><span class="sxs-lookup"><span data-stu-id="916d6-106">Valid XPath statement.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="916d6-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="916d6-107">Pushed Value</span></span>  
 <span data-ttu-id="916d6-108">Valor de cadena del resultado encontrado mediante la ejecución de la instrucción XPath.</span><span class="sxs-lookup"><span data-stu-id="916d6-108">String value of the result found by executing the XPath statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="916d6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="916d6-109">Remarks</span></span>  
 <span data-ttu-id="916d6-110">Debe usar una instrucción XPath válida.</span><span class="sxs-lookup"><span data-stu-id="916d6-110">You must use a valid XPath statement.</span></span>  
  
 <span data-ttu-id="916d6-111">En el caso en el que haya varias coincidencias, se usará sólo la primera de éstas.</span><span class="sxs-lookup"><span data-stu-id="916d6-111">In the case of multiple matches, only the first match is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="916d6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="916d6-112">Example</span></span>  
 <span data-ttu-id="916d6-113">En la siguiente expresión de ejemplo se construye un valor de correlación mediante la concatenación de una constante "C_" con el Id. de pedido de compra del mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="916d6-113">The following example expression constructs a correlation value by concatenating a constant "C_" with the purchase order ID from the current message.</span></span> <span data-ttu-id="916d6-114">El Id. de pedido de compra se recupera mediante el uso de la operación XPath.</span><span class="sxs-lookup"><span data-stu-id="916d6-114">The purchase order ID is retrieved by using the XPath operation.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="916d6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="916d6-115">See Also</span></span>  
 [<span data-ttu-id="916d6-116">Operaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="916d6-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)