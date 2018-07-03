---
title: 'De sesión único: Evento 10603 | Microsoft Docs'
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
ms.openlocfilehash: 5416ae8a2dcfdf5a3da6d8c1d00eb5a556fc3599
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970069"
---
# <a name="single-sign-on-event-10603"></a><span data-ttu-id="43c6b-102">De sesión único: Evento 10603</span><span class="sxs-lookup"><span data-stu-id="43c6b-102">Single Sign-On: Event 10603</span></span>
## <a name="details"></a><span data-ttu-id="43c6b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="43c6b-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="43c6b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="43c6b-104">Product Name</span></span>   |                                                             <span data-ttu-id="43c6b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="43c6b-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="43c6b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="43c6b-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="43c6b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="43c6b-107">Event ID</span></span>     |                                                                       <span data-ttu-id="43c6b-108">10603</span><span class="sxs-lookup"><span data-stu-id="43c6b-108">10603</span></span>                                                                        |
|  <span data-ttu-id="43c6b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="43c6b-109">Event Source</span></span>   |                                                                       <span data-ttu-id="43c6b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="43c6b-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="43c6b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="43c6b-111">Component</span></span>    |                                                                        <span data-ttu-id="43c6b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="43c6b-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="43c6b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="43c6b-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="43c6b-114">SSO_WARN_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="43c6b-114">SSO_WARN_DB_ACCESS</span></span>                                                                 |
|  <span data-ttu-id="43c6b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="43c6b-115">Message Text</span></span>   | <span data-ttu-id="43c6b-116">No se pudo obtener acceso a la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="43c6b-116">Could not access the SSO database.</span></span> <span data-ttu-id="43c6b-117">Si esta condición persiste, el servicio SSO se desconectará.%r</span><span class="sxs-lookup"><span data-stu-id="43c6b-117">If this condition persists, the SSO service will go offline.%r</span></span><br /><br /> <span data-ttu-id="43c6b-118">%1.%r</span><span class="sxs-lookup"><span data-stu-id="43c6b-118">%1.%r</span></span><br /><br /> <span data-ttu-id="43c6b-119">Código de Error SQL: %2</span><span class="sxs-lookup"><span data-stu-id="43c6b-119">SQL Error code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="43c6b-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="43c6b-120">Explanation</span></span>  
 <span data-ttu-id="43c6b-121">La base de datos de SSO no está disponible.</span><span class="sxs-lookup"><span data-stu-id="43c6b-121">The SSO database is unavailable.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43c6b-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="43c6b-122">User Action</span></span>  
 <span data-ttu-id="43c6b-123">Compruebe el código de error de SQL de la advertencia.</span><span class="sxs-lookup"><span data-stu-id="43c6b-123">Check the SQL error code contained in the warning.</span></span> <span data-ttu-id="43c6b-124">Es posible que ésta ofrezca ayuda.</span><span class="sxs-lookup"><span data-stu-id="43c6b-124">This may offer some guidance.</span></span> <span data-ttu-id="43c6b-125">De lo contrario, póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43c6b-125">If not, contact Microsoft Product Support Services.</span></span>