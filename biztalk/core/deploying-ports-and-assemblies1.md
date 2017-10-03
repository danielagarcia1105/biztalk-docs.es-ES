---
title: "Implementación de puertos y Assemblies1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- deployment, ports
- deployment, assemblies
- assemblies, deploying
ms.assetid: e259f7fe-c443-4015-a630-f08220e5437a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2515cd5ee80f62a55e0b26b33bb93c3685ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="d0eb7-102">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="d0eb7-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="d0eb7-103">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d0eb7-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="d0eb7-104">El asistente exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d0eb7-104">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="d0eb7-105">Mediante BizTalk Server se pueden realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0eb7-105">You use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="d0eb7-106">Implementar o quitar ensamblados de BizTalk Server en una base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d0eb7-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="d0eb7-107">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="d0eb7-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="d0eb7-108">Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="d0eb7-108">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="d0eb7-109">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="d0eb7-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0eb7-110">El adaptador de Microsoft BizTalk para TIBCO Rendezvous solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="d0eb7-110">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="d0eb7-111">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="d0eb7-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0eb7-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d0eb7-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d0eb7-113">Comprobar la configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="d0eb7-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup3.md)  
  
-   [<span data-ttu-id="d0eb7-114">Cómo limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="d0eb7-114">How to Clean the Target Computer</span></span>](../core/how-to-clean-the-target-computer1.md)