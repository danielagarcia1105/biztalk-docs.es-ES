---
title: Estado de artefactos de archivo durante la implementación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="status-of-file-artifacts-during-deployment"></a><span data-ttu-id="0bae3-102">Estado de artefactos de archivo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="0bae3-102">Status of File Artifacts During Deployment</span></span>
<span data-ttu-id="0bae3-103">Es posible que deba saber qué artefactos basados en archivos existen en el sistema de archivos cuando se ejecuta una secuencia de comandos previa o posterior al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="0bae3-103">You may need to know what file-based artifacts exist on the file system when a pre- or post-processing script executes.</span></span> <span data-ttu-id="0bae3-104">Por ejemplo, puede que quiera ejecutar una secuencia de comandos posterior al procesamiento durante la desinstalación y eliminar un archivo de artefacto concreto del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="0bae3-104">For example, you might want a post-processing script to run during uninstallation and delete a certain artifact file from the file system.</span></span> <span data-ttu-id="0bae3-105">Los artefactos basados en archivos consisten en artefactos que pueden existir como archivos en el sistema de archivos local, además de su representación en las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0bae3-105">File-based artifacts are artifacts that can exist as files on the local file system, in addition to their representation in the BizTalk databases.</span></span> <span data-ttu-id="0bae3-106">Algunos ejemplos de artefactos basados en archivos son los componentes COM, los ensamblados .NET, los ensamblados de BizTalk, los artefactos de BAM, los archivos ad hoc, las secuencias de comandos y los archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="0bae3-106">Examples of file-based artifacts are COM components, .NET assemblies, BizTalk assemblies, BAM artifacts, ad hoc files, scripts, and binding files.</span></span>  
  
 <span data-ttu-id="0bae3-107">En la tabla siguiente se resume el estado de los archivos de artefacto en cada momento del proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="0bae3-107">The following table summarizes the status of the artifact files at each point in the deployment process.</span></span>  
  
|<span data-ttu-id="0bae3-108">Punto del proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="0bae3-108">Point in the Deployment Process</span></span>|<span data-ttu-id="0bae3-109">Estado de los archivos de artefacto de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0bae3-109">Status of Application Artifact Files</span></span>|  
|-------------------------------------|------------------------------------------|  
|<span data-ttu-id="0bae3-110">Anterior a la instalación</span><span class="sxs-lookup"><span data-stu-id="0bae3-110">Pre-installation</span></span>|<span data-ttu-id="0bae3-111">Solo hay archivos del tipo System.BizTalk.File en el sistema de archivos local.\*</span><span class="sxs-lookup"><span data-stu-id="0bae3-111">Only files of the type System.BizTalk.File exist on the local file system.\*</span></span>|  
|<span data-ttu-id="0bae3-112">Posterior a la instalación</span><span class="sxs-lookup"><span data-stu-id="0bae3-112">Post-installation</span></span>|<span data-ttu-id="0bae3-113">Todos los archivos se encuentran en el sistema de archivos local.\*</span><span class="sxs-lookup"><span data-stu-id="0bae3-113">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="0bae3-114">Anterior a la desinstalación</span><span class="sxs-lookup"><span data-stu-id="0bae3-114">Pre-uninstallation</span></span>|<span data-ttu-id="0bae3-115">Todos los archivos se encuentran en el sistema de archivos local.\*</span><span class="sxs-lookup"><span data-stu-id="0bae3-115">All files exist on the local file system.\*</span></span>|  
|<span data-ttu-id="0bae3-116">Posterior a la desinstalación</span><span class="sxs-lookup"><span data-stu-id="0bae3-116">Post-uninstallation</span></span>|<span data-ttu-id="0bae3-117">Todos los archivos se han eliminado del sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="0bae3-117">All files have been deleted from the local file system.</span></span>|  
|<span data-ttu-id="0bae3-118">Anterior a la importación</span><span class="sxs-lookup"><span data-stu-id="0bae3-118">Pre-import</span></span>|<span data-ttu-id="0bae3-119">No hay archivos en el sistema de archivos local a menos que se haya instalado la aplicación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0bae3-119">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
|<span data-ttu-id="0bae3-120">Posterior a la importación</span><span class="sxs-lookup"><span data-stu-id="0bae3-120">Post-import</span></span>|<span data-ttu-id="0bae3-121">No hay archivos en el sistema de archivos local a menos que se haya instalado la aplicación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0bae3-121">No files exist on the local file system unless the application has been installed on the local computer.</span></span>|  
  
 <span data-ttu-id="0bae3-122">\* Archivos del sistema de archivos local sólo existen si se especificó una ubicación de destino válida cuando se agregó el archivo a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bae3-122">\* Files exist on the local file system only if a valid destination location was specified when the file was added to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bae3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bae3-123">See Also</span></span>  
 [<span data-ttu-id="0bae3-124">Uso de scripts previos y posteriores al procesamiento para personalizar la implementación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0bae3-124">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)