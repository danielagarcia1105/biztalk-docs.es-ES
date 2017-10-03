---
title: Propiedades de fecha de vigencia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="effective-date-properties"></a>Propiedades de fecha efectiva
PeopleSoft Enterprise permite programar y realizar un seguimiento de los elementos planificados usando una propiedad especial denominada Fecha de vigencia (abreviada como EFFDT por sus siglas en inglés). Tales elementos están en vigor o meramente planificados, en función de si su fecha es anterior o posterior a la fecha actual de PeopleSoft.  
  
 Si las propiedades de una interfaz de componente contienen tales elementos con fecha de vigencia (es decir, un campo con el nombre EFFDT), el adaptador permite que quienes realizan llamadas recuperen el conjunto de valores completo o únicamente los valores que aún no están en vigor (los que aún pueden modificarse).  
  
## <a name="gethistoryitems-parameter"></a>Parámetro getHistoryItems  
 Para las interfaces de componentes con propiedades que incluyan una fecha de vigencia, el adaptador proporciona un parámetro adicional, denominado `getHistoryItems`, a las operaciones Get. Este parámetro es del tipo booleano, y, si está configurado como True, se devolverán todos los elementos con fecha de vigencia. Entre ellos se incluyen todos los elementos pasados, actuales y futuros con fecha de vigencia.  
  
 Si el parámetro `getHistoryItems` está configurado como False, solamente se devolverán los elementos actuales y futuros con fecha de vigencia. Elija False si su intención es agregar o cambiar estos elementos (porque no se puedan cambiar los elementos antiguos).  
  
 También es posible tener varios elementos con fecha de vigencia que tengan la misma fecha de vigencia. En tal caso, deberá proporcionarse asimismo una propiedad adicional, Secuencia de vigencia (EFFSEQ, por sus siglas en inglés). Los valores de EFFSEQ deben ser únicos para diferenciar elementos que tengan la misma fecha de vigencia. Consulte la documentación de PeopleSoft para obtener más información.  
  
## <a name="modifying-past-effective-dated-items"></a>Modificación de los elementos cuya fecha de vigencia ya haya pasado  
 El `correctionMode` argumento tanto en el [UpdateEx](../core/updateex-method.md) y [DeleteOnly](../core/deleteonly-method.md) métodos controlan si se pueden modificar los últimos elementos con fecha efectivos. Si se establece en true, todos los elementos se pueden modificar. En caso contrario, la modificación de los elementos con fecha de vigencia que ya haya pasado genera una excepción.  
  
 Cuando se llama al obsoleto método `Update` en una interfaz de componente con elementos con fecha de vigencia, deberá tener cuidado de no incluir ninguna fecha de vigencia con valor anterior a la fecha de vigencia actual de PeopleSoft, para evitar que la llamada falle con una excepción. Sin embargo, se puede incluir el elemento con fecha de vigencia actual, pues se omite al configurar las propiedades. Si existe la Secuencia de vigencia, todos los elementos con fecha de vigencia actual cuyas Secuencias de vigencia coincidan en el servidor se omitirán al configurar las propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)