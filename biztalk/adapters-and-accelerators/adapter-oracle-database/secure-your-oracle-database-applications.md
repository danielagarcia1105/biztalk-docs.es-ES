---
title: Proteger las aplicaciones de base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8601463c02e32221c369023f05ed2fd3731bb4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-oracle-database-applications"></a>Proteger las aplicaciones de base de datos de Oracle
## <a name="data-protection-and-security-overview"></a>Información general de seguridad y protección de datos
A menudo, una base de datos contiene la información empresarial confidencial, como los detalles de cuenta del cliente. Las aplicaciones que utilizan el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión. Seguridad y protección de datos normalmente se considera de en los siguientes términos:  
  
-   *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
-   *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
-   *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
-   *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
 Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. El adaptador utiliza estas credenciales para abrir las conexiones a la base de datos de Oracle. Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] proporciona métodos que puede usar para proporcionar estas credenciales de forma más segura.  
  
 Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre la base de datos de Oracle y el adaptador](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [Seguridad con el adaptador de la base de datos de Oracle y el servidor BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [Programación segura con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [Prácticas recomendadas](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)