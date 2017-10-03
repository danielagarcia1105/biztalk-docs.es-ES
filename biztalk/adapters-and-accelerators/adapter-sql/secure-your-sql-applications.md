---
title: Proteger las aplicaciones SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sql-applications"></a>Proteger las aplicaciones de SQL
## <a name="overview"></a>Información general
Las bases de datos de SQL Server suelen contengan información empresarial confidencial, como los detalles de cuenta del cliente. Las aplicaciones que utilizan el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión. Seguridad y protección de datos normalmente se considera de en los siguientes términos:  
  
-   *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
-   *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
-   *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
-   *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
 Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. El adaptador utiliza estas credenciales para abrir conexiones con el sistema SQL. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no permitir credenciales debe proporcionarse en el URI de conexión. Esto impide que las credenciales obtener expone accidentalmente. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona dos métodos alternativos para proporcionar estas credenciales de un modo más seguro:  
  
 Seguridad integrada. En este caso, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credenciales. Debe configurar el servidor de SQL server para que acepte estas credenciales para que funcione este método.  
  
 Enterprise Single Sign-on (SSO). Para obtener más información acerca del uso de SSO, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .  
  
 Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre el servidor SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [Seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [Programación segura con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [Prácticas recomendadas](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)