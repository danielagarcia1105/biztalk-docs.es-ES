---
title: Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a>Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF
Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de SQL Server.  
  
 Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que expone el modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en la base de datos SQL. Este control procede del hecho de que en el modelo de canal WCF, puede controlar directamente el contenido de los mensajes que envía a través del canal.  
  
 En determinados escenarios, este nivel adicional de control puede ser beneficioso. Por ejemplo, cuando se usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar selectivamente las columnas de las filas de destino mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje. Las únicas columnas que son necesarias son los que tienen "nillable = false" en el archivo WSDL. El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipada de la plantilla que incluye todas las columnas en el esquema de tabla.  
  
 Las secciones en este tema explica cómo realizar operaciones en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el modelo de canal WCF.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el modelo de canal WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [Crear un canal con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [Recibir mensajes de cambio de datos basado en sondeo de SQL Server mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)