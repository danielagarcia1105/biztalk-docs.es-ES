---
title: Administradores de propiedades | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="property-managers"></a>Administradores de propiedades
Los administradores de propiedades permiten a una extensión agregar propiedades personalizadas (normalmente como anotaciones XSD) a los elementos y atributos de la representación XSD del esquema, así como ampliar la funcionalidad de la ventana Propiedades para incluir propiedades personalizadas asociadas con la extensión.  
  
 Un administrador de propiedades es un objeto que implementa el **IPropertyManager** interfaz, una referencia a la que se obtiene mediante una llamada a **IExtension.GetPropertyManager**y pasar un  **ITreeNode** objeto como parámetro de entrada. Normalmente, la extensión proporciona una **IPropertyManager** para cada objeto **ITreeNode** objeto. El Administrador de propiedades es responsable de la colección de propiedades personalizadas para que **ITreeNode** objeto.  
  
 Una propiedad personalizada se representa mediante un **System.ComponentModel.PropertyDescriptor** objeto, que puede obtenerse de la colección devuelta por la **IPropertyManager.GetProperties** método.  
  
 Usar **PropertyDescriptor** objetos que representan las propiedades personalizadas asociadas con la extensión facilita la integración con Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades. Cuando **PropertyDescriptor** objetos se utilizan, resulta sencillo para el Editor de BizTalk para integrar las propiedades personalizadas de la extensión en el conjunto de propiedades de nodo estándar ya existentes en la ventana Propiedades. Información de propiedad personalizada, como el nombre para mostrar, el valor de presentación, el tipo de control de propiedad, la descripción de propiedad y la categoría de propiedad se obtiene de la **PropertyDescriptor** objeto.  
  
 Las propiedades personalizadas se almacenan en la representación XSD del esquema como atributos de un elemento dentro del elemento de anotación del elemento correspondiente al nodo relevante del árbol de esquema. Cada propiedad personalizada de un nodo del árbol de esquema puede ser un atributo de un elemento común o, como alternativa, cada una puede tener su propio elemento asociado.  
  
## <a name="see-also"></a>Vea también  
 [Extender el Editor de BizTalk](../core/extending-biztalk-editor.md)