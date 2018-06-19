---
title: 'Inicio de sesión único: Evento 10596 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051fdf627edc3f560a8d02026207dc2fe5bb3533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270148"
---
# <a name="single-sign-on-event-10596"></a><span data-ttu-id="d4eac-102">Inicio de sesión único: Evento 10596</span><span class="sxs-lookup"><span data-stu-id="d4eac-102">Single Sign-On: Event 10596</span></span>
## <a name="details"></a><span data-ttu-id="d4eac-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4eac-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4eac-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d4eac-104">Product Name</span></span>|<span data-ttu-id="d4eac-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d4eac-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d4eac-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d4eac-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d4eac-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d4eac-107">Event ID</span></span>|<span data-ttu-id="d4eac-108">10596</span><span class="sxs-lookup"><span data-stu-id="d4eac-108">10596</span></span>|  
|<span data-ttu-id="d4eac-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d4eac-109">Event Source</span></span>|<span data-ttu-id="d4eac-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d4eac-110">ENTSSO</span></span>|  
|<span data-ttu-id="d4eac-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d4eac-111">Component</span></span>|<span data-ttu-id="d4eac-112">N/D</span><span class="sxs-lookup"><span data-stu-id="d4eac-112">N/A</span></span>|  
|<span data-ttu-id="d4eac-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d4eac-113">Symbolic Name</span></span>|<span data-ttu-id="d4eac-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="d4eac-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span></span>|  
|<span data-ttu-id="d4eac-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d4eac-115">Message Text</span></span>|<span data-ttu-id="d4eac-116">No se puede canjear el vale porque el usuario para el que se emitió no es miembro de la cuenta de usuarios de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="d4eac-116">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="d4eac-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d4eac-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="d4eac-118">Vale emitido para: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d4eac-118">Ticket Issued For: %2%r</span></span><br /><br /> <span data-ttu-id="d4eac-119">Los usuarios de aplicación: %3</span><span class="sxs-lookup"><span data-stu-id="d4eac-119">Application Users: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4eac-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="d4eac-120">Explanation</span></span>  
 <span data-ttu-id="d4eac-121">No se puede canjear el vale porque el usuario para el que se emitió no es miembro de la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4eac-121">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4eac-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d4eac-122">User Action</span></span>  
 <span data-ttu-id="d4eac-123">Vuelva a emitir el vale para un usuario que sea miembro de la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4eac-123">Reissue the ticket to a user who is a member of the Application Users account.</span></span>