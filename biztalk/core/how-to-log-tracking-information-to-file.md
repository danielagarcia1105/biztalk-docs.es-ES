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
# <a name="how-to-log-tracking-information-to-file"></a>Cómo registrar información de seguimiento en el archivo
Cuando se ejecuta el motor de reglas de negocios, pasa la información de seguimiento de la ejecución a un interceptor. El motor está configurado para usar el interceptor de BizTalk que se usa cuando se supervisan datos de eventos de mensajes e instancias de servicio. Si está llamando al motor fuera de la orquestación de BizTalk, puede pasar el interceptor que desee utilizar cuando ejecute la directiva. Además del interceptor de BizTalk, también puede usar el **DebugTrackingInterceptor** a la información de seguimiento al archivo de salida. En el ejemplo de código siguiente se muestra cómo utilizar **DebugTrackingInterceptor**.  
  
```  
DebugTrackingInterceptor tracker = new DebugTrackingInterceptor("TrackingOutput.txt");  
policy.Execute(shortTermFacts,tracker);  
```