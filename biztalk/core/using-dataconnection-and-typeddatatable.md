---
title: Utilizar DataConnection y TypedDataTable | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Assert function [Business Rules Engine], TypedData table
- Business Rules Engine, DataConnection tips
- TypedData table
- Business Rules Engine, TypedData table tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], DataConnection
ms.assetid: e825803e-6626-4ddd-a77e-75a3ba2b74a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-dataconnection-and-typeddatatable"></a>Utilizar DataConnection y TypedDataTable
En muchos escenarios, el uso **DataConnection** proporciona un mejor rendimiento y consume menos memoria que el uso de **TypedDataTable**. Sin embargo, **TypedDataTable** puede ser necesario en algunos casos debido a ciertas restricciones sobre el uso de **DataConnection**. En otros casos, con **TypedDataTable** , se puede obtener un mejor rendimiento que el uso de **DataConnection**. En este tema se describen los criterios y factores que se deben tener en cuenta para elegir el enfoque adecuado.  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a>Cuándo utilizar TypedDataTable en lugar de DataConnection  
 Utilice TypedDataTable en lugar de DataConnection en los casos siguientes:  
  
-   Es necesario realizar cambios en los datos, pero la tabla no posee una clave principal. Para realizar cambios de datos mediante el uso de **DataConnection**, se requiere una clave principal. Por lo tanto, si no hay ninguna clave principal, **TypedDataTable** es el único enfoque viable.  
  
    > [!NOTE]
    >  El motor de reglas sólo actualiza los valores de memoria para un **TypedDataTable**. Es el usuario que llama quien debe hacer permanentes estos cambios.  
  
-   La selectividad es alta, lo que significa que un alto porcentaje de filas de la tabla pasará las pruebas especificadas como condiciones de reglas. En este caso, **DataConnection** no proporciona demasiadas ventajas y puede funcionar peor que **TypedDataTable**.  
  
-   Por regla general, se trata de una tabla pequeña que contiene menos de 500 filas. Tenga en cuenta que este número puede variar en función de la forma de regla y de la memoria que esté disponible en el motor de reglas.  
  
-   El comportamiento del encadenamiento de reglas se encuentra en un conjunto de reglas. Llamar a la **actualización** funcionen en una **DataConnection** no es compatible, pero podría invocar **DataConnection.Update** en una regla mediante un método auxiliar. Cuando se requiere, el encadenamiento de reglas **TypedDataTable** es una opción mejor.  
  
-   Una o varias columnas de la tabla contienen una gran cantidad de datos que no resultan de utilidad para las reglas. Un ejemplo podría ser una base de datos de imágenes, donde las columnas contienen la imagen (una gran cantidad de datos), el nombre, la fecha, etc. Si la imagen no es necesaria, seleccione únicamente las columnas que utilizarán las reglas. Por ejemplo, emitir una consulta como "Seleccionar nombre y fecha en la tabla" puede ser más eficaz que el uso de **DataConnection**.  
  
-   Si muchas reglas necesitan o actualización la misma fila de la base de datos, utilizando un **TypedDataTable**, la fila se comparte entre todas las reglas, y si la condición es el mismo (por ejemplo, Table.Column == 5), se puede optimizar la evaluación de condición. Con un **DataConnection**, por lo general, se genera una consulta para cada regla que usa la **DataConnection**. Aunque las filas se reutilizan (si la tabla tiene una clave primaria), pueden generarse varias consultas para obtener los mismos datos cada vez.  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a>Cuándo utilizar DataConnection en lugar de TypedDataTable  
 Utilice DataConnection en lugar de TypedDataTable en los siguientes casos:  
  
-   La tabla contiene un gran número de filas, pero la selectividad es baja, solo un pequeño porcentaje de filas cumplirán las condiciones de regla.  
  
-   Solo existe una tabla de base de datos grande y el resto de objetos que se utilizan en la regla poseen un número reducido de instancias. En el peor de los casos, el número de consultas que se ejecutan en la base de datos coincide con la suma de todas las instancias utilizadas en la regla.  
  
-   Las reglas están formadas exclusivamente por condiciones conjuntivas y en ellas se utilizan objetos ajenos a la tabla de base de datos.  
  
## <a name="see-also"></a>Vea también  
 [Acceso a datos en el motor de reglas de negocios](../core/data-access-in-the-business-rule-engine.md)