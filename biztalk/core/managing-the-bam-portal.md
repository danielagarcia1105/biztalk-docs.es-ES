---
title: Administrar el Portal de BAM en BizTalk Server | Documentos de Microsoft
Description: Información general de instalar y configurar el portal de BAM en BizTalk Server
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7908c9c7ce8e4b731e0b88569e3dc3fb228a1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262572"
---
# <a name="manage-the-bam-portal"></a><span data-ttu-id="06ddc-103">Administrar el portal de BAM</span><span class="sxs-lookup"><span data-stu-id="06ddc-103">Manage the BAM portal</span></span>

## <a name="set-up-bam-portal"></a><span data-ttu-id="06ddc-104">Configurar el portal de BAM</span><span class="sxs-lookup"><span data-stu-id="06ddc-104">Set up BAM portal</span></span>
<span data-ttu-id="06ddc-105">Los administradores configuran el portal de BAM al ejecutar la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06ddc-105">Administrators set up the BAM portal by running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="06ddc-106">Use la herramienta de configuración de BizTalk Server para determinar si BAM está habilitado y para determinar las cuentas de servicio web, los grupos de Windows que pueden ver el portal y el sitio web que hospedará el portal.</span><span class="sxs-lookup"><span data-stu-id="06ddc-106">Use the BizTalk Server configuration tool to specify whether BAM is enabled, and to specify the Web service accounts, the Windows groups that can view portal, and the Web site that will host the portal.</span></span> <span data-ttu-id="06ddc-107">Es necesario actualizar la configuración del portal de BAM una vez que lo haya configurado. Use la herramienta de configuración para actualizar los parámetros de configuración, tal como el grupo de usuarios del portal, la cuenta del grupo de aplicaciones y el usuario de los servicios web de administración.</span><span class="sxs-lookup"><span data-stu-id="06ddc-107">If it becomes necessary to update the BAM portal configuration once you have set up the BAM portal, you use the configuration tool to update the configuration settings such as the portal users group, the Application Pool account, and the management Web services user.</span></span>  
  
 <span data-ttu-id="06ddc-108">Para obtener más información acerca de cómo instalar el portal de BAM, consulte [instalación y configuración de BAM en entornos de varios equipos](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span><span class="sxs-lookup"><span data-stu-id="06ddc-108">For more information about installing the BAM portal, see [Install and Configure BAM in Multiple Computer Environments](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span></span>  
  
 <span data-ttu-id="06ddc-109">Para obtener más información acerca de cómo configurar el portal de BAM, consulte [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="06ddc-109">For more information about configuring the BAM portal, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
 <span data-ttu-id="06ddc-110">El portal de BAM tiene muchos parámetros personalizables a los que se puede obtener acceso modificando el archivo webconfig.xml.</span><span class="sxs-lookup"><span data-stu-id="06ddc-110">The BAM portal has many customizable settings that are accessed by modifying the webconfig.xml file.</span></span> <span data-ttu-id="06ddc-111">Estos parámetros controlan el rendimiento y el funcionamiento del portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="06ddc-111">These settings control the performance and operation of the BAM portal.</span></span> <span data-ttu-id="06ddc-112">El resto de esta sección describe la forma de personalizar la configuración de su portal de BAM.</span><span class="sxs-lookup"><span data-stu-id="06ddc-112">This rest of this section describes how to customize your BAM portal configuration.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="06ddc-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="06ddc-113">Next steps</span></span> 
  
-   [<span data-ttu-id="06ddc-114">Personalizar la configuración del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="06ddc-114">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)  
  
-   [<span data-ttu-id="06ddc-115">Cómo configurar el Portal de BAM para trabajar en un clúster NLB</span><span class="sxs-lookup"><span data-stu-id="06ddc-115">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a><span data-ttu-id="06ddc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="06ddc-116">See Also</span></span>  
 [<span data-ttu-id="06ddc-117">Administración de la infraestructura dinámica de BAM</span><span class="sxs-lookup"><span data-stu-id="06ddc-117">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)