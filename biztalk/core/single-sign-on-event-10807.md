---
title: 'Inicio de sesión único: Evento 10807 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277700"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="69236-102">Inicio de sesión único: Evento 10807</span><span class="sxs-lookup"><span data-stu-id="69236-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="69236-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="69236-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69236-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="69236-104">Product Name</span></span>|<span data-ttu-id="69236-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="69236-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="69236-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="69236-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="69236-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="69236-107">Event ID</span></span>|<span data-ttu-id="69236-108">10807</span><span class="sxs-lookup"><span data-stu-id="69236-108">10807</span></span>|  
|<span data-ttu-id="69236-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="69236-109">Event Source</span></span>|<span data-ttu-id="69236-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="69236-110">ENTSSO</span></span>|  
|<span data-ttu-id="69236-111">Componente</span><span class="sxs-lookup"><span data-stu-id="69236-111">Component</span></span>|<span data-ttu-id="69236-112">N/D</span><span class="sxs-lookup"><span data-stu-id="69236-112">N/A</span></span>|  
|<span data-ttu-id="69236-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="69236-113">Symbolic Name</span></span>|<span data-ttu-id="69236-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="69236-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>|  
|<span data-ttu-id="69236-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="69236-115">Message Text</span></span>|<span data-ttu-id="69236-116">Demasiadas notificaciones sin confirmar.</span><span class="sxs-lookup"><span data-stu-id="69236-116">Too many unconfirmed notifications.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69236-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="69236-117">Explanation</span></span>  
 <span data-ttu-id="69236-118">Cada vez que se envía una notificación de cambio de contraseña, se recibe un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="69236-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="69236-119">En este caso, se ha superado el límite de notificaciones sin confirmación.</span><span class="sxs-lookup"><span data-stu-id="69236-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69236-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="69236-120">User Action</span></span>  
 <span data-ttu-id="69236-121">Compruebe el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="69236-121">Check the password sync adapter.</span></span>