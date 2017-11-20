---
title: "Inicio de sesión único: Evento 11026 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecee6d3c3e6dcf01b8489c4041f4aab717eba585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11026"></a><span data-ttu-id="95e39-102">Inicio de sesión único: Evento 11026</span><span class="sxs-lookup"><span data-stu-id="95e39-102">Single Sign-On: Event 11026</span></span>
## <a name="details"></a><span data-ttu-id="95e39-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="95e39-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95e39-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="95e39-104">Product Name</span></span>|<span data-ttu-id="95e39-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="95e39-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="95e39-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="95e39-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="95e39-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="95e39-107">Event ID</span></span>|<span data-ttu-id="95e39-108">11026</span><span class="sxs-lookup"><span data-stu-id="95e39-108">11026</span></span>|  
|<span data-ttu-id="95e39-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="95e39-109">Event Source</span></span>|<span data-ttu-id="95e39-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="95e39-110">ENTSSO</span></span>|  
|<span data-ttu-id="95e39-111">Componente</span><span class="sxs-lookup"><span data-stu-id="95e39-111">Component</span></span>|<span data-ttu-id="95e39-112">N/D</span><span class="sxs-lookup"><span data-stu-id="95e39-112">N/A</span></span>|  
|<span data-ttu-id="95e39-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="95e39-113">Symbolic Name</span></span>|<span data-ttu-id="95e39-114">SSO_WARN_EXISTING_GROUP_MAPPING</span><span class="sxs-lookup"><span data-stu-id="95e39-114">SSO_WARN_EXISTING_GROUP_MAPPING</span></span>|  
|<span data-ttu-id="95e39-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="95e39-115">Message Text</span></span>|<span data-ttu-id="95e39-116">No se pudo crear la asignación de grupo nueva debido a un conflicto con una asignación existente.</span><span class="sxs-lookup"><span data-stu-id="95e39-116">A new group mapping could not be created because there is a conflict with an existing mapping.</span></span> <span data-ttu-id="95e39-117">Elimine la asignación existente y vuelva a intentarlo.%r</span><span class="sxs-lookup"><span data-stu-id="95e39-117">Please delete the existing mapping and try again.%r</span></span><br /><br /> <span data-ttu-id="95e39-118">Asignación existente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="95e39-118">Existing Mapping: %1%r</span></span><br /><br /> <span data-ttu-id="95e39-119">Nueva asignación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="95e39-119">New Mapping: %2%r</span></span><br /><br /> <span data-ttu-id="95e39-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="95e39-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="95e39-121">Nombre de la aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="95e39-121">Application Name: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95e39-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="95e39-122">Explanation</span></span>  
 <span data-ttu-id="95e39-123">La causa más probable es que el sistema está usando una versión anterior de Inicio de sesión único empresarial y aplicaciones de grupo antiguas.</span><span class="sxs-lookup"><span data-stu-id="95e39-123">The most likely cause is that your system is using an old version of Enterprise Single Sign-On, and old group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95e39-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="95e39-124">User Action</span></span>  
 <span data-ttu-id="95e39-125">Elimine la asignación y vuelva a crearla según se recomienda en la advertencia.</span><span class="sxs-lookup"><span data-stu-id="95e39-125">Delete and recreate the mapping as suggested in the warning.</span></span> <span data-ttu-id="95e39-126">Si esto no funciona, es posible que deba actualizar a una versión más reciente de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="95e39-126">If this fails, you may need to upgrade to a more recent version of Enterprise Single Sign-On.</span></span>