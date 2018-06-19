---
title: Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78181aae7921cad3996e4bd408e604857a2bd15e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214956"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con las funciones, procedimientos y paquetes de Oracle de la siguiente manera:  
  
-   **Funciones** aparecen como operaciones. El nombre de la operación es el nombre de la función de Oracle. EN fuera y en espera parámetros son compatibles, así como, valores devuelvan.  
  
-   **Procedimientos** aparecen como operaciones. El nombre de la operación es el nombre del procedimiento de Oracle. Se admiten parámetros en fuera y en espera.  
  
-   **Empaqueta los procedimientos y funciones** aparecen como operaciones. El nombre y espacio de nombres de la operación (función o procedimiento) está calificada por el nombre del paquete de Oracle. Las sobrecargas se admiten en paquetes (vea la siguiente viñeta).  
  
-   **Sobrecargar funciones y procedimientos** en paquetes aparecen como operaciones. Cada función sobrecargada o procedimiento aparece con una cadena que se anexa al nombre que identifica la sobrecarga. Esta cadena es parte de la secuencia "overload1", "overload2", "overload3" y así sucesivamente.  
  
-   **Tipos de REF CURSOR** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT DEVUELVEN valores. Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).  
  
-   **Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT DEVUELVEN valores. Se admiten tipos de registros (anidados) simples y complejos. [Operaciones en funciones y procedimientos con tipos de registro](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
 Para obtener más información acerca de:  
  
-   Invoca una función o un procedimiento de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos de la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) y [invocar sobrecargar funciones y procedimientos de la base de datos de Oracle mediante El servidor BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).  
  
-   Invoca una función o un procedimiento de Oracle mediante el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
-   Invocar una función o un procedimiento de Oracle mediante el modelo de canal WCF, vea [invocar una función de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).  
  
-   Estructura y acciones de SOAP que se usan para invocar funciones y procedimientos de Oracle, vea mensajes [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)