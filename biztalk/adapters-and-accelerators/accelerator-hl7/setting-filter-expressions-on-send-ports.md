---
title: Establecer expresiones de filtro en puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206084"
---
# <a name="setting-filter-expressions-on-send-ports"></a>Expresiones de filtro de la configuración de puertos de envío
Establecer propiedades de contexto en expresiones de filtro en el puerto de envío para controlar el puerto que envía. Puede establecer las expresiones de filtro con un número de operadores que ofrecen flexibilidad en cómo filtrar la propiedad (igualdad o desigualdad, existe, mayor que, mayor o igual a, menor que y menor o igual que).  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a>Para establecer la expresión de filtro en un puerto de envío  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** (u otra aplicación). Haga clic en **puertos de envío**.  
  
2.  Haga clic en el puerto de envío que desea establecer la expresión de filtro para y, a continuación, haga clic en **propiedades**.  
  
3.  En el árbol de consola del cuadro de diálogo Propiedades de puerto de envío, haga clic en **filtros**.  
  
4.  Haga clic en el cuadro de texto en el **propiedad** columna y, a continuación, seleccione la propiedad de contexto de la **propiedad** lista desplegable.  
  
5.  Haga clic en el **operador** cuadro en la fila de la propiedad y seleccione el operador para la propiedad de la lista desplegable.  
  
6.  Haga clic en el **valor** cuadro en la fila de la propiedad y escriba una expresión de valor.  
  
7.  Si necesita agregar otra cláusula para la expresión de filtro, haga clic en el **Group By** cuadro en la fila de la propiedad y seleccione **y** o **o** para determinar la relación de la cláusulas.  
  
8.  Repita los pasos del 4 al 6 para agregar otra cláusula de filtro.  
  
9. Compruebe que la expresión de filtro es correcta en el panel en la parte inferior de la **filtros** panel.  
  
10. Cuando haya agregado todas las cláusulas de filtro, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Usar propiedades de contexto](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)