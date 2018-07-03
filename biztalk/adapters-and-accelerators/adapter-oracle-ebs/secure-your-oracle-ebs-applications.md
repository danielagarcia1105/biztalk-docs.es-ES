---
title: Proteger las aplicaciones de Oracle EBS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bf79d6a1324658101c2f12de758848ce7794fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996949"
---
# <a name="secure-your-oracle-ebs-applications"></a>Proteger las aplicaciones de Oracle EBS
Las aplicaciones de Oracle E-Business tratan con la información empresarial confidencial, como los detalles de la cuenta de cliente. Las aplicaciones que usan el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] para tener acceso y modificar esta información ya sea localmente o a través de una red distribuida podría accidentalmente exponerla para tener acceso a los actores no autorizado, a menos que se realizan los esfuerzos para proteger y asegurar los datos durante transmisión. Seguridad y protección de datos normalmente son pensar en los siguientes términos:  
  
- *Autorización* controla el acceso a un recurso basado en la identidad del solicitante.  
  
- *Autenticación* proporciona mecanismos para comprobar la identidad de un solicitante.  
  
- *Confidencialidad de los datos* proporciona mecanismos para proteger la privacidad de los datos mediante cifrado.  
  
- *Integridad de los datos* proporciona mecanismos para firmar digitalmente los datos, para que el receptor puede asegurarse de que los datos no se ha modificado en tránsito.  
  
  Otra área importante de preocupación es las credenciales de contraseña de nombre de usuario que proporcione a los [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. El adaptador usa estas credenciales para abrir las conexiones a la base de datos de Oracle. Estas credenciales se pueden proporcionar en la conexión URI; Sin embargo, dado que el nombre de usuario y la contraseña son texto no cifrado, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona los métodos alternativos que puede usar para proporcionar estas credenciales en forma más segura.  
  
  Los temas de esta sección proporcionan directrices para ayudarle a mejorar la seguridad de las soluciones que se desarrollan con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
