---
title: Desinstalar y quitar la configuración de BizTalk Server para quitarlo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ab66d347795a0b8264a8bb6238149ab1b64572b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990637"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a>Desinstalar y quitar la configuración de BizTalk Server para quitarlo
Desinstale y quite la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 
  
##  <a name="BKMK_BeforeYouBegin"></a> Antes de comenzar  
  
- Antes de la desinstalación, debe quitar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- En este tema se enumeran los diferentes trabajos, paquetes y bases de datos que deben eliminarse. Los nombres que figuran son los nombres predeterminados. Puede que su entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] use nombres no predeterminados.  
  
- Siga los pasos en el orden que se indica. De lo contrario, la desinstalación no será completa.  
  
##  <a name="BKMK_Unconfigure"></a> Quitar la configuración de BizTalk Server  
  
1. Haga clic con el botón derecho en **Configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y seleccione **Ejecutar como administrador**.  
  
2. En la configuración, seleccione **Quitar la configuración de características**.  
  
3. Seleccione las características cuya configuración quiere quitar y haga clic en **Aceptar**. Si se le solicita que continúe, seleccione **Sí**. Para quitarlo todo del equipo, puede seleccionar todas las características.  
  
4. Seleccione **Siguiente** y continúe con el asistente.  
  
   Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: C:\Usuarios\nombreDeUsuario\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.  
  
##  <a name="BKMK_Uninstall"></a> Desinstalar los componentes en tiempo de ejecución de BizTalk Server  
  
1. Abra **Programas y características**.  
  
2. Seleccione en la lista su versión de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y haga clic en **Desinstalar**.  
  
3. Seleccione **Quitar** y continúe con el asistente.  
  
   Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: \Usuarios\\*nombreDeUsuario*\AppData\Local\Setup(083016 xxxxxx).htm.  
  
##  <a name="BKMK_UninstallSSO"></a> Desinstalar Enterprise Single Sign-On  
  
1. Abra **Programas y características**.  
  
2. Seleccione **Microsoft Enterprise Single Sign-On** en la lista y haga clic en **Desinstalar**.  
  
3. Seleccione **Quitar** y continúe con el asistente.  
  
   Se genera un archivo de registro en una carpeta temporal, similar a la siguiente: \Usuarios\\*nombreDeUsuario*\AppData\Local\Setup(083016 xxxxxx).htm.  
  
##  <a name="BKMK_RemoveRemaining"></a> Eliminar trabajos de SQL, bases de datos y paquetes  
  
#### <a name="delete-sql-server-agent-jobs"></a>Eliminar trabajos del Agente SQL Server  
  
1.  Abra **SQL Server Management Studio** como administrador.  
  
2.  En **SQL Server Management Studio**, conéctese al **Motor de base de datos**, expanda **Agente de SQL Server** y expanda **Trabajos**.  
  
3.  Elimine los trabajos siguientes (haga clic con el botón derecho en el trabajo y seleccione **Eliminar**):  
  
    -   Copia de seguridad de BizTalk Server (BizTalkMgmtDb)  
  
    -   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
    -   DTA Purge and Archive (BizTalkDTADb)  
  
    -   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
    -   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
    -   Supervisar el servidor BizTalk Server (BizTalkMgmtDb)  
  
    -   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
    -   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
    -   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
    -   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
        > [!NOTE]
        >  Si ha implementado BAM, también es posible que deba quitar la tabla bam_\<*nombre del cubo*\>_\<*nombre de la vista* \> trabajo.  
  
#### <a name="delete-biztalk-server-databases"></a>Eliminar bases de datos de BizTalk Server  
  
1.  En el **Explorador de objetos**, expanda **Bases de datos**.  
  
2.  Elimine las bases de datos siguientes (haga clic con el botón derecho en la base de datos y seleccione **Eliminar**):  
  
    -   BAMArchive  
  
    -   BAMPrimaryImport  
  
    -   BAMStarSchema  
  
    -   BizTalkDTADb  
  
    -   BizTalkMgmtDb  
  
    -   BizTalkMsgBoxDb  
  
    -   BizTalkRuleEngineDb  
  
    -   SSODB  
  
#### <a name="remove-sql-server-integration-services-packages"></a>Eliminar paquetes de SQL Server Integration Services  
  
1.  En el **Explorador de objetos**, **conéctese** a **Integration Services**.  
  
2.  Expanda **Paquetes almacenados** y **MSDB**.  
  
3.  Elimine los paquetes con los prefijos siguientes (haga clic con el botón derecho en el paquete y seleccione **Eliminar**):  
  
    -   BAM_AN_\<*nombre del cubo*\>  
  
    -   BAM_DM_\<*nombre de vista*\>  
  
