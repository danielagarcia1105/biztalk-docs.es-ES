---
title: "Implementación de puertos y Assemblies2 | Documentos de Microsoft"
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
ms.assetid: abbc1391-2b90-42a5-a747-416bc517bb39
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3cc840b9dca222d1b55e9277b1ffd6cf326db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="cca0e-102">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="cca0e-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="cca0e-103">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="cca0e-103">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cca0e-104">configuración de la ubicación de recepción/puertos de envío de exportaciones en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="cca0e-104"> exports send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="cca0e-105">Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cca0e-105">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="cca0e-106">Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cca0e-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="cca0e-107">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="cca0e-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="cca0e-108">Importar información de enlace de ensamblado de BizTalk a archivos de enlace o exportarla a ellos.</span><span class="sxs-lookup"><span data-stu-id="cca0e-108">Import or export BizTalk assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="cca0e-109">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="cca0e-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cca0e-110">Microsoft BizTalk Adapter para TIBCO Enterprise Message Service solo necesita que disponga de Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="cca0e-110">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="cca0e-111">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="cca0e-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cca0e-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cca0e-112">In This Section</span></span>  
  
-   [<span data-ttu-id="cca0e-113">Comprobar la configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="cca0e-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup2.md)  
  
-   [<span data-ttu-id="cca0e-114">Cómo limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="cca0e-114">How to Clean the Target Computer</span></span>](../core/how-to-clean-the-target-computer2.md)  
  
-   [<span data-ttu-id="cca0e-115">Limitaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="cca0e-115">Deployment Limitations</span></span>](../core/deployment-limitations1.md)