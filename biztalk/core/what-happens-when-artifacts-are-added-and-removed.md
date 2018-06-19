---
title: ¿Qué ocurre cuando se agregan y quitan artefactos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288884"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a><span data-ttu-id="63d4a-102">¿Qué ocurre cuando se agregan y se quitan los artefactos?</span><span class="sxs-lookup"><span data-stu-id="63d4a-102">What Happens When Artifacts Are Added and Removed</span></span>
<span data-ttu-id="63d4a-103">En este tema se describe lo que sucede cuando se agregan artefactos a una aplicación.</span><span class="sxs-lookup"><span data-stu-id="63d4a-103">This topic describes what happens when you add artifacts to an application.</span></span> <span data-ttu-id="63d4a-104">Puede agregar artefactos basados en archivos a una aplicación mediante la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask.</span><span class="sxs-lookup"><span data-stu-id="63d4a-104">You can add file-based artifacts to an application by using the BizTalk Server Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="63d4a-105">Los artefactos basados en archivos incluyen los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="63d4a-105">File-based artifacts include the following types:</span></span>  
  
-   <span data-ttu-id="63d4a-106">Ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="63d4a-106">BizTalk assemblies</span></span>  
  
-   <span data-ttu-id="63d4a-107">Ensamblados .NET que no son específicos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="63d4a-107">.NET assemblies that are not BizTalk-specific</span></span>  
  
-   <span data-ttu-id="63d4a-108">Archivos (.xml) de enlace</span><span class="sxs-lookup"><span data-stu-id="63d4a-108">Binding (.xml) files</span></span>  
  
-   <span data-ttu-id="63d4a-109">Componentes COM</span><span class="sxs-lookup"><span data-stu-id="63d4a-109">COM components</span></span>  
  
-   <span data-ttu-id="63d4a-110">Certificados</span><span class="sxs-lookup"><span data-stu-id="63d4a-110">Certificates</span></span>  
  
-   <span data-ttu-id="63d4a-111">Secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="63d4a-111">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="63d4a-112">Directivas</span><span class="sxs-lookup"><span data-stu-id="63d4a-112">Policies</span></span>  
  
-   <span data-ttu-id="63d4a-113">Archivos ad hoc, como archivos Léame</span><span class="sxs-lookup"><span data-stu-id="63d4a-113">Ad hoc files, such as Readme files</span></span>  
  
-   <span data-ttu-id="63d4a-114">Directorios virtuales</span><span class="sxs-lookup"><span data-stu-id="63d4a-114">Virtual directories</span></span>  
  
-   <span data-ttu-id="63d4a-115">Artefactos de BAM</span><span class="sxs-lookup"><span data-stu-id="63d4a-115">BAM artifacts</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d4a-116">Los puertos de envío, grupos de puertos de envío, ubicaciones de recepción y puertos de recepción no son artefactos basados en archivos y no se pueden agregar a una aplicación.</span><span class="sxs-lookup"><span data-stu-id="63d4a-116">Send ports, send port groups, receive locations, and receive ports are not file-based artifacts and cannot be added to an application.</span></span> <span data-ttu-id="63d4a-117">Debe crear estos artefactos dentro de una determinada aplicación.</span><span class="sxs-lookup"><span data-stu-id="63d4a-117">You must create these artifacts within a given application.</span></span> <span data-ttu-id="63d4a-118">A continuación, puede moverlos a una aplicación diferente si desea.</span><span class="sxs-lookup"><span data-stu-id="63d4a-118">You can then move them to a different application, if you want.</span></span> <span data-ttu-id="63d4a-119">Las orquestaciones, los esquemas, las asignaciones y las canalizaciones se implementan y se administran como parte de los ensamblados que contienen estos elementos.</span><span class="sxs-lookup"><span data-stu-id="63d4a-119">Orchestrations, schemas, maps and pipelines are all deployed and managed as part of the assemblies that contain them.</span></span>  
  
 <span data-ttu-id="63d4a-120">Cuando agregue un artefacto a una aplicación, el artefacto se asocia a la aplicación de la base de datos de administración de BizTalk y los datos basados en archivos del artefacto se agregan también a la base de datos de administración.</span><span class="sxs-lookup"><span data-stu-id="63d4a-120">When you add an artifact to an application, the artifact is associated with the application in the BizTalk Management database, and file-based data for the artifact is added to the Management database as well.</span></span> <span data-ttu-id="63d4a-121">Esto le permite transportar aplicaciones y artefactos con facilidad de un grupo de BizTalk a otro ya que puede exportar la aplicación y los datos de los artefactos a un archivo .msi desde la base de datos de administración y, a continuación, importarlos a una base de datos de administración de un grupo de BizTalk diferente.</span><span class="sxs-lookup"><span data-stu-id="63d4a-121">This allows you to easily transport applications and artifacts from one BizTalk group to another because you can export the application and the data for its artifacts into an .msi file from the Management database, and then import it into a Management database in a different BizTalk group.</span></span>  
  
 <span data-ttu-id="63d4a-122">Cuando agrega un archivo de enlace a una aplicación, puede especificar el entorno de implementación de destino en el que desea que se apliquen los enlaces.</span><span class="sxs-lookup"><span data-stu-id="63d4a-122">When you add a binding file to an application, you can specify the target deployment environment in which you want the bindings to be applied.</span></span> <span data-ttu-id="63d4a-123">A diferencia de lo que ocurre al importar un archivo de enlace, cuando agrega un archivo de enlace no se aplican los enlaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="63d4a-123">Unlike importing a binding file, when you add a binding file, its bindings are not applied.</span></span>  
  
 <span data-ttu-id="63d4a-124">Al agregar un ensamblado de BizTalk o un ensamblado .NET a una aplicación, éste se agrega a la caché de ensamblados global si especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="63d4a-124">When you add a BizTalk assembly or a .NET assembly to an application, the assembly is added to the global assembly cache if you specify this option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d4a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="63d4a-125">See Also</span></span>  
 <span data-ttu-id="63d4a-126">[¿Qué ocurre con los artefactos durante la implementación de aplicaciones](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="63d4a-126">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="63d4a-127">[Cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="63d4a-127">[How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md) </span></span>  
 <span data-ttu-id="63d4a-128">[Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="63d4a-128">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="63d4a-129">Cómo exportar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="63d4a-129">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)