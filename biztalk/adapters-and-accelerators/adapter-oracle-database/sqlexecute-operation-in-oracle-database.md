---
title: Operación SQLEXECUTE en la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfae55d12ce3b244001bf04aef48ff40b97d97a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000515"
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Operación SQLEXECUTE en la base de datos de Oracle
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto estándar de operaciones en los artefactos de base de datos de Oracle. Mediante el uso de estas operaciones, puede hacer cosas como la llamada a una función de Oracle o un procedimiento, o realizar operaciones del lenguaje (DML) de manipulación de datos de básica SQL en tablas. Sin embargo, puede haber escenarios controlados por la lógica de negocios que necesitan realizar operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no se exponen. Por ejemplo, es posible que desee:  
  
- Realizar una operación en artefactos de base de datos que no se exponen mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtener el CURVAL o NEXTVAL de una secuencia de Oracle.  
  
- Realizar operaciones de lenguaje de definición de datos; Por ejemplo, cree una tabla.  
  
- Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal creada por la lógica de negocios.  
  
- Realizar operaciones más complejas de DML en tablas que las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies; por ejemplo, para realizar una consulta que incluye una cláusula JOIN.  
  
  Para estos tipos de escenarios, la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone la operación SQLEXECUTE. La operación SQLEXECUTE aparece bajo el nodo raíz (/) en el **seleccionar una categoría** panel en el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
  Mediante el uso de la operación SQLEXECUTE, puede realizar una instrucción SQL con parámetros en la base de datos de Oracle. La operación SQLEXECUTE admite un bloque de parámetro de entrada que consta de conjuntos de parámetros que permiten ejecutar la misma instrucción SQL una vez para cada conjunto. La operación SQLEXECUTE devuelve los resultados de la instrucción SQL en un conjunto de registros genérico.  
  
> [!NOTE]
>  Puede pasar IN y OUT en parámetros de procedimientos, funciones y paquetes en la operación SQLEXECUTE. El artefacto invocado se ejecutará con los parámetros proporcionados en la base de datos de Oracle; Sin embargo, la operación SQLEXECUTE no devuelve el valor de salida y los parámetros IN OUT al cliente. Si desea invocar procedimientos, funciones o los paquetes, se recomienda hacerlo invocando las operaciones dedicadas que los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.  
  
 Para obtener más información acerca de:  
  
- Realizar una operación SQLEXECUTE mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [operación SQLEXECUTE ejecutar utilizando BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md).  
  
- Realizar una operación SQLEXECUTE mediante el modelo de servicio WCF, consulte [ejecutar operación SQLEXECUTE mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).  
  
- Realizar la operación SQLEXECUTE mediante el modelo de canal WCF, consulte [ejecutar operación SQLEXECUTE mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).  
  
- Mensaje de la estructura y las acciones de SOAP para llevar a cabo una operación SQLEXECUTE, vea [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)