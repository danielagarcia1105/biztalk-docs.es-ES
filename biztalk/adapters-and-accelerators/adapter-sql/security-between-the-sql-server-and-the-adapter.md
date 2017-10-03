---
title: Seguridad entre el servidor SQL Server y el adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8673aee316a8a2ef83011ab3dd85016a99df1162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sql-server-and-the-adapter"></a>Seguridad entre el servidor SQL Server y el adaptador
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es compatible con los métodos estándar, como IPSEC y SSO se usan para proteger intercambios de datos con el servidor de base de datos. Intercambios de datos no segura pueden exponer datos a los agentes no autorizados. Para obtener información sobre los problemas de seguridad con SQL Server, vea [consideraciones de seguridad para SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=196954) en la documentación de SQL.  
  
 Puede mejorar la seguridad de los intercambios de datos mediante el uso de seguridad de protocolo de Internet (IPsec). IPsec es un marco de estándares abiertos para proteger las comunicaciones a través de redes de protocolo de Internet (IP). Con IPSec, los datos intercambian entre el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL server a través de la red está cifrada, lo que dificulta actores no autorizados usar los datos. Para obtener más información acerca de IPsec y sobre el uso de IPsec con productos de Microsoft, vea el artículo de Microsoft TechNet [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955).  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite SSO y la seguridad integrada para la autenticación en las conexiones que establece con la base de datos. Con SSO, las credenciales se cifran y almacenan en el registro. El sistema usa estas credenciales para determinar el acceso en lugar de requerir al usuario que escriba ellos donde podría verse por los actores no autorizados. La seguridad integrada utiliza las credenciales del usuario con sesión iniciada para tener acceso a SQL server. Esto también elimina la necesidad de los usuarios escriban las credenciales. El Administrador de base de datos debe configurar SQL para aceptar las credenciales de los usuarios para la seguridad integrada para que funcione correctamente.  
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)