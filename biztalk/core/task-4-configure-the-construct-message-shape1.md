---
title: 'Tarea 4: Configurar el forma1 de mensaje de construcción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278212"
---
# <a name="task-4-configure-the-construct-message-shape"></a>Tarea 4: Configurar la forma construir mensaje
Las formas Construir mensaje contienen asignaciones de mensajes con las instrucciones para el código Begin, Edit y End Doc.  
  
 Utilice este procedimiento para configurar la forma Construir mensaje.  
  
### <a name="to-configure-the-construct-message-shape"></a>Para configurar la forma Construir mensaje  
  
1.  Arrastre una forma Construir mensaje entre ReceiveBeginDoc y SendBeginDoc.  
  
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
  
         Esto indica al adaptador que desea iniciar una sesión. El valor de SessionID se inicializa como 0 pero cuando vuelve la respuesta se le asignará el Id. de forma el J.D. Servidor de Edwards EnterpriseOne.  
  
     ![Editor de expresiones de mensaje](../core/media/message-expression-editor.gif "message_expression_editor")  
  
2.  Arrastre una forma Construir mensaje delante de SendEditLine.  
  
    -   **Mensajes construidos:** EditLineSessionMsg  
  
    -   **Nombre:** ConstructEditLineMessageWithSession  
  
     ![Enviar Editar línea](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")  
  
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
  
     ![Editar línea Editor](../core/media/editline-editor.gif "editline_editor")  
  
3.  Arrastre una forma construir mensaje delante de SendEndDoc.  
  
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
 [Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md)   
 [Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md)   
 [Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [Tarea 5: Configurar la forma transformación](../core/task-5-configure-the-transform-shape2.md)