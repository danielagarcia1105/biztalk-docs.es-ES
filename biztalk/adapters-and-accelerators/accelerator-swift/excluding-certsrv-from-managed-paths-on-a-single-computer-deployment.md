---
title: "Exclusión de CertSrv de rutas de acceso en la implementación de una solo equipo administradas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a><span data-ttu-id="4c373-102">Exclusión de CertSrv de rutas de acceso administradas en la implementación de una solo equipo</span><span class="sxs-lookup"><span data-stu-id="4c373-102">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>
<span data-ttu-id="4c373-103">Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también instala el servidor de certificados en el mismo equipo, debe excluir el servidor de certificados (CertSrv) de las rutas de acceso administradas en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Administración Central de SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="4c373-103">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer and also installed the certificate server on the same computer, you need to exclude the certificate server (CertSrv) from the managed paths in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server Central Administration.</span></span>  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a><span data-ttu-id="4c373-104">Para excluir CertSrv de las rutas de acceso administradas</span><span class="sxs-lookup"><span data-stu-id="4c373-104">To exclude CertSrv from the managed paths</span></span>  
  
1.  <span data-ttu-id="4c373-105">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="4c373-105">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="4c373-106">En la ventana de Administración Central, en la **configuración del servidor Virtual** sección, haga clic en **configurar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="4c373-106">In the Central Administration window, in the **Virtual Server Configuration** section, click **Configure virtual server settings**.</span></span>  
  
3.  <span data-ttu-id="4c373-107">En la ventana Lista de servidores virtuales, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="4c373-107">In the Virtual Server List window, click **Default Web Site**.</span></span>  
  
4.  <span data-ttu-id="4c373-108">En la ventana de configuración del servidor Virtual, en la **administración del servidor Virtual** sección, haga clic en **definir rutas administradas**.</span><span class="sxs-lookup"><span data-stu-id="4c373-108">In the Virtual Server Settings window, in the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
5.  <span data-ttu-id="4c373-109">En la ventana Definir rutas de acceso administradas, en la **agregar una nueva ruta de acceso** sección, escriba **CertSrv** en el **ruta de acceso** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4c373-109">In the Define Managed Paths window, in the **Add a New Path** section, enter **CertSrv** in the **Path** text box.</span></span> <span data-ttu-id="4c373-110">En el **tipo** sección, haga clic en **ruta excluida**.</span><span class="sxs-lookup"><span data-stu-id="4c373-110">In the **Type** section, click **Excluded Path**.</span></span> <span data-ttu-id="4c373-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c373-111">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="4c373-112">Cierre la ventana de definir rutas de acceso administradas.</span><span class="sxs-lookup"><span data-stu-id="4c373-112">Close the Define Managed Paths window.</span></span>