---
title: Cómo establecer las propiedades del nodo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c79eac-d9ba-45e2-a6e9-770b2bcb2067
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dc0f13814808a69c4c4b9c3976e9047acde5b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255452"
---
# <a name="how-to-set-node-properties"></a>Cómo establecer propiedades de nodo
Tras insertar un nodo en un esquema de BizTalk, normalmente tendrá que cambiar los valores predeterminados de las propiedades de dicho nodo. Cada tipo de nodo tiene un conjunto específico de propiedades y, dentro de dicho conjunto, la configuración de una propiedad puede afectar a la disponibilidad de otras propiedades. Por ejemplo, antes de establecer el **carácter de ajuste predeterminado** propiedad de la **esquema** nodo, debe establecer el **tipo de carácter de ajuste predeterminado** propiedad a cualquier **Caracteres** o **Hexadecimal**, con lo que se establece el formato en el que se va a representar la propiedad anterior. Además, de estas propiedades está disponible, ni es toda la **analizar** propiedad categoría a la que pertenecen, a menos que **extensión de archivo sin formato** se habilita mediante la **Editor de esquemas Extensiones** propiedad.  

 Las propiedades de los nodos son amplias y pueden ser complejas, del mismo modo que lo es el lenguaje de definición de esquemas XML (XSD) que admiten. Este tema únicamente describe de forma breve los pasos generales necesarios para examinar y establecer las propiedades de los nodos Para obtener información detallada acerca de estas propiedades, como, por ejemplo, información sobre su valor predeterminado y valores permitidos, consulte la **referencia de esquema de propiedad**. Para obtener información sobre los conceptos XSD y los elementos subyacentes a la mayoría de estas propiedades de nodo incluso más detallan, consulte directamente la información sobre [XSD en la Web](../core/xsd-resources-on-the-web.md).  

Obtener más información sobre estas propiedades y la referencia de propiedad de esquema [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

  
## <a name="examine-a-node-property-value"></a>Examinar un valor de propiedad de nodo  
  
1.  En el Editor de BizTalk, abra el esquema que contiene la propiedad que desea examinar y, a continuación, seleccione el nodo que contiene dicha propiedad.  
  
2.  Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.  
  
3.  Si fuera necesario, desplácese por la ventana Propiedades para buscar la propiedad que le interese y anote su valor.  
  
     Puede usar los botones de la parte superior de la ventana Propiedades para cambiar cómo se ordenan las propiedades, de forma alfabética dentro de categorías o de forma alfabética sin tener en cuenta (ni mostrar) las categorías.  
  
## <a name="set-a-node-property-value"></a>Establecer un valor de propiedad de nodo  
  
1.  En el Editor de BizTalk, abra el esquema que contiene la propiedad que desea establecer y, a continuación, seleccione el nodo que contiene dicha propiedad.  
  
2.  Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.  
  
3.  Si fuera necesario, desplácese por la ventana Propiedades para buscar la propiedad que le interese.  
  
     Puede usar los botones de la parte superior de la ventana Propiedades para cambiar cómo se ordenan las propiedades, de forma alfabética dentro de categorías o de forma alfabética sin tener en cuenta (ni mostrar) las categorías.  
  
4.  Establezca el valor de la propiedad en el campo de valores que se encuentra a la derecha del nombre de la propiedad. Dependiendo del tipo de propiedad, podrá escribir un valor o seleccionarlo de la lista desplegable que se muestra al seleccionar el campo de valores. Algunas propiedades permiten ambas operaciones. Algunas propiedades muestran puntos suspensivos (**...** ) que el botón cuando ha hecho clic se abre un cuadro de diálogo en el que valores más complejos, como colecciones, se puede establecer.  
  
5.  Si ha escrito un valor nuevo para la propiedad, presione ENTRAR para finalizar.  
  
##  <a name="clear-a-node-property-value"></a>Borrar un valor de propiedad de nodo  
  
1.  Seleccione el nodo que contiene la propiedad que le interesa.  
  
2.  En la ventana Propiedades, haga doble clic en el valor de propiedad que desea borrar, haga clic en el valor de propiedad y, a continuación, haga clic en **eliminar**.  
  
## <a name="restore-a-node-property-to-its-default-value"></a>Restaurar una propiedad de nodo a su valor predeterminado  
  
1.  Seleccione el nodo que contiene la propiedad que le interesa.  
  
2.  En la ventana Propiedades, haga clic en el nombre de propiedad que desea restablecer a su valor predeterminado y, a continuación, haga clic en **restablecer**.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con nodos existentes](../core/working-with-existing-nodes.md)