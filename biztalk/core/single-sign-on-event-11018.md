---
title: 'De sesión único: Evento 11018 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b98a1f-6390-4271-8e81-b855c4d30ec3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318928225c18a8d134d799db039058c862b034e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024522"
---
# <a name="single-sign-on-event-11018"></a><span data-ttu-id="3ec93-102">De sesión único: Evento 11018</span><span class="sxs-lookup"><span data-stu-id="3ec93-102">Single Sign-On: Event 11018</span></span>
## <a name="details"></a><span data-ttu-id="3ec93-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3ec93-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3ec93-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3ec93-104">Product Name</span></span>   |                                                                                                                              <span data-ttu-id="3ec93-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3ec93-105">Enterprise Single Sign-On</span></span>                                                                                                                              |
| <span data-ttu-id="3ec93-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3ec93-106">Product Version</span></span> |                                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                              |
|    <span data-ttu-id="3ec93-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3ec93-107">Event ID</span></span>     |                                                                                                                                        <span data-ttu-id="3ec93-108">11018</span><span class="sxs-lookup"><span data-stu-id="3ec93-108">11018</span></span>                                                                                                                                        |
|  <span data-ttu-id="3ec93-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3ec93-109">Event Source</span></span>   |                                                                                                                                       <span data-ttu-id="3ec93-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3ec93-110">ENTSSO</span></span>                                                                                                                                        |
|    <span data-ttu-id="3ec93-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3ec93-111">Component</span></span>    |                                                                                                                                         <span data-ttu-id="3ec93-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3ec93-112">N/A</span></span>                                                                                                                                         |
|  <span data-ttu-id="3ec93-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3ec93-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="3ec93-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="3ec93-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span></span>                                                                                                                            |
|  <span data-ttu-id="3ec93-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3ec93-115">Message Text</span></span>   | <span data-ttu-id="3ec93-116">No se pudo comprobar si la asignación era miembro la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3ec93-116">Failed to check whether the mapping was a member of the Application Users account.</span></span> <span data-ttu-id="3ec93-117">Se ignorará la asignación.%r</span><span class="sxs-lookup"><span data-stu-id="3ec93-117">The mapping will be ignored.%r</span></span><br /><br /> <span data-ttu-id="3ec93-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3ec93-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3ec93-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3ec93-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="3ec93-120">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3ec93-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="3ec93-121">Usuarios de aplicación: %4 %r</span><span class="sxs-lookup"><span data-stu-id="3ec93-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="3ec93-122">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="3ec93-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3ec93-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="3ec93-123">Explanation</span></span>  
 <span data-ttu-id="3ec93-124">Error no especificado en el lado de Windows.</span><span class="sxs-lookup"><span data-stu-id="3ec93-124">An unspecified error has occurred on the Windows side.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ec93-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3ec93-125">User Action</span></span>  
 <span data-ttu-id="3ec93-126">Recopile la información de la advertencia (Id. de seguimiento, cuenta de Windows, nombre de aplicación, usuarios de aplicación y código de error) y póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ec93-126">Gather the information from the warning (Tracking ID, Windows Account, Application Name, Application Users, and Error Code) and contact Microsoft Product Support Services.</span></span>