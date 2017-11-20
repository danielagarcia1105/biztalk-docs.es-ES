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
ms.openlocfilehash: b06c7383dee805612a3f599148f1d631891ace79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="b8fdb-102">Instalar el ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="b8fdb-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="b8fdb-103">Esta sección describe el proceso de instalación del ejemplo de servicio de resolución.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="b8fdb-104">El servicio de resolución depende el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] principales de la solución.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="b8fdb-105">Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automáticamente copia e instala los ensamblados básicos necesarios para este ejemplo en las ubicaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="b8fdb-106">**Para instalar el ejemplo de servicio de la resolución del proyecto de la solución**</span><span class="sxs-lookup"><span data-stu-id="b8fdb-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="b8fdb-107">En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService\Install\Scripts.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="b8fdb-108">Haga doble clic en el archivo Setup_bin.cmd.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="b8fdb-109">Para confirmar la correcta instalación del ejemplo, o si se están produciendo problemas al ejecutar aplicaciones, puede usar la lista proporcionada en la tabla siguiente para comprobar la presencia de los ensamblados necesarios y otros artefactos.</span><span class="sxs-lookup"><span data-stu-id="b8fdb-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="b8fdb-110">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b8fdb-110">Location</span></span>|<span data-ttu-id="b8fdb-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="b8fdb-111">Category</span></span>|<span data-ttu-id="b8fdb-112">Nombre y versión del componente</span><span class="sxs-lookup"><span data-stu-id="b8fdb-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="b8fdb-113">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-114">Orquestaciones</span><span class="sxs-lookup"><span data-stu-id="b8fdb-114">Orchestrations</span></span>|<span data-ttu-id="b8fdb-115">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-115">(none)</span></span>|  
|<span data-ttu-id="b8fdb-116">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-117">Puertos de envío</span><span class="sxs-lookup"><span data-stu-id="b8fdb-117">Send Ports</span></span>|<span data-ttu-id="b8fdb-118">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-118">(none)</span></span>|  
|<span data-ttu-id="b8fdb-119">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-120">Puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="b8fdb-120">Receive Ports</span></span>|<span data-ttu-id="b8fdb-121">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-121">(none)</span></span>|  
|<span data-ttu-id="b8fdb-122">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-123">Ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="b8fdb-123">Receive Locations</span></span>|<span data-ttu-id="b8fdb-124">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-124">(none)</span></span>|  
|<span data-ttu-id="b8fdb-125">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-126">Esquemas</span><span class="sxs-lookup"><span data-stu-id="b8fdb-126">Schemas</span></span>|<span data-ttu-id="b8fdb-127">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-127">(none)</span></span>|  
|<span data-ttu-id="b8fdb-128">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-129">Canalizaciones</span><span class="sxs-lookup"><span data-stu-id="b8fdb-129">Pipelines</span></span>|<span data-ttu-id="b8fdb-130">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-130">(none)</span></span>|  
|<span data-ttu-id="b8fdb-131">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-132">Recursos</span><span class="sxs-lookup"><span data-stu-id="b8fdb-132">Resources</span></span>|<span data-ttu-id="b8fdb-133">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-133">(none)</span></span>|  
|<span data-ttu-id="b8fdb-134">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-135">Directivas</span><span class="sxs-lookup"><span data-stu-id="b8fdb-135">Policies</span></span>|<span data-ttu-id="b8fdb-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="b8fdb-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="b8fdb-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="b8fdb-137">ResolveMap</span></span>|  
|<span data-ttu-id="b8fdb-138">Aplicación de BizTalk GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="b8fdb-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="b8fdb-139">Mapas</span><span class="sxs-lookup"><span data-stu-id="b8fdb-139">Maps</span></span>|<span data-ttu-id="b8fdb-140">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-140">(none)</span></span>|  
|<span data-ttu-id="b8fdb-141">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="b8fdb-141">Global assembly cache</span></span>|<span data-ttu-id="b8fdb-142">Ensamblados</span><span class="sxs-lookup"><span data-stu-id="b8fdb-142">Assemblies</span></span>|<span data-ttu-id="b8fdb-143">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-143">(none)</span></span>|  
|<span data-ttu-id="b8fdb-144">% Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline componentes</span><span class="sxs-lookup"><span data-stu-id="b8fdb-144">%Program Files%\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline Components</span></span>|<span data-ttu-id="b8fdb-145">Componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="b8fdb-145">Pipeline components</span></span>|<span data-ttu-id="b8fdb-146">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="b8fdb-146">(none)</span></span>|