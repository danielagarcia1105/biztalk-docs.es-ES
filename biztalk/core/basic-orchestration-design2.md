---
title: "Orquestación básica Design2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, design
ms.assetid: fcdcb232-6a8f-41f3-b863-3b9e2cda28e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 713d37d2736b8fac4563b098572dd9e49a3fd634
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>Diseño de orquestación básica
Cuando crea una orquestación básica, recibe un XML en el puerto de recepción de la orquestación. El XML se envía al sistema back-end para que se procese. En el sistema back-end, podría producirse una excepción que pudo detener la orquestación. La excepción que se produce proporciona información de que no se ha completado la orquestación.  
  
 Cuando se produce un error, se suspende la llamada. En el registro del visor de eventos, puede ver el error y el motivo correspondiente.  
  
 Para evitar que la orquestación entre en un estado de suspensión y redirija el error, puede crear una CatchExpression. Para capturar la excepción que genera el back-end y ayudar a la identificación del motivo del problema, puede usar la forma Ámbito en la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling3.md)