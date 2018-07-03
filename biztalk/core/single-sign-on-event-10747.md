---
title: 'De sesión único: Evento 10747 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6303d7dd39c2168d67d206401bdf8d2c30f5d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993917"
---
# <a name="single-sign-on-event-10747"></a><span data-ttu-id="980f8-102">De sesión único: Evento 10747</span><span class="sxs-lookup"><span data-stu-id="980f8-102">Single Sign-On: Event 10747</span></span>
## <a name="details"></a><span data-ttu-id="980f8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="980f8-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="980f8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="980f8-104">Product Name</span></span>   |                                                       <span data-ttu-id="980f8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="980f8-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="980f8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="980f8-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    <span data-ttu-id="980f8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="980f8-107">Event ID</span></span>     |                                                                 <span data-ttu-id="980f8-108">10747</span><span class="sxs-lookup"><span data-stu-id="980f8-108">10747</span></span>                                                                  |
|  <span data-ttu-id="980f8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="980f8-109">Event Source</span></span>   |                                                                  <span data-ttu-id="980f8-110">N\D</span><span class="sxs-lookup"><span data-stu-id="980f8-110">N\A</span></span>                                                                   |
|    <span data-ttu-id="980f8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="980f8-111">Component</span></span>    |                                                                  <span data-ttu-id="980f8-112">N\D</span><span class="sxs-lookup"><span data-stu-id="980f8-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="980f8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="980f8-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="980f8-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="980f8-114">SSO_ERROR_UNKNOWN_NOTIFICATION</span></span>                                                     |
|  <span data-ttu-id="980f8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="980f8-115">Message Text</span></span>   | <span data-ttu-id="980f8-116">Se recibió un tipo de notificación desconocido.%r</span><span class="sxs-lookup"><span data-stu-id="980f8-116">An unknown notification type was received.%r</span></span><br /><br /> <span data-ttu-id="980f8-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="980f8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="980f8-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="980f8-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="980f8-119">Tipo de notificación: %3</span><span class="sxs-lookup"><span data-stu-id="980f8-119">Notification Type: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="980f8-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="980f8-120">Explanation</span></span>  
 <span data-ttu-id="980f8-121">Este evento de error indica que el servicio SSO detectó un error interno con un tipo de notificación no válido.</span><span class="sxs-lookup"><span data-stu-id="980f8-121">This Error event indicates that an internal error with an invalid notification type was detected by the SSO service.</span></span>  

## <a name="user-action"></a><span data-ttu-id="980f8-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="980f8-122">User Action</span></span>  
 <span data-ttu-id="980f8-123">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="980f8-123">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="980f8-124">Compruebe los registros de eventos de aplicación y del sistema para eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="980f8-124">Check the system and application event logs for associated events.</span></span>  

  <span data-ttu-id="980f8-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="980f8-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="980f8-126">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="980f8-126">Using SSO</span></span>](../core/using-sso.md)
