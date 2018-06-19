---
title: CorrelationID | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1192de4a49c300220ce0b297bbc1ee02ce64c6dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237772"
---
# <a name="correlationid"></a><span data-ttu-id="b5978-102">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="b5978-102">CorrelationID</span></span>
<span data-ttu-id="b5978-103">El elemento `CorrelationID` se usa para especificar un Id. de correlación para un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b5978-103">The `CorrelationID` element is used to specify a correlation ID for a message.</span></span>  
  
## <a name="format"></a><span data-ttu-id="b5978-104">Formato</span><span class="sxs-lookup"><span data-stu-id="b5978-104">Format</span></span>  
 <span data-ttu-id="b5978-105">El elemento `CorrelationID` se compone de un elemento `Expression` que usa uno o más elementos `Operation` para especificar la cadena que se debe usar como Id. de correlación.</span><span class="sxs-lookup"><span data-stu-id="b5978-105">The `CorrelationID` element consists of an `Expression` element that uses one or more `Operation` elements to specify the string to use as the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5978-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5978-106">Remarks</span></span>  
 <span data-ttu-id="b5978-107">En expresiones de Id. de correlación, no se permiten las operaciones comunes siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5978-107">The following common operations are not allowed in correlation ID expressions:</span></span>  
  
-   <span data-ttu-id="b5978-108">And</span><span class="sxs-lookup"><span data-stu-id="b5978-108">And</span></span>  
  
-   <span data-ttu-id="b5978-109">Es igual a</span><span class="sxs-lookup"><span data-stu-id="b5978-109">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5978-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5978-110">Example</span></span>  
 <span data-ttu-id="b5978-111">El bloque de configuración del ejemplo del interceptor de Workflow Foundation (WF) siguiente usa "OrderNum" para establecer un Id. de correlación.</span><span class="sxs-lookup"><span data-stu-id="b5978-111">The following Workflow Foundation (WF) interceptor sample configuration block uses "OrderNum" to establish a correlation ID.</span></span> <span data-ttu-id="b5978-112">Mediante WF y las operaciones comunes, se pueden generar expresiones sofisticadas para construir un Id. de correlación adecuado para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5978-112">Using the WF and common operations, you can build sophisticated expressions to construct an appropriate correlation ID for your workflow.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="b5978-113">En el caso de aplicaciones de Windows Communication Foundation (WCF), se pueden usar operaciones comunes y específicas de WCF para construir un Id. de correlación.</span><span class="sxs-lookup"><span data-stu-id="b5978-113">For Windows Communication Foundation (WCF) applications, you can use WCF-specific and common operations to construct a correlation ID.</span></span> <span data-ttu-id="b5978-114">El siguiente ejemplo se utiliza la **XPath** operación y XPath para recuperar un número de tarjeta de crédito de un mensaje para su uso como un identificador de correlación:</span><span class="sxs-lookup"><span data-stu-id="b5978-114">The following sample uses the **XPath** operation and XPath to retrieve a credit card number from a message for use as a correlation ID:</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5978-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5978-115">See Also</span></span>  
 [<span data-ttu-id="b5978-116">Elemento OnEvent del interceptor</span><span class="sxs-lookup"><span data-stu-id="b5978-116">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)