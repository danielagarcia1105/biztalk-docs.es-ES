---
title: Orquestación básica Diseño1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: fd2e1d89-6230-4634-8a33-1cda26fd55f5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d302428cd713b826e7c4629ea75eb6f6268d7400
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>Diseño de orquestación básica
Cuando se crea una orquestación básica, recibe un XML en el puerto de recepción de la orquestación. El XML se envía al sistema back-end para que se procese. En el sistema de servidor, se puede producir una excepción que detenga la orquestación y genere un error. La excepción que se genera, se proporciona información que no se completó la orquestación.  
  
 ![](../core/media/jdeoneworld-01.gif "JdeOneWorld_01")  
Control de excepciones  
  
 Cuando se produce un error, se suspende la llamada. En el registro del visor de eventos, puede ver el error y el motivo correspondiente.  
  
 Para evitar que la orquestación entre en un estado de suspensión y redirija el error, puede crear una CatchExpression. Para capturar la excepción generada por el sistema back-end y para ayudar a localizar la causa del problema, puede usar el **ámbito** forma en la orquestación.  
  
 ![](../core/media/jdeoneworld-02.gif "JdeOneWorld_02")  
Total de control de excepciones  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling1.md)