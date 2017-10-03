---
title: Reglas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="rules"></a>Reglas
Las reglas de negocios son instrucciones declarativas que rigen el comportamiento de los procesos empresariales. Una regla consta de una condición y de acciones. La condición se evalúa, y si se evalúa como **true**, el motor de reglas inicia una o varias acciones.  
  
 En el marco de trabajo de reglas de negocios, las reglas se definen con el formato siguiente:  
  
 IF`condition` , A CONTINUACIÓN,`action`  
  
 Considere el ejemplo siguiente:  
  
 SI el importe es inferior o igual a los fondos disponibles  
  
 ENTONCES se debe realizar la transacción e imprimir el recibo  
  
 Esta regla determina si se realizará una transacción mediante la aplicación de lógica de negocios, en forma de una comparación de dos valores monetarios, a datos o hechos, en forma de un importe de transacción y los fondos disponibles.  
  
 Puede usar el Compositor de reglas de negocio para crear, modificar, establecer la versión e implementar reglas de negocios. Como alternativa, puede realizar las tareas anteriores mediante programación.  
  
## <a name="conditions"></a>Condiciones  
 Una condición es una expresión true o falsa (booleana) que consta de uno o más predicados aplicados a datos.  
  
 En nuestro ejemplo, el predicado **menor o igual a** se aplica a los hechos **cantidad** y **fondos disponibles**. Esta condición siempre se evaluará como **true** o **false**.  
  
 Los predicados se pueden combinar con los operadores lógicos **AND**, **o**, y **no** para formar una expresión lógica que posiblemente es bastante grande, pero que se siempre se evalúan como cualquier **true** o **false**.  
  
## <a name="actions"></a>Acciones  
 Las acciones son las consecuencias funcionales de la evaluación de las condiciones. Si se cumple la condición de una regla, se inicia la acción o las acciones correspondientes.  
  
 En este ejemplo, "realizar transacción" e "imprimir recibo" son las acciones que se ejecutan cuando se cumple la condición (en este caso, "SI el importe es inferior o igual a los fondos disponibles").  
  
 Las acciones se representan en el marco de trabajo de reglas de negocios al invocar métodos o establecer propiedades de objetos, o bien al realizar operaciones set en documentos XML o tablas de bases de datos.  
  
## <a name="facts"></a>Hechos  
 Los datos son la información para la que se ejecutan las reglas. En este ejemplo, los datos son "cantidad" y "fondos disponibles". Para obtener más información, consulte [hechos](../core/facts.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear directivas y reglas](../core/how-to-create-policies-and-rules.md)