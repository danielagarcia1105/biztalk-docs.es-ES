---
title: "Inicio de sesión único: Evento 10601 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34711cf02711ec0ee2a259cc7d8f8fca9c87b7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="f181f-102">Inicio de sesión único: Evento 10601</span><span class="sxs-lookup"><span data-stu-id="f181f-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="f181f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f181f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f181f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f181f-104">Product Name</span></span>|<span data-ttu-id="f181f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f181f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f181f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f181f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f181f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f181f-107">Event ID</span></span>|<span data-ttu-id="f181f-108">10601</span><span class="sxs-lookup"><span data-stu-id="f181f-108">10601</span></span>|  
|<span data-ttu-id="f181f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f181f-109">Event Source</span></span>|<span data-ttu-id="f181f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f181f-110">ENTSSO</span></span>|  
|<span data-ttu-id="f181f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f181f-111">Component</span></span>|<span data-ttu-id="f181f-112">N/D</span><span class="sxs-lookup"><span data-stu-id="f181f-112">N/A</span></span>|  
|<span data-ttu-id="f181f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f181f-113">Symbolic Name</span></span>|<span data-ttu-id="f181f-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f181f-114">SSO_WARN_INVALID_FLAGS</span></span>|  
|<span data-ttu-id="f181f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f181f-115">Message Text</span></span>|<span data-ttu-id="f181f-116">Marcadores no válidos para crear este tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f181f-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="f181f-117">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="f181f-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="f181f-118">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f181f-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="f181f-119">Los indicadores especificados: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f181f-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="f181f-120">Marcadores permitidos: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f181f-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="f181f-121">Marcadores no permitidos: %4</span><span class="sxs-lookup"><span data-stu-id="f181f-121">Not Allowed Flags: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f181f-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="f181f-122">Explanation</span></span>  
 <span data-ttu-id="f181f-123">Marcadores no válidos para crear este tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f181f-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="f181f-124">La advertencia enumera la aplicación específica, además de los marcadores permitidos y no permitidos.</span><span class="sxs-lookup"><span data-stu-id="f181f-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f181f-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f181f-125">User Action</span></span>  
 <span data-ttu-id="f181f-126">Vuelva a crear la aplicación respetando las pautas descritas en el mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="f181f-126">Recreate the application following the guidelines outlined in the warning message.</span></span>