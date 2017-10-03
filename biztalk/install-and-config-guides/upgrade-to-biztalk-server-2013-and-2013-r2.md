---
title: Actualizar a BizTalk Server 2013 y 2013 R2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, BizTalk Server
- deploying [BizTalk Server], upgrading
- BizTalk Server, upgrading
- upgrading
ms.assetid: acb0a96e-091b-45c3-8d41-affe9ffcf134
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97337438ca6be06b542baf61ad8d26fa2045180a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="0a9a2-102">Actualizar a BizTalk Server 2013 y 2013 R2</span><span class="sxs-lookup"><span data-stu-id="0a9a2-102">Upgrade to BizTalk Server 2013 and 2013 R2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a9a2-103"> está diseñado para que la actualización de versiones anteriores resulte muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="0a9a2-103"> is designed to allow for an easy upgrade experience from previous versions.</span></span> <span data-ttu-id="0a9a2-104">La guía de actualización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 y 2013 R2 está disponible en [Guías de instalación relacionadas con BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span><span class="sxs-lookup"><span data-stu-id="0a9a2-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 and 2013 R2 Upgrade Guide is available at [Installation Guides Related to BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a9a2-105">El archivo comprimido de esquemas se sustituirá al realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="0a9a2-105">The compressed file of schemas will be replaced when an upgrade is performed.</span></span> <span data-ttu-id="0a9a2-106">Si actualiza Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a una compilación posterior (por ejemplo, de una versión beta a la versión de lanzamiento de detalle), el archivo MicrosoftEdiXSDTemplates.exe de la instalación se sustituirá por el archivo MicrosoftEdiXSDTemplates.exe asociado a la actualización.</span><span class="sxs-lookup"><span data-stu-id="0a9a2-106">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build (for example, from a beta version to the retail release version), the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="0a9a2-107">Si prevé continuar usando los esquemas del archivo comprimido antiguo, ya no tendrá acceso al archivo comprimido después de la actualización a menos que realice una copia de seguridad del archivo comprimido antiguo.</span><span class="sxs-lookup"><span data-stu-id="0a9a2-107">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span> <span data-ttu-id="0a9a2-108">Para obtener más información, consulte **esquemas EDI instalar** en [pasos posteriores a la configuración para optimizar el entorno](post-configuration-steps-to-optimize-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0a9a2-108">For more information, see **Install EDI schemas** at [Post-configuration steps to optimize your environment](post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a9a2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a9a2-109">See Also</span></span>  
[<span data-ttu-id="0a9a2-110">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0a9a2-110">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)