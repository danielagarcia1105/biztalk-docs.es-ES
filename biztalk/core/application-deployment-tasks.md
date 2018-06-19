---
title: Las tareas de implementación de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed5dd5b2a15bd8408ee11934d7dd6274e81651b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230428"
---
# <a name="application-deployment-tasks"></a><span data-ttu-id="1df51-102">Tareas de implementación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1df51-102">Application Deployment Tasks</span></span>
<span data-ttu-id="1df51-103">En los temas de esta sección se proporcionan detalles de las siguientes tareas que intervienen en las fases del proceso de implementación de la aplicación para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1df51-103">The topics in this section provide details about the following tasks involved in each phase of the application deployment process for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="1df51-104">**Desarrollo.**</span><span class="sxs-lookup"><span data-stu-id="1df51-104">**Development.**</span></span> <span data-ttu-id="1df51-105">El programador implementa los ensamblados de BizTalk que deben incluirse en la aplicación de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutando en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1df51-105">The developer deploys the BizTalk assemblies that are to be included in the BizTalk application from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on the development computer.</span></span> <span data-ttu-id="1df51-106">De este modo, se crea la aplicación de forma automática y se rellena con los artefactos que se incluyen en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1df51-106">This automatically creates the application and populates it with the artifacts contained in the assemblies.</span></span> <span data-ttu-id="1df51-107">Todos los elementos que conforman una solución empresarial de BizTalk son artefactos, incluidos los ensamblados de BizTalk, los ensamblados .NET, los esquemas, las asignaciones, los enlaces, certificados, etc.</span><span class="sxs-lookup"><span data-stu-id="1df51-107">Artifacts are all of the items that comprise a BizTalk business solution, including BizTalk assemblies, .NET assemblies, schemas, maps, bindings, certificates, and so forth.</span></span> <span data-ttu-id="1df51-108">El programador finaliza la aplicación mediante la agregación de cualquier artefacto adicional o la realización de otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="1df51-108">The developer completes the application by adding any additional artifacts to it or performing additional configuration.</span></span> <span data-ttu-id="1df51-109">A continuación, el programador instala la aplicación desde el archivo .msi, lo prueba para comprobar la funcionalidad, soluciona los posibles problemas y, por último, exporta la aplicación desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="1df51-109">The developer then installs the application from the .msi file, tests it to verify functionality, fixes any issues, and then exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
2.  <span data-ttu-id="1df51-110">**Las pruebas.**</span><span class="sxs-lookup"><span data-stu-id="1df51-110">**Testing.**</span></span> <span data-ttu-id="1df51-111">El evaluador importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutando en un equipo de prueba, que crea la aplicación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1df51-111">The tester imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a test computer, which creates the application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1df51-112">El evaluador instala también la aplicación en los equipos host desde el archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="1df51-112">The tester also installs the application on the host computers from the .msi file.</span></span> <span data-ttu-id="1df51-113">Una vez completadas las pruebas y la corrección de errores, el evaluador exporta la aplicación desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como un archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="1df51-113">After testing and bug-fixing is complete, the tester exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
3.  <span data-ttu-id="1df51-114">**Almacenamiento provisional.**</span><span class="sxs-lookup"><span data-stu-id="1df51-114">**Staging.**</span></span> <span data-ttu-id="1df51-115">El Administrador de TI importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutando en un servidor de ensayo, lo configura para el entorno de producción, lo instala en equipos host, comprueba la funcionalidad y, a continuación, exporta la aplicación finalizada como un archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="1df51-115">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a staging server, configures it for the production environment, installs it on host computers, verifies the functionality, and then exports the finished application as an .msi file.</span></span>  
  
4.  <span data-ttu-id="1df51-116">**Producción.**</span><span class="sxs-lookup"><span data-stu-id="1df51-116">**Production.**</span></span> <span data-ttu-id="1df51-117">El Administrador de TI importa el archivo .msi en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecutando en un entorno de producción, instala la aplicación en los equipos host y, a continuación, inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1df51-117">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running in a production environment, installs the application on the host computers, and then starts the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1df51-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1df51-118">In This Section</span></span>  
  
-   [<span data-ttu-id="1df51-119">Tareas de desarrollo para la implementación de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1df51-119">Development Tasks for BizTalk Application Deployment</span></span>](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="1df51-120">Tareas de prueba para la implementación de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1df51-120">Testing Tasks for BizTalk Application Deployment</span></span>](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="1df51-121">Tareas de ensayo para la implementación de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1df51-121">Staging Tasks for BizTalk Application Deployment</span></span>](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="1df51-122">Tareas de producción para la implementación de aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1df51-122">Production Tasks for BizTalk Application Deployment</span></span>](../core/production-tasks-for-biztalk-application-deployment.md)