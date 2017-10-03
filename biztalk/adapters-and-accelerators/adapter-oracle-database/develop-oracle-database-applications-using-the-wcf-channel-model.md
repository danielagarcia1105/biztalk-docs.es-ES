---
title: Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77fb9b6ca1fc70a55b59c6708450b8d94a01eff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de la base de datos de Oracle.  
  
 Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en la base de datos de Oracle. ¿Por qué? En el modelo del canal WCF controla directamente el contenido de los mensajes que envía a través del canal.  
  
 En determinados escenarios, este nivel adicional de control puede ser beneficioso. Por ejemplo, cuando se usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar selectivamente las columnas de las filas de destino mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje. El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipada de la plantilla que incluye todas las columnas en el esquema de tabla. Si tiene una columna "nillable = false" en el archivo WSDL, debe actualizarse mediante el modelo de servicio WCF.  
  
 Otra ventaja clave que proporciona el modelo de canal WCF en el modelo de servicio WCF es compatible con más completa-to-end de transmisión por secuencias de tipos de datos de objetos grandes (LOB) de Oracle. Mediante el modelo de canal WCF puede realizar-to-end de transmisión por secuencias:  
  
-   Para actualizar una columna LOB en una tabla o vista mediante la operación de UpdateLOB.  
  
-   En horizontal y en los parámetros que contienen datos devueltos por procedimientos y funciones de LOB.  
  
-   En los datos LOB que se encuentra en el resultado de una operación SQLEXECUTE.  
  
-   En las columnas de datos LOB que se devuelven en la operación de POLLINGSTMT.  
  
-   En las columnas de datos LOB que son devueltos por una operación Select en una tabla o vista.  
  
 Esto es porque en el modelo de canal WCF puede controlar directamente cómo proporcionar el cuerpo del mensaje en los mensajes salientes y la forma de procesar el cuerpo del mensaje en los mensajes entrantes.  
  
 En cambio, solo se proporciona el modelo de servicio WCF:  
  
-   To-end para datos LOB en una operación, la operación de ReadLOB de transmisión por secuencias.  
  
-   Ninguna capacidad de actualizar los datos LOB en la base de datos de Oracle de manera secuenciada.  
  
 Las secciones en este tema explica cómo realizar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de canal WCF con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [Crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [Invocar operaciones en la base de datos de Oracle utilizando el modelo del canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Ejecutar una operación SQLEXECUTE en base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Ejecutar una operación Insert en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Invocar una función de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Recibir mensajes de cambio de datos basado en sondeo de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [Transmisión por secuencias tipos de datos LOB de base de datos de Oracle, utilizando el modelo del canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)