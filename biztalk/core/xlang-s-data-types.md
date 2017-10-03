---
title: Tipos de datos de XLANG-s | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ed77c5fdd56485514d17ed75e921c63a56212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-data-types"></a>Tipos de datos de XLANG-s
XLANG/s define los tipos de valores estándar que son un reflejo de sus homólogos en C#. Puede tratarse de **booleano**, **bytes**, **Char**, **Decimal**, **doble**, **Int16** , **Int32**, **Int64**, **SByte**, **único**, **cadena**,  **UInt16**, **UInt32**, y **UInt64**. XLANG/s admite matrices unidimensionales, pero no literales de matriz.  
  
 XLANG/s también ofrece una gran compatibilidad con el control de mensajes. Los mensajes pueden basarse en esquemas, clases .NET, tipos de mensajes Web (WSDL) o tipos de mensajes complejos. XLANG/s admite lo siguientes tipos de datos complejos:  
  
-   **MessageType.** este tipo de datos define los tipos de mensajes con varias partes que se definen como combinaciones de elementos de datos, mensajes basados en XSD y tipos de método-mensaje (mensajes que coinciden con el formato de firma de un método de una clase o interfaz).  
  
-   **portType.** este tipo de datos define una colección de operaciones de puertos sobre la que puede actuar una instancia de puerto de ese tipo.  
  
-   **correlationsettype.** este tipo de datos define los datos que se usarán en cualquier instancia de una variable de conjuntos de correlaciones. Los datos de los conjuntos de correlaciones son el mecanismo de enrutamiento utilizado para garantizar que los mensajes que se desplazan por el sistema se entregan a la instancia en ejecución adecuada de un proceso empresarial. Por ejemplo, si se envía un pedido a un socio comercial para su procesamiento, resulta fundamental que se invoque la instancia correcta del proceso empresarial en el momento de su devolución.  
  
-   **servicelinktype.** Este tipo de datos define el conjunto de **porttype** valores que forman un grupo de puertos utilizados en un proceso empresarial lógicamente coherente. El uso de vínculos de servicios constituye un mecanismo eficaz que permite la asignación dinámica a un grupo de puertos en el tiempo de ejecución. Esto permite definir un proceso empresarial único que puede utilizarse para interactuar con varios socios comerciales.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de XLANG-s](../core/xlang-s-statements.md)   
 [Operadores y Variables de XLANG-s](../core/xlang-s-variables-and-operators.md)   
 [Expresiones de XLANG-s](../core/xlang-s-expressions.md)   
 [Palabras reservadas de XLANG-s](../core/xlang-s-reserved-words.md)   
 [XLANG-s para las conversiones de tipo de BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)