---
title: Implementar aplicaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.deployment.application
helpviewer_keywords:
- deploying [applications]
- managing [applications], deploying
- applications, deploying
ms.assetid: eef12d8a-6f5c-4eb2-b85b-df9281c0b88e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56417fa7e9c4aef40a6c76144a8e2d9e5bae548f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239076"
---
# <a name="deploying-biztalk-applications"></a><span data-ttu-id="67b0b-102">Implementar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="67b0b-102">Deploying BizTalk Applications</span></span>
<span data-ttu-id="67b0b-103">Esta sección proporciona la siguiente información acerca de la implementación de aplicaciones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="67b0b-103">This section provides the following information about deploying BizTalk applications:</span></span>  
  
-   <span data-ttu-id="67b0b-104">Exportar una aplicación y los artefactos correspondientes a un archivo de Windows Installer (.msi)</span><span class="sxs-lookup"><span data-stu-id="67b0b-104">Exporting an application and its artifacts to a Windows Installer (.msi) file</span></span>  
  
-   <span data-ttu-id="67b0b-105">Importar el archivo .msi en otro grupo de BizTalk para crear la aplicación y los artefactos correspondientes en el grupo nuevo</span><span class="sxs-lookup"><span data-stu-id="67b0b-105">Importing the .msi file into another BizTalk group to create the application and its artifacts in the new group</span></span>  
  
-   <span data-ttu-id="67b0b-106">Instalar la aplicación en los equipos que la ejecutarán</span><span class="sxs-lookup"><span data-stu-id="67b0b-106">Installing the application on the computers that will run it</span></span>  
  
-   <span data-ttu-id="67b0b-107">Instalar ensamblados de BizTalk en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="67b0b-107">Installing BizTalk assemblies to the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="67b0b-108">Supervisar el progreso de la implementación y probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="67b0b-108">Monitoring the progress of the deployment and testing the application</span></span>  
  
-   <span data-ttu-id="67b0b-109">Implementar una aplicación en un socio comercial</span><span class="sxs-lookup"><span data-stu-id="67b0b-109">Deploying an application to a business partner</span></span>  
  
-   <span data-ttu-id="67b0b-110">Editar un archivo de enlace para personalizar los enlaces para los distintos entornos de implementación</span><span class="sxs-lookup"><span data-stu-id="67b0b-110">Editing a binding file to customize the bindings for different deployment environments</span></span>  
  
 <span data-ttu-id="67b0b-111">Para las listas de comprobación de las tareas que debe realizar en escenarios de implementación de aplicación diferente, consulte [listas de comprobación de administración y la implementación de aplicaciones de BizTalk](../core/biztalk-application-deployment-and-management-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="67b0b-111">For checklists of tasks that you need to perform in different application deployment scenarios, see [BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md).</span></span> <span data-ttu-id="67b0b-112">Para obtener información general sobre las aplicaciones de BizTalk y su implementación, consulte [implementación de aplicación de BizTalk de descripción y administración](../core/understanding-biztalk-application-deployment-and-management.md).</span><span class="sxs-lookup"><span data-stu-id="67b0b-112">For background information on BizTalk applications and their deployment, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="67b0b-113">Para obtener información acerca de cómo crear una aplicación y cómo modificarla agregando o quitando artefactos o agregar una referencia a otra aplicación, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="67b0b-113">For information about creating an application and modifying it by adding or removing artifacts or adding a reference to another application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span> <span data-ttu-id="67b0b-114">Para obtener información sobre cómo implementar ensamblados de BizTalk, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="67b0b-114">For information about deploying BizTalk assemblies, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67b0b-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="67b0b-115">In This Section</span></span>  
  
-   [<span data-ttu-id="67b0b-116">Exportar aplicaciones de BizTalk, los enlaces y directivas</span><span class="sxs-lookup"><span data-stu-id="67b0b-116">Exporting BizTalk Applications, Bindings, and Policies</span></span>](../core/exporting-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="67b0b-117">Importación de directivas, los enlaces y las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="67b0b-117">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="67b0b-118">Cómo instalar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="67b0b-118">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)  
  
-   [<span data-ttu-id="67b0b-119">Supervisar el progreso de la implementación de aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="67b0b-119">Monitoring the Progress of Your BizTalk Application Deployment</span></span>](../core/monitoring-the-progress-of-your-biztalk-application-deployment.md)