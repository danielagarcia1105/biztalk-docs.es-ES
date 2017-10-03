---
title: "Tipos de vínculos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compiler directives, links
- elastic links [maps]
- maps, links
- BizTalk Mapper, links
- partial links [maps]
- fixed links [maps]
ms.assetid: 348fae77-2e25-4b79-93bb-d42f3d18a3f7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d6f1039e65989a2de0243a1a9a09f30165e603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="types-of-links"></a>Tipos de vínculos
En la siguiente lista se resumen los diferentes tipos de vínculos disponibles en el Asignador de BizTalk:  
  
-   **Vínculos elásticos.** El término elástico se aplica a un vínculo conforme se está creando, antes de que los dos extremos del vínculo estén conectados. Por ejemplo, si arrastra un vínculo desde un campo del esquema de origen, pero todavía no lo ha conectado a su campo correspondiente en el esquema de destino, el vínculo es elástico. Cuando haya completado la conexión, el vínculo elástico se convierte en un vínculo fijo.  
  
     Puede arrastrar un extremo de un vínculo a otro nodo o a un functoid. Para obtener más información acerca de la sustitución de vínculos, consulte [cómo crear vínculos](../core/how-to-create-links.md).  
  
-   **Vínculos fijos.** El término fijo se aplica a un vínculo generado explícitamente para representar el movimiento de un valor desde un mensaje de instancia de origen hasta un mensaje de instancia de destino o, al menos, una parte de este movimiento. Vínculos fijos que conectan directamente un **registro** o **campo** nodo del esquema de origen a un **registro** o **campo** nodo en el destino esquema representa una copia directa de datos en tiempo de ejecución. Los vínculos fijos que se conectan con un functoid en un extremo u otro representan parte del movimiento de datos desde un mensaje de instancia de entrada hasta un mensaje de instancia de salida en tiempo de ejecución. Varios de éstos juntos, al completar el vínculo entre los esquemas de origen y de destino, representan el movimiento entero de un elemento de datos.  
  
-   **Vínculos parciales.** El término parcial se aplica a los vínculos que se no pueden ver actualmente exactos **registro** o **campo** nodo al que se conectan en los esquemas de origen o destino. Esto se produce cuando el **registro** o **campo** nodo al que se adjunta no se muestra porque uno de sus nodos antecesores está contraído en la representación en árbol del esquema. Para obtener más información sobre los vínculos parciales, consulte [cómo optimizar la presentación de vínculos](../core/how-to-optimize-the-display-of-links.md).  
  
-   **Vínculos de compilador.** El término compilador se aplica a los vínculos que el Asignador de BizTalk crea automáticamente cuando se genera un proyecto de BizTalk. Por ejemplo, si configura bucles controlados por tablas, los vínculos de compilador muestran la relación y los vínculos entre los registros y campos del esquema de origen y los registros y campos del esquema de destino. Este tipo de vínculo pueden generarlo automáticamente directivas de compilador o puede ser dirigido por el usuario.  
  
 El Asignador de BizTalk muestra de forma predeterminada los diversos tipos de vínculos mediante líneas de colores diferentes para ayudar a distinguir el detalle de las asignaciones. Puede cambiar los colores utilizados para los distintos tipos de vínculos con la **opciones** comando el **herramientas** menú. Para obtener más información acerca de cómo el cambio de color presenta diferentes categorías de vínculos, consulte [cómo personalizar colores y fuentes en el asignador de BizTalk](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilizar vínculos para especificar el registro y las asignaciones de campos](../core/using-links-to-specify-record-and-field-mappings.md)