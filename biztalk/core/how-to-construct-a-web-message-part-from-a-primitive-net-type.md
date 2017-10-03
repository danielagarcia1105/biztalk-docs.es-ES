---
title: "Cómo construir una parte de mensaje Web desde un tipo .NET primitivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a>Cómo construir una parte de mensaje web a partir de un tipo .NET primitivo
Crear una parte de mensaje Web desde un tipo .NET primitivo mediante un **asignación de mensajes** forma. Como alternativa, puede crear una parte de mensaje Web a partir de un tipo .NET primitivo mediante la utilización de una clase .NET auxiliar para establecer las partes. Para obtener más información sobre cómo crear tipos de mensaje mediante una clase. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a>Para construir una parte de mensaje Web a partir de un tipo .NET primitivo  
  
1.  Con una orquestación abierta, abra el **cuadro de herramientas** y haga clic en el **orquestaciones de BizTalk** ficha.  
  
2.  Arrastre un **construir mensaje** forma a la orquestación.  
  
3.  Editar la **construir mensaje** propiedad para incluir la instancia de mensaje que ha creado para el tipo de mensaje Web.  
  
4.  Arrastre un **asignación de mensajes** forma en la **construir mensaje** forma.  
  
5.  Haga doble clic en el **asignación de mensajes** forma para abrir el Editor de expresiones de BizTalk.  
  
6.  Establezca las partes del tipo de mensaje Web en sus valores necesarios en la casilla Editor de expresiones de BizTalk.  
  
     Por ejemplo, el siguiente código establece la expresión en una cadena:  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Construcción de mensajes Web](../core/constructing-web-messages.md)