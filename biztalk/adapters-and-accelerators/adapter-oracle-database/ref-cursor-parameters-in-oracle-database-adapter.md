---
title: Operaciones en funciones y procedimientos con parámetros REF CURSOR en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IN REF CURSOR
- REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: 691c4aca-3454-41d6-b211-a4d37f215331
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b1d3ac6ff54fa15c300962e7ecfdae91414bff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014813"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>Operaciones en funciones y procedimientos con parámetros REF CURSOR en la base de datos de Oracle
Un REF CURSOR es un tipo de datos de PL/SQL que representa un puntero a un conjunto de resultados del lado servidor generado al ejecutar una consulta. Un tipo REF CURSOR permite la entrada y salida de transmisión por secuencias de datos y es ideal para transferir grandes cantidades de datos hacia y desde un código PL/SQL. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] proporciona compatibilidad para fuertemente tipadas y débilmente tipada (SYS_REFCURSOR) cursores REF cursor que puede pasarse a los procedimientos de PL/SQL y las funciones como IN, OUT o IN OUT parámetros.  
  
- **REF CURSOR**. Los clientes del adaptador deben usar un REF CURSOR de IN proporcionando un código de PL/SQL (como cadena) que se abre el REF CURSOR en la base de datos de Oracle. El adaptador crea la variable y lo establece el REF CURSOR abierto y llama a una función o procedimiento con esa variable. Por lo tanto, procedimiento almacenan de parámetros en REF CURSOR de PL/SQL y las funciones deben representarse como cadenas que toman un bloque de código PL/SQL como valor de entrada marcar la variable de salida de REF CURSOR con un "?".  
  
- **SALIDA DE REF CURSOR**. SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipada o débilmente tipada. El tipo de conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como fuertemente tipados o débilmente tipada REF CURSOR en la definición de función o procedimiento almacenada en el servidor de Oracle.  
  
- **EN los parámetros de salida de REF CURSOR**. Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] modela parámetros IN REF CURSOR como cadenas y los parámetros de salida de REF CURSOR como tipos complejos, que no admite un tipo único para un parámetro OUT en REF CURSOR. Por este motivo, trata los parámetros OUT en REF CURSOR como dos parámetros distintos: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.  
  
  Para obtener más información acerca de:  
  
- Invocar una función o procedimiento que implica parámetros REF CURSOR utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos con cursores REF cursor en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md).  
  
- Invocar una función o procedimiento que implica parámetros REF CURSOR utilizando el modelo de servicio WCF, vea [ejecutar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).  
  
- Estructura XML de los cursores REF CURSOR compatibles con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para cursores REF cursor](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a la base de datos de Oracle mediante el adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)