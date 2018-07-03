---
title: Parámetros de entrada de functoid | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cca24f93-74a8-460c-b9ab-9aa2c767fe2f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a93d827a5f58401bb9b8fcdf9727c2a61767e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008101"
---
# <a name="functoid-input-parameters"></a>Parámetros de entrada de functoid
Un aspecto crucial de la utilización de functoids en las asignaciones es la correcta configuración de los parámetros de entrada del functoid. Mientras que el orden de los parámetros de entrada no es crítico para todos los functoids (como el **adición** functoid, que muestra el mismo propiedades de asociación que cabe esperar de suma), muchos functoids deben tener los parámetros de entrada especificada en el orden correcto.  
  
## <a name="create-input-paramaters"></a>Crear parámetros de entrada
 Los parámetros de entrada de functoid se pueden crear de dos maneras:  
  
- Creando vínculos en la parte izquierda de un functoid en la página de cuadrícula que se muestra. El orden en que se crean los vínculos es el mismo en que los parámetros de entrada asociados se transmiten al functoid.  
  
- Abriendo el **configurar \<Functoid\> Functoid** cuadro de diálogo y agregando nuevos parámetros de entrada. Este cuadro de diálogo también es importante porque permite reorganizar los parámetros de entrada a un functoid para que estén en el orden correcto. Por ejemplo, si crea vínculos al functoid en el orden adecuado, puede ir a este cuadro de diálogo y realizar las correcciones necesarias. Para obtener instrucciones paso a paso sobre cómo configurar los parámetros de entrada para un functoid, consulte [cómo configurar parámetros de entrada del Functoid](../core/how-to-configure-functoid-input-parameters.md).  
  
  Debe usar el **configurar \<Functoid\> Functoid** cuadro de diálogo para crear parámetros de entrada que son constantes.  
  
  Al proporcionar una etiqueta para un vínculo o functoid utilizando el **etiqueta** propiedad en la ventana Propiedades cuando se selecciona el vínculo o functoid, esa etiqueta se mostrará en el **configurar \<Functoid\> Functoid** cuadro de diálogo en lugar del XPath correspondiente de un nodo de esquema o el nombre de un functoid que se va a usar como un parámetro de entrada. Con las etiquetas, será mucho más fácil distinguir los parámetros y ordenarlos correctamente.  
  
  Para obtener información sobre el orden correcto de parámetros de entrada de functoid definitivo, consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
 [Configurar parámetros de entrada de Functoid](../core/how-to-configure-functoid-input-parameters.md)   
 [Configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md)   
 [Configurar los functoids de bucle de tabla y de extractor de tablas](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)