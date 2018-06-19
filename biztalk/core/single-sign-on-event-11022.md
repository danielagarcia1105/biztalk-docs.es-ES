---
title: 'Inicio de sesión único: Evento 11022 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccae36e9beef672e6c5fb7917c88341ce4bb3c08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276996"
---
# <a name="single-sign-on-event-11022"></a><span data-ttu-id="fcc90-102">Inicio de sesión único: Evento 11022</span><span class="sxs-lookup"><span data-stu-id="fcc90-102">Single Sign-On: Event 11022</span></span>
## <a name="details"></a><span data-ttu-id="fcc90-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fcc90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcc90-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fcc90-104">Product Name</span></span>|<span data-ttu-id="fcc90-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="fcc90-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fcc90-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fcc90-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fcc90-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fcc90-107">Event ID</span></span>|<span data-ttu-id="fcc90-108">11022</span><span class="sxs-lookup"><span data-stu-id="fcc90-108">11022</span></span>|  
|<span data-ttu-id="fcc90-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fcc90-109">Event Source</span></span>|<span data-ttu-id="fcc90-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fcc90-110">ENTSSO</span></span>|  
|<span data-ttu-id="fcc90-111">Componente</span><span class="sxs-lookup"><span data-stu-id="fcc90-111">Component</span></span>|<span data-ttu-id="fcc90-112">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc90-112">N/A</span></span>|  
|<span data-ttu-id="fcc90-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fcc90-113">Symbolic Name</span></span>|<span data-ttu-id="fcc90-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="fcc90-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="fcc90-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fcc90-115">Message Text</span></span>|<span data-ttu-id="fcc90-116">El cambio de contraseña externa habría provocado el cambio de una cuenta externa diferente.%r</span><span class="sxs-lookup"><span data-stu-id="fcc90-116">An external password change would have caused a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="fcc90-117">El cambio se impidió porque el adaptador de este sistema externo está configurado para no permitir conflictos de asignación.%r</span><span class="sxs-lookup"><span data-stu-id="fcc90-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="fcc90-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fcc90-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fcc90-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fcc90-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="fcc90-120">Cuenta de Windows: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fcc90-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="fcc90-121">Cuenta externa 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="fcc90-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="fcc90-122">Cuenta externa 2: %5</span><span class="sxs-lookup"><span data-stu-id="fcc90-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fcc90-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="fcc90-123">Explanation</span></span>  
 <span data-ttu-id="fcc90-124">Este mensaje de información notifica el error de cambio de contraseña externa que habría provocado el cambio de una cuenta externa diferente.</span><span class="sxs-lookup"><span data-stu-id="fcc90-124">This is an informational message reporting the failure of an external password change which would have caused a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fcc90-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fcc90-125">User Action</span></span>  
 <span data-ttu-id="fcc90-126">Si bien el cambio no se llevó a cabo (porque el sistema está configurado para no permitir conflictos de asignación), debe confirmar de inmediato que este intento se realizó con su conocimiento y autorización.</span><span class="sxs-lookup"><span data-stu-id="fcc90-126">Although no change was made (because this system is configured to not allow mapping conflicts) you should confirm immediately that this attempt was made with your knowledge and authorization.</span></span> <span data-ttu-id="fcc90-127">Si es así, no se necesitan acciones.</span><span class="sxs-lookup"><span data-stu-id="fcc90-127">If so, no action is required.</span></span> <span data-ttu-id="fcc90-128">De lo contrario, averigüe dónde se inició el cambio y confirme que se trata de una ubicación segura del sistema.</span><span class="sxs-lookup"><span data-stu-id="fcc90-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>