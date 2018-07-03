---
title: Desarrollar aplicaciones de SQL en BizTalk Server | Microsoft Docs
description: Crear aplicaciones de adaptador SQL mediante WCF, o en el servidor BizTalk Server con el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac4b5b0-2980-4784-a081-e795654292ed
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b003010ae8cb9394dd956a97bd3e05ef855d3e73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978461"
---
# <a name="develop-your-sql-applications"></a>Desarrollar aplicaciones de SQL

## <a name="overview"></a>Información general
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace. Las aplicaciones cliente pueden consumir el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para invocar operaciones en los artefactos de SQL Server. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pueden utilizarse:  
  
- A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Mediante la invocación de métodos en una instancia de un proxy de cliente.  
  
- Como un servicio WCF hospedado.  
  
- Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el modelo de canal WCF.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>Canal WCF de BizTalk frente a WCF service frente a    
 En la tabla siguiente:  
  
- Enumera las distintas operaciones que se pueden realizar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
- Proporciona vínculos a temas que contienen información acerca de cómo realizar la tarea mediante el enfoque elegido ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo de servicio WCF, el modelo del canal WCF).  
  
|Tarea|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|  
|----------|--------------------|-----------------------|-----------------------|  
|Realizar básicas Insert, Update, Delete y las operaciones Select en las tablas y vistas|[Insertar, actualizar, eliminar o seleccionar las operaciones mediante BizTalk Server con el adaptador de SQL](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)|[Insertar, actualizar, eliminar o seleccionar las operaciones en tablas y vistas que usan el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)|  
|Columnas de tipo de la realización de operaciones en tablas y vistas con datos de gran tamaño<br /><br /> (También incluye información acerca de las operaciones de FILESTREAM mediante el adaptador)|[Operaciones en tablas y vistas que contienen tipos de datos de gran tamaño mediante el adaptador de SQL](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)|[Ejecutar operaciones en tablas y vistas con tipos de datos grandes en SQL mediante el modelo de servicio de WCF](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)|-|  
|Ejecutar procedimientos almacenados|[Ejecutar procedimientos almacenados en SQL Server mediante BizTalk Server](execute-stored-procedures-in-sql-server-using-biztalk-server.md)|[Invocar procedimientos almacenados en SQL mediante el modelo de servicio de WCF](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)|-|  
|Ejecutar procedimientos almacenados con parámetros de inicio único sin utilizar una orquestación de BizTalk|[Ejecutar procedimientos almacenados con un solo parámetro XML en SQL Server mediante BizTalk Server](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)|-|-|  
|Ejecutar procedimientos almacenados que contienen una cláusula FOR XML en la definición|[Ejecutar procedimientos almacenados con una cláusula FOR XML en SQL Server mediante BizTalk Server](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)|-|-|  
|Realizar operaciones compuestas en SQL Server|[Ejecutar operaciones compuestas en SQL Server con BizTalk Server](run-composite-operations-on-sql-server-using-biztalk-server.md)|-|-|  
|Invocar funciones escalares en SQL Server|[Invocar funciones escalares en SQL Server mediante BizTalk Server](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)|[Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|Invocar funciones con valores de tabla en SQL Server|[Invocar funciones con valores de tabla en SQL Server mediante BizTalk Server](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)|[Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|Realizar **ExecuteReader**, **ExecuteScalar**, o **ExecuteNonQuery** operaciones|[ExecuteReader, ExecuteScalar o ExecuteNonQuery operaciones en SQL con BizTalk Server](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)|[Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)|-|  
|Recepción de mensajes de cambio de datos basados en sondeos|[Sondear el servidor SQL con el adaptador de SQL BizTalk Server](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)|[Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)|[Recibir mensajes basados en sondeos de cambio de datos de SQL Server mediante el modelo de canal de WCF](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)|  
|Recibir notificaciones de SQL Server|[Recibir notificaciones de consulta SQL con BizTalk Server](receive-sql-query-notifications-using-biztalk-server.md)|[Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF](receive-query-notifications-from-sql-using-the-wcf-service-model.md)|-|  

## <a name="next-steps"></a>Pasos siguientes  
 Los temas de esta sección proporcionan información de procedimientos y ejemplos que le ayudarán a desarrollar aplicaciones que consumen el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y soluciones de programación. NET. 

- [Crear una conexión a SQL Server](create-a-connection-to-sql-server.md)
- [Obtener metadatos para operaciones de SQL Server en Visual Studio](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
- [Identificadores de nodo de metadatos](metadata-node-ids2.md)
- [Trabajar con las propiedades de enlace](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
- [Requisito previo: configurar MSDTC](configure-msdtc-on-sql-server-and-adapter-client.md)
- [Desarrollar aplicaciones de BizTalk con el adaptador de SQL](develop-biztalk-applications-using-the-sql-adapter.md)
- [Desarrollar aplicaciones con el modelo de servicio WCF](develop-sql-applications-using-the-wcf-service-model.md)
- [Desarrollar aplicaciones con el modelo de canal WCF](develop-sql-applications-using-the-wcf-channel-model.md)
- [Ejemplos](samples-for-the-sql-adapter.md)
- [Configurar el nivel de aislamiento de transacción y el tiempo de espera de la transacción](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
  
