---
title: 'Inicio de sesión único: Evento 10603 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738d2939f4178fdfaa115b8dfcc2273935c37b85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270396"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="5028e-102">Inicio de sesión único: Evento 10603</span><span class="sxs-lookup"><span data-stu-id="5028e-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="5028e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5028e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5028e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5028e-104">Product Name</span></span>|<span data-ttu-id="5028e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5028e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5028e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5028e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5028e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5028e-107">Event ID</span></span>|<span data-ttu-id="5028e-108">10603</span><span class="sxs-lookup"><span data-stu-id="5028e-108">10603</span></span>|  
|<span data-ttu-id="5028e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5028e-109">Event Source</span></span>|<span data-ttu-id="5028e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5028e-110">ENTSSO</span></span>|  
|<span data-ttu-id="5028e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5028e-111">Component</span></span>|<span data-ttu-id="5028e-112">N/D</span><span class="sxs-lookup"><span data-stu-id="5028e-112">N/A</span></span>|  
|<span data-ttu-id="5028e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5028e-113">Symbolic Name</span></span>|<span data-ttu-id="5028e-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="5028e-114">SSO_WARN_DB_ACCESS</span></span>|  
|<span data-ttu-id="5028e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5028e-115">Message Text</span></span>|<span data-ttu-id="5028e-116">No se pudo obtener acceso a la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="5028e-116">Could not access the SSO database.</span></span> <span data-ttu-id="5028e-117">Si esta condición persiste, el servicio SSO se desconectará.%r</span><span class="sxs-lookup"><span data-stu-id="5028e-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="5028e-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="5028e-118">%1.%r</span></span><br /><br /> <span data-ttu-id="5028e-119">Código de Error de SQL: %2</span><span class="sxs-lookup"><span data-stu-id="5028e-119">SQL Error code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5028e-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="5028e-120">Explanation</span></span>  
 <span data-ttu-id="5028e-121">La base de datos de SSO no está disponible.</span><span class="sxs-lookup"><span data-stu-id="5028e-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5028e-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5028e-122">User Action</span></span>  
 <span data-ttu-id="5028e-123">Compruebe el código de error de SQL de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="5028e-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="5028e-124">Es posible que ésta ofrezca ayuda.</span><span class="sxs-lookup"><span data-stu-id="5028e-124">This may offer some guidance.</span></span> <span data-ttu-id="5028e-125">De lo contrario, póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5028e-125">If not, contact Microsoft Product Support Services.</span></span>