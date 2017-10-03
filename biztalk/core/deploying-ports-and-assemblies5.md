---
title: "Implementación de puertos y Assemblies5 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 11d980c4-2502-4da2-b505-d7326aae619a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31df94e2a659fa29e6f21d2bd705de31da3c6b9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="b7311-102">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="b7311-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="b7311-103">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="b7311-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b7311-104"> exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="b7311-104"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="b7311-105">Utilice [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las siguiente tareas:</span><span class="sxs-lookup"><span data-stu-id="b7311-105">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
-   <span data-ttu-id="b7311-106">Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b7311-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="b7311-107">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="b7311-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="b7311-108">Importar o exportar información de enlace de ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde archivos de enlace o a archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="b7311-108">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="b7311-109">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b7311-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7311-110">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="b7311-110">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="b7311-111">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="b7311-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7311-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7311-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b7311-113">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="b7311-113">Importing Binding Files</span></span>](../core/importing-binding-files1.md)  
  
-   [<span data-ttu-id="b7311-114">Limitaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="b7311-114">Deployment Limitations</span></span>](../core/deployment-limitations3.md)