---
title: "Inicio de sesión único: Evento 11020 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa6a0d72-ece6-4094-9263-dbf69bb068c8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 444a61beec74a9d7141df79d05d8863cc10d6dc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11020"></a><span data-ttu-id="5dfda-102">Inicio de sesión único: Evento 11020</span><span class="sxs-lookup"><span data-stu-id="5dfda-102">Single Sign-On: Event 11020</span></span>
## <a name="details"></a><span data-ttu-id="5dfda-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5dfda-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5dfda-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5dfda-104">Product Name</span></span>|<span data-ttu-id="5dfda-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5dfda-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5dfda-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5dfda-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5dfda-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5dfda-107">Event ID</span></span>|<span data-ttu-id="5dfda-108">11020</span><span class="sxs-lookup"><span data-stu-id="5dfda-108">11020</span></span>|  
|<span data-ttu-id="5dfda-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5dfda-109">Event Source</span></span>|<span data-ttu-id="5dfda-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5dfda-110">ENTSSO</span></span>|  
|<span data-ttu-id="5dfda-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5dfda-111">Component</span></span>|<span data-ttu-id="5dfda-112">N/D</span><span class="sxs-lookup"><span data-stu-id="5dfda-112">N/A</span></span>|  
|<span data-ttu-id="5dfda-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5dfda-113">Symbolic Name</span></span>|<span data-ttu-id="5dfda-114">SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="5dfda-114">SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="5dfda-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5dfda-115">Message Text</span></span>|<span data-ttu-id="5dfda-116">El cambio de contraseña de Windows provocará el cambio de una cuenta de Windows diferente.%r</span><span class="sxs-lookup"><span data-stu-id="5dfda-116">A Windows password change will cause a different Windows account to be changed.%r</span></span><br /><br /> <span data-ttu-id="5dfda-117">Esto se permite porque el adaptador de este sistema externo está configurado para permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="5dfda-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="5dfda-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5dfda-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="5dfda-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5dfda-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="5dfda-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5dfda-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="5dfda-121">Cuenta de Windows 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="5dfda-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="5dfda-122">Cuenta de Windows 2: %5</span><span class="sxs-lookup"><span data-stu-id="5dfda-122">Windows Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5dfda-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="5dfda-123">Explanation</span></span>  
 <span data-ttu-id="5dfda-124">Este mensaje de información indica que el cambio de contraseña de Windows provocará el cambio de una cuenta de Windows diferente.</span><span class="sxs-lookup"><span data-stu-id="5dfda-124">This is an informational message stating that a Windows password change will cause a different Windows account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5dfda-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5dfda-125">User Action</span></span>  
 <span data-ttu-id="5dfda-126">Debe confirmar de inmediato que este cambio se efectuó con su conocimiento y autorización.</span><span class="sxs-lookup"><span data-stu-id="5dfda-126">You should confirm immediately that this change was made with your knowledge and authorization.</span></span> <span data-ttu-id="5dfda-127">Si es así, no se necesitan acciones.</span><span class="sxs-lookup"><span data-stu-id="5dfda-127">If so, no action is required.</span></span> <span data-ttu-id="5dfda-128">De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.</span><span class="sxs-lookup"><span data-stu-id="5dfda-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>