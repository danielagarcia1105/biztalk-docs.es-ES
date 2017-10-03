---
title: "Información general sobre el adaptador de BizTalk para SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d0c1fd3ce3a9f07367b7cc75ffeeb98f84b119
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>Información general sobre el adaptador de BizTalk para SQL Server
La [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone la base de datos de SQL Server como un servicio WCF. Los clientes de adaptador pueden realizar operaciones en la base de datos de SQL Server mediante el intercambio de mensajes SOAP con el adaptador. El adaptador consume el mensaje SOAP y realiza llamadas ADO.NET adecuadas para realizar la operación. El adaptador devuelve la respuesta de la base de datos de SQL Server al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] metadatos de las superficies de artefactos de la base de datos de SQL Server (por ejemplo, tablas, vistas y procedimientos).  Estos metadatos describen la estructura de un mensaje SOAP con el formato de lenguaje de descripción de servicios Web (WSDL). El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones. El adaptador también genera artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectar con SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza ADO.NET para comunicarse con la base de datos de SQL Server. Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para comunicarse con la base de datos de SQL Server de las maneras siguientes:  
  
-   Al desarrollar aplicaciones de BizTalk. Para obtener más información, consulte [BizTalk desarrollar aplicaciones](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).  
  
-   Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Para obtener más información, consulte [desarrollar las aplicaciones que usan el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).  
  
-   Mediante el modelo de canal WCF. Para obtener más información, consulte [desarrollar aplicaciones con el modelo del canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador de SQL Server?](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [¿Cómo los metadatos de adaptador expuesta de SQL Server?](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [Las operaciones que son compatibles con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)