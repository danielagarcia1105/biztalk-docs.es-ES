---
title: Designar un servidor de secreto principal nuevo manualmente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9453ade3d447e874609d1357e2383a5c21686f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975101"
---
# <a name="designating-a-new-master-secret-server-manually"></a>Designar un servidor de secreto principal nuevo manualmente
El hardware del clúster puede ser costoso. Si el costo de hardware es un problema, tenga en cuenta que designa manualmente a otro servidor de inicio de sesión único (SSO) empresarial para ser el servidor secreto principal durante situaciones de error. Con esta opción, se puede promover cualquier otro servidor de inicio de sesión único en el grupo de inicio de sesión único para el servidor secreto principal. Cuando el principal está inactivo, puede promover manualmente uno de los servidores SSO que el servidor secreto principal. La principal desventaja de esta técnica es que no se puede editar las implementaciones existentes, reinicie existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios o implementar nuevas aplicaciones de BizTalk hasta que promueva un nuevo servidor secreto principal.  
  
 Para realizar el proceso de conexión directa, deberá implementar algún mecanismo de supervisión para que se detectará el error tan pronto como sea posible. También puede automatizar el proceso de promoción mediante el uso de una aplicación de supervisión, como System Center Operations Manager.  
  
 Para obtener más información acerca de cómo mover manualmente el servidor secreto principal, consulte [cómo mover el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=156841) (<http://go.microsoft.com/fwlink/?LinkId=156841>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Agrupación en clústeres del servidor de secreto maestro](../technical-guides/clustering-the-master-secret-server.md)