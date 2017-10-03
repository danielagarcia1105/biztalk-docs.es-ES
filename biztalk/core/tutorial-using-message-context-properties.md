---
title: 'Tutorial: Usar propiedades de contexto de mensaje | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, changing priority
- message context properties, tutorial
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122215baa5660294e159e4f1d6967a2df5ba9b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-message-context-properties"></a>Tutorial: Usar propiedades de contexto de mensaje
En este tutorial se muestra cómo usar las propiedades de contexto de BizTalk Server para establecer los campos de descriptor de mensajes de TIBCO Enterprise Message Service (EMS) en la orquestación. El tutorial supone que dispone de una orquestación que recibe un mensaje de un puerto de recepción y lo envía a un puerto de envío enlazado al adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service.  
  
 En el siguiente procedimiento se muestra cómo cambiar la prioridad del mensaje de TIBCO EMS mediante el cambio del valor de la propiedad de contexto TibcoEMS.Priority. En BizTalk Server, los mensajes son inmutables. Por lo tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje. Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción. No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades TIBCO EMS.  
  
### <a name="to-reference-the-schema-dll"></a>Para hacer referencia al esquema DLL  
  
1.  Abra **el Explorador de soluciones** en Visual Studio.  
  
2.  Haga clic en **referencias**y seleccione **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
3.  Haga clic en el **examinar** ficha.  
  
     El **Seleccionar componente** aparece el cuadro de diálogo.  
  
4.  Busque  **\<EMS_Adapter_installation_directory TIBCO > \bin**y, a continuación, seleccione **Microsoft.Adapters.TibcoEMSProperties.dll**.  
  
5.  Haga clic en **Abrir**.  
  
     El archivo DLL aparece en la **componentes seleccionados** en el **Agregar referencia** cuadro de diálogo.  
  
6.  Haga clic en **Aceptar** y, a continuación, haga doble clic en la orquestación para obtener acceso al diseñador de orquestaciones.  
  
7.  En el **vista** menú, elija **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
8.  En la Vista orquestación, haga clic en **mensajes** y seleccione **nuevo mensaje**.  
  
9. Editar las propiedades de mensaje nuevo y asignar un **tipo de mensaje**.  
  
     Asignará Message_1 a Message_2. Por lo tanto, se debe asignar el mismo tipo de mensaje a ambos mensajes.  
  
10. En el menú **Ver** , haga clic en **Cuadro de herramientas**.  
  
11. Arrastre un **asignación de mensajes** forma en la orquestación donde desea crear un nuevo mensaje.  
  
12. Modifique la forma ConstructMessage_1 externa y seleccione el nuevo mensaje, Message_2, en la **mensajes construidos** propiedad.  
  
13. Haga doble clic en la forma MessageAssignment_1 interna.  
  
     Aparecerá el Editor de expresiones de BizTalk.  
  
14. En el Editor de expresiones de BizTalk, escriba el código.  
  
15. En primer lugar, copie un mensaje existente y asigne los valores a las propiedades de contexto de mensaje.  
  
     La sintaxis es `Message(property) = value;`. Por ejemplo:  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     Vea TIBCO EMS para obtener una lista de propiedades admitidas que puede usar en el mensaje personalizado.  
  
16. Haga clic en **Aceptar** para cerrar el Editor de expresiones de BizTalk y guarde el código.  
  
17. Haga clic en la forma envío y asignar el **mensaje** como **Message_2**.  
  
18. Compruebe que las formas del flujo de mensajes restantes funcionan en el mensaje correspondiente.  
  
19. Haga clic en el proyecto en el Explorador de soluciones y seleccione **generar**.  
  
20. Haga clic en el proyecto y seleccione **implementar**.  
  
21. Seleccione **enlazar**, **dar de alta**, y **iniciar** en el Explorador de BizTalk para probar su orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de contexto de mensaje](../core/message-context-properties2.md)