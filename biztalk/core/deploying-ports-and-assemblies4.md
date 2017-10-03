---
title: "Implementación de puertos y Assemblies4 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying assemblies
- ports, deploying
- Deployment Wizard
- deploying ports
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 5a94a2c8-748c-4d1c-a87e-1cd763565886
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b83df400cba64ee55cab230826bf5bf75b1bca69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="5a735-102">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="5a735-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="5a735-103">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="5a735-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="5a735-104">BizTalk Server exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="5a735-104">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="5a735-105">Puede usar BizTalk Server para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5a735-105">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="5a735-106">Implementar o quitar los ensamblados de BizTalk Server en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5a735-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="5a735-107">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="5a735-107">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="5a735-108">Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="5a735-108">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a735-109">El adaptador de Microsoft BizTalk para JD Edwards OneWorld solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="5a735-109">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="5a735-110">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="5a735-110">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a735-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5a735-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5a735-112">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="5a735-112">Importing Binding Files</span></span>](../core/importing-binding-files3.md)  
  
-   [<span data-ttu-id="5a735-113">Limitaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="5a735-113">Deployment Limitations</span></span>](../core/deployment-limitations2.md)