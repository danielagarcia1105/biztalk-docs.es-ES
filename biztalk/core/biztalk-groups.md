---
title: Grupos de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9cd38012f0e2a7ba5f4cfcb56ae63678aacbf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231284"
---
# <a name="biztalk-groups"></a>Grupos de BizTalk

## <a name="overview"></a>Información general
El *grupo de BizTalk* es una unidad de organización que normalmente representa una empresa, departamento, concentrador u otra unidad de negocio que requiere una implementación contenida de BizTalk Server. El grupo de BizTalk tiene una relación uno a uno con una base de datos de administración de BizTalk Server (conocida como la base de datos de configuración de BizTalk Server en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).  
  
> [!NOTE]
>  Aunque los grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden contener varios equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cualquier equipo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dado solo puede estar asociado con un único grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 La base de datos de administración de BizTalk almacena información de configuración para el grupo de BizTalk y los equipos con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de ese grupo. Esta información de configuración especifica parte de la lógica de procesamiento de mensajes de los servidores y también dónde se ejecutará físicamente esta lógica. Para obtener más información acerca de la base de datos de administración de BizTalk Server, vea [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).  
  
 Debe especificar la misma base de datos de administración de BizTalk Server para todas las instalaciones de servidor del grupo, de modo que pueda administrar todos los servidores desde la consola de administración.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [Administración de grupos](../core/managing-groups.md)   
 [Entidades](../core/entities.md)