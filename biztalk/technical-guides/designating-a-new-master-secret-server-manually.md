---
title: "La designación de un nuevo servidor de secreto principal manualmente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="designating-a-new-master-secret-server-manually"></a>La designación de un nuevo servidor de secreto principal manualmente
El hardware del clúster puede resultar costoso. Si el costo de hardware es un problema, puede considerar manualmente la designación de otro servidor de inicio de sesión único (SSO) empresarial para ser el servidor secreto principal durante situaciones de error. Con esta opción, se puede promover otro servidor SSO en el grupo SSO para el servidor secreto principal. Cuando el maestro está inactivo, puede promover manualmente uno de los servidores SSO como servidor secreto principal. El principal inconveniente de esta técnica es que no se puede editar las implementaciones existentes, reinicie existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, o implementar nuevas aplicaciones de BizTalk hasta que se promueve a un nuevo servidor secreto principal.  
  
 Para facilitar el proceso sin problemas, debe implementar algún mecanismo de supervisión, por lo que lo detectará el error tan pronto como sea posible. También puede automatizar el proceso de promoción mediante el uso de una aplicación de supervisión, como System Center Operations Manager.  
  
 Para obtener más información acerca de cómo mover manualmente el servidor secreto principal, consulte [cómo mover el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=156841) (http://go.microsoft.com/fwlink/?LinkId=156841) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [El servidor secreto principal de agrupación en clústeres](../technical-guides/clustering-the-master-secret-server.md)