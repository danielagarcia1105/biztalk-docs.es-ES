---
title: "Orquestación básica Design3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, design
ms.assetid: c1df6d0e-51cf-4728-8d55-60eff21611b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9823c2ab9221e9348ef891ab4ceb19a732ffbcbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>Diseño de orquestación básica
Cuando crea una orquestación básica, recibe un XML en el puerto de recepción de la orquestación. El XML se envía al sistema back-end para que se procese. En el sistema back-end se puede producir una excepción que detenga la orquestación. La excepción que se produce proporciona información de que no se ha completado la orquestación.  
  
 Cuando se produce un error, se suspende la llamada. En el registro del visor de eventos, puede ver el error y el motivo correspondiente.  
  
 Para evitar que la orquestación entre en un estado de suspensión y redirija el error, puede crear una CatchExpression. Para capturar la excepción que genera el back-end y ayudar a la identificación del motivo del problema, puede usar la forma Ámbito en la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling5.md)