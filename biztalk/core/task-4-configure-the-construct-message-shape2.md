---
title: 'Tarea 4: Configurar el Shape2 mensaje construcción | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c9e667248150a705841d0947bfb0cb3799a516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012701"
---
# <a name="task-4-configure-the-construct-message-shape"></a>Tarea 4: Configurar la forma construir mensaje
Las formas Construir mensaje contienen asignaciones de mensajes con las instrucciones para el código Begin, Edit y End Doc.  
  
 Utilice este procedimiento para configurar la forma Construir mensaje.  
  
### <a name="to-configure-the-construct-message-shape"></a>Para configurar la forma Construir mensaje  
  
1. Arrastre una forma Construir mensaje entre ReceiveBeginDoc y SendBeginDoc.  
  
   -   **Mensajes construidos:** BeginDocSessionMsg  
  
   -   **Nombre:** ConstructBeginDocMessageWithSession  
  
   1.  Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.  
  
   2.  Haga doble clic en la forma MessageAssignment_1 interna.  
  
        Aparecerá el Editor de expresiones de BizTalk.  
  
   3.  Escriba su código, por ejemplo:  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    Esto indica al adaptador que desea iniciar una sesión. SessionID se inicializa como 0 pero cuando vuelve la respuesta el J.D. asignará el Id. Servidor de Edwards OneWorld.  
  
    ![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")  
  
2. Arrastre una forma Construir mensaje delante de SendEditLine.  
  
   - **Mensajes construidos:** EditLineSessionMsg  
  
   - **Nombre:** ConstructEditLineMessageWithSession  
  
     ![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")  
  
   1.  Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.  
  
   2.  Haga doble clic en la forma MessageAssignment_1 interna.  
  
        Aparecerá el Editor de expresiones de BizTalk.  
  
   3.  Escriba su código, por ejemplo:  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    ![](../core/media/jde-editline-editor.gif "JDE_editline_editor")  
  
3. Arrastre una forma Construir mensaje delante de SendEndDoc.  
  
   -   **Mensajes construidos:** EndDocSessionMsg  
  
   -   **Nombre:** ConstructEndDocMessageWithSession  
  
   1.  Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.  
  
   2.  Haga doble clic en la forma MessageAssignment_1 interna.  
  
        Aparecerá el Editor de expresiones de BizTalk.  
  
   3.  Escriba su código, por ejemplo:  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a>Vea también  
 [Tarea 1: Creación de los puertos](../core/task-1-create-the-ports2.md)   
 [Tarea 2: Creación de los mensajes](../core/task-2-create-the-messages1.md)   
 [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [Tarea 5: Configurar la forma Transformación](../core/task-5-configure-the-transform-shape1.md)