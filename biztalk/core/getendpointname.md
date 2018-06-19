---
title: GetEndpointName | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7e7a310c222cead89efd23e3f8202ade9eb47ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968762"
---
# <a name="getendpointname"></a><span data-ttu-id="d5ba0-102">GetEndpointName (operación)</span><span class="sxs-lookup"><span data-stu-id="d5ba0-102">GetEndpointName</span></span>
<span data-ttu-id="d5ba0-103">Inserta el nombre del extremo de interceptación actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-103">Pushes the name of the current interception endpoint onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ba0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5ba0-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5ba0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5ba0-105">Parameters</span></span>  
 <span data-ttu-id="d5ba0-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="d5ba0-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="d5ba0-107">Pushed Value</span></span>  
 <span data-ttu-id="d5ba0-108">Cadena que contiene el nombre del extremo de interceptación actual.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-108">String containing the current interception endpoint name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5ba0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5ba0-109">Remarks</span></span>  
 <span data-ttu-id="d5ba0-110">Resulta importante tener en cuenta que las aplicaciones cliente y servidor devolverán nombres distintos para el mismo nombre de extremo especificado en los archivos App.config.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-110">It is important to note that the client and server applications will return different names for the same endpoint name specified in the App.config files.</span></span>  
  
 <span data-ttu-id="d5ba0-111">En el caso de las aplicaciones cliente, el nombre del extremo recuperado por la operación GetEndPointName será el nombre del enlace seguido por un guión bajo y el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-111">For client applications, the endpoint name retrieved by the GetEndPointName operation is the binding name followed by an underscore and the contract name.</span></span>  
  
 <span data-ttu-id="d5ba0-112">Por ejemplo, si no se establece la propiedad de nombre en ServiceEndpoint, pero se establece el enlace, el nombre se establecerá \< *enlace*\>_\<*contrato* \>.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-112">For example, if the Name property on ServiceEndpoint is not set but the binding is set, the name will be set to \<*binding*\>_\<*contract*\>.</span></span>  
  
 <span data-ttu-id="d5ba0-113">Si no se establecen el nombre y el enlace, se establecerá la propiedad Name \< *contrato*\>.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-113">If the name and binding are not set, the Name property will be set to \<*contract*\>.</span></span>  
  
 <span data-ttu-id="d5ba0-114">En el caso del servicio, el nombre recuperado será el nombre del extremo especificado en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-114">For the service, the name retrieved is the endpoint name specified in the App.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5ba0-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5ba0-115">Example</span></span>  
 <span data-ttu-id="d5ba0-116">La expresión de filtro de ejemplo siguiente define una interceptación para la operación Receive correspondiente al punto de llamada de contrato ServiceRequest para el extremo PurchaseOrder_EP.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-116">The following example filter expression defines an interception for the Receive operation for the ServiceRequest contract call point for the PurchaseOrder_EP endpoint.</span></span> <span data-ttu-id="d5ba0-117">Se lleva a cabo mediante los pasos lógicos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5ba0-117">This is done in the following logical steps:</span></span>  
  
1.  <span data-ttu-id="d5ba0-118">Compare el nombre de la operación actual con "Receive" e inserte el resultado (True o False) en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-118">Compare the current operation name to "Receive" and push the result (true or false) onto the stack.</span></span>  
  
2.  <span data-ttu-id="d5ba0-119">Compare el punto de llamada de contrato de servicio con "ServiceRequest" e inserte el resultado (True o False) en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-119">Compare the current service contract call point to "ServiceRequest" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="d5ba0-120">Ahora hay dos valores booleanos en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-120">There are now two Boolean values on the stack.</span></span>  
  
3.  <span data-ttu-id="d5ba0-121">Comparar los resultados de los pasos anteriores con un valor booleano **y** operación e inserte el resultado en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-121">Compare the results of the preceding steps using a Boolean **And** operation and push the result on the stack.</span></span> <span data-ttu-id="d5ba0-122">Esto deja un valor booleano en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-122">This leaves one Boolean value on the stack.</span></span>  
  
4.  <span data-ttu-id="d5ba0-123">Compare el extremo actual con "PurchaseOrder_EP" e inserte el resultado (True o False) en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-123">Compare the current endpoint to "PurchaseOrder_EP" and push the result (true or false) onto the stack.</span></span> <span data-ttu-id="d5ba0-124">Ahora hay dos valores booleanos en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-124">There are now two Boolean values on the stack.</span></span>  
  
5.  <span data-ttu-id="d5ba0-125">Por último, compare los dos valores booleanos de la pila mediante un valor booleano **y** operación e inserte el resultado en la pila.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-125">Finally, compare the two Boolean values on the stack using a Boolean **And** operation and push the result onto the stack.</span></span> <span data-ttu-id="d5ba0-126">De este modo, se comprueba el resultado de la comparación del extremo con un valor booleano, cuyo valor es True si el nombre de la operación y el punto de llamada de contrato coinciden correctamente y que, en caso contrario, será False.</span><span class="sxs-lookup"><span data-stu-id="d5ba0-126">This checks the result of the endpoint comparison against a Boolean value, which is true if the operation name and contract call point successfully matched, and which is false otherwise.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5ba0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5ba0-127">See Also</span></span>  
 [<span data-ttu-id="d5ba0-128">Operaciones en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d5ba0-128">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)