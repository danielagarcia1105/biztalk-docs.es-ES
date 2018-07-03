---
title: 'De sesión único: Evento 11025 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015901"
---
# <a name="single-sign-on-event-11025"></a><span data-ttu-id="96646-102">De sesión único: Evento 11025</span><span class="sxs-lookup"><span data-stu-id="96646-102">Single Sign-On: Event 11025</span></span>
## <a name="details"></a><span data-ttu-id="96646-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="96646-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="96646-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="96646-104">Product Name</span></span>   |                                                                                                 <span data-ttu-id="96646-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="96646-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="96646-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="96646-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    <span data-ttu-id="96646-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="96646-107">Event ID</span></span>     |                                                                                                           <span data-ttu-id="96646-108">11025</span><span class="sxs-lookup"><span data-stu-id="96646-108">11025</span></span>                                                                                                            |
|  <span data-ttu-id="96646-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="96646-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="96646-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="96646-110">ENTSSO</span></span>                                                                                                           |
|    <span data-ttu-id="96646-111">Componente</span><span class="sxs-lookup"><span data-stu-id="96646-111">Component</span></span>    |                                                                                                            <span data-ttu-id="96646-112">N/D</span><span class="sxs-lookup"><span data-stu-id="96646-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="96646-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="96646-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="96646-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96646-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span></span>                                                                                             |
|  <span data-ttu-id="96646-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="96646-115">Message Text</span></span>   | <span data-ttu-id="96646-116">Valor de tiempo de espera de vale no válido para actualización de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="96646-116">The ticket time-out value is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="96646-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="96646-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="96646-118">Tiempo de espera de vale: %2 minutos %r</span><span class="sxs-lookup"><span data-stu-id="96646-118">Ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="96646-119">Tiempo de espera máximo de vale: %3 minutos %r</span><span class="sxs-lookup"><span data-stu-id="96646-119">Maximum ticket time-out: %3 minutes%r</span></span><br /><br /> <span data-ttu-id="96646-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="96646-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="96646-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="96646-121">Explanation</span></span>  
 <span data-ttu-id="96646-122">El valor de tiempo de espera de vale no es válido.</span><span class="sxs-lookup"><span data-stu-id="96646-122">The ticket time-out value is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96646-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="96646-123">User Action</span></span>  
 <span data-ttu-id="96646-124">Para obtener más información sobre los tiempos de espera de vale, consulte [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="96646-124">For more information on ticket time-outs, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>