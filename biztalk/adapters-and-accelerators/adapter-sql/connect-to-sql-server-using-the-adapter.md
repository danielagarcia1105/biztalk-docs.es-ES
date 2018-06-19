---
title: Conectarse a SQL Server mediante el adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 727d73e6-fb84-48ce-ae72-5de70dcae8b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b837aa4e0bc0a815434307b10d249dccf54d70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222140"
---
# <a name="connect-to-sql-server-using-the-adapter"></a>Conectarse a SQL Server mediante el adaptador
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] requiere que los clientes de adaptador proporcionar una cadena de conexión, llamada a la conexión Uniform Resource Identifier (URI), para conectarse a la base de datos de SQL Server. Internamente, la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] asigna el URI en una cadena de conexión de base de datos para conectarse a la base de datos de SQL Server. Con un URI de conexión, los clientes de adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
 En el URI de conexión, también puede especificar el nombre de una base de datos de SQL Server de conmutación por error en un equipo en espera para conectarse a si la base de datos principal de SQL Server no está disponible. La base de datos de SQL Server de conmutación por error debe ser un reflejo de la base de datos principal de SQL Server. La base de datos de SQL Server de conmutación por error se especifica utilizando un parámetro opcional, FailoverPartner, en el URI de conexión. Proporcionar una base de datos de SQL Server de conmutación por error garantiza la alta disponibilidad y redundancia de datos. Para obtener más información sobre la alta disponibilidad con respecto a SQL Server, vea [creación de reflejo de base de datos en SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).
  
 Asegúrese de que cumple con las normas de seguridad al establecer una conexión con la base de datos de SQL Server. Para obtener más información acerca de las instrucciones de seguridad, consulte [proteger sus aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [Crear una conexión a SQL Server](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)