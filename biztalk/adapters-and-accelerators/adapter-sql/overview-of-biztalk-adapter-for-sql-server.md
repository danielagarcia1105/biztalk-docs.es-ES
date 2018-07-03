---
title: Información general del adaptador de BizTalk para SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c9393504332da636de8b09cca0e76f4dfe0da6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983461"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>Información general del adaptador de BizTalk para SQL Server
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone la base de datos de SQL Server como un servicio WCF. Los clientes del adaptador pueden realizar operaciones en la base de datos de SQL Server mediante el intercambio de mensajes SOAP con el adaptador. El adaptador consume el mensaje SOAP y realiza llamadas ADO.NET adecuadas para realizar la operación. El adaptador devuelve la respuesta de la base de datos de SQL Server al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] superficies de metadatos de artefactos de la base de datos de SQL Server (por ejemplo, tablas, vistas y procedimientos).  Estos metadatos describen la estructura de un mensaje SOAP en forma de lenguaje de descripción de servicios Web (WSDL). El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes del adaptador recuperar metadatos para las operaciones. El adaptador genera también los artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectar con SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa ADO.NET para comunicarse con la base de datos de SQL Server. Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para comunicarse con la base de datos de SQL Server de las maneras siguientes:  
  
- Mediante el desarrollo de aplicaciones de BizTalk. Para obtener más información, consulte [BizTalk desarrollar aplicaciones](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).  
  
- Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Para obtener más información, consulte [desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).  
  
- Mediante el modelo de canal WCF. Para obtener más información, consulte [desarrollar aplicaciones con el modelo de canal WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador de SQL Server?](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [¿Cómo los metadatos de adaptador expuesta de SQL Server?](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [Las operaciones que son compatibles con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Descripción del adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)