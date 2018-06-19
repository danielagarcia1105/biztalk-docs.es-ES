---
title: Cómo agregar un bloque de compensación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246540"
---
# <a name="how-to-add-a-compensation-block"></a>Cómo agregar un bloque de compensación
Si no agrega su propia compensación, el motor de tiempo de ejecución llevará a cabo una compensación predeterminada que invoca las compensaciones de las transacciones anidadas contenidas en la transacción actual. En primer lugar, invoca la compensación de la transacción completada más recientemente y va retrocediendo hasta que se han compensado todas las transacciones anidadas.  
  
 Esto es cierto incluso cuando la compensación tenga lugar dentro de una forma bucle: las compensaciones se ejecutarán en orden inverso. En primer lugar, se invocará la compensación de la última iteración del bucle, luego la de la iteración anterior, y así sucesivamente.  
  
> [!CAUTION]
>  Dado que los datos persisten en la memoria física para que la compensación funcione, el uso de compensaciones dentro de un bucle puede afectar al rendimiento, lo que podría convertirse en un problema si el número de iteraciones es elevado.  
  
 Si el orden predeterminado no se ajusta a los requisitos, puede escribir su propio controlador de compensación para llamar explícitamente a los controladores de compensación de los ámbitos anidados en el orden que desee especificar.  
  
### <a name="to-add-a-compensation-block"></a>Para agregar un bloque de compensación  
  
1.  Haga clic en el **ámbito** forma para la transacción a la que desea agregar un **bloque de compensación**y, a continuación, haga clic en **nuevo bloque de compensación**.  
  
    > [!NOTE]
    >  Para agregar una **bloque de compensación** a una **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Atómica** o **de larga ejecución**.  
  
     A **bloque de compensación** se agrega a la orquestación inmediatamente después asociado **ámbito** forma.  
  
2.  Dentro de la **bloque de compensación** forma, agregue formas a fin de crear el proceso para deshacer una transacción confirmada.