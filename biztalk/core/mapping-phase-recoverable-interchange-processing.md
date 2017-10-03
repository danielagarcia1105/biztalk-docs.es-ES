---
title: "Asignación de fase (procesamiento de intercambio recuperable) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 544d85c7-bc47-46c1-8990-82b48a8f2f23
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b3e45cf337702457dc8e5986db54df6bea5e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-phase-recoverable-interchange-processing"></a><span data-ttu-id="214cc-102">Asignación de fase (procesamiento de intercambio recuperable)</span><span class="sxs-lookup"><span data-stu-id="214cc-102">Mapping Phase (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="214cc-103">De forma predeterminada, cuando un mensaje de un intercambio falla en la fase de asignación de un puerto de recepción, se suspende todo el intercambio.</span><span class="sxs-lookup"><span data-stu-id="214cc-103">By default, when a message in an interchange fails at the mapping phase of a receive port, the entire interchange is suspended.</span></span> <span data-ttu-id="214cc-104">Puede cambiar este comportamiento mediante la adición de una propiedad denominada **BTS. SuspendMessageOnMapFailure** en el contexto del mensaje y estableciendo el valor de la propiedad de contexto `True` desde un componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="214cc-104">You can change this behavior by adding a property named **BTS.SuspendMessageOnMapFailure** to the message context, and by setting the value of the context property to `True` from a pipeline component.</span></span> <span data-ttu-id="214cc-105">Cuando esta propiedad está configurada en `True`, el administrador del extremo coloca el mensaje que falló durante la asignación en la cola de suspensión y continúa procesando los demás mensajes del intercambio.</span><span class="sxs-lookup"><span data-stu-id="214cc-105">When this property is set to `True`, the end point manager places the message that failed during mapping in the suspended queue and continues to process remaining messages in the interchange.</span></span>  
  
 <span data-ttu-id="214cc-106">El código siguiente establece el valor de la **SuspendMessageOnFailure** propiedad en True.</span><span class="sxs-lookup"><span data-stu-id="214cc-106">The following code sets the value of the **SuspendMessageOnFailure** property to True.</span></span>  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```