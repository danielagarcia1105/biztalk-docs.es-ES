---
title: Proteger las aplicaciones de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7f61e15b94d741e6bfc2a9f951655ff4358a001
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982917"
---
# <a name="secure-your-oracle-database-applications"></a>Proteger las aplicaciones de base de datos de Oracle
## <a name="data-protection-and-security-overview"></a>Información general de seguridad y protección de datos
A menudo, una base de datos contiene información empresarial confidencial, como los detalles de la cuenta de cliente. Las aplicaciones que usan el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión. Seguridad y protección de datos normalmente son pensar en los siguientes términos:  
  
- *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
- *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
- *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
- *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
  Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. El adaptador usa estas credenciales para abrir las conexiones a la base de datos de Oracle. Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] proporciona los métodos alternativos que puede usar para proporcionar estas credenciales en forma más segura.  
  
  Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre la base de datos de Oracle y el adaptador](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [Seguridad con el adaptador de base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [Programación segura con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [Procedimientos recomendados](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)