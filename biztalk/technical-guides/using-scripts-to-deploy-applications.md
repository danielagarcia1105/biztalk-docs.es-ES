---
title: Uso de Scripts para implementar aplicaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc96c3b591baf81806182b6c3e988a46dd208ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="using-scripts-to-deploy-applications"></a>Uso de Scripts para implementar aplicaciones
Debe utilizar secuencias de comandos para implementar aplicaciones de BizTalk siempre que sea posible. Secuencias de comandos, reducen el riesgo de error humano durante el proceso de implementación. También debe documentar los procedimientos de implementación en profundidad. Debe documentar todo lo que no script con pasos muy detallados. Esto incluye documentar los cambios a sistemas externos y a la implementación de componentes de terceros.  
  
## <a name="using-btstask"></a>Uso de BTSTask  
 Puede usar BTSTask.exe para incluir la creación de aplicaciones de BizTalk, así como para importar archivos de script en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] paquetes .msi. Si se crea el script la creación de las aplicaciones, a continuación, los paquetes pueden se generan automáticamente mediante un proceso automatizado en un servidor de compilación.  
  
 Vea los temas siguientes para obtener más información acerca del scripting de las implementaciones de aplicaciones de BizTalk:  
  
-   [Implementar y administrar aplicaciones de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)  
  
-   [Descripción de implementación de aplicación de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)  
  
    > [!NOTE]  
    >  En este último artículo también se aplica a BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: configuración de BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)