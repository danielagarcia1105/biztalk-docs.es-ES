---
title: GetOperationName | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e22020add39840b0d2fe4c2fd88156321a18c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246140"
---
# <a name="getoperationname"></a><span data-ttu-id="695bc-102">GetOperationName (operación)</span><span class="sxs-lookup"><span data-stu-id="695bc-102">GetOperationName</span></span>
<span data-ttu-id="695bc-103">Inserta el nombre de la operación en curso en la pila.</span><span class="sxs-lookup"><span data-stu-id="695bc-103">Pushes the name of the current operation onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="695bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="695bc-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="695bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="695bc-105">Parameters</span></span>  
 <span data-ttu-id="695bc-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="695bc-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="695bc-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="695bc-107">Pushed Value</span></span>  
 <span data-ttu-id="695bc-108">Cadena que contiene el nombre de la operación actual.</span><span class="sxs-lookup"><span data-stu-id="695bc-108">String containing the name of the current operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="695bc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="695bc-109">Remarks</span></span>  
 <span data-ttu-id="695bc-110">Cuando use GetOperationName, asegúrese de que compara el nombre de la operación cuando la aplicación la invoca.</span><span class="sxs-lookup"><span data-stu-id="695bc-110">When using GetOperationName, make sure you compare the operation name as it is invoked by your application.</span></span> <span data-ttu-id="695bc-111">Por ejemplo, si usa el atributo de nombre en un contrato de servicio para asignar un nombre personalizado, el cliente tendrá su proxy predeterminado generado con el nombre personalizado para el método.</span><span class="sxs-lookup"><span data-stu-id="695bc-111">For example, if you use the name attribute on a service contract to assign a custom name, the client will have its default proxy generated with the custom name for the method.</span></span> <span data-ttu-id="695bc-112">Sin embargo, la aplicación del servidor utilizará los nombres reales de métodos para las operaciones correspondientes y no el que se especifique en el atributo de nombre.</span><span class="sxs-lookup"><span data-stu-id="695bc-112">However, the server application will use the actual method names for the corresponding operations and not the one specified in the name attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="695bc-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="695bc-113">Example</span></span>  
 <span data-ttu-id="695bc-114">En el siguiente ejemplo, `GetOperationName` se usa para crear una expresión que filtra la operación denominada "AuthorizePayment".</span><span class="sxs-lookup"><span data-stu-id="695bc-114">In the following sample, `GetOperationName` is used to build an expression that filters for the operation named "AuthorizePayment".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="695bc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="695bc-115">See Also</span></span>  
 [<span data-ttu-id="695bc-116">Operaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="695bc-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)