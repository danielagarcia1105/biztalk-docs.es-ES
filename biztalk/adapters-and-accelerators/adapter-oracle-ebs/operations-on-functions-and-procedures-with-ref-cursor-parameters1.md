---
title: Operaciones en funciones y procedimientos con REF CURSOR Parameters1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6801c1e-7992-40a0-bab7-87957840cedd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dee169bca7546c404edaccce6b7a1835e3c209a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>Operaciones en funciones y procedimientos con parámetros REF CURSOR
Un REF CURSOR es un tipo de datos de PL/SQL que representa un puntero a un conjunto de resultados de servidor generado mediante la ejecución de una consulta. Un tipo de REF CURSOR habilita la entrada y salida de transmisión por secuencias de datos y es ideal para transferir grandes cantidades de datos desde y hacia un código de PL/SQL. 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>Fuertemente tipadas y cursores REF CURSOR débilmente tipada
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] proporciona compatibilidad para fuertemente tipadas y débilmente tipada (SYS_REFCURSOR) cursores REF cursor que se puede pasar a procedimientos de PL/SQL y funciones como en y los parámetros de salida.  
  
-   **REF CURSOR**. Los clientes de adaptador deben usar un REF CURSOR de IN proporcionando un código de PL/SQL (como cadena) que se abre REF CURSOR en la base de datos de Oracle. El adaptador crea la variable y establece el REF CURSOR abierto y llama a una función o procedimiento con esa variable. Por lo tanto, procedimiento almacenan de parámetros en REF CURSOR de PL/SQL y funciones deben estar representadas como cadenas que toman un bloque de código de PL/SQL como valor de entrada marcar la variable de salida de REF CURSOR con un "?".  
  
-   **SALIDA DE REF CURSOR**. SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipado o débilmente tipada. El tipo del conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como un REF CURSOR fuertemente tipado o débilmente tipada en la definición de función o un procedimiento almacenada en el servidor Oracle.  
  
-   **EN los parámetros de salida de REF CURSOR**.  Dado que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] modela parámetros IN REF CURSOR como cadenas y parámetros de salida de REF CURSOR como tipos complejos, que no admite un único tipo para un parámetro OUT en REF CURSOR. Por esta razón, trata los parámetros OUT en REF CURSOR como dos parámetros diferentes: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)