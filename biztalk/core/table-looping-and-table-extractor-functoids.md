---
title: Bucle de tabla y Functoids de Extractor de tabla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d4433255ac00d51c88b45bd1a2b5205bd1c735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278364"
---
# <a name="table-looping-and-table-extractor-functoids"></a>Bucle de tabla y Functoids de Extractor de tabla

## <a name="overview"></a>Información general
En una asignación, generalmente se tiene una estructura en el mensaje de instancia de salida para cada estructura del mensaje de instancia de entrada. No obstante, hay ocasiones en las que necesita que una estructura de instancia de entrada produzca múltiples estructuras de instancia de salida. El bucle controlado por tablas permite crear asignaciones que generen esa serie de estructuras.  
  
 Usos de bucle controlado por tablas el **bucle de tabla** functoid y **Extractor de tablas** functoid. El **bucle de tabla** el functoid tiene una tabla interna configurable. Para cada entrada de registro o campo, el **bucle de tabla** functoid genera las filas de la tabla, de uno en uno. Por ejemplo, si hay diez registros en el mensaje de instancia de entrada y dos filas en la tabla interna de la **bucle de tabla**, el functoid genera un total de veinte filas, dos para cada uno de los diez registros. El **Extractor de tablas** functoid extrae el elemento deseado de una fila y lo pasa al mensaje de instancia de salida.  
  
 Para obtener más información, consulte el **referencia de Functoid de bucle de tabla** y **referencia de Functoid de Extractor de tabla** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Functoid de bucle de tabla](../core/table-looping-functoid.md)  
  
-   [Functoid de Extractor de tablas](../core/table-extractor-functoid.md)  
  
-   [Configuración de bucle controlado por tablas](../core/table-driven-looping-configuration.md)  
  
-   [Ejemplo de bucle controlado por tablas](../core/table-driven-looping-example.md)