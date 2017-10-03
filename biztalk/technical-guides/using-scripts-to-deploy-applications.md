---
title: Uso de Scripts para implementar aplicaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4566a810489a9f6c46424a525908aa5a2fbb6bee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="b227e-102">Uso de Scripts para implementar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b227e-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="b227e-103">Debe utilizar secuencias de comandos para implementar aplicaciones de BizTalk siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="b227e-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="b227e-104">Secuencias de comandos, reducen el riesgo de error humano durante el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="b227e-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="b227e-105">También debe documentar los procedimientos de implementación en profundidad.</span><span class="sxs-lookup"><span data-stu-id="b227e-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="b227e-106">Debe documentar todo lo que no script con pasos muy detallados.</span><span class="sxs-lookup"><span data-stu-id="b227e-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="b227e-107">Esto incluye documentar los cambios a sistemas externos y a la implementación de componentes de terceros.</span><span class="sxs-lookup"><span data-stu-id="b227e-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="b227e-108">Uso de BTSTask</span><span class="sxs-lookup"><span data-stu-id="b227e-108">Using BTSTask</span></span>  
 <span data-ttu-id="b227e-109">Puede usar BTSTask.exe para incluir la creación de aplicaciones de BizTalk, así como para importar archivos de script en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] paquetes .msi.</span><span class="sxs-lookup"><span data-stu-id="b227e-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="b227e-110">Si se crea el script la creación de las aplicaciones, a continuación, los paquetes pueden se generan automáticamente mediante un proceso automatizado en un servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="b227e-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="b227e-111">Vea los temas siguientes para obtener más información acerca del scripting de las implementaciones de aplicaciones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="b227e-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="b227e-112">[Implementar y administrar aplicaciones de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="b227e-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="b227e-113">[Descripción de implementación de aplicación de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="b227e-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b227e-114">En este último artículo también se aplica a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b227e-114">This latter article also applies to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b227e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b227e-115">See Also</span></span>  
 [<span data-ttu-id="b227e-116">Lista de comprobación: Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b227e-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)