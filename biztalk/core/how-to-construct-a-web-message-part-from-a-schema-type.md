---
title: Cómo construir una parte de mensaje Web desde un tipo de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8fd01e67309387749e7e512eca84bdb0f83db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984797"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a>Cómo construir una parte de mensaje Web a partir de un tipo de esquema
Crear una parte de mensaje Web desde un tipo de esquema mediante el uso de un **transformar** forma. Como alternativa, puede crear una parte de mensaje Web a partir de un tipo de esquema mediante la utilización de una clase .NET auxiliar para establecer las partes. Para obtener más información sobre cómo crear tipos de mensajes mediante el uso de una clase. NET, consulte [construir mensajes en código de usuario](../core/constructing-messages-in-user-code.md).  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a>Para construir una parte de mensaje Web a partir de un tipo de esquema  
  
1. Agregue una nueva asignación. Para obtener información sobre la creación de mapas, vea [cómo crear asignaciones nuevas](../core/how-to-create-new-maps.md).  
  
2. En el asignador de BizTalk, haga clic en **Abrir esquema de destino** en el **esquema de destino** panel del mapa y, en el **selector de tipos de BizTalk** cuadro de diálogo, expanda el  **Esquemas** nodo, seleccione el esquema para la referencia Web agregada y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  El formato del esquema de referencia Web es  **\<espacio de nombres predeterminado del proyecto\>.\< Nombre de referencia Web\>. Referencia**.  
  
3. En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione un nodo raíz para el esquema de destino y, a continuación, haga clic en **Aceptar**. Para obtener más información sobre cómo determinar un nodo raíz para un tipo de parte de mensaje Web, consulte [cómo determinar un tipo de parte de mensaje Web](../core/how-to-determine-a-web-message-part-type.md).  
  
4. Haga clic en **Abrir esquema de origen** en el **esquema de origen** panel del mapa y, en el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo, seleccione el esquema de origen para asignar datos de y, a continuación, haga clic en **Aceptar**.  
  
5. En el Asignador de BizTalk, cree vínculos entre el esquema de origen y el de destino.  
  
6. Abra una orquestación existente (o cree una nueva orquestación), abra el **cuadro de herramientas**y haga clic en el **orquestaciones de BizTalk** ficha.  
  
7. Arrastre un **construir mensaje** forma a la orquestación.  
  
8. Editar el **mensaje construido** propiedad debe incluir el mensaje de instancia que ha creado para el tipo de mensaje Web.  
  
9. Arrastre un **transformar** dar forma a la **construir mensaje** dar forma y haga doble clic para abrir el **configuración de transformación** cuadro de diálogo.  
  
10. Haga clic en el **mapa existente** botón y seleccione la asignación que creó en el paso uno en el **nombre completo de asignación** cuadro de lista.  
  
11. En el **transformar** panel, seleccione **origen**. En el **transformación del origen** panel, seleccione la instancia de un mensaje válido en el cuadro de lista.  
  
12. En el **transformar** panel, seleccione **destino**. En el **transformación de destino** panel, seleccione el mensaje Web de instancia en el cuadro de lista y, a continuación, haga clic en **Aceptar**.  
  
    Para obtener más información sobre el uso de la **configuración de transformación** cuadro de diálogo, vea [cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md).  
  
    También puede usar este procedimiento para asignar la instancia de mensaje de respuesta del método Web a otra instancia de mensaje Web.  
  
## <a name="see-also"></a>Vea también  
 [Construcción de mensajes web](../core/constructing-web-messages.md)