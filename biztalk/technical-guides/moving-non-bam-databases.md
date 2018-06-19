---
title: Mover bases de datos de BAM no | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e548e72-db0e-4f07-a07a-8d210425dfa5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c836840fef8b49cb907e7ac039612c68c1f6fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298228"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="93db8-102">Mover bases de datos de BAM no</span><span class="sxs-lookup"><span data-stu-id="93db8-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="93db8-103">Puede usar este procedimiento para mover las bases de datos principales de BizTalk Server a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="93db8-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="93db8-104">También se puede utilizar este mismo procedimiento básico para mover las bases de datos de BizTalk Server desde un servidor SQL Server local a un servidor SQL remoto o a un clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93db8-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="93db8-105">Esta sección describe cómo mover la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos que no están relacionados con la de BAM.</span><span class="sxs-lookup"><span data-stu-id="93db8-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93db8-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="93db8-106">In This Section</span></span>  
 <span data-ttu-id="93db8-107">Para mover el BAM no las bases de datos siguen los pasos descritos en el tema [cómo mover las bases de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=210646) (http://go.microsoft.com/fwlink/?LinkId=210646) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="93db8-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (http://go.microsoft.com/fwlink/?LinkId=210646) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="93db8-108">Esta sección también contiene un tema que describe los procedimientos que se deben seguir después de mover determinado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.</span><span class="sxs-lookup"><span data-stu-id="93db8-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="93db8-109">Complete los pasos en el tema según corresponda para su entorno.</span><span class="sxs-lookup"><span data-stu-id="93db8-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="93db8-110">Consideraciones al mover la base de datos de seguimiento si no se está moviendo la base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="93db8-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)