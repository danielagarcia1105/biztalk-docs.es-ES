---
title: Operaciones en funciones y procedimientos con REF CURSOR Parameters1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6801c1e-7992-40a0-bab7-87957840cedd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7227d6fd100714c0b467f0b43537b364af98d37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978653"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters"></a>Operaciones en funciones y procedimientos con parámetros REF CURSOR
Un REF CURSOR es un tipo de datos de PL/SQL que representa un puntero a un conjunto de resultados del lado servidor generado al ejecutar una consulta. Un tipo REF CURSOR permite la entrada y salida de transmisión por secuencias de datos y es ideal para transferir grandes cantidades de datos hacia y desde un código PL/SQL. 

## <a name="strongly-typed-and-weakly-typed-ref-cursors"></a>Fuertemente tipadas y cursores REF CURSOR débilmente tipada
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] proporciona compatibilidad para fuertemente tipadas y débilmente tipada (SYS_REFCURSOR) cursores REF cursor que puede pasarse a los procedimientos de PL/SQL y las funciones como en y los parámetros OUT.  
  
- **REF CURSOR**. Los clientes del adaptador deben usar un REF CURSOR de IN proporcionando un código de PL/SQL (como cadena) que se abre el REF CURSOR en la base de datos de Oracle. El adaptador crea la variable y lo establece el REF CURSOR abierto y llama a una función o procedimiento con esa variable. Por lo tanto, procedimiento almacenan de parámetros en REF CURSOR de PL/SQL y las funciones deben representarse como cadenas que toman un bloque de código PL/SQL como valor de entrada marcar la variable de salida de REF CURSOR con un "?".  
  
- **SALIDA DE REF CURSOR**. SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipada o débilmente tipada. El tipo de conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como fuertemente tipados o débilmente tipada REF CURSOR en la definición de función o procedimiento almacenada en el servidor de Oracle.  
  
- **EN los parámetros de salida de REF CURSOR**.  Dado que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] modela parámetros IN REF CURSOR como cadenas y los parámetros de salida de REF CURSOR como tipos complejos, que no admite un tipo único para un parámetro OUT en REF CURSOR. Por este motivo, trata los parámetros OUT en REF CURSOR como dos parámetros distintos: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)