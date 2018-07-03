---
title: 'De sesión único: Evento 11035 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194d3069f0b74022e6b16a28de1c7f81ae3030f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001725"
---
# <a name="single-sign-on-event-11035"></a><span data-ttu-id="8a63c-102">De sesión único: Evento 11035</span><span class="sxs-lookup"><span data-stu-id="8a63c-102">Single Sign-On: Event 11035</span></span>
## <a name="details"></a><span data-ttu-id="8a63c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a63c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8a63c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8a63c-104">Product Name</span></span>   |                                                                                                                                               <span data-ttu-id="8a63c-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8a63c-105">Enterprise Single Sign-On</span></span>                                                                                                                                                |
| <span data-ttu-id="8a63c-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8a63c-106">Product Version</span></span> |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    <span data-ttu-id="8a63c-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8a63c-107">Event ID</span></span>     |                                                                                                                                                         <span data-ttu-id="8a63c-108">11035</span><span class="sxs-lookup"><span data-stu-id="8a63c-108">11035</span></span>                                                                                                                                                          |
|  <span data-ttu-id="8a63c-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8a63c-109">Event Source</span></span>   |                                                                                                                                                         <span data-ttu-id="8a63c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8a63c-110">ENTSSO</span></span>                                                                                                                                                         |
|    <span data-ttu-id="8a63c-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8a63c-111">Component</span></span>    |                                                                                                                                                          <span data-ttu-id="8a63c-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8a63c-112">N/A</span></span>                                                                                                                                                           |
|  <span data-ttu-id="8a63c-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8a63c-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="8a63c-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="8a63c-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span></span>                                                                                                                                            |
|  <span data-ttu-id="8a63c-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8a63c-115">Message Text</span></span>   | <span data-ttu-id="8a63c-116">Cambio de contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="8a63c-116">Windows password change.</span></span> <span data-ttu-id="8a63c-117">Se detectó una asignación para esta cuenta de Windows pero se la ignoró porque la sincronización de contraseñas no está configurada para la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="8a63c-117">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.%r</span></span><br /><br /> <span data-ttu-id="8a63c-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8a63c-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8a63c-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8a63c-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="8a63c-120">Aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8a63c-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="8a63c-121">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="8a63c-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="8a63c-122">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="8a63c-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8a63c-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="8a63c-123">Explanation</span></span>  
 <span data-ttu-id="8a63c-124">Se detectó una asignación para esta cuenta de Windows pero se la ignoró porque la sincronización de contraseñas no está configurada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a63c-124">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a63c-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8a63c-125">User Action</span></span>  
 <span data-ttu-id="8a63c-126">Para obtener información sobre cómo configurar la sincronización de contraseñas, consulte [la sincronización de contraseña](../core/password-synchronization2.md).</span><span class="sxs-lookup"><span data-stu-id="8a63c-126">For information on configuring Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>