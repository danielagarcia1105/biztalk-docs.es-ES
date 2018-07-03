---
title: Mover bases de datos de BAM no | Microsoft Docs
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
ms.openlocfilehash: 6b9038e443784ae0f2839c2656f62131e9a0fdfa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011381"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="62b75-102">Mover bases de datos que no son de BAM</span><span class="sxs-lookup"><span data-stu-id="62b75-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="62b75-103">Puede usar este procedimiento para mover las bases de datos principales de BizTalk Server a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="62b75-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="62b75-104">También se puede usar este mismo procedimiento básico para mover las bases de datos de BizTalk Server desde un servidor SQL Server local a un servidor SQL remoto o a un clúster de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62b75-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="62b75-105">En esta sección se describe cómo mover la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos que no están relacionados con la de BAM.</span><span class="sxs-lookup"><span data-stu-id="62b75-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62b75-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="62b75-106">In This Section</span></span>  
 <span data-ttu-id="62b75-107">Para mover la implementación de BAM no las bases de datos siguen los pasos descritos en el tema [cómo mover las bases de datos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=210646) (<http://go.microsoft.com/fwlink/?LinkId=210646>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="62b75-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (<http://go.microsoft.com/fwlink/?LinkId=210646>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="62b75-108">Esta sección también contiene un tema que describe los procedimientos que se deben seguir después de mover determinado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.</span><span class="sxs-lookup"><span data-stu-id="62b75-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="62b75-109">Complete los pasos del tema según corresponda para su entorno.</span><span class="sxs-lookup"><span data-stu-id="62b75-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="62b75-110">Consideraciones al mover la base de datos de seguimiento si no se está moviendo la base de datos de cuadros de mensaje</span><span class="sxs-lookup"><span data-stu-id="62b75-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)