---
title: 'Tutorial: Usar propiedades de contexto del mensaje TIBCO EMS | Documentos de Microsoft'
description: "Guía paso a paso para usar los campos de descriptor de mensajes de TIBCO Enterprise Message Service en la orquestación de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fafde77ad1e6edcae71d2c33a722ac63ab8e75b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a>Tutorial: Descriptores de mensaje uso TIBCO EMS

## <a name="overview"></a>Información general
En este tutorial se muestra cómo usar las propiedades de contexto de BizTalk Server para establecer los campos de descriptor de mensajes de TIBCO Enterprise Message Service (EMS) en la orquestación. El tutorial supone que dispone de una orquestación que recibe un mensaje de un puerto de recepción y lo envía a un puerto de envío enlazado al adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service.  
  
 En el siguiente procedimiento se muestra cómo cambiar la prioridad del mensaje de TIBCO EMS mediante el cambio del valor de la propiedad de contexto TibcoEMS.Priority. En BizTalk Server, los mensajes son inmutables. Por lo tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje. Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción. No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades TIBCO EMS.  
  
## <a name="reference-the-schema-dll"></a>Hacer referencia al esquema DLL  
  
1.  En Visual Studio, abra el proyecto de BizTalk Server y abra **el Explorador de soluciones** .  
  
2.  Haga clic en **referencias**y seleccione **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
3.  Haga clic en el **examinar** ficha.  
  
     El **Seleccionar componente** aparece el cuadro de diálogo.  
  
4.  Busque  **\<TIBCO EMS_Adapter_installation_directory\>\bin**y, a continuación, seleccione **Microsoft.Adapters.TibcoEMSProperties.dll**.  
  
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
[Propiedades de contexto del mensaje de TIBCO EMS](../core/message-context-properties-in-biztalk-server.md)