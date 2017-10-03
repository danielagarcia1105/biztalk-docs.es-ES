---
title: "Functoids lógicos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7907d1045fde39d5ece963bd78e00d027e8a9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="logical-functoids"></a>Functoids lógicos

## <a name="overview"></a>Información general
**Lógico** functoids se utilizan para realizar los siguientes tipos de operaciones:  
  
-   Realizar pruebas lógicas específicas en tiempo de ejecución. El **operador lógico OR**, **NOT lógico** y **lógico y** functoids pueden utilizarse para determinar si se crea un registro en un mensaje de instancia de destino, como la siguiente:  
  
     Si ShipTo **o** OrderedBy están presentes, cree el registro de dirección BillTo.  
  
     También puede usar estos functoids junto con el **bucle** functoid para configurar el número de veces bucles realiza un registro.  
  
-   Controlar si un registro específico se crea en un mensaje de instancia de destino en tiempo de ejecución. Functoids como **IsNil**, **numérico lógico**, **inferior a**, y **Greater Than** puede utilizarse para controlar si se crea un registro.  
  
     Si el resultado de uno de estos functoids lógicos es **True**, se genera el registro correspondiente en el mensaje de instancia de destino. Si el resultado es **False**, no se genera el registro correspondiente en el mensaje de instancia de destino.  
  
 Los functoids **IsNil**, **fecha lógica**, **existencia lógica**, **NOT lógico**, **numérico lógico**, y **cadena lógica** solo aceptan un parámetro. Los functoids **igual**, **Greater Than**, **mayor o igual que**, **inferior a**, **menor o igual a**, y **no es igual a** aceptan dos parámetros de entrada. Mientras que, el **lógico y** y **operador lógico OR** functoids aceptan parámetros de entrada entre 2 y 100.  
  
 La salida de un **lógicos** functoid también puede aceptarse como entrada para otro functoid en un mapa. Si un **lógicos** functoid un functoid de bucle están vinculados entre sí y, a continuación, vinculados a un registro en el esquema de destino, se usa el functoid de bucle solo cuando la **lógicos** salida del functoid es  **True**.  
  
 También puede usar **lógicos** functoids con los **Value Mapping** o **asignación de valores (sin formato)** functoids para controlar si un registro en el mensaje de instancia de destino se crea.  
  
> [!IMPORTANT]
>  Si vincula dos registros o campos del esquema de origen a dos diferentes **lógicos** functoids y, a continuación, vincula cada uno de los **lógicos** functoids en el mismo registro en el esquema de destino, solo la primera  **Lógico** functoid se utiliza en el generado Extensible Stylesheet Language (XSLT). El segundo vínculo de la segunda **lógicos** functoid, se omite.  
  
> [!NOTE]
>  Cuando se comparan las dos cadenas, los functoids lógicos distinguen entre mayúsculas y minúsculas. Por ejemplo, "Abc" y "abc" no son iguales. La excepción a esta regla es cuando **lógicos** functoids comparan cadenas que representan los valores booleanos **True** y **False**. Por ejemplo, "True" y "true" son iguales.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **lógicos** functoids son: 

* Igual
* Mayor que
* Mayor o igual que
* IsNil
* Menor que
* Menor o igual que
* Y lógico
* Fecha lógica
* Existencia lógica
* NOT lógico
* Valor numérico lógico
* O lógico
* Cadena lógica
* No igual

Para obtener más información sobre estas funciones es [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="see-also"></a>Vea también  
-  [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **Referencia a Functoids lógicos**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]