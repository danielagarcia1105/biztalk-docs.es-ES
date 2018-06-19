---
title: Cómo realizar copias de y restaurar trabajos del Agente SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247204"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a>Cómo realizar copias de seguridad y restaurar trabajos del Agente SQL
En este tema se describe cómo crear una copia de seguridad de los trabajos del Agente SQL Server y restaurarlos. Debe crear copia de seguridad de los trabajos SQL después de configurarlos.  
  
## <a name="biztalk-server-jobs"></a>Trabajos de BizTalk Server  
 Los siguientes trabajos del Agente SQL Server están asociados a BizTalk Server. Los trabajos instalados en cada servidor son diferentes según las características instaladas y configuradas. La mayoría de estos trabajos se crea durante la instalación de BizTalk Server. Algunos se crean al configurar el envío de registro.  
  
-   Copia de seguridad de BizTalk Server (BizTalkMgmtDb)  
  
-   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
-   DTA Purge and Archive (BizTalkDTADb)  
  
-   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
-   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
-   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
-   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
-   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
-   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
-   Envío de registro BTS - Obtener historial de copias de seguridad  
  
-   Envío de registro BTS - Restaurar base de datos  
  
-   Envío de registro BTS - Restaurar en marca  
  
## <a name="back-up-a-job-using-a-script"></a>Un trabajo de copia de seguridad mediante un script  
  
1.  Abra **SQL Server Management Studio**.  
  
2.  Expanda **Agente SQL Server** y **Trabajos**.  
  
3.  Haga clic en el trabajo que desea crear un script para copia de seguridad y, a continuación, seleccione **incluir trabajo como**.  
  
4.  Seleccione **CREATE To** o **DROP To**, a continuación, seleccione **nueva ventana del Editor de consultas**, **archivo**, o **Portapapeles** Para seleccionar un destino para la secuencia de comandos. Normalmente, el destino es un archivo con un **.sql** extensión.  
  
5.  Repita este procedimiento en el paso 3 para cada trabajo que desee incluir en el script. Consulte la lista de trabajos relacionados con BizTalk Server para determinar qué trabajos debe incluir en el script.  
  
     Como mínimo, debe realizar una copia de la **copia de seguridad de BizTalk Server (BizTalkMgmtDb)** tras la configuración del trabajo.  
  
## <a name="restore-a-job-from-a-script"></a>Un trabajo de restauración de una secuencia de comandos  
  
1.  Abra **SQL Server Management Studio**.  
  
2.  En el **archivo** menú, **abiertos** el archivo que contiene el trabajo con scripts.  
  
3.  Ejecute el script para crear el trabajo.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Cómo realizar copias de y restaurar inicios de sesión SQL Server](../core/how-to-back-up-and-restore-sql-server-logins.md)