---
title: "Cómo copiar mensajes controlados en la base de datos de seguimiento de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a>Cómo copiar mensajes de los que se ha realizado un seguimiento en la base de datos de seguimiento de BizTalk
El proceso de archivo y purga puede obtener acceso a las bases de datos de servidores SQL Server diferentes o actualizarlas, por lo que es preciso configurar servidores vinculados entre las instancias implicadas de servidor SQL Server. Puede copiar directamente mensajes de los que se ha efectuado un seguimiento del servidor de base de datos de cuadro de mensajes (BizTalkMsgBoxDb) a la base de datos de seguimiento de BizTalk (BizTalkDTADb) a través de un servidor vinculado. Debe configurar servidores vinculados entre:  
  
-   Cada una de sus bases de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) y la base de datos de seguimiento de BizTalk (BizTalkDTADb)  
  
-   La base de datos de seguimiento de BizTalk (BizTalkDTADb) y el servidor de validación para la validación de archivos.  
  
-   Las cuentas de servicio del Agente SQL Server del equipo que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) deben contar con los permisos db_datareader y db_datawriter para la base de datos de seguimiento de BizTalk (BizTalkDTADb) del servidor vinculado.  
  
> [!NOTE]
>  En el Agente SQL Server, compruebe que el trabajo de copia se ejecuta sin que se produzcan errores. De lo contrario, los errores podrían impedir que los datos se movieran a la base de datos de seguimiento.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a>Para copiar mensajes controlados en la base de datos de seguimiento de BizTalk (SQL Server 2008)  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectar con el servidor SQL server apropiado.  
  
3.  En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.  
  
4.  En el panel de detalles, haga clic en **TrackedMessages_Copy_BizTalkMsgBoxDb**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **propiedades del trabajo - TrackedMessages_Copy_BizTalkMsgBoxDb** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.  
  
6.  En **lista de pasos de trabajo**, haga clic en **purgar**y, a continuación, haga clic en **editar**.  
  
7.  En el **comando** cuadro, edite los parámetros de los nombres de base de datos según corresponda y el servidor de seguimiento y, a continuación, haga clic en **Aceptar**.  
  
8.  En el **propiedades del trabajo - TrackedMessages_Copy_BizTalkMsgBoxDb** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
     Los mensajes se copiarán de la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) a la base de datos de seguimiento de BizTalk (BizTalkDTADb).  
  
> [!IMPORTANT]
>  Si agrega una nueva base de datos de cuadro de mensajes, tendrá que volver a realizar este procedimiento para ella.  
  
## <a name="see-also"></a>Vea también  
 [Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md)