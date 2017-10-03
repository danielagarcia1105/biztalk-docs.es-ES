---
title: "Implementación de puertos y Assemblies3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- Deployment Wizard
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 92de8d9f-79d4-4c7a-a66a-12928bce350f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c37a677904143d4a925d035c409f485f43958ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="0a0c9-102">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="0a0c9-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="0a0c9-103">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="0a0c9-103">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a0c9-104"> exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="0a0c9-104"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="0a0c9-105">Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a0c9-105">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="0a0c9-106">Implementar o quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0a0c9-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="0a0c9-107">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="0a0c9-107">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="0a0c9-108">Importar o exportar información de vínculos de ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde y a archivos de vínculos</span><span class="sxs-lookup"><span data-stu-id="0a0c9-108">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
 <span data-ttu-id="0a0c9-109">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0a0c9-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a0c9-110">El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="0a0c9-110">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="0a0c9-111">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="0a0c9-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a0c9-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a0c9-112">In This Section</span></span>  
  
-   [<span data-ttu-id="0a0c9-113">Comprobar la configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="0a0c9-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup1.md)  
  
-   [<span data-ttu-id="0a0c9-114">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="0a0c9-114">Importing Binding Files</span></span>](../core/importing-binding-files2.md)  
  
-   [<span data-ttu-id="0a0c9-115">Limitaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="0a0c9-115">Deployment Limitations</span></span>](../core/deployment-limitations4.md)