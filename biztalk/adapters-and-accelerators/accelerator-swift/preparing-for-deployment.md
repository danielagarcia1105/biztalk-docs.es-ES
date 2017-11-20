---
title: "Preparación para la implementación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deploying, planning
ms.assetid: 437caa31-f7f8-42e0-af1f-13aaee0955cd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c24a3404a5ea6a35269cd29ae792a46034a69f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-for-deployment"></a><span data-ttu-id="64933-102">Preparación para la implementación</span><span class="sxs-lookup"><span data-stu-id="64933-102">Preparing for Deployment</span></span>
<span data-ttu-id="64933-103">Esta sección proporciona información acerca de la fase de planificación y preparación de la implementación.</span><span class="sxs-lookup"><span data-stu-id="64933-103">This section provides information about the planning and preparation phase of the deployment.</span></span> <span data-ttu-id="64933-104">Antes de implementar una implementación, realice los preparativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="64933-104">Before implementing a deployment, make the following preparations:</span></span>  
  
1.  <span data-ttu-id="64933-105">Leer y comprender los problemas conocidos y preparar el equipo:</span><span class="sxs-lookup"><span data-stu-id="64933-105">Read and understand any known issues, and prepare the equipment:</span></span>  
  
    -   <span data-ttu-id="64933-106">Crear una lista de comprobación del hardware y software necesarios para la implementación y una red diagrama e implementación hoja de cálculo que reflejan la variación de la implementación (basada en el diagrama de red y la arquitectura de implementación que ha seleccionado).</span><span class="sxs-lookup"><span data-stu-id="64933-106">Create a checklist of the hardware and software required for your deployment, and a network diagram and deployment worksheet that reflect your variation of the deployment (based on the network diagram and for the deployment architecture you have selected).</span></span>  
  
    -   <span data-ttu-id="64933-107">Adquirir el hardware y software en la lista de comprobación.</span><span class="sxs-lookup"><span data-stu-id="64933-107">Acquire the hardware and software on your checklist.</span></span> <span data-ttu-id="64933-108">Esta adquisición incluye la descarga de todos los service packs, revisiones y actualizaciones de software que son necesarias para la implementación.</span><span class="sxs-lookup"><span data-stu-id="64933-108">This acquisition includes downloading all of the service packs, hotfixes, and software updates that are required for your deployment.</span></span>  
  
         <span data-ttu-id="64933-109">Descargar estos componentes de software mediante un equipo con acceso a Internet y, a continuación, copie estos componentes de software en un CD-ROM para su distribución sea más fácil.</span><span class="sxs-lookup"><span data-stu-id="64933-109">Download these software components using a computer with Internet access and then copy these software components onto a CD-ROM for easier distribution.</span></span>  
  
2.  <span data-ttu-id="64933-110">Separar la implementación en distintas fases e identificar las tareas asociadas a cada fase.</span><span class="sxs-lookup"><span data-stu-id="64933-110">Separate your deployment into different stages and identify the tasks associated with each stage.</span></span> <span data-ttu-id="64933-111">Esta estrategia simplifica el proceso de implementación, organice las tareas en función de una fase de implementación específica.</span><span class="sxs-lookup"><span data-stu-id="64933-111">This strategy simplifies the deployment process by organizing the tasks according to a specific deployment stage.</span></span> <span data-ttu-id="64933-112">Por ejemplo, la implementación recomendada incluye las siguientes fases de implementación de servidor:</span><span class="sxs-lookup"><span data-stu-id="64933-112">For example, the prescribed deployment includes the following server deployment stages:</span></span>  
  
3.  <span data-ttu-id="64933-113">Configurar el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="64933-113">Configuring the domain controller.</span></span>  
  
4.  <span data-ttu-id="64933-114">Configuración de las bases de datos (incluido el tiempo de ejecución [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] tiempo de diseño y el clúster de servidor de base de datos).</span><span class="sxs-lookup"><span data-stu-id="64933-114">Configuring the databases (including the run-time [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] cluster and design-time database server).</span></span>  
  
5.  <span data-ttu-id="64933-115">Configurar los servidores BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="64933-115">Configuring the BizTalk servers.</span></span>  
  
 <span data-ttu-id="64933-116">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="64933-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="64933-117">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="64933-117">Network Requirements</span></span>](../../adapters-and-accelerators/accelerator-swift/network-requirements.md)  
  
-   [<span data-ttu-id="64933-118">Requisitos de hardware y Software para la implementación</span><span class="sxs-lookup"><span data-stu-id="64933-118">Hardware and Software Requirements for Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/hardware-and-software-requirements-for-deployment.md)