---
title: 'De sesión único: Evento 10807 | Microsoft Docs'
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
ms.openlocfilehash: d9e23aefbb950160f29b6145e64bfaa1784dc3f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985413"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="3b27b-102">De sesión único: Evento 10807</span><span class="sxs-lookup"><span data-stu-id="3b27b-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="3b27b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b27b-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="3b27b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3b27b-104">Product Name</span></span>   |                 <span data-ttu-id="3b27b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3b27b-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="3b27b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3b27b-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="3b27b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3b27b-107">Event ID</span></span>     |                           <span data-ttu-id="3b27b-108">10807</span><span class="sxs-lookup"><span data-stu-id="3b27b-108">10807</span></span>                            |
|  <span data-ttu-id="3b27b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3b27b-109">Event Source</span></span>   |                           <span data-ttu-id="3b27b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3b27b-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="3b27b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3b27b-111">Component</span></span>    |                            <span data-ttu-id="3b27b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3b27b-112">N/A</span></span>                             |
|  <span data-ttu-id="3b27b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b27b-113">Symbolic Name</span></span>  |        <span data-ttu-id="3b27b-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="3b27b-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>         |
|  <span data-ttu-id="3b27b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b27b-115">Message Text</span></span>   |            <span data-ttu-id="3b27b-116">Demasiadas notificaciones sin confirmar.</span><span class="sxs-lookup"><span data-stu-id="3b27b-116">Too many unconfirmed notifications.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="3b27b-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b27b-117">Explanation</span></span>  
 <span data-ttu-id="3b27b-118">Cada vez que se envía una notificación de cambio de contraseña, se recibe un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="3b27b-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="3b27b-119">En este caso, se ha superado el límite de notificaciones sin confirmación.</span><span class="sxs-lookup"><span data-stu-id="3b27b-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b27b-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b27b-120">User Action</span></span>  
 <span data-ttu-id="3b27b-121">Compruebe el adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="3b27b-121">Check the password sync adapter.</span></span>