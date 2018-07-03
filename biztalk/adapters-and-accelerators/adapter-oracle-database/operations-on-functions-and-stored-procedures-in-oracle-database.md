---
title: Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle | Microsoft Docs
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
ms.openlocfilehash: 856e6bf882605737380f0bbe6185dce8a56c5828
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979613"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a>Operaciones en funciones y procedimientos almacenados en la base de datos de Oracle
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con las funciones, procedimientos y paquetes de Oracle en la siguiente manera:  
  
- **Funciones** se exponen como operaciones. El nombre de la operación es el nombre de la función de Oracle. IN, OUT y en espera parámetros son compatibles, además, los valores devuelvan.  
  
- **Procedimientos** se exponen como operaciones. El nombre de la operación es el nombre del procedimiento de Oracle. Se admiten parámetros IN, OUT y en espera.  
  
- **Empaqueta las funciones y procedimientos** se exponen como operaciones. El nombre y espacio de nombres de la operación (función o procedimiento) está calificada por el nombre del paquete de Oracle. Se admiten las sobrecargas en paquetes (vea la siguiente viñeta).  
  
- **Sobrecargar funciones y procedimientos** en paquetes que se exponen como operaciones. Cada función sobrecargada o procedimiento aparece con una cadena que se anexa al nombre que identifica la sobrecarga. Esta cadena es parte de la secuencia "overload1", "overload2", "overload3" y así sucesivamente.  
  
- **Tipos de REF CURSOR** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores. Para obtener más información, consulte [operaciones en funciones y procedimientos con parámetros REF CURSOR](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).  
  
- **Tipos de registro** son compatibles con IN, OUT y en los parámetros de procedimientos y funciones, así como para la función OUT devolver valores. Se admiten tipos de registros (anidados) simples y complejos. [Operaciones en funciones y procedimientos con tipos RECORD](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
  Para obtener más información acerca de:  
  
- Invocar un procedimiento de Oracle o una función mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos de la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) y [invocar sobrecargar funciones y procedimientos de uso de la base de datos de Oracle BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).  
  
- Invocar un procedimiento de Oracle o una función con el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
- Invocar un procedimiento de Oracle o una función con el modelo de canal WCF, vea [invocar una función de base de datos de Oracle mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).  
  
- Estructura y las acciones de SOAP utilizadas para invocar funciones y procedimientos de Oracle, vea mensajes [esquemas de mensaje para funciones y procedimientos](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)