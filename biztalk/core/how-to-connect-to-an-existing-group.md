---
title: "Cómo conectarse a un grupo existente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b452ef2f29eb5019eb126181e0cd47b66f82f7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-connect-to-an-existing-group"></a>Cómo efectuar una conexión a un grupo existente
La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede usarse en cualquier equipo de la empresa para administrar de forma remota uno o varios grupos de BizTalk Server en ella, siempre y cuando estos grupos se encuentre en equipos del mismo dominio o en dominios de confianza.  
  
 El nodo Administración de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] en la consola de administración de BizTalk Server constituye el nodo de nivel más alto para todos los grupos de BizTalk; asimismo, es el nivel que se usa al agregar un grupo de BizTalk Server existente a la consola de administración de BizTalk Server. Al agregar un grupo, es preciso especificar un servidor existente y una base de datos de administración de BizTalk con la cual se desea efectuar la conexión.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe iniciar sesión como miembro del grupo de operadores de BizTalk Server o de administradores de BizTalk Server.  
  
### <a name="to-connect-to-an-existing-group"></a>Para efectuar una conexión a un grupo existente  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, haga clic en **administración de BizTalk Server**y, a continuación, haga clic en **conectar a grupo existente**.  
  
3.  En el **conectarse a base de configuración de servidor de BizTalk existente** cuadro de diálogo, en la **nombre de SQL Server** lista desplegable, seleccione el nombre de la instancia de Microsoft SQL Server que hospeda el BizTalk Base de datos de administración (conocido también como la base de datos de configuración). Al seleccionar la instancia de servidor SQL Server, BizTalk Server intenta detectar automáticamente las bases de datos de BizTalk Server del equipo.  
  
4.  En el **nombre de base de datos** lista desplegable, seleccione la base de datos de administración de BizTalk Server (**BizTalkMgmtDb**) al que desea conectarse y, a continuación, haga clic en **Aceptar**.  
  
     La consola de administración de BizTalk Server agrega el grupo de BizTalk Server en el árbol de consola.  
  
    > [!NOTE]
    >  Si la base de datos de administración de BizTalk Server se aloja en un clúster de SQL Server y éste lleva a cabo una conmutación por error, es posible que aparezca un error similar al siguiente cuando se intenta efectuar la conexión con la base de datos de administración:  
    >   
    >  No se pudo cargar el grupo [\<nombreDeServidor >:\<base de datos de administración >] proveedores de datos.  
    >   
    >  And  
    >   
    >  INFORMACIÓN ADICIONAL:  
    >   
    >  No se encuentra la instancia de la clase WMI. (WinMgmt)  
    >   
    >  Este error puede producirse a causa de la falta de disponibilidad de las bases de datos de BizTalk mientras se efectúa la conmutación por error. Para solucionar este problema, espere a que la instancia en clúster de servidores SQL Server se encuentre en línea antes de intentar conectarla a la consola de administración de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Administración de grupos](../core/managing-groups.md)   
 [Grupos de BizTalk](../core/biztalk-groups.md)