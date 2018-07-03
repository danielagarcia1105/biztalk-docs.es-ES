---
title: Cómo agregar un mensaje para un Exception2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57cd4e3e0cdcfe34dd172282ef83768eb63b93fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000805"
---
# <a name="how-to-add-a-message-for-an-exception"></a>Cómo agregar un mensaje para una excepción
La primera vez que crea un puerto en el sistema de servidor, contiene una solicitud y una respuesta. Debe agregar un mensaje de forma que pueda asignarlo al error.  
  
### <a name="to-add-a-fault-message"></a>Para agregar un mensaje de error  
  
1. En el **Vista orquestación** ventana, haga clic en **mensajes**y, a continuación, seleccione **nuevo mensaje**.  
  
    De este modo, se crea Message_3, que puede asignar específicamente al error.  
  
2. Haga clic en **Message_3**y seleccione **propiedades**.  
  
3. Establecer el **tipo de mensaje** como sigue: seleccione **clases .NET**y, a continuación, seleccione **del sistema, cadena**  
  
   ![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")  
  
## <a name="see-also"></a>Vea también  
 [Uso del control de excepciones de BizTalk Server](../core/using-biztalk-server-exception-handling1.md)