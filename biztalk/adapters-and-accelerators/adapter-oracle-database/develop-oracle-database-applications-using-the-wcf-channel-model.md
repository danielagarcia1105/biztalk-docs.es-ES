---
title: Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4990ebb9e9aad612a82af42b3d186643da1e91ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002733"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] mediante el envío de mensajes XML directamente a través de una instancia de canal creada con el enlace de la base de datos de Oracle.  
  
 Una ventaja de utilizar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo de canal proporciona un control más minucioso sobre las operaciones que se realizan en la base de datos de Oracle. ¿Por qué? En el modelo de canal WCF controla directamente el contenido de los mensajes que envían a través del canal.  
  
 En determinados escenarios, este nivel adicional de control puede ser beneficioso. Por ejemplo, cuando usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar columnas de las filas de destino selectivamente mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje. El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipados para la plantilla que incluye todas las columnas en el esquema de tabla. Si tiene una columna "nillable = false" en el archivo WSDL, debe actualizarse mediante el modelo de servicio WCF.  
  
 Otra ventaja clave que proporciona el modelo de canal WCF con respecto al modelo de servicio WCF es compatible con más completa al extremo de streaming de tipos de datos de objetos grandes (LOB) de Oracle. Mediante el modelo de canal WCF puede realizar streaming to-end:  
  
- Para actualizar una columna LOB de una tabla o vista mediante la operación UpdateLOB.  
  
- Al final y en los parámetros que contienen LOB datos devueltos por procedimientos y funciones.  
  
- En los datos LOB que se encuentra en el resultado de una operación SQLEXECUTE.  
  
- En las columnas de datos LOB que se devuelven en la operación POLLINGSTMT.  
  
- En las columnas de datos LOB que son devueltos por una operación Select en una tabla o vista.  
  
  Esto es porque en el modelo de canal WCF directamente controlar cómo proporcionar el cuerpo del mensaje en los mensajes salientes y cómo se procesa el cuerpo del mensaje en los mensajes entrantes.  
  
  En cambio, sólo se proporciona el modelo de servicio WCF:  
  
- To-end para los datos LOB en una sola operación, la operación ReadLOB de transmisión por secuencias.  
  
- Ninguna posibilidad de actualizar los datos LOB en la base de datos de Oracle de manera secuenciada.  
  
  Las secciones de este tema explican cómo realizar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general del modelo del canal WCF con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [Crear un canal con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [Invocar operaciones en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Ejecutar una operación SQLEXECUTE en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Ejecutar una operación de inserción en la base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Invocar una función de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [Streaming tipos de datos LOB de base de datos de Oracle, mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)