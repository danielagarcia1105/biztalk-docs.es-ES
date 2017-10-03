---
title: "Cómo agregar un Message2 error | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a>Cómo agregar un mensaje de error
Al crear un puerto en el sistema de servidor, contiene una solicitud y una respuesta. Debe agregar un mensaje de forma que pueda asignarlo al error.  
  
### <a name="to-add-a-fault-message"></a>Para agregar un mensaje de error  
  
1.  En el **Vista orquestación** ventana, haga clic en **mensajes**y seleccione **nuevo mensaje**.  
  
     De este modo, se crea Message_3, que puede asignar específicamente al error.  
  
2.  Haga clic en Message_3 y seleccione **propiedades**.  
  
3.  En el **propiedades** cuadro de diálogo, establezca la **tipo de mensaje**.  
  
     Seleccione **clases .NET** y, a continuación, seleccione **SystemString**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling3.md)