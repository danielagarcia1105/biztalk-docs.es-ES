---
title: ContinuationToken | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0d36737ddd16e34ecfe4680c7660e16c99f676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001869"
---
# <a name="continuationtoken"></a><span data-ttu-id="09355-102">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="09355-102">ContinuationToken</span></span>
<span data-ttu-id="09355-103">Un token de continuación se usa para correlacionar información heterogénea dentro de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="09355-103">A continuation token is used to correlate heterogeneous information within the BAM infrastructure.</span></span> <span data-ttu-id="09355-104">Considere un proceso empresarial que construye los siguientes tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="09355-104">Consider a business process that constructs the following types of messages:</span></span>  
  
- <span data-ttu-id="09355-105">Pedido de compra identificado por un número de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="09355-105">Purchase order identified by a purchase order number</span></span>  
  
- <span data-ttu-id="09355-106">Pedido de venta identificado por un número de pedido de venta</span><span class="sxs-lookup"><span data-stu-id="09355-106">Sales order identified by a sales order number</span></span>  
  
- <span data-ttu-id="09355-107">Pedido de envío identificado por un número de pedido de envío</span><span class="sxs-lookup"><span data-stu-id="09355-107">Shipping order identified by a shipping order number</span></span>  
  
  <span data-ttu-id="09355-108">En este proceso, hay tres identificadores importantes: Id. de pedido, Id. de pedido de ventas y trasvase de registros de Id. de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="09355-108">In this process, there are three important identifiers: purchase order ID, sales order ID and shipping order ID.</span></span> <span data-ttu-id="09355-109">Cada uno de estos identificadores señalan un evento importante en el período de vida del pedido original, pero no pueden correlacionarse directamente.</span><span class="sxs-lookup"><span data-stu-id="09355-109">Each of these identifiers signals an important event in the lifetime of the original order, but they cannot be directly correlated.</span></span> <span data-ttu-id="09355-110">Para realizar un seguimiento de los eventos relacionados con un pedido de compra, la información común entre los mensajes debe identificarse para ayudar a la infraestructura de seguimiento de BAM a correlacionar de forma precisa los eventos.</span><span class="sxs-lookup"><span data-stu-id="09355-110">To track events related to a purchase order, the information that is common between the messages must be identified to help the BAM tracking infrastructure accurately correlate the events.</span></span>  
  
## <a name="format"></a><span data-ttu-id="09355-111">Formato</span><span class="sxs-lookup"><span data-stu-id="09355-111">Format</span></span>  
 <span data-ttu-id="09355-112">Un token de continuación consta de un elemento de expresión y de una o varias operaciones:</span><span class="sxs-lookup"><span data-stu-id="09355-112">A continuation token consists of an expression element and one or more operations:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a><span data-ttu-id="09355-113">Notas</span><span class="sxs-lookup"><span data-stu-id="09355-113">Remarks</span></span>  
 <span data-ttu-id="09355-114">En expresiones de ContinuationToken, no se permiten las operaciones comunes siguientes:</span><span class="sxs-lookup"><span data-stu-id="09355-114">The following common operations are not allowed in ContinuationToken expressions:</span></span>  
  
- <span data-ttu-id="09355-115">And</span><span class="sxs-lookup"><span data-stu-id="09355-115">And</span></span>  
  
- <span data-ttu-id="09355-116">Es igual a</span><span class="sxs-lookup"><span data-stu-id="09355-116">Equals</span></span>  
  
  <span data-ttu-id="09355-117">[El encabezado de la sección de operaciones de WF/WCF debe tener gráficos similares y otros gráficos según sea necesario]</span><span class="sxs-lookup"><span data-stu-id="09355-117">[Operations section header in WF/WCF should have similar chart and other charts as needed]</span></span>  
  
## <a name="example"></a><span data-ttu-id="09355-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09355-118">Example</span></span>  
 <span data-ttu-id="09355-119">En este ejemplo, un token de continuación de un proceso de WF se recupera del flujo de trabajo mediante el uso de `GetWorkflowProperty`.</span><span class="sxs-lookup"><span data-stu-id="09355-119">In this example, a continuation token for a WF process is retrieved from the workflow by using `GetWorkflowProperty`.</span></span> <span data-ttu-id="09355-120">Aquí el programador ha decidido proporcionar asistencia para la continuación en el flujo de trabajo mediante el uso de código personalizado, probablemente porque el proceso para la determinación del token de continuación implica más de dos o tres expresiones y puede depender de los datos externos.</span><span class="sxs-lookup"><span data-stu-id="09355-120">Here the developer decided to provide support for continuation in the workflow by using custom code, probably because the process for determining the continuation token involves more than two or three expressions and may rely on external data.</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 <span data-ttu-id="09355-121">Puede elegir proporcionar funcionalidades similares en sus nuevas aplicaciones WF o WCF, o bien, si el token es fácil de establecer mediante el uso de operaciones de expresiones, puede evitar escribir el código adicional.</span><span class="sxs-lookup"><span data-stu-id="09355-121">You may choose to provide similar functionality in your new WF or WCF applications or, if the token is easy to establish using expression operations, you can avoid writing additional code.</span></span>  
  
 <span data-ttu-id="09355-122">El siguiente ejemplo establece un token de continuación para un proceso WCF mediante el uso de un **XPath** operación para recuperar el número de tarjeta de crédito del mensaje actual y el **constante** y  **concatenar** operaciones para anteponer la cadena "CID_" al número recuperado:</span><span class="sxs-lookup"><span data-stu-id="09355-122">The following example establishes a continuation token for a WCF process by using an **XPath** operation to retrieve the credit card number from the current message and the **constant** and **concatenate** operations to prepend the string "CID_" to the retrieved number:</span></span>  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09355-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="09355-123">See Also</span></span>  
 [<span data-ttu-id="09355-124">Elemento OnEvent del interceptor</span><span class="sxs-lookup"><span data-stu-id="09355-124">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)