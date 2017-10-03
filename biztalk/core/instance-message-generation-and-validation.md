---
title: "Validación y generación de mensaje de instancia | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a306846-3942-4ba1-a74e-6ead8deb0322
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 964f9bd2ee2b8bb20872bc593723cea778b5ed81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-generation-and-validation"></a>Generación y validación de mensajes de instancia
Una vez validado un esquema, puede usarlo para generar un mensaje de instancia de ejemplo. El mensaje de instancia de ejemplo generado contiene la estructura de elementos y atributos especificada por el esquema y genera datos falsos si es necesario.  
  
> [!NOTE]
>  El mecanismo de generación de datos utilizado al generar mensajes de instancia no posee el nivel de complejidad necesario para generar datos según los valores especificados para varias propiedades. Por ejemplo, si el esquema contiene todos los valores de la **patrón** propiedad, que está disponible en la **restricciones** categoría para **elemento de campo** nodos y **Atributo de campo** nodos cuando sus **Derived By** propiedad está establecida en **restricción**, el mensaje de instancia generado no se puede usar tal cual, como entrada para el **Validar instancia** operación.  
  
 Para generar un mensaje de instancia de ejemplo de un esquema, use la **generar instancia** comando en el menú contextual asociado al esquema en el Explorador de soluciones. Los resultados de la operación de generación del mensaje de instancia se muestran en la ventana Resultados de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  El **generar instancia** operación incluye el **Validar esquema** operación. Si hay errores en la validación, no se generará ningún mensaje de instancia de ejemplo.  
  
 Para obtener instrucciones paso a paso acerca de cómo generar un mensaje de instancia de un esquema, incluido cómo configurar un archivo de salida para que contenga el mensaje de instancia generado, consulte [generar mensajes de instancia](../core/how-to-generate-instance-messages.md).  
  
> [!NOTE]
>  Si no especifica un valor para el **referencia raíz** propiedad de la **esquema** nodo, el Editor de BizTalk genera un mensaje de instancia para el primer nodo raíz del esquema. Si especifica un valor para el **referencia raíz** propiedad, el Editor de BizTalk genera un mensaje de instancia para la raíz especificada.  
  
 Si ha validado el esquema, puede usar el Editor de BizTalk para determinar si un mensaje de instancia se ajusta a ese esquema.  
  
 Para validar un mensaje de instancia con un esquema, utilice la **Validar instancia** comando en el menú contextual asociado al esquema en el Explorador de soluciones. Los resultados de la validación aparecen en la ventana Resultados de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  Hay casos en los que un mensaje de instancia generado no superará la validación frente al mismo esquema desde el que se generó. Por ejemplo, si intenta validar un mensaje de instancia que se generó utilizando el **generar instancia** comando en el Editor de BizTalk y el esquema correspondiente incluye cualquier **elemento de campo** nodos o  **Atributo de campo** nodos que tienen sus **Derived By** propiedad establecida en **restricción** y que usan la **patrón** propiedad para especificar un patrón al que deben cumplir los datos correspondientes, la validación se producirá un error. Esto es porque el mecanismo de generación de datos que se utilizan al generar mensajes de instancia no es muy sofisticado para generar datos según los valores especificados para la **patrón** propiedad. También existen otros casos.  
  
 Para obtener instrucciones paso a paso acerca de cómo validar un mensaje de instancia, incluido cómo especificar el mensaje de instancia que se debe validar, consulte [validar esquemas](../core/how-to-validate-schemas-in-visual-studio.md).  
  
## <a name="see-also"></a>Vea también  
 [Acerca de los esquemas](../core/about-schemas.md)   
 [Comprobación de esquemas](../core/testing-schemas.md)