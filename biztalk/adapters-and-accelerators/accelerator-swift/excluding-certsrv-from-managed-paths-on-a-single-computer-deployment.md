---
title: Exclusión de CertSrv de rutas de acceso en la implementación de una único equipo administradas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1651131369ef4a8e0c4683b82f5b97163e33382f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987845"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a><span data-ttu-id="d2176-102">Exclusión de CertSrv de las rutas administradas en una único equipo de implementación</span><span class="sxs-lookup"><span data-stu-id="d2176-102">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>
<span data-ttu-id="d2176-103">Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también instala el servidor de certificados en el mismo equipo, deberá excluir el servidor de certificados (CertSrv) desde las rutas de acceso administradas en Administración Central de Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="d2176-103">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer and also installed the certificate server on the same computer, you need to exclude the certificate server (CertSrv) from the managed paths in Microsoft SharePoint Server Central Administration.</span></span>  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a><span data-ttu-id="d2176-104">Para excluir CertSrv de las rutas de acceso administradas</span><span class="sxs-lookup"><span data-stu-id="d2176-104">To exclude CertSrv from the managed paths</span></span>  
  
1.  <span data-ttu-id="d2176-105">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d2176-105">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="d2176-106">En la ventana de Administración Central, en el **configuración del servidor Virtual** sección, haga clic en **configurar servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="d2176-106">In the Central Administration window, in the **Virtual Server Configuration** section, click **Configure virtual server settings**.</span></span>  
  
3.  <span data-ttu-id="d2176-107">En la ventana Lista de servidores virtuales, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="d2176-107">In the Virtual Server List window, click **Default Web Site**.</span></span>  
  
4.  <span data-ttu-id="d2176-108">En la ventana de configuración del servidor Virtual, en el **administración del servidor Virtual** sección, haga clic en **definir rutas administradas**.</span><span class="sxs-lookup"><span data-stu-id="d2176-108">In the Virtual Server Settings window, in the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
5.  <span data-ttu-id="d2176-109">En la ventana Definir rutas administradas, en el **agregar una nueva ruta de acceso** sección, escriba **CertSrv** en el **ruta** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d2176-109">In the Define Managed Paths window, in the **Add a New Path** section, enter **CertSrv** in the **Path** text box.</span></span> <span data-ttu-id="d2176-110">En el **tipo** sección, haga clic en **ruta excluida**.</span><span class="sxs-lookup"><span data-stu-id="d2176-110">In the **Type** section, click **Excluded Path**.</span></span> <span data-ttu-id="d2176-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2176-111">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d2176-112">Cierre la ventana de definir rutas administradas.</span><span class="sxs-lookup"><span data-stu-id="d2176-112">Close the Define Managed Paths window.</span></span>