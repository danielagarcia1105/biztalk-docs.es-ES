---
title: Proteger las aplicaciones de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eabb9c260ed835a7c4cac3183000327767bb9cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014517"
---
# <a name="secure-your-sql-applications"></a>Proteger las aplicaciones de SQL
## <a name="overview"></a>Información general
Las bases de datos de SQL Server suelen contengan información empresarial confidencial, como los detalles de la cuenta de cliente. Las aplicaciones que usan el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión. Seguridad y protección de datos normalmente son pensar en los siguientes términos:  
  
- *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
- *Autenticación* proporciona mecanismos para comprobar la identidad del solicitante.  
  
- *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
- *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
  Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. El adaptador usa estas credenciales para abrir conexiones con el sistema SQL. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite las credenciales que proporcionarse en el URI de conexión. Esto impide que las credenciales de introducción expuesto accidentalmente. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] proporciona dos métodos alternativos para proporcionar estas credenciales en un modo más seguro:  
  
  Seguridad integrada. En este caso, el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credenciales. Debe configurar el servidor de SQL server para que acepte estas credenciales para que funcione este método.  
  
  Enterprise Single Sign-on (SSO). Para obtener más información sobre el uso de SSO, vea [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .  
  
  Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre el servidor SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [Seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [Programación segura con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [Procedimientos recomendados](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)