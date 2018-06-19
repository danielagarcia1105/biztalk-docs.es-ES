---
title: AutoGenerateCorrelationToken | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e396fd0b2c6153a5252d336b9af9c22bf9421fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230260"
---
# <a name="autogeneratecorrelationtoken"></a><span data-ttu-id="b8a9f-102">AutoGenerateCorrelationToken (operación)</span><span class="sxs-lookup"><span data-stu-id="b8a9f-102">AutoGenerateCorrelationToken</span></span>
<span data-ttu-id="b8a9f-103">Genera automáticamente un token de correlación y lo coloca en la pila.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-103">Automatically generates a correlation token and places it onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8a9f-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8a9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8a9f-105">Parameters</span></span>  
 <span data-ttu-id="b8a9f-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b8a9f-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="b8a9f-107">Pushed Value</span></span>  
 <span data-ttu-id="b8a9f-108">Cadena que contiene el token de correlación.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-108">String containing the correlation token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a9f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8a9f-109">Remarks</span></span>  
 <span data-ttu-id="b8a9f-110">Esta operación se puede usar cuando no hay ningún token de correlación presente en el mensaje, pero se sigue queriendo correlacionar la información procedente de una solicitud y una respuesta.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-110">This operation can be used when there is no correlation token present in the message but you still want to correlate the information from a request and a reply.</span></span> <span data-ttu-id="b8a9f-111">Puede emplearse para correlacionar una solicitud/respuesta concreta en el cliente o en el servicio.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-111">It can be used to correlate a particular request/reply on either the client or the service side.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8a9f-112">Si se quieren correlacionar los datos recopilados por la solicitud y la respuesta para el cliente y el servicio (a continuación), habrá que usar un elemento o elementos de datos procedentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-112">If you want to correlate the data gathered by the request and the reply for both the client and the service (a continuation), you will need to use a data element or elements from your message.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a9f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8a9f-113">Example</span></span>  
 <span data-ttu-id="b8a9f-114">La expresión de correlación del ejemplo siguiente se basa en `AutoGenerateCorrelationToken` para generar un token de correlación.</span><span class="sxs-lookup"><span data-stu-id="b8a9f-114">The following example correlation expression relies on the `AutoGenerateCorrelationToken` to generate a correlation token.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8a9f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a9f-115">See Also</span></span>  
 [<span data-ttu-id="b8a9f-116">Operaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b8a9f-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)