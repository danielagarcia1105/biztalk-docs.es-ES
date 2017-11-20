---
title: "Cómo registrar información de seguimiento al archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, tracking
- DebugTrackingInterceptor
- Business Rules Framework, code samples
ms.assetid: c832b763-aa08-4a0e-9086-776dccb0a6ef
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cdaae8e727cedc784ecaade83178cf50f863f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-tracking-information-to-file"></a><span data-ttu-id="a9381-102">Cómo registrar información de seguimiento en el archivo</span><span class="sxs-lookup"><span data-stu-id="a9381-102">How to Log Tracking Information to File</span></span>
<span data-ttu-id="a9381-103">Cuando se ejecuta el motor de reglas de negocios, pasa la información de seguimiento de la ejecución a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="a9381-103">When the Business Rule Engine executes, it passes execution tracking information to an interceptor.</span></span> <span data-ttu-id="a9381-104">El motor está configurado para usar el interceptor de BizTalk que se usa cuando se supervisan datos de eventos de mensajes e instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="a9381-104">The engine is configured to use the BizTalk interceptor which is used when tracking message events and service instance data.</span></span> <span data-ttu-id="a9381-105">Si está llamando al motor fuera de la orquestación de BizTalk, puede pasar el interceptor que desee utilizar cuando ejecute la directiva.</span><span class="sxs-lookup"><span data-stu-id="a9381-105">If you are calling the engine outside of BizTalk orchestration, you can pass the interceptor you want to use when you execute the policy.</span></span> <span data-ttu-id="a9381-106">Además del interceptor de BizTalk, también puede usar el **DebugTrackingInterceptor** a la información de seguimiento al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a9381-106">In addition to the BizTalk interceptor, you can also use the **DebugTrackingInterceptor** to output the tracking information to file.</span></span> <span data-ttu-id="a9381-107">En el ejemplo de código siguiente se muestra cómo utilizar **DebugTrackingInterceptor**.</span><span class="sxs-lookup"><span data-stu-id="a9381-107">The following code example demonstrates how to use **DebugTrackingInterceptor**.</span></span>  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```