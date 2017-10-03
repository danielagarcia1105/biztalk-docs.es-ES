---
title: "Mensajes de instancia de valores de nodos vacíos en origen | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a36271f5e9d66efc8ef0c50cdc9582f4de1261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="empty-node-values-in-source-instance-messages"></a>Valores de nodos vacíos en mensajes de instancia de origen
En ocasiones puede que no desee tener contenido en todos los nodos de esquema cuando está comprobando una asignación.  
  
## <a name="ceate-empty-node-values"></a>Valores de cree nodos vacíos  
  
1.  Genere datos de instancia con el Editor de BizTalk. Para obtener más información acerca de la generación de datos de instancia, consulte [cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md).  
  
2.  Abra el mensaje de instancia de entrada en un editor de texto, elimine los datos de elementos y atributos que desee que estén vacíos y, a continuación, guarde el archivo de instancia modificado.  
  
3.  Configure el Asignador de BizTalk para utilizar el archivo que acaba de modificar cuando se valida y comprueba el esquema. Establezca el archivo en la ventana Propiedades para el esquema. Para obtener más información acerca de las propiedades de configuración, consulte **propiedades de archivo de mapa** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
-  [Cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md)   
-  **Referencia de esquema de propiedad**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]