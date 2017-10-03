---
title: Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server | Documentos de Microsoft
description: Estructura XML de mensajes y tipos de datos utilizado por el adaptador de SQL Server para que BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b1e45f0a20500253e2ca831138a21efa24df3c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a>Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server

## <a name="overview"></a>Información general
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones. Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal. Si es necesario recibir una respuesta, se devuelve en un mensaje SOAP en el mismo canal.  
  
 Como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone metadatos para sus operaciones y tipos de datos mediante estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mecanismos. Las secciones de este tema describen la estructura XML de los mensajes y los tipos de datos que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Tipos de datos básicos de SQL Server](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [Esquemas de mensaje para insertar, actualizar, eliminar y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [Esquemas de mensaje para los procedimientos y funciones](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [Esquemas de mensaje para las operaciones de TypedPolling y sondeo](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [Esquemas de mensaje de notificación de consulta](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [Esquemas de mensaje para operaciones compuestas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [Esquemas de mensaje para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  
