---
title: Designar un servidor de secreto principal nuevo manualmente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9453ade3d447e874609d1357e2383a5c21686f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975101"
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="bc7f3-102">Designar un servidor de secreto principal nuevo manualmente</span><span class="sxs-lookup"><span data-stu-id="bc7f3-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="bc7f3-103">El hardware del clúster puede ser costoso.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="bc7f3-104">Si el costo de hardware es un problema, tenga en cuenta que designa manualmente a otro servidor de inicio de sesión único (SSO) empresarial para ser el servidor secreto principal durante situaciones de error.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="bc7f3-105">Con esta opción, se puede promover cualquier otro servidor de inicio de sesión único en el grupo de inicio de sesión único para el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="bc7f3-106">Cuando el principal está inactivo, puede promover manualmente uno de los servidores SSO que el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="bc7f3-107">La principal desventaja de esta técnica es que no se puede editar las implementaciones existentes, reinicie existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios o implementar nuevas aplicaciones de BizTalk hasta que promueva un nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="bc7f3-108">Para realizar el proceso de conexión directa, deberá implementar algún mecanismo de supervisión para que se detectará el error tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="bc7f3-109">También puede automatizar el proceso de promoción mediante el uso de una aplicación de supervisión, como System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="bc7f3-110">Para obtener más información acerca de cómo mover manualmente el servidor secreto principal, consulte [cómo mover el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=156841) (<http://go.microsoft.com/fwlink/?LinkId=156841>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="bc7f3-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (<http://go.microsoft.com/fwlink/?LinkId=156841>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7f3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc7f3-111">See Also</span></span>  
 [<span data-ttu-id="bc7f3-112">Agrupación en clústeres del servidor de secreto maestro</span><span class="sxs-lookup"><span data-stu-id="bc7f3-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)