---
title: Consideraciones al mover la base de datos de seguimiento si no se está moviendo la base de datos de cuadro de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee4066cb-da5b-4d04-a3b8-23fbf2d0c92a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb2fcb6ad9ead42bd3e09c84a8895758d82293f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299924"
---
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a>Consideraciones al mover la base de datos de seguimiento si no se está moviendo la base de datos de cuadro de mensajes
Si va a mover la base de datos de seguimiento, pero no la base de datos, cuando se edita el archivo SampleUpdateInfo.xml, asegúrese de que incluye una entrada para la base de datos de cuadro de mensajes, aunque no se está moviendo la base de datos de cuadro de mensajes. Esto debe hacerse para asegurarse de que el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajo del agente TrackedMessages_Copy_BizTalkMsgBoxDb se actualiza con la ubicación de la nueva base de datos de seguimiento.  
  
 Por ejemplo, en el siguiente archivo SampleUpdateInfo.xml, solo la base de datos de seguimiento se ha movido desde OldServer a NuevoServidor. La base de datos de cuadro de mensajes se halle en OldServer:  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos](../technical-guides/moving-databases.md)