---
title: 'De sesión único: Evento 11026 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 452ccc24174a1e32a133c0ccc6c7a0b5f09c530f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013493"
---
# <a name="single-sign-on-event-11026"></a><span data-ttu-id="4d856-102">De sesión único: Evento 11026</span><span class="sxs-lookup"><span data-stu-id="4d856-102">Single Sign-On: Event 11026</span></span>
## <a name="details"></a><span data-ttu-id="4d856-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4d856-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4d856-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4d856-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="4d856-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4d856-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="4d856-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4d856-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="4d856-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4d856-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="4d856-108">11026</span><span class="sxs-lookup"><span data-stu-id="4d856-108">11026</span></span>                                                                                                                                          |
|  <span data-ttu-id="4d856-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4d856-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="4d856-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4d856-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="4d856-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4d856-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="4d856-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4d856-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="4d856-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4d856-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="4d856-114">SSO_WARN_EXISTING_GROUP_MAPPING</span><span class="sxs-lookup"><span data-stu-id="4d856-114">SSO_WARN_EXISTING_GROUP_MAPPING</span></span>                                                                                                                             |
|  <span data-ttu-id="4d856-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4d856-115">Message Text</span></span>   | <span data-ttu-id="4d856-116">No se pudo crear la asignación de grupo nueva debido a un conflicto con una asignación existente.</span><span class="sxs-lookup"><span data-stu-id="4d856-116">A new group mapping could not be created because there is a conflict with an existing mapping.</span></span> <span data-ttu-id="4d856-117">Elimine la asignación existente y vuelva a intentarlo.%r</span><span class="sxs-lookup"><span data-stu-id="4d856-117">Please delete the existing mapping and try again.%r</span></span><br /><br /> <span data-ttu-id="4d856-118">Asignación existente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4d856-118">Existing Mapping: %1%r</span></span><br /><br /> <span data-ttu-id="4d856-119">Nueva asignación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4d856-119">New Mapping: %2%r</span></span><br /><br /> <span data-ttu-id="4d856-120">Cuenta externa: %3 %r</span><span class="sxs-lookup"><span data-stu-id="4d856-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="4d856-121">Nombre de la aplicación: %4</span><span class="sxs-lookup"><span data-stu-id="4d856-121">Application Name: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4d856-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="4d856-122">Explanation</span></span>  
 <span data-ttu-id="4d856-123">La causa más probable es que el sistema está usando una versión anterior de Inicio de sesión único empresarial y aplicaciones de grupo antiguas.</span><span class="sxs-lookup"><span data-stu-id="4d856-123">The most likely cause is that your system is using an old version of Enterprise Single Sign-On, and old group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d856-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4d856-124">User Action</span></span>  
 <span data-ttu-id="4d856-125">Elimine la asignación y vuelva a crearla según se recomienda en la advertencia.</span><span class="sxs-lookup"><span data-stu-id="4d856-125">Delete and recreate the mapping as suggested in the warning.</span></span> <span data-ttu-id="4d856-126">Si esto no funciona, es posible que deba actualizar a una versión más reciente de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="4d856-126">If this fails, you may need to upgrade to a more recent version of Enterprise Single Sign-On.</span></span>