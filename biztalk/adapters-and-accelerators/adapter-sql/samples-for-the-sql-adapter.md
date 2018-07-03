---
title: Ejemplos de adaptadores de SQL | Microsoft Docs
description: Ejemplos de adaptadores de WCF SQL que se pueden usar con BizTalk Server, el modelo de servicio WCF y el modelo del canal WCF
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f7ff1e686fd8de344c4de4513fbda84003c69a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982637"
---
# <a name="samples-for-the-sql-adapter"></a>Ejemplos del adaptador de SQL

Ejemplos para [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] se clasifican en categorías:  
  
- Ejemplos de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
- Ejemplos de modelo de servicio WCF  
  
- Ejemplos de modelo de canal WCF  
  
Los ejemplos están disponibles en [BizTalk Adapter Pack 2010: ejemplos de adaptadores de SQL](https://www.microsoft.com/download/details.aspx?id=22455). Los scripts SQL para crear los objetos que utilizan en los ejemplos, como la base de datos, tablas, y se incluyen los procedimientos. 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
En la lista siguiente describe los ejemplos.
  
## <a name="biztalk-server-samples"></a>Ejemplos de BizTalk Server  
  
|  Nombre del directorio de ejemplo  |                                                                                          Descripción                                                                                          |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ExecuteStoredProcedure  |      Se muestra cómo invocar un procedimiento almacenado en la base de datos de SQL Server mediante el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .      |
|       SelectTable       |  Muestra cómo realizar una operación Select en una tabla de base de datos de SQL Server mediante el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  |
|   CompositeOperations   |    Muestra cómo realizar operaciones compuestas en una base de datos de SQL Server mediante el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].    |
|      TypedPolling       |   Muestra cómo realizar el sondeo fuertemente tipada en una base de datos de SQL Server mediante el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].   |
|   FILESTREAMOperation   | Muestra cómo realizar operaciones de FILESTREAM en una base de datos de SQL Server 2008 con el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. |
| IncrementalNotification | Muestra cómo recibir notificaciones incrementales de una base de datos de SQL Server mediante el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. |
| Employee_PurchaseOrder  |                  Ejemplo basado en [Tutorial 2: empleado: proceso de pedido de compra mediante el adaptador de SQL](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).                  |
  
## <a name="wcf-service-model-samples"></a>Ejemplos de modelo de servicio WCF   
  
|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|EmployeeBasicOps|Muestra cómo realizar Insert, Select, Update y, en una base de datos de SQL Server mediante el adaptador de la operación de eliminación.|  
|ExecuteReader|Muestra cómo invocar una operación ExecuteReader en una base de datos de SQL Server mediante el adaptador.|  
|Execute_StoredProc|Muestra cómo invocar un procedimiento almacenado en la base de datos de SQL Server mediante el adaptador.|  
|Execute_TypedStoredProcedure|Muestra cómo invocar un procedimiento almacenado en la base de datos de SQL Server mediante el adaptador fuertemente tipado.|  
|Records_FILESTREAM_Op|Muestra cómo actualizar los datos FILESTREAM en una tabla de base de datos de SQL Server mediante el adaptador.|  
|ScalarFunction_ServiceModel|Muestra cómo invocar funciones escalares en una base de datos de SQL Server mediante el adaptador.|  
|TableFunction_ServiceModel|Muestra cómo invocar funciones con valores de tabla en una base de datos de SQL Server mediante el adaptador.|  
|Polling_ServiceModel|Muestra cómo recibir mensajes de cambio de datos basados en sondeos de una base de datos de SQL Server mediante el adaptador.|  
|TypedPolling_ServiceModel|Muestra cómo recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde una base de datos de SQL Server mediante el adaptador.|  
|Notification_ServiceModel|Muestra cómo recibir notificaciones de consulta de una base de datos de SQL Server mediante el adaptador.|  
  
## <a name="wcf-channel-model-samples"></a>Ejemplos de modelo de canal WCF 
  
|Nombre del directorio de ejemplo|Descripción|  
|---------------------------|-----------------|  
|EmployeeInsertOp|Muestra cómo realizar una operación de inserción en una base de datos de SQL Server mediante el adaptador.|  
|Polling_ChannelModel|Muestra cómo recibir mensajes de cambio de datos basados en sondeos de una base de datos de SQL Server mediante el adaptador.|  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones SQL](develop-your-sql-applications.md)