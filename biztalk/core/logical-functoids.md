---
title: Functoids lógicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873e2b0ea1189586f9cabfbcb43c6ef276f34e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007597"
---
# <a name="logical-functoids"></a>Functoids lógicos

## <a name="overview"></a>Información general
**Lógico** functoids se utilizan para realizar los siguientes tipos de operaciones:  

- Realizar pruebas lógicas específicas en tiempo de ejecución. El **o lógico**, **NOT lógico** y **lógico y** functoids puede usarse para determinar si se crea un registro en un mensaje de instancia de destino, como la siguiente:  

   Si ShipTo **o** OrderedBy están presentes, cree el registro de dirección BillTo.  

   También puede usar estos functoids junto con el **bucle** functoid para configurar el número de veces que un registro bucles.  

- Controlar si un registro específico se crea en un mensaje de instancia de destino en tiempo de ejecución. Functoids como **IsNil**, **numérico lógico**, **menor**, y **mayor** puede utilizarse para controlar si se crea un registro.  

   Si el resultado de uno de estos functoids lógicos es **True**, se genera el registro correspondiente en el mensaje de instancia de destino. Si el resultado es **False**, no se genera el registro correspondiente en el mensaje de instancia de destino.  

  Los functoids **IsNil**, **fecha lógica**, **existencia lógica**, **NOT lógico**, **numérico lógico**, y **cadena lógica** solo aceptan un parámetro. Los functoids **igual**, **mayor**, **mayor o igual que**, **menor**, **menor o igual que**, y **distinto** acepta dos parámetros de entrada. Mientras que, el **lógico y** y **o lógico** functoids aceptan parámetros de entrada entre 2 y 100.  

  La salida de un **lógicos** functoid también se puede aceptar como entrada para otro functoid en un mapa. Si ambos un **lógicos** functoid un functoid de bucle están vinculados entre sí y, a continuación, vinculados a un registro en el esquema de destino, se usa el functoid de bucle solo cuando el **lógicos** salida del functoid es  **True**.  

  También puede usar **lógicos** functoids con los **Value Mapping** o **asignación de valores (sin formato)** functoids para controlar si un registro en el mensaje de instancia de destino se crea.  

> [!IMPORTANT]
>  Si vincula dos registros o campos del esquema de origen a dos diferentes **lógicos** functoids y, a continuación, vincula cada uno de los **lógicos** functoids en el mismo registro en el esquema de destino, la primera  **Lógico** functoid se usa en el generado Extensible Stylesheet Language Transformations (XSLT). El segundo vínculo, en la segunda **lógicos** functoid, se omite.  

> [!NOTE]
>  Cuando se comparan las dos cadenas, los functoids lógicos distinguen entre mayúsculas y minúsculas. Por ejemplo, "Abc" y "abc" no son iguales. La excepción a esta regla es cuando **lógicos** functoids comparan cadenas que representan los valores booleanos **True** y **False**. Por ejemplo, "True" y "true" son iguales.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **lógicos** functoids son: 

* Igual
* Mayor que
* Mayor o igual que
* IsNil
* Menor que
* Menor o igual a
* Y lógico
* Fecha lógica
* Existencia lógica
* NOT lógico
* Valor numérico lógico
* O lógico
* Cadena lógica
* No igual

Encontrará más detalles sobre estas funciones [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
- [Cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md)   
- **Referencia a Functoids lógicos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
