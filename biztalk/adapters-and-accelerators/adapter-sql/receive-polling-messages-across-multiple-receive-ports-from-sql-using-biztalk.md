---
title: Recepción de sondeo el mensajes a través de varios puertos de recepción de SQL con BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be084ca9e0a90813a541563bf6f600ea277aec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223964"
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a>Recepción de sondeo mensajes a través de varios puertos de recepción de SQL con BizTalk Server
Considere un escenario donde desea crear una aplicación de BizTalk que incluye dos operaciones de sondeo. Cada operación de sondeo sondea tablas independientes, empleados y clientes, desde la misma base de datos. Al implementar este tipo de aplicación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe crear dos puertos de recepción. El URI de conexión para cada puerto de recepción será:  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 Dado que los procesos de recepción puertos están recibiendo mensajes de sondeo de la misma base de datos en el mismo servidor, el URI de conexión para ambos serán los mismos. Sin embargo, una aplicación de BizTalk no puede tener dos puertos con el mismo URI de conexión de recepción.  
  
 Para permitir que los clientes de adaptador tiene dos puertos de recepción que sondean la misma base de datos (o incluso la misma tabla en una base de datos) en una aplicación de BizTalk, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona una propiedad de conexión, **InboundID**. Puede especificar cualquier valor para esta propiedad de conexión. Al agregar el identificador de entrada, una conexión URI se convierte en único. Por ejemplo:  
  
 El URI de conexión para el puerto de recepción de mensajes de sondeo de la tabla de empleados puede ser:  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 De forma similar, puede ser el URI de conexión para el puerto de recepción de mensajes de sondeo para la tabla Customer:  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 Dado que el URI de conexión se convierten en únicos agregando el **InboundID** propiedad, ahora puede tener varios sondear la misma base de datos o tabla en una sola aplicación de BizTalk de puertos de recepción.  
  
> [!IMPORTANT]
>  Puede especificar el **InboundID** propiedad de conexión tanto para el **sondeo** y **TypedPolling** operaciones.  
  
## <a name="see-also"></a>Vea también  
 [Sondear el servidor de SQL con el adaptador de SQL BizTalk Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)