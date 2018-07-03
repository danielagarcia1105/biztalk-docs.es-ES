---
title: Eliminar un Host | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65c2997fa19ed961515285ce04f51acc4c196e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995285"
---
# <a name="delete-a-host"></a>Eliminar un Host
Solo se puede eliminar un host en las siguientes circunstancias:  

- No es el host predeterminado.  

- No es el único host que realiza el seguimiento de host.  

- No aloja ningún controlador de adaptadores.  

- No posee orquestaciones dadas de alta.  

- No hay instancias iniciadas del host.  

- Si el host no está agrupado.  

  Para obtener más información acerca de los hosts, consulte [Hosts](../core/hosts.md).  

## <a name="prerequisites"></a>Requisitos previos  
 Debe disponer de los siguientes derechos de usuario para crear hosts, modificar propiedades de hosts y eliminar hosts:  

-   Además, debe ser miembro del grupo de administradores de BizTalk Server.  

-   Debe disponer de los siguientes derechos en SQL Server:  

    -   Debe ser administrador de SQL Server o miembro de las funciones de base de datos db_owner o db_securityadmin de SQL Server en la base de datos de seguimiento de BizTalk (BizTalk DTADb), bases de datos de cuadro de mensajes (BizTalkMsgBoxDb) y la base de datos de importación principal de BAM (BAMPrimaryImport).  

    -   Debe ser miembro del rol sysadmin de SQL Server en todos los equipos donde haya bases de datos de cuadro de mensajes, o miembro del rol db_owner o db_ddladmin de SQL Server para todas las bases de datos de cuadro de mensajes.  

## <a name="steps"></a>Pasos 

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **configuración de plataforma**y, a continuación, haga clic en **Hosts**.  

3. En el panel de detalles, haga clic en el host que desea eliminar y, a continuación, haga clic en **eliminar**.  

4. En el **Confirmar eliminación de host** cuadro de diálogo, haga clic en **Sí**.  

## <a name="see-also"></a>Vea también  
- [Administrar hosts de BizTalk e instancias de host](../core/managing-biztalk-hosts-and-host-instances.md)   
- [Cómo crear un nuevo Host](../core/how-to-create-a-new-host.md)   
- [Cómo modificar las propiedades del Host](../core/how-to-modify-host-properties.md)   
- **MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
