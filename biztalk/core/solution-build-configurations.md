---
title: "Configuraciones de compilación de soluciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e537ca4bc2dd85722ddf3afd4eaba443aab7a25b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="solution-build-configurations"></a><span data-ttu-id="d135a-102">Configuraciones de generación de soluciones</span><span class="sxs-lookup"><span data-stu-id="d135a-102">Solution Build Configurations</span></span>
<span data-ttu-id="d135a-103">Al igual que ocurre con otros proyectos generados en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], es posible utilizar el Administrador de configuración para especificar configuraciones de generación de soluciones.</span><span class="sxs-lookup"><span data-stu-id="d135a-103">As with other projects that you build in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can use Configuration Manager to specify solution build configurations.</span></span> <span data-ttu-id="d135a-104">Las configuraciones de generación de soluciones permiten seleccionar qué proyectos se incluirán en las diferentes generaciones de una solución y si se van a implementar.</span><span class="sxs-lookup"><span data-stu-id="d135a-104">Solution build configurations enable you to determine which projects to include in builds of a solution and if they will be deployed.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="d135a-105">admite tanto **depurar** y **versión** configuraciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="d135a-105"> supports both **Debug** and **Release** build configurations.</span></span>  
  
 <span data-ttu-id="d135a-106">Una generación de soluciones configuración con una marca de verificación en la **generar** columna le permite crear una solución y para generar un ensamblado cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="d135a-106">A solution build configuration with a check mark in the **Build** column enables you to build a solution and to generate an assembly when you are finished.</span></span> <span data-ttu-id="d135a-107">Si también hay una marca de verificación en la **implementar** columna y, a continuación, la aplicación se implementará en función de la configuración de implementación en el Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="d135a-107">If a check mark is also present in the **Deploy** column, then the application will be deployed based on deployment settings in the Project Designer.</span></span>  
  
 <span data-ttu-id="d135a-108">Una referencia completa a Configuration Manager y la configuración de opciones proporcionados por el cuadro de diálogo cuadro puede encontrarse en el siguiente vínculo de referencia: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span><span class="sxs-lookup"><span data-stu-id="d135a-108">A complete reference to Configuration Manager and the configuration options provided by the dialog box can be found at the following reference link: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span></span>  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a><span data-ttu-id="d135a-109">Para configurar las propiedades de generación en el Administrador de configuración</span><span class="sxs-lookup"><span data-stu-id="d135a-109">To configure build properties in Configuration Manager</span></span>  
  
1.  <span data-ttu-id="d135a-110">En el menú **Compilar** , haga clic en **Administrador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="d135a-110">On the **Build** menu, click **Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="d135a-111">En el **Configuration Manager** cuadro de diálogo, seleccione uno de estos procedimientos para configurar las propiedades de compilación.</span><span class="sxs-lookup"><span data-stu-id="d135a-111">In the **Configuration Manager** dialog box, select one of following to configure the build properties.</span></span>  
  
    |<span data-ttu-id="d135a-112">Use</span><span class="sxs-lookup"><span data-stu-id="d135a-112">Use this</span></span>|<span data-ttu-id="d135a-113">Para</span><span class="sxs-lookup"><span data-stu-id="d135a-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d135a-114">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="d135a-114">**Configuration**</span></span>|<span data-ttu-id="d135a-115">Elegir entre **versión** o **depurar** configuraciones para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d135a-115">Choose from **Release** or **Debug** configurations for the project.</span></span> <span data-ttu-id="d135a-116">También puede crear una nueva configuración o modificar una existente.</span><span class="sxs-lookup"><span data-stu-id="d135a-116">Alternatively, create a new configuration or edit an existing one.</span></span>|  
    |<span data-ttu-id="d135a-117">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="d135a-117">**Platform**</span></span>|<span data-ttu-id="d135a-118">Elija una plataforma para el proyecto que represente la arquitectura de CPU del ensamblado compilado.</span><span class="sxs-lookup"><span data-stu-id="d135a-118">Choose a platform for the project representing the CPU architecture of the compiled assembly.</span></span> <span data-ttu-id="d135a-119">También puede crear una nueva plataforma o modificar una existente.</span><span class="sxs-lookup"><span data-stu-id="d135a-119">Alternatively, create a new platform or edit an existing one.</span></span>|  
    |<span data-ttu-id="d135a-120">**Compilar**</span><span class="sxs-lookup"><span data-stu-id="d135a-120">**Build**</span></span>|<span data-ttu-id="d135a-121">Active la casilla de esta columna para que un proyecto tenga el proyecto generado o regenerado como respuesta a un comando de generación para la solución.</span><span class="sxs-lookup"><span data-stu-id="d135a-121">Check the box in this column for a project to have the project built or rebuilt in response to a build command for the solution.</span></span>|  
    |<span data-ttu-id="d135a-122">**Implementación**</span><span class="sxs-lookup"><span data-stu-id="d135a-122">**Deploy**</span></span>|<span data-ttu-id="d135a-123">Active la casilla de esta columna para que se implemente el proyecto en función de la configuración de implementación cuando se emita un comando de generación para la solución o el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d135a-123">Check the box in this column to have the project deployed based on deployment settings when a build command is issued for the solution or project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d135a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d135a-124">See Also</span></span>  
 <span data-ttu-id="d135a-125">[Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d135a-125">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="d135a-126">Cómo crear proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d135a-126">How to Create BizTalk Projects</span></span>](../core/how-to-create-biztalk-projects.md)