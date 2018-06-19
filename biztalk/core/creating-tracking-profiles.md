---
title: Creación de perfiles de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 62598529-9763-4c73-acbe-06ce5650134a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ce1edcab724201dc03792a37b0b796625201351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238276"
---
# <a name="creating-tracking-profiles"></a><span data-ttu-id="e6e7b-102">Crear perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e6e7b-102">Creating Tracking Profiles</span></span>
<span data-ttu-id="e6e7b-103">Puede crear un perfil de seguimiento nuevo o modificar uno existente para administrar y controlar mejor un determinado proceso empresarial de la organización.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-103">You create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span> <span data-ttu-id="e6e7b-104">El Editor de perfiles de seguimiento (TPE) permite definir los datos que deben recopilarse para satisfacer los requisitos del analista de negocios.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-104">The Tracking Profile Editor (TPE) allows you to define the data to collect to meet the business analyst's requirement.</span></span> <span data-ttu-id="e6e7b-105">El perfil que cree o modifique podrá ser tan simple o tan complejo como desee, en función de los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-105">The profile you create or modify can be as simple or as complex as you like depending on your business requirements.</span></span>  
  
 <span data-ttu-id="e6e7b-106">Como programador, debe crear un perfil nuevo basado en una definición de actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-106">As a developer, you create a new profile based on a BAM activity definition.</span></span> <span data-ttu-id="e6e7b-107">Una definición de actividad implementada podría tener ya un perfil definido.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-107">A deployed activity definition may already have a profile defined for it.</span></span> <span data-ttu-id="e6e7b-108">De no ser así, debe crear un perfil de seguimiento llevando a cabo las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6e7b-108">If not, you create a tracking profile by performing these tasks:</span></span>  
  
-   <span data-ttu-id="e6e7b-109">Seleccionar un servidor y una base de datos de implementación.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-109">Selecting a deployment server and database</span></span>  
  
-   <span data-ttu-id="e6e7b-110">Seleccionar una definición de actividad de BAM implementada de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-110">Selecting a deployed BAM activity definition from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="e6e7b-111">Definir los datos que deben extraerse de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-111">Defining the data to be extracted from the orchestration</span></span>  
  
-   <span data-ttu-id="e6e7b-112">Conectar actividades, si la implementación real del proceso empresarial abarca más de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="e6e7b-112">Connecting activities, if the actual implementation of your business process spans more than one orchestration</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6e7b-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e6e7b-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e6e7b-114">Cómo crear un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e6e7b-114">How to Create a Tracking Profile</span></span>](../core/how-to-create-a-tracking-profile.md)  
  
-   [<span data-ttu-id="e6e7b-115">Cómo asignar orígenes de eventos</span><span class="sxs-lookup"><span data-stu-id="e6e7b-115">How to Map Event Sources</span></span>](../core/how-to-map-event-sources.md)  
  
-   [<span data-ttu-id="e6e7b-116">Cómo asignar datos de elemento</span><span class="sxs-lookup"><span data-stu-id="e6e7b-116">How to Map Item Data</span></span>](../core/how-to-map-item-data.md)  
  
-   [<span data-ttu-id="e6e7b-117">Cómo crear una continuación</span><span class="sxs-lookup"><span data-stu-id="e6e7b-117">How to Create a Continuation</span></span>](../core/how-to-create-a-continuation.md)  
  
-   [<span data-ttu-id="e6e7b-118">Cómo asignar varios ensamblados</span><span class="sxs-lookup"><span data-stu-id="e6e7b-118">How to Map Multiple Assemblies</span></span>](../core/how-to-map-multiple-assemblies.md)  
  
-   [<span data-ttu-id="e6e7b-119">Cómo aplicar y quitar un perfil de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e6e7b-119">How to Apply and Remove a Tracking Profile</span></span>](../core/how-to-apply-and-remove-a-tracking-profile.md)