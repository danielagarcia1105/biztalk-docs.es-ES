---
title: "La designación de un nuevo servidor de secreto principal manualmente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fa44143-8d29-49ba-9c71-96be2c9ded67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6d635312d3765c37f1ab9c2b64505698f93e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="designating-a-new-master-secret-server-manually"></a><span data-ttu-id="16d0b-102">La designación de un nuevo servidor de secreto principal manualmente</span><span class="sxs-lookup"><span data-stu-id="16d0b-102">Designating a New Master Secret Server Manually</span></span>
<span data-ttu-id="16d0b-103">El hardware del clúster puede resultar costoso.</span><span class="sxs-lookup"><span data-stu-id="16d0b-103">Cluster hardware can be expensive.</span></span> <span data-ttu-id="16d0b-104">Si el costo de hardware es un problema, puede considerar manualmente la designación de otro servidor de inicio de sesión único (SSO) empresarial para ser el servidor secreto principal durante situaciones de error.</span><span class="sxs-lookup"><span data-stu-id="16d0b-104">If hardware cost is a concern, you can consider manually designating another Enterprise Single Sign-On (SSO) server to be the master secret server during failure scenarios.</span></span> <span data-ttu-id="16d0b-105">Con esta opción, se puede promover otro servidor SSO en el grupo SSO para el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="16d0b-105">Using this option, any other SSO server in the SSO group can be promoted to the master secret server.</span></span> <span data-ttu-id="16d0b-106">Cuando el maestro está inactivo, puede promover manualmente uno de los servidores SSO como servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="16d0b-106">When the master is down, you can manually promote one of the SSO servers to be the master secret server.</span></span> <span data-ttu-id="16d0b-107">El principal inconveniente de esta técnica es que no se puede editar las implementaciones existentes, reinicie existente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, o implementar nuevas aplicaciones de BizTalk hasta que se promueve a un nuevo servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="16d0b-107">The biggest disadvantage of this technique is that you cannot edit the existing deployments, restart the existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services, or deploy new BizTalk applications until you promote a new master secret server.</span></span>  
  
 <span data-ttu-id="16d0b-108">Para facilitar el proceso sin problemas, debe implementar algún mecanismo de supervisión, por lo que lo detectará el error tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="16d0b-108">To make the process seamless, you will need to implement some monitoring mechanism so you will discover the failure as soon as possible.</span></span> <span data-ttu-id="16d0b-109">También puede automatizar el proceso de promoción mediante el uso de una aplicación de supervisión, como System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="16d0b-109">You can also automate the promotion process by using a monitoring application such as System Center Operations Manager.</span></span>  
  
 <span data-ttu-id="16d0b-110">Para obtener más información acerca de cómo mover manualmente el servidor secreto principal, consulte [cómo mover el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=156841) (http://go.microsoft.com/fwlink/?LinkId=156841) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="16d0b-110">For more information about manually moving the master secret server, see [How to Move the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156841) (http://go.microsoft.com/fwlink/?LinkId=156841) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d0b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="16d0b-111">See Also</span></span>  
 [<span data-ttu-id="16d0b-112">El servidor secreto principal de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="16d0b-112">Clustering the Master Secret Server</span></span>](../technical-guides/clustering-the-master-secret-server.md)