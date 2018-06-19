---
title: La operación SQLEXECUTE en base de datos de Oracle | Documentos de Microsoft
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
ms.openlocfilehash: 6ac8d5c8284e1f273d4b9aef17e79e25636dc581
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215620"
---
# <a name="sqlexecute-operation-in-oracle-database"></a>Operación SQLEXECUTE en base de datos de Oracle
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto estándar de operaciones en artefactos de base de datos de Oracle. Mediante el uso de estas operaciones, puede hacer cosas como llamada a una función de Oracle o un procedimiento, o realizar operaciones del lenguaje (DML) de manipulación de datos de básico SQL en tablas. Sin embargo, pueden haber escenarios controlados por la lógica de negocios que requieren realizar operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no expuesta. Por ejemplo, puede:  
  
-   Realizar una operación en artefactos de base de datos que no se exponen a través de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtenga el CURVAL o NEXTVAL de las secuencias de Oracle.  
  
-   Realizar operaciones de lenguaje de definición de datos; Por ejemplo, crear una tabla.  
  
-   Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal que se crea mediante la lógica de negocios.  
  
-   Realizar operaciones más complejas de DML en tablas que las operaciones que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies; por ejemplo, para realizar una consulta que incluye una cláusula de combinación.  
  
 Para estos tipos de escenarios, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] emerge la operación SQLEXECUTE. La operación SQLEXECUTE aparece bajo el nodo raíz (/) en el **seleccione una categoría de** panel en el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].  
  
 Mediante la operación SQLEXECUTE, puede realizar una instrucción SQL con parámetros en la base de datos de Oracle. La operación SQLEXECUTE admite un bloque de parámetro de entrada que consta de los conjuntos de parámetros que permiten ejecutar la misma instrucción SQL una vez para cada conjunto. La operación SQLEXECUTE devuelve los resultados de la instrucción SQL en un conjunto de registros genérico.  
  
> [!NOTE]
>  Puede pasar en y en los parámetros OUT procedimientos, funciones y paquetes en la operación SQLEXECUTE. El artefacto invocado se ejecutará con los parámetros proporcionados en la base de datos de Oracle; Sin embargo, la operación SQLEXECUTE devuelve el valor de salida y los parámetros en espera para el cliente. Si desea invocar procedimientos, funciones o paquetes, se recomienda hacerlo mediante la invocación de las operaciones dedicadas que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.  
  
 Para obtener más información acerca de:  
  
-   Realizar una operación SQLEXECUTE mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operación SQLEXECUTE mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md).  
  
-   Realizar una operación SQLEXECUTE mediante el modelo de servicio WCF, vea [ejecutar SQLEXECUTE operación mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).  
  
-   Realizar la operación SQLEXECUTE mediante el modelo de canal WCF, consulte [ejecutar SQLEXECUTE operación mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).  
  
-   Estructura y acciones SOAP para llevar a cabo una operación SQLEXECUTE mensajes, vea [esquemas de mensaje para la operación SQLEXECUTE](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)