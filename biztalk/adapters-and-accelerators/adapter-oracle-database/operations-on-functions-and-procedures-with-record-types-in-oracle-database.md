---
title: Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2635ac4b21173fe1a12603c60263dfa70b5a18e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974205"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a>Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle
Tipos de registros de Oracle se usan para representar información jerárquica de los parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite los siguientes tipos de los tipos de registros:  
  
- Tipos de registros que se declaran como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.  
  
- Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL, por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));  
  
- Tipos de registros que contienen registros anidados.  
  
- Tipos de registros que aparecen como IN, OUT o IN OUT parámetros a procedimientos o funciones.  
  
- Tipos de registros que son los valores devueltos de funciones.  
  
  > [!NOTE]
  >  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.  
  
  Para obtener información acerca de:  
  
- Invocar una función o procedimiento que implican tipos de registros mediante el modelo de servicio WCF, vea [ejecutar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).  
  
- Invocar una función o procedimiento que implica el registro de tipos que utilizan [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos con tipos de registros por mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).  
  
- Estructura XML de registro de los tipos compatibles con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para tipos de registros](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)