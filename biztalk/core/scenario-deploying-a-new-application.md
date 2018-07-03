---
title: 'Escenario: Implementar una aplicación nueva | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c706e990154f43f264e3c529a8ee7ce59efcc166
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986237"
---
# <a name="scenario-deploying-a-new-application"></a><span data-ttu-id="dc068-102">Escenario: Implementar una aplicación nueva</span><span class="sxs-lookup"><span data-stu-id="dc068-102">Scenario: Deploying a New Application</span></span>
<span data-ttu-id="dc068-103">En este tema se describe la implementación de una aplicación en un entorno nuevo en el que no se ha implementado antes; por ejemplo, la implementación de una aplicación que se ha configurado en un entorno de ensayo en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="dc068-103">This topic describes the scenario of deploying an application into a new environment where it has not been deployed before; for example, deploying an application that has been configured in a staging environment into a production environment.</span></span>  
  
 <span data-ttu-id="dc068-104">Como se describe en [el proceso de implementación de aplicación](../core/the-application-deployment-process.md), cuando desea mover una aplicación de un entorno a otro, exporte la aplicación a un archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="dc068-104">As described in [The Application Deployment Process](../core/the-application-deployment-process.md), when you want to move an application from one environment to another, you export the application into an .msi file.</span></span> <span data-ttu-id="dc068-105">Después importa el archivo .msi al grupo de BizTalk del entorno nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc068-105">You then import the .msi file into the BizTalk group in the new environment.</span></span> <span data-ttu-id="dc068-106">También instala la aplicación en los equipos de dicho grupo que ejecutarán la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc068-106">You also install the application on the computers in that group that will run the application.</span></span> <span data-ttu-id="dc068-107">Antes de que pueda comenzar a funcionar, debe instalar la aplicación en cada equipo que vaya a ejecutarla y también iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc068-107">Before it can begin functioning, you must install the application on each computer that will run it and also start the application.</span></span>  
  
 <span data-ttu-id="dc068-108">En el diagrama siguiente, la aplicación 1 se importa desde un archivo .msi en el grupo B de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dc068-108">In the following diagram, Application1 is imported from an .msi file into BizTalk Group B.</span></span>  
  
 <span data-ttu-id="dc068-109">![Implementar una aplicación de BizTalk](../core/media/deployapplication.gif "DeployApplication")</span><span class="sxs-lookup"><span data-stu-id="dc068-109">![Deploying a BizTalk application](../core/media/deployapplication.gif "DeployApplication")</span></span>  
  
 <span data-ttu-id="dc068-110">De este modo, se importan artefactos en las distintas bases de datos de BizTalk Server como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dc068-110">This imports artifacts into the various BizTalk Server databases as follows:</span></span>  
  
- <span data-ttu-id="dc068-111">El ensamblado de BizTalk, el ensamblado .NET, los enlaces, el archivo de enlace, la plantilla de BAM, el componente COM, el certificado y el archivo de texto se agregan todos ellos a la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dc068-111">The BizTalk assembly, .NET assembly, bindings, binding file, BAM template, COM component, certificate, and text file are all added to the BizTalk Management database.</span></span>  
  
- <span data-ttu-id="dc068-112">La directiva y el vocabulario se agregan a la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="dc068-112">The policy and vocabulary are added to the Rule Engine database.</span></span>  
  
- <span data-ttu-id="dc068-113">La plantilla de BAM y el archivo de definición de BAM se agregan a la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="dc068-113">The BAM template and BAM definition file are both added to the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="dc068-114">Cada uno de estos artefactos también se asocia a la aplicación 1 en la base de datos administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dc068-114">Each of these artifacts is also associated with Application1 in the BizTalk Management database.</span></span>  
  
  <span data-ttu-id="dc068-115">La aplicación también se instala en un equipo local desde el archivo .msi.</span><span class="sxs-lookup"><span data-stu-id="dc068-115">The application is also installed on a local computer from the .msi file.</span></span> <span data-ttu-id="dc068-116">De este modo se instalan distintos artefactos incluidos en el archivo .msi, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dc068-116">This installs various artifacts that are included in the .msi file, as follows:</span></span>  
  
- <span data-ttu-id="dc068-117">El directorio virtual, denominado VirtualDirectory, se crea en la metabase de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dc068-117">The virtual directory, named VirtualDirectory, is created in the Internet Information Services (IIS) metabase.</span></span>  
  
- <span data-ttu-id="dc068-118">El certificado se agrega al almacén de certificados local.</span><span class="sxs-lookup"><span data-stu-id="dc068-118">The certificate is added to the local certificate store.</span></span>  
  
- <span data-ttu-id="dc068-119">El archivo de texto y el componente COM se copian en el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="dc068-119">The text file and COM component are copied to the local file system.</span></span>  
  
- <span data-ttu-id="dc068-120">El ensamblado de BizTalk y el ensamblado .NET se agregan a la caché de ensamblados global (GAC) si se ha seleccionado esta opción de implementación para ellos.</span><span class="sxs-lookup"><span data-stu-id="dc068-120">The BizTalk assembly and .NET assembly are added to the global assembly cache (GAC), if this deployment option was selected for them.</span></span>  
  
- <span data-ttu-id="dc068-121">El ensamblado .NET y el componente COM se agregan al Registro de Windows si se ha seleccionado esta opción de implementación para ellos.</span><span class="sxs-lookup"><span data-stu-id="dc068-121">The .NET assembly and COM component are added to the Windows registry, if that deployment option was selected for them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc068-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc068-122">See Also</span></span>  
 <span data-ttu-id="dc068-123">[Implementación de aplicaciones y escenarios de administración](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="dc068-123">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="dc068-124">Implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="dc068-124">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)