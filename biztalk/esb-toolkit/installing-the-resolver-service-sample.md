---
title: "Instalar el ejemplo de servicio de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd438725b53362cda1b041af697283e68d77ba7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="2b43a-102">Instalar el ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="2b43a-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="2b43a-103">Esta sección describe el proceso de instalación del ejemplo de servicio de resolución.</span><span class="sxs-lookup"><span data-stu-id="2b43a-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="2b43a-104">El servicio de resolución depende el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] principales de la solución.</span><span class="sxs-lookup"><span data-stu-id="2b43a-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="2b43a-105">Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automáticamente copia e instala los ensamblados básicos necesarios para este ejemplo en las ubicaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="2b43a-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="2b43a-106">**Para instalar el ejemplo de servicio de la resolución del proyecto de la solución**</span><span class="sxs-lookup"><span data-stu-id="2b43a-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="2b43a-107">En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService\Install\Scripts.</span><span class="sxs-lookup"><span data-stu-id="2b43a-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="2b43a-108">Haga doble clic en el archivo Setup_bin.cmd.</span><span class="sxs-lookup"><span data-stu-id="2b43a-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="2b43a-109">Para confirmar la correcta instalación del ejemplo, o si se están produciendo problemas al ejecutar aplicaciones, puede usar la lista proporcionada en la tabla siguiente para comprobar la presencia de los ensamblados necesarios y otros artefactos.</span><span class="sxs-lookup"><span data-stu-id="2b43a-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="2b43a-110">Ubicación</span><span class="sxs-lookup"><span data-stu-id="2b43a-110">Location</span></span>|<span data-ttu-id="2b43a-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="2b43a-111">Category</span></span>|<span data-ttu-id="2b43a-112">Nombre y versión del componente</span><span class="sxs-lookup"><span data-stu-id="2b43a-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="2b43a-113">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-114">Orquestaciones</span><span class="sxs-lookup"><span data-stu-id="2b43a-114">Orchestrations</span></span>|<span data-ttu-id="2b43a-115">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-115">(none)</span></span>|  
|<span data-ttu-id="2b43a-116">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-117">Puertos de envío</span><span class="sxs-lookup"><span data-stu-id="2b43a-117">Send Ports</span></span>|<span data-ttu-id="2b43a-118">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-118">(none)</span></span>|  
|<span data-ttu-id="2b43a-119">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-120">Puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="2b43a-120">Receive Ports</span></span>|<span data-ttu-id="2b43a-121">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-121">(none)</span></span>|  
|<span data-ttu-id="2b43a-122">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-123">Ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="2b43a-123">Receive Locations</span></span>|<span data-ttu-id="2b43a-124">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-124">(none)</span></span>|  
|<span data-ttu-id="2b43a-125">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-126">Esquemas</span><span class="sxs-lookup"><span data-stu-id="2b43a-126">Schemas</span></span>|<span data-ttu-id="2b43a-127">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-127">(none)</span></span>|  
|<span data-ttu-id="2b43a-128">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-129">Canalizaciones</span><span class="sxs-lookup"><span data-stu-id="2b43a-129">Pipelines</span></span>|<span data-ttu-id="2b43a-130">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-130">(none)</span></span>|  
|<span data-ttu-id="2b43a-131">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-132">Recursos</span><span class="sxs-lookup"><span data-stu-id="2b43a-132">Resources</span></span>|<span data-ttu-id="2b43a-133">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-133">(none)</span></span>|  
|<span data-ttu-id="2b43a-134">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-135">Directivas</span><span class="sxs-lookup"><span data-stu-id="2b43a-135">Policies</span></span>|<span data-ttu-id="2b43a-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b43a-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="2b43a-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="2b43a-137">ResolveMap</span></span>|  
|<span data-ttu-id="2b43a-138">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="2b43a-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="2b43a-139">Mapas</span><span class="sxs-lookup"><span data-stu-id="2b43a-139">Maps</span></span>|<span data-ttu-id="2b43a-140">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-140">(none)</span></span>|  
|<span data-ttu-id="2b43a-141">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="2b43a-141">Global assembly cache</span></span>|<span data-ttu-id="2b43a-142">Ensamblados</span><span class="sxs-lookup"><span data-stu-id="2b43a-142">Assemblies</span></span>|<span data-ttu-id="2b43a-143">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-143">(none)</span></span>|  
|<span data-ttu-id="2b43a-144">% Program Files %\\componentes BizTalk Server\Pipeline</span><span class="sxs-lookup"><span data-stu-id="2b43a-144">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="2b43a-145">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="2b43a-145">Pipeline components</span></span>|<span data-ttu-id="2b43a-146">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="2b43a-146">(none)</span></span>|