---
title: Cómo conectarse a un grupo existente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e29b57f39ab1cb86e34a9e744063ff248d12ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994357"
---
# <a name="how-to-connect-to-an-existing-group"></a>Cómo efectuar una conexión a un grupo existente
La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede usarse en cualquier equipo de la empresa para administrar de forma remota uno o varios grupos de BizTalk Server en ella, siempre y cuando estos grupos se encuentre en equipos del mismo dominio o en dominios de confianza.  
  
 El nodo de administración de BizTalk Server en la consola de administración de BizTalk Server es el nodo de nivel superior para todos los grupos de BizTalk y es el nivel que se utiliza al agregar un grupo de BizTalk Server existente a la consola de administración de BizTalk Server. Al agregar un grupo, es preciso especificar un servidor existente y una base de datos de administración de BizTalk con la cual se desea efectuar la conexión.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe iniciar sesión como miembro del grupo de operadores de BizTalk Server o de administradores de BizTalk Server.  
  
### <a name="to-connect-to-an-existing-group"></a>Para efectuar una conexión a un grupo existente  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, haga clic en **administración de BizTalk Server**y, a continuación, haga clic en **conectar a grupo existente**.  
  
3. En el **conectarse a base de configuración de servidor BizTalk existente** cuadro de diálogo el **nombre de SQL Server** lista desplegable, seleccione el nombre de la instancia de Microsoft SQL Server que hospeda el BizTalk La base de datos de administración (denominada también la base de datos de configuración). Al seleccionar la instancia de servidor SQL Server, BizTalk Server intenta detectar automáticamente las bases de datos de BizTalk Server del equipo.  
  
4. En el **nombre de base de datos** lista desplegable, seleccione la base de datos de administración de BizTalk Server (**BizTalkMgmtDb**) al que desea conectarse y, a continuación, haga clic en **Aceptar**.  
  
    La consola de administración de BizTalk Server agrega el grupo de BizTalk Server en el árbol de consola.  
  
   > [!NOTE]
   >  Si la base de datos de administración de BizTalk Server se aloja en un clúster de SQL Server y éste lleva a cabo una conmutación por error, es posible que aparezca un error similar al siguiente cuando se intenta efectuar la conexión con la base de datos de administración:  
   >   
   >  No se pudo cargar el grupo [\<servername\>:\<base de datos de administración\>] proveedores de datos.  
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