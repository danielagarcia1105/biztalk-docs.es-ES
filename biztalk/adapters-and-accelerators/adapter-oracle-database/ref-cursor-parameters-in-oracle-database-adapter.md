---
title: Operaciones en funciones y procedimientos con parámetros REF CURSOR en la base de datos de Oracle | Documentos de Microsoft
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
ms.openlocfilehash: a918553cd687d80a5898c7171981dffbcf7b092c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215604"
---
# <a name="operations-on-functions-and-procedures-with-ref-cursor-parameters-in-oracle-database"></a>Operaciones en funciones y procedimientos con parámetros REF CURSOR en la base de datos de Oracle
Un REF CURSOR es un tipo de datos de PL/SQL que representa un puntero a un conjunto de resultados de servidor generado mediante la ejecución de una consulta. Un tipo de REF CURSOR habilita la entrada y salida de transmisión por secuencias de datos y es ideal para transferir grandes cantidades de datos desde y hacia un código de PL/SQL. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] proporciona compatibilidad para fuertemente tipadas y débilmente tipada (SYS_REFCURSOR) cursores REF cursor que se puede pasar a procedimientos de PL/SQL y funciones como IN, OUT o IN a parámetros.  
  
-   **REF CURSOR**. Los clientes de adaptador deben usar un REF CURSOR de IN proporcionando un código de PL/SQL (como cadena) que se abre REF CURSOR en la base de datos de Oracle. El adaptador crea la variable y establece el REF CURSOR abierto y llama a una función o procedimiento con esa variable. Por lo tanto, procedimiento almacenan de parámetros en REF CURSOR de PL/SQL y funciones deben estar representadas como cadenas que toman un bloque de código de PL/SQL como valor de entrada marcar la variable de salida de REF CURSOR con un "?".  
  
-   **SALIDA DE REF CURSOR**. SALIDA de REF CURSOR parámetros se devuelven como conjuntos de resultados fuertemente tipado o débilmente tipada. El tipo del conjunto de resultados devuelto depende de si el parámetro REF CURSOR se declara como un REF CURSOR fuertemente tipado o débilmente tipada en la definición de función o un procedimiento almacenada en el servidor Oracle.  
  
-   **EN los parámetros de salida de REF CURSOR**. Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] modela parámetros IN REF CURSOR como cadenas y parámetros de salida de REF CURSOR como tipos complejos, que no admite un único tipo para un parámetro OUT en REF CURSOR. Por esta razón, trata los parámetros OUT en REF CURSOR como dos parámetros diferentes: un parámetro IN en el mensaje de solicitud y un parámetro OUT en el mensaje de respuesta.  
  
 Para obtener más información acerca de:  
  
-   Invocar una función o procedimiento que implica parámetros REF CURSOR mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos con cursores REF cursor en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md).  
  
-   Invocar una función o procedimiento que implica parámetros REF CURSOR mediante el modelo de servicio WCF, vea [ejecutar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).  
  
-   Estructura XML de los cursores REF cursor compatible con la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para los cursores REF cursor](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a la base de datos de Oracle mediante el adaptador](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-using-the-adapter.md)