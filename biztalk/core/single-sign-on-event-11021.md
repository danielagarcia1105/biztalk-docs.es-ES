---
title: "Inicio de sesión único: Evento 11021 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e246ac3d0bbab4e991b17c091567b4b59131b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11021"></a><span data-ttu-id="3c574-102">Inicio de sesión único: Evento 11021</span><span class="sxs-lookup"><span data-stu-id="3c574-102">Single Sign-On: Event 11021</span></span>
## <a name="details"></a><span data-ttu-id="3c574-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c574-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c574-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3c574-104">Product Name</span></span>|<span data-ttu-id="3c574-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3c574-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3c574-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3c574-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3c574-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3c574-107">Event ID</span></span>|<span data-ttu-id="3c574-108">11021</span><span class="sxs-lookup"><span data-stu-id="3c574-108">11021</span></span>|  
|<span data-ttu-id="3c574-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3c574-109">Event Source</span></span>|<span data-ttu-id="3c574-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c574-110">ENTSSO</span></span>|  
|<span data-ttu-id="3c574-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3c574-111">Component</span></span>|<span data-ttu-id="3c574-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3c574-112">N/A</span></span>|  
|<span data-ttu-id="3c574-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c574-113">Symbolic Name</span></span>|<span data-ttu-id="3c574-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="3c574-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="3c574-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c574-115">Message Text</span></span>|<span data-ttu-id="3c574-116">El cambio de contraseña externa provocará el cambio de una cuenta externa diferente.%r</span><span class="sxs-lookup"><span data-stu-id="3c574-116">An external password change will cause a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="3c574-117">Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="3c574-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="3c574-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3c574-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3c574-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3c574-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3c574-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3c574-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="3c574-121">Cuenta externa 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="3c574-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="3c574-122">Cuenta externa 2: %5</span><span class="sxs-lookup"><span data-stu-id="3c574-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c574-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c574-123">Explanation</span></span>  
 <span data-ttu-id="3c574-124">Este mensaje de información indica que el cambio de contraseña externa provocará el cambio de una cuenta externa diferente.</span><span class="sxs-lookup"><span data-stu-id="3c574-124">This is an informational message stating that an external password change will cause a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c574-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c574-125">User Action</span></span>  
 <span data-ttu-id="3c574-126">Debe confirmar de inmediato que este cambio se efectuó con su conocimiento y autorización.</span><span class="sxs-lookup"><span data-stu-id="3c574-126">You should confirm immediately that this change was made with your knowledge and authorization.</span></span> <span data-ttu-id="3c574-127">Si es así, no se necesitan acciones.</span><span class="sxs-lookup"><span data-stu-id="3c574-127">If so, no action is required.</span></span> <span data-ttu-id="3c574-128">De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.</span><span class="sxs-lookup"><span data-stu-id="3c574-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>