---
title: Procesamiento de mensajes de instancia con campos distintivos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4dca22ff1b09a0d1cfb261a9d5726da8b1b17b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-processing-using-distinguished-fields"></a>Procesar mensajes de instancia con campos distintivos
Promocionar propiedades mediante la **campo distintivo** mecanismo no requiere la creación de un esquema de propiedad. Como con la promoción de propiedades, use el **promocionar propiedades** cuadro de diálogo, que es accesible mediante la **promocionar propiedades** propiedad de la **esquema** nodo esquemas de mensaje o mediante el **promover &#124; Mostrar promociones** comando el **BizTalk** o menús contextuales.  
  
 En el **promocionar propiedades** diálogo cuadro, asegúrese del **campos distintivos** ficha está seleccionada en el lado derecho del cuadro de diálogo. A continuación, expanda los nodos del árbol de esquema en el lado izquierdo del cuadro de diálogo para buscar y seleccionar la **elemento de campo** nodo o **atributo de campo** nodo que desea promover como campo distintivo y, a continuación, Haga clic en **agregar**. Para obtener instrucciones detalladas acerca de la promoción de propiedades para **campos distintivos** mediante la **promocionar propiedades** cuadro de diálogo, vea [copiar datos en el contexto del mensaje como completos Campos](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md).  
  
> [!NOTE]
>  También puede promocionar un **registro** nodo a un nodo de elemento de campo en el esquema de propiedades, pero solo si la **tipo de contenido** propiedad de la **registro** nodo se establece en  **SimpleContent**.  
  
 Para quitar un nodo del conjunto de propiedades que se va a promocionar como campos distintivos, seleccione la propiedad promocionada en el **campos distintivos** ficha y haga clic en **quitar**.  
  
 Si promociona las propiedades con el mecanismo de campo distintivo, se agregará un fragmento del lenguaje de definición de esquemas XML (XSD) dentro del subelemento de anotación del elemento raíz. En el siguiente ejemplo, el fragmento muestra dos propiedades promocionadas mediante el mecanismo de campo distintivo.  
  
```  
<b:properties>  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field1']" />  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field5' and position()='1']" />  
</b:properties>  
```  
  
## <a name="see-also"></a>Vea también  
 [Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [Cómo copiar los datos en el contexto del mensaje como campos distintivos](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)