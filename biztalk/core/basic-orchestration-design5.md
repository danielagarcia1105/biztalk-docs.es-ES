---
title: "Orquestación básica Design5 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, design
- exception handling, orchestration design
ms.assetid: 0941d617-e30c-4ca7-852f-193e16781ca7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b8e507fc9319a2a4b66006914b3ebc27a8421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>Diseño de orquestación básica
Cuando crea una orquestación básica en el adaptador de BizTalk para PeopleSoft Enterprise, recibe un XML en el puerto de recepción de su orquestación. El código XML, a continuación, se envía al sistema back-end para procesarse. En el sistema back-end, podría producirse una excepción que detiene la orquestación y genere un error. El error que se produce proporciona información de que no se ha completado la orquestación. Esto no es de gran utilidad en la depuración de la causa del error.  
  
 ![](../core/media/siebeladapter-15-exceptionhandling-start.gif "SiebelAdapter_15_ExceptionHandling_Start")  
Control de excepciones  
  
 Cuando se produce un error, se suspende la llamada. En el registro de auditoría, la llamada se establece en Error. Cuando hace clic con el botón secundario en Error en el registro de auditoría, se abre un mensaje emergente en la llamada que contenga el error. Cuando haga clic en la selección de informes, se muestra el error y el motivo de éste en el sistema de servidor.  
  
 Para evitar que la orquestación entre en un estado de suspensión y redirija el error, puede crear una CatchExpression. Para interceptar la excepción que genera el servidor y ayudar a la identificación del motivo del error, puede utilizar la forma Ámbito en su orquestación.  
  
 ![](../core/media/siebeladapter-16-exceptionhandling-total.gif "SiebelAdapter_16_ExceptionHandling_Total")  
Total de control de excepciones  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling2.md)