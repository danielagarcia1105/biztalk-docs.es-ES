---
title: 'Inicio de sesión único: Evento 10611 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3582ee070b960b7eb17facc8d48e0b3e11dc5b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270420"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="69660-102">Inicio de sesión único: Evento 10611</span><span class="sxs-lookup"><span data-stu-id="69660-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="69660-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="69660-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69660-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="69660-104">Product Name</span></span>|<span data-ttu-id="69660-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="69660-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="69660-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="69660-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="69660-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="69660-107">Event ID</span></span>|<span data-ttu-id="69660-108">10611</span><span class="sxs-lookup"><span data-stu-id="69660-108">10611</span></span>|  
|<span data-ttu-id="69660-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="69660-109">Event Source</span></span>|<span data-ttu-id="69660-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="69660-110">ENTSSO</span></span>|  
|<span data-ttu-id="69660-111">Componente</span><span class="sxs-lookup"><span data-stu-id="69660-111">Component</span></span>|<span data-ttu-id="69660-112">N/D</span><span class="sxs-lookup"><span data-stu-id="69660-112">N/A</span></span>|  
|<span data-ttu-id="69660-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="69660-113">Symbolic Name</span></span>|<span data-ttu-id="69660-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="69660-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>|  
|<span data-ttu-id="69660-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="69660-115">Message Text</span></span>|<span data-ttu-id="69660-116">Se está iniciando el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="69660-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="69660-117">Nombre de equipo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="69660-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="69660-118">Nombre SQL Server: %2 %r</span><span class="sxs-lookup"><span data-stu-id="69660-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="69660-119">Nombre de la base de datos SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="69660-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="69660-120">No se usa SSL.</span><span class="sxs-lookup"><span data-stu-id="69660-120">Not using SSL.</span></span> <span data-ttu-id="69660-121">Consulte la documentación para obtener información detallada sobre el procedimiento para proteger la conexión con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69660-121">See documentation for details on how to secure the SQL Server connection.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69660-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="69660-122">Explanation</span></span>  
 <span data-ttu-id="69660-123">El servicio ENTSSO se está iniciando sin usar la Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="69660-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="69660-124">Se recomienda proteger la conexión entre el servicio SSO y SQL.</span><span class="sxs-lookup"><span data-stu-id="69660-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69660-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="69660-125">User Action</span></span>  
 <span data-ttu-id="69660-126">Consulte la documentación en [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="69660-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="69660-127">.</span><span class="sxs-lookup"><span data-stu-id="69660-127">.</span></span>