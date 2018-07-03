---
title: 'De sesión único: Evento 11033 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed8e984-2b6c-4a9e-8603-175fdcabeb0a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25db9678dbef67672c2d86273f8938e94de09000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011725"
---
# <a name="single-sign-on-event-11033"></a><span data-ttu-id="4d968-102">De sesión único: Evento 11033</span><span class="sxs-lookup"><span data-stu-id="4d968-102">Single Sign-On: Event 11033</span></span>
## <a name="details"></a><span data-ttu-id="4d968-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4d968-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4d968-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4d968-104">Product Name</span></span>   |                                                                                                                                   <span data-ttu-id="4d968-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4d968-105">Enterprise Single Sign-On</span></span>                                                                                                                                   |
| <span data-ttu-id="4d968-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4d968-106">Product Version</span></span> |                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                   |
|    <span data-ttu-id="4d968-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4d968-107">Event ID</span></span>     |                                                                                                                                             <span data-ttu-id="4d968-108">11033</span><span class="sxs-lookup"><span data-stu-id="4d968-108">11033</span></span>                                                                                                                                             |
|  <span data-ttu-id="4d968-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4d968-109">Event Source</span></span>   |                                                                                                                                            <span data-ttu-id="4d968-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4d968-110">ENTSSO</span></span>                                                                                                                                             |
|    <span data-ttu-id="4d968-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4d968-111">Component</span></span>    |                                                                                                                                              <span data-ttu-id="4d968-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4d968-112">N/A</span></span>                                                                                                                                              |
|  <span data-ttu-id="4d968-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4d968-113">Symbolic Name</span></span>  |                                                                                                                              <span data-ttu-id="4d968-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="4d968-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span></span>                                                                                                                              |
|  <span data-ttu-id="4d968-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4d968-115">Message Text</span></span>   | <span data-ttu-id="4d968-116">Cambio de contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="4d968-116">Windows password change.</span></span> <span data-ttu-id="4d968-117">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque la aplicación está deshabilitada.%r</span><span class="sxs-lookup"><span data-stu-id="4d968-117">A mapping for this Windows account has been detected but ignored because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="4d968-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4d968-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4d968-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4d968-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="4d968-120">Aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="4d968-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="4d968-121">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="4d968-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="4d968-122">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="4d968-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4d968-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="4d968-123">Explanation</span></span>  
 <span data-ttu-id="4d968-124">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque la aplicación está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4d968-124">A mapping for this Windows account has been detected but ignored because the application is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d968-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4d968-125">User Action</span></span>  
 <span data-ttu-id="4d968-126">Para habilitar la aplicación, consulte [cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="4d968-126">To enable the application, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>