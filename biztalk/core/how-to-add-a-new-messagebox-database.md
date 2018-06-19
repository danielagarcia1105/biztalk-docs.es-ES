---
title: Cómo agregar una nueva base de datos de cuadro de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cab4fd370aab2d85519b3fd52e0dadcd9583275e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247244"
---
# <a name="how-to-add-a-new-messagebox-database"></a>Cómo agregar una nueva base de datos de cuadro de mensajes
Utilice la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para agregar una nueva base de datos de cuadro de mensaje a la implementación de BizTalk Server. Las bases de datos de cuadro de mensajes son la base para los elementos de equilibrio de carga de red entre servidores que realizan procesamiento cooperativo. Para aumentar el número de mensajes que puede procesar el sistema, puede ser necesario agregar bases de datos de cuadro de mensajes adicionales.  
  
 No se puede crear una base de datos de cuadro de mensajes nueva y dar de alta orquestaciones, puertos de envío o grupos de puertos de envío al mismo tiempo. Las orquestaciones, puertos de envío o grupos de puertos de envío dados de alta obtienen acceso a datos que BizTalk Server debe copiar en la nueva base de datos de cuadro de mensajes. Mientras se tiene acceso a estos datos, BizTalk Server no puede copiarlos en la nueva base de datos de cuadro de mensajes.  
  
 Puede designar bases de datos locales y remotas como bases de datos de cuadro de mensajes. Para obtener información acerca de las bases de datos de BizTalk Server, vea [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).  
  
> [!IMPORTANT]
>  El Agente SQL Server debe estar ejecutándose en todos los servidores SQL a los que desee agregar una nueva base de datos de cuadro de mensajes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios. Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:  
  
-   Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
-   Debe ser administrador de SQL Server en el equipo donde reside la base de datos.  
  
### <a name="to-add-a-new-messagebox-database"></a>Para agregar una base de datos de cuadro de mensaje nueva  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk y, a continuación, haga clic en **configuración de plataforma**.  
  
3.  Haga clic en **cuadros de mensaje**, haga clic en **New**y, a continuación, haga clic en **cuadro de mensaje**.  
  
4.  En el **propiedades de cuadro de mensaje** cuadro de diálogo, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**SQL Server**|Mostrar el nombre del servidor SQL que aloja la base de datos de cuadro de mensajes.|  
    |**Base de datos**|Mostrar el nombre de la base de datos de cuadro de mensajes.|  
    |**Cuadro de mensaje de suscripción principal**|Indicar si la base de datos de cuadros de mensajes seleccionada es la principal. Si la base de datos de cuadro de mensajes es la principal, esta casilla está activada y no disponible. La primera base de datos de cuadro de mensajes creada cuando se ejecuta el Asistente para Configuración es la principal de forma predeterminada.|  
    |**Deshabilitar la publicación de mensajes nuevos**|Activar esta casilla para especificar que no desea que esta base de datos de cuadro de mensajes reciba mensajes de activación.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md)   
 [Cómo deshabilitar la publicación de mensajes nuevos](../core/how-to-disable-new-message-publication.md)   
 [Cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md)   
 [Copia de seguridad y restaurar bases de datos de servidor BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [La base de datos de cuadro de mensajes](../core/the-messagebox-database.md)