---
title: Proteger las aplicaciones de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad63e44e4d2dde5ffee743e0758a37e48a3d4d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012061"
---
# <a name="secure-your-siebel-applications"></a>Proteger las aplicaciones de Siebel
El sistema de Siebel a menudo contiene información empresarial confidencial, como los detalles de la cuenta de cliente. Las aplicaciones que usan el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión. Seguridad y protección de datos normalmente son pensar en los siguientes términos:  
  
- *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
- *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
- *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
- *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
  Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. El adaptador usa estas credenciales para abrir conexiones con el sistema Siebel. Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona los métodos alternativos que puede usar para proporcionar estas credenciales en forma más segura.  
  
  Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Seguridad entre el sistema de Siebel y el adaptador](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [Programación segura con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [Procedimientos recomendados para proteger el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)