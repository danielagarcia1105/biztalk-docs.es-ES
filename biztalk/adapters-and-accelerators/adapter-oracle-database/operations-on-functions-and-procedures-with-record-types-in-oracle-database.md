---
title: Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle | Documentos de Microsoft
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
ms.openlocfilehash: 46daadeaa5d1fc1060217f044a9d143488c38d7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214412"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a>Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle
Tipos de registros de Oracle se usan para representar la información jerárquica de parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con los siguientes tipos de tipos de registros:  
  
-   Tipos de registro que se declaran como tabla % ROWTYPE parámetros en procedimientos almacenados y funciones.  
  
-   Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL, por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));  
  
-   Tipos de registros que contienen registros anidados.  
  
-   Tipos de registro que aparecen como IN, OUT o IN los parámetros OUT procedimientos o funciones.  
  
-   Tipos de registros que son los valores devueltos de funciones.  
  
    > [!NOTE]
    >  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.  
  
 Para obtener información acerca de:  
  
-   Invocar una función o procedimiento que afectan a los tipos de registro mediante el modelo de servicio WCF, vea [ejecutar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).  
  
-   Invocar una función o procedimiento que implica el registro de tipos que utilizan [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos con tipos de registros por mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).  
  
-   Los tipos de estructura XML de registro como compatible con la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para tipos de registros](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)