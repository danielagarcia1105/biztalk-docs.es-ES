---
title: Trabajar con esquemas grandes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c5ef679070009b5dfb5fdd403d238cfe243cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-large-schemas"></a>Trabajar con esquemas grandes
Cuando los esquemas lleguen a ser muy grandes, tal vez note una mayor lentitud al actualizar la vista XSD, así como que la respuesta de otros aspectos de la interfaz de usuario también se pueden haber visto afectados. La solución a este problema consiste en desactivar la característica de actualización automática y utilice en su lugar el manual **actualizar** vínculo en la vista XSD para actualizar periódicamente la vista XSD. Para obtener instrucciones paso a paso sobre cómo activar la característica de actualización automática en una desactivados, vea el procedimiento "para activar y desactivar la actualización automática de la vista XSD" en [administrar la vista XSD](../core/how-to-manage-the-xsd-view.md).  
  
 Rendimiento también puede ser lento en esquemas grandes con varias raíces conectadas a la **esquema** nodo. Establecer el **referencia raíz** propiedad puede aumentar el rendimiento de la interfaz de usuario. Establecer **referencia raíz** mejora el rendimiento porque el compilador crea clases de C# para todos los esquemas de raíz. Una única raíz implica la creación de menos clases.  
  
 **Validar instancia** puede parecer lento en la interfaz de usuario porque la validación se realiza siempre en el esquema antes de validar la instancia. La validación del esquema solo tiene lugar en la interfaz de usuario. Establecer el **referencia raíz** propiedad también mejora el rendimiento de la interfaz de usuario en este caso.  
  
## <a name="see-also"></a>Vea también  
 [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)