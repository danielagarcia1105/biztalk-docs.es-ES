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
# <a name="considerations-when-moving-the-tracking-database-if-the-messagebox-database-is-not-being-moved"></a><span data-ttu-id="ffb11-102">Consideraciones al mover la base de datos de seguimiento si no se está moviendo la base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="ffb11-102">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>
<span data-ttu-id="ffb11-103">Si va a mover la base de datos de seguimiento, pero no la base de datos, cuando se edita el archivo SampleUpdateInfo.xml, asegúrese de que incluye una entrada para la base de datos de cuadro de mensajes, aunque no se está moviendo la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ffb11-103">If you are moving the Tracking database but not the MessageBox database, when you edit the SampleUpdateInfo.xml file, make sure that you include an entry for the MessageBox database as well, even though the MessageBox database is not being moved.</span></span> <span data-ttu-id="ffb11-104">Esto debe hacerse para asegurarse de que el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajo del agente TrackedMessages_Copy_BizTalkMsgBoxDb se actualiza con la ubicación de la nueva base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ffb11-104">This must be done to ensure that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job TrackedMessages_Copy_BizTalkMsgBoxDb is updated with the location of the new Tracking database.</span></span>  
  
 <span data-ttu-id="ffb11-105">Por ejemplo, en el siguiente archivo SampleUpdateInfo.xml, solo la base de datos de seguimiento se ha movido desde OldServer a NuevoServidor.</span><span class="sxs-lookup"><span data-stu-id="ffb11-105">For example, in the following SampleUpdateInfo.xml file, only the Tracking database is being moved from OldServer to NewServer.</span></span> <span data-ttu-id="ffb11-106">La base de datos de cuadro de mensajes se halle en OldServer:</span><span class="sxs-lookup"><span data-stu-id="ffb11-106">The MessageBox database is staying on OldServer:</span></span>  
  
```  
<UpdateConfiguration>  
     <MessageBoxDB oldDBName="BizTalkMgmtDb" oldDBServer="OldServer" newDBName="BizTalkMgmtDb" newDBServer="OldServer" IsMaster="1"/>  
     <TrackingDB oldDBName="BizTalkDTADB" oldDBServer="OldServer" newDBName="BizTalkDTADB" newDBServer="NewServer"/>  
     <OtherDatabases>  
     </OtherDatabases>  
</UpdateConfiguration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffb11-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffb11-107">See Also</span></span>  
 [<span data-ttu-id="ffb11-108">Mover bases de datos</span><span class="sxs-lookup"><span data-stu-id="ffb11-108">Moving Databases</span></span>](../technical-guides/moving-databases.md)