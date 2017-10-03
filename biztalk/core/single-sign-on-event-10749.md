---
title: "Inicio de sesión único: Evento 10749 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 864c887cb6c115a2f766f9c06cbaa292fdbeace2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10749"></a><span data-ttu-id="a0da0-102">Inicio de sesión único: Evento 10749</span><span class="sxs-lookup"><span data-stu-id="a0da0-102">Single Sign-On: Event 10749</span></span>
## <a name="details"></a><span data-ttu-id="a0da0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a0da0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0da0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a0da0-104">Product Name</span></span>|<span data-ttu-id="a0da0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a0da0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a0da0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a0da0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a0da0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a0da0-107">Event ID</span></span>|<span data-ttu-id="a0da0-108">10749</span><span class="sxs-lookup"><span data-stu-id="a0da0-108">10749</span></span>|  
|<span data-ttu-id="a0da0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a0da0-109">Event Source</span></span>|<span data-ttu-id="a0da0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a0da0-110">ENTSSO</span></span>|  
|<span data-ttu-id="a0da0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a0da0-111">Component</span></span>|<span data-ttu-id="a0da0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="a0da0-112">N\A</span></span>|  
|<span data-ttu-id="a0da0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a0da0-113">Symbolic Name</span></span>|<span data-ttu-id="a0da0-114">SSO_WARN_PS_CLIENT_PING</span><span class="sxs-lookup"><span data-stu-id="a0da0-114">SSO_WARN_PS_CLIENT_PING</span></span>|  
|<span data-ttu-id="a0da0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a0da0-115">Message Text</span></span>|<span data-ttu-id="a0da0-116">No se pudo establecer la conexión con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="a0da0-116">Could not contact the destination SSO server.</span></span><br /><br /> <span data-ttu-id="a0da0-117">Compruebe si el servicio SSO está en ejecución en ese servidor y si se puede establecer la conexión con éste.%r</span><span class="sxs-lookup"><span data-stu-id="a0da0-117">Check that the SSO service is running on that server and that it can be contacted.%r</span></span><br /><br /> <span data-ttu-id="a0da0-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a0da0-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a0da0-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a0da0-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a0da0-120">Nombre del servidor SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a0da0-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="a0da0-121">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="a0da0-121">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a0da0-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="a0da0-122">Explanation</span></span>  
 <span data-ttu-id="a0da0-123">Este evento de advertencia indica que la sincronización de contraseñas de SSO no pudo establecer la comunicación con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="a0da0-123">This Warning event indicates that SSO Password Sync could not contact the specified destination SSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a0da0-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a0da0-124">User Action</span></span>  
 <span data-ttu-id="a0da0-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0da0-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="a0da0-126">Use el complemento de servidores de ENTSSO para comprobar el servidor.</span><span class="sxs-lookup"><span data-stu-id="a0da0-126">Use the ENTSSO Servers Snap-In to check the server.</span></span>  
  
-   <span data-ttu-id="a0da0-127">Inicie el servicio de inicio de sesión único empresarial si no está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a0da0-127">Start the Enterprise Single Sign-On Service if it is not running.</span></span>  
  
-   <span data-ttu-id="a0da0-128">Compruebe la conexión de red con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="a0da0-128">Check the network connection to the destination SSO server.</span></span>  
  
-   <span data-ttu-id="a0da0-129">Compruebe el firewall en el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="a0da0-129">Check firewall on the destination SSO Server.</span></span>  
  
 <span data-ttu-id="a0da0-130">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0da0-130">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="a0da0-131">Cómo usar el complemento de servidores</span><span class="sxs-lookup"><span data-stu-id="a0da0-131">How to Use the Servers Snap-in</span></span>](../core/how-to-use-the-servers-snap-in.md)