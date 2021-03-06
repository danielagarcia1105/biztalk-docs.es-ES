---
title: Las operaciones que son compatibles con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e61230ed2244bc4bb7c79f87c18879c3c83f7f95
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011277"
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a>Las operaciones que son compatibles con el adaptador de SQL
Puede usar a los clientes del adaptador para realizar operaciones en la base de datos de SQL Server mediante:  
  
- Crear proyectos de BizTalk  
  
- Mediante el modelo de servicio WCF  
  
- Mediante el modelo de canal WCF  
  
  La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones. Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal. Si se requiere una respuesta, se devuelve en un mensaje SOAP a través del canal mismo. Para obtener información acerca de la estructura del mensaje y la acción de SOAP asociada con cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).  
  
  Esta sección proporciona información acerca de las operaciones admitidas en la base de datos de SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)