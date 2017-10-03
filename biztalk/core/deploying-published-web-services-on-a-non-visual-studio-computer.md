---
title: "Implementación de publica servicios Web en un equipo que no tenga Visual Studio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- deploying, Web services
- Web services, planning
- Web services, deploying
ms.assetid: e9f8e801-21f3-4458-b05c-206b72868916
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad894c257bdd2eed6462b63c0e921f78ca13c17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a><span data-ttu-id="81026-102">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="81026-102">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>
<span data-ttu-id="81026-103">Para implementar el servicio Web publicado en un equipo que no tenga [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] instalado, es necesario crear un proyecto de configuración de Web, distribuir el paquete de configuración Web (archivo .msi), instalar el paquete en el equipo que no dispone de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y configurar el servicio Web instalado.</span><span class="sxs-lookup"><span data-stu-id="81026-103">To deploy your published Web service on a computer that does not have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed, you need to create a Web setup project, distribute the Web setup package (.msi file), install the package on the non-[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] computer, and configure the installed Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81026-104">También puede usar la consola de administración de BizTalk Server para crear archivos MSI donde se empaquetan aplicaciones de BizTalk que contienen los proyectos de servicios Web publicados.</span><span class="sxs-lookup"><span data-stu-id="81026-104">You can also use BizTalk Server Administration Console to create MSI files packaging BizTalk Applications containing the published Web service projects.</span></span> <span data-ttu-id="81026-105">Estos archivos MSI se pueden usar para implementar los proyectos de servicios Web en un equipo que no disponga de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81026-105">This MSI files can be used to deploy the Web service projects on a Non [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Computer.</span></span> <span data-ttu-id="81026-106">Para obtener más información sobre cómo crear archivos MSI mediante la consola de administración de BizTalk Server, vea [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="81026-106">For more information about how to create MSI files using BizTalk Server Administration console, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81026-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="81026-107">In This Section</span></span>  
  
-   [<span data-ttu-id="81026-108">Cómo crear un programa de instalación de Web para el servicio Web publicado</span><span class="sxs-lookup"><span data-stu-id="81026-108">How to Create a Web Setup for Your Published Web Service</span></span>](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [<span data-ttu-id="81026-109">Cómo distribuir el paquete de instalación de Web</span><span class="sxs-lookup"><span data-stu-id="81026-109">How to Distribute the Web Setup Package</span></span>](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [<span data-ttu-id="81026-110">Cómo instalar el paquete de instalación de Web</span><span class="sxs-lookup"><span data-stu-id="81026-110">How to Install the Web Setup Package</span></span>](../core/how-to-install-the-web-setup-package.md)  
  
-   [<span data-ttu-id="81026-111">Cómo configurar el servicio Web instalado</span><span class="sxs-lookup"><span data-stu-id="81026-111">How to Configure the Installed Web Service</span></span>](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="81026-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="81026-112">See Also</span></span>  
 [<span data-ttu-id="81026-113">Implementar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="81026-113">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)