---
title: "Cómo copiar los datos en el contexto del mensaje como campos distintivos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 004a13ca-a162-4a5e-9f72-8a5c55bbb7a6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea68bc0b83c5a8f886416107e1dc98ea8ad8d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-data-to-the-message-context-as-distinguished-fields"></a>Cómo copiar los datos en el contexto del mensaje como campos distintivos
Este tema proporciona instrucciones paso a paso para promocionar una propiedad como un **campo distintivo**.  
  
 Puede elegir **campo distintivo** promoción sobre **campo de propiedad** promoción por las razones siguientes:  
  
-   **Campo de propiedad** valores se limitan a 255 caracteres de longitud.  
  
-   **Campo de propiedad** valores se almacenan en una base de datos y, por tanto, tienen más sobrecarga que **campos distintivos**. **Campos distintivos** no requieren ningún almacenamiento adicional; son básicamente un alias para una **XPath**, lo cual permite, por tanto, las orquestaciones más acceder fácilmente a los valores relevantes directamente desde el mensaje.  
  
### <a name="to-promote-a-property-as-a-distinguished-field"></a>Para promocionar una propiedad como un campo distintivo  
  
1.  En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo distintivo**.  
  
    > [!NOTE]
    >  Los nodos registro nunca se pueden promocionar como **campos distintivos**, independientemente del tipo de contenido que incluyan.  
  
2.  Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **mostrar promociones**.  
  
     El **promocionar propiedades** abre el cuadro de diálogo con la muestra el nodo seleccionado en el árbol de esquema en el lado izquierdo del cuadro de diálogo.  
  
3.  En el **promocionar propiedades** cuadro de diálogo, seleccione la **campos distintivos** ficha.  
  
4.  Con el nodo para promocionar todavía seleccionado en el árbol de esquema en el lado izquierdo de la **promocionar propiedades** cuadro de diálogo, haga clic en **agregar**.  
  
     Si se permite, el nodo seleccionado se agrega a la lista en la **campos distintivos** ficha. En caso de no permitirse, un cuadro de mensajes proporciona una explicación.  
  
5.  Puede seleccionar nodos adicionales para promocionarlos en el árbol de esquema en el lado izquierdo del cuadro de diálogo, haga clic en **agregar** después de cada selección.  
  
6.  Cuando haya terminado, haga clic en **Aceptar**.  
  
     Los nodos seleccionados para promocionar son ahora **campos distintivos**.  
  
## <a name="see-also"></a>Vea también  
 [Promoción de propiedades](../core/promoting-properties.md)   
 [Cómo crear esquemas de propiedades](../core/how-to-create-property-schemas.md)   
 [Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md)