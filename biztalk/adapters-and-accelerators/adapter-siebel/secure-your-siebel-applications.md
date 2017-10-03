---
title: Proteger sus aplicaciones Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b597120de91b6a09fdc26b90a2cb357cdc7dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-siebel-applications"></a>Proteger las aplicaciones de Siebel
El sistema Siebel a menudo contiene información empresarial confidencial, como los detalles de cuenta del cliente. Las aplicaciones que utilizan el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida puede accidentalmente exponerla obtener acceso a los actores no autorizados, a menos que se haga un esfuerzo para proteger y proteger los datos durante la transmisión. Seguridad y protección de datos normalmente se considera de en los siguientes términos:  
  
-   *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
-   *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
-   *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
-   *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, por lo que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
 Otra área importante del problema es las credenciales de contraseña de nombre de usuario que proporcione al [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. El adaptador utiliza estas credenciales para abrir conexiones con el sistema Siebel. Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona métodos que puede usar para proporcionar estas credenciales de forma más segura.  
  
 Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que desarrolle con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre el adaptador y el sistema Siebel](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [Programación segura con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [Prácticas recomendadas para proteger el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)