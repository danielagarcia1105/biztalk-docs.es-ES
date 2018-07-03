---
title: Desarrollar aplicaciones de base de datos de Oracle en BizTalk Server | Microsoft Docs
description: Crear aplicaciones de base de datos de Oracle mediante WCF, o en el servidor BizTalk Server con el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a685b2-ac17-4949-bc77-001f56450847
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f83d335f92798a8d1b2c4c2c32cb20e23ffe26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977669"
---
# <a name="develop-your-oracle-database-applications"></a>Desarrollar aplicaciones de base de datos de Oracle

## <a name="overview"></a>Información general
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Las aplicaciones cliente pueden consumir el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para invocar operaciones en los artefactos de base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] pueden utilizarse:  
  
- A través de un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Mediante la invocación de métodos en una instancia de un [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] proxy de cliente.  
  
- Como hospedados [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service.  
  
- Mediante el envío de mensajes SOAP a través de una instancia de canal en el código que usa el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal.  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>Canal WCF de BizTalk frente a WCF service frente a  
 En la tabla siguiente:  
  
- Enumera las distintas operaciones que se pueden realizar en una base de datos de Oracle mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
- Proporciona vínculos a temas que contienen información acerca de cómo realizar la tarea mediante el enfoque elegido ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], modelo o el modelo de canal WCF del servicio WCF).  
  
|Tarea|BizTalk Server|Modelo de servicio WCF|Modelo del canal de WCF|  
|----------|--------------------|-----------------------|-----------------------|  
|Básicas Insert, Update, Delete y las operaciones Select en las tablas y vistas|[Insertar, actualizar, eliminar o seleccionar las operaciones mediante BizTalk Server con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)|[Insertar, actualizar, eliminar o seleccionar las operaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)|[Ejecutar una operación de inserción en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|Operaciones en tablas y vistas que contienen datos de LOB|[Ejecutar operaciones en tablas con tipos de datos de objetos grandes en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)|[Completar operaciones en tablas con tipos de datos de gran tamaño en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)||  
|Operaciones en funciones y procedimientos almacenados|[Invocar funciones y procedimientos de la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)|[Invocar una función de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)|  
|Invocar funciones y procedimientos sobrecargados|[Invocar funciones sobrecargadas y los procedimientos de la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)||  
|Operaciones en funciones y procedimientos parámetros con REF CURSOR|[Invocar funciones y procedimientos con cursores REF cursor en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)|[Ejecutar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)||  
|Operaciones en funciones y procedimientos con tipos de registros|[Invocar funciones y procedimientos con tipos de registros en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)|[Ejecutar operaciones de uso de tipos de registro de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)||  
|Operaciones en tablas y vistas con tipos de datos BFILE|[Ejecutar operaciones en tablas con tipos de datos BFILE de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)|||  
|Operación SQLEXECUTE|[Ejecutar la operación SQLEXECUTE en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)|[Ejecutar la operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)|[Ejecutar una operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|Recepción de mensajes de cambio de datos basados en sondeos|[Sondeo de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)|[Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)|[Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)|  
|Realizar operaciones compuestas en la base de datos de Oracle|[Ejecutar operaciones compuestas en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)|||  
|Recibir notificaciones de cambio de base de datos|[Recibir notificaciones de cambio de base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[Recibir notificaciones de cambio de base de datos de Oracle mediante el Modelo1 de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)||  
  

  
## <a name="next-steps"></a>Pasos siguientes
 Los temas de esta sección proporcionan información de procedimientos y ejemplos que le ayudarán a desarrollar aplicaciones que consumen el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] tanto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] programación de soluciones. 
  
-   [Crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)
  
-   [Obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) 
  
-   [Configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)
  
-   [Hacer streaming de tipos de datos de objetos grandes en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)
  
-   [Recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)
  
-   [Desarrollo de aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md)
  
-   [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)  
  
-   [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
  
-   [Obtener metadatos mediante programación de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)  
  
-   [Usar el adaptador de base de datos de Oracle con SharePoint](../../adapters-and-accelerators/adapter-oracle-database/use-the-oracle-database-adapter-with-sharepoint.md)
  
-   [Ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)  
  
-   [Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)

- [Usar svcutil.exe](use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)