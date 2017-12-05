---
title: "Parámetros de entrada de functoid | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a430b96f7a76ad6f99a7b3f9ee151f17c7b55a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="functoid-input-parameters"></a>Parámetros de entrada de functoid
Un aspecto crucial de la utilización de functoids en las asignaciones es la correcta configuración de los parámetros de entrada del functoid. Aunque el orden de los parámetros de entrada no es crítico para todos los functoids (como el **adición** functoid, que muestra el mismo propiedades de asociación que cabe esperar de la suma), muchos functoids deben tener sus parámetros de entrada especificado en el orden correcto.  
  
## <a name="create-input-paramaters"></a>Crear parámetros de entrada
 Los parámetros de entrada de functoid se pueden crear de dos maneras:  
  
-   Creando vínculos en la parte izquierda de un functoid en la página de cuadrícula que se muestra. El orden en que se crean los vínculos es el mismo en que los parámetros de entrada asociados se transmiten al functoid.  
  
-   Abriendo el **configurar \<Functoid\> Functoid** cuadro de diálogo y agregando nuevos parámetros de entrada. Este cuadro de diálogo también es importante porque permite reorganizar los parámetros de entrada a un functoid para que estén en el orden correcto. Por ejemplo, si crea vínculos al functoid en el orden adecuado, puede ir a este cuadro de diálogo y realizar las correcciones necesarias. Para obtener instrucciones paso a paso acerca de cómo configurar los parámetros de entrada de un functoid, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).  
  
 Debe utilizar el **configurar \<Functoid\> Functoid** cuadro de diálogo para crear parámetros de entrada que son constantes.  
  
 Cuando se proporciona una etiqueta para un vínculo o functoid utilizando la **etiqueta** propiedad en la ventana Propiedades cuando se selecciona el vínculo o functoid, esa etiqueta se mostrará en el **configurar \<Functoid\> Functoid** cuadro de diálogo en lugar de la expresión XPath correspondiente de un nodo de esquema o el nombre de un functoid que se va a usar como un parámetro de entrada. Con las etiquetas, será mucho más fácil distinguir los parámetros y ordenarlos correctamente.  
  
 Para obtener una información sobre el orden correcto de parámetros de entrada de functoid, consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Configurar los parámetros de entrada de Functoid](../core/how-to-configure-functoid-input-parameters.md)   
 [Configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md)   
 [Configurar los functoids de bucle de tabla y de extractor de tablas](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)