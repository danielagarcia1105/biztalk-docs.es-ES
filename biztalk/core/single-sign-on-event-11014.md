---
title: "Inicio de sesión único: Evento 11014 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138a580122beb34b82f642dfa4d60aa6d422b445
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="853d9-102">Inicio de sesión único: Evento 11014</span><span class="sxs-lookup"><span data-stu-id="853d9-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="853d9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="853d9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="853d9-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="853d9-104">Product Name</span></span>|<span data-ttu-id="853d9-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="853d9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="853d9-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="853d9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="853d9-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="853d9-107">Event ID</span></span>|<span data-ttu-id="853d9-108">11014</span><span class="sxs-lookup"><span data-stu-id="853d9-108">11014</span></span>|  
|<span data-ttu-id="853d9-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="853d9-109">Event Source</span></span>|<span data-ttu-id="853d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="853d9-110">ENTSSO</span></span>|  
|<span data-ttu-id="853d9-111">Componente</span><span class="sxs-lookup"><span data-stu-id="853d9-111">Component</span></span>|<span data-ttu-id="853d9-112">N/D</span><span class="sxs-lookup"><span data-stu-id="853d9-112">N/A</span></span>|  
|<span data-ttu-id="853d9-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="853d9-113">Symbolic Name</span></span>|<span data-ttu-id="853d9-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="853d9-114">SSO_ERROR_ACCESS_CHECK</span></span>|  
|<span data-ttu-id="853d9-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="853d9-115">Message Text</span></span>|<span data-ttu-id="853d9-116">Error al comprobar el acceso.%r</span><span class="sxs-lookup"><span data-stu-id="853d9-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="853d9-117">El usuario cliente: %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="853d9-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="853d9-118">Nombre de la aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="853d9-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="853d9-119">Datos adicionales: %4 %r</span><span class="sxs-lookup"><span data-stu-id="853d9-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="853d9-120">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="853d9-120">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="853d9-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="853d9-121">Explanation</span></span>  
 <span data-ttu-id="853d9-122">Se produjo un error al comprobar el acceso para el cliente y la aplicación enumerados.</span><span class="sxs-lookup"><span data-stu-id="853d9-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="853d9-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="853d9-123">User Action</span></span>  
 <span data-ttu-id="853d9-124">La información adicional debe permitirle solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="853d9-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="853d9-125">Para evitar este error en el futuro, también puede reducir el nivel de auditoría.</span><span class="sxs-lookup"><span data-stu-id="853d9-125">To avoid this error in the future, you can also lower the audit level.</span></span>