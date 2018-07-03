---
title: 'De sesión único: Evento 10576 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b2d9904-4302-41b7-bced-7db46cc05d7f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae438c35d99ab9b81f44d4cf24a087e1a217fd3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966333"
---
# <a name="single-sign-on-event-10576"></a><span data-ttu-id="0e7d4-102">De sesión único: Evento 10576</span><span class="sxs-lookup"><span data-stu-id="0e7d4-102">Single Sign-On: Event 10576</span></span>
## <a name="details"></a><span data-ttu-id="0e7d4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e7d4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e7d4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0e7d4-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="0e7d4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0e7d4-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="0e7d4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0e7d4-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="0e7d4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0e7d4-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="0e7d4-108">10576</span><span class="sxs-lookup"><span data-stu-id="0e7d4-108">10576</span></span>                                                                                                        |
|  <span data-ttu-id="0e7d4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0e7d4-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="0e7d4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e7d4-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="0e7d4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0e7d4-111">Component</span></span>    |                                                                                                         <span data-ttu-id="0e7d4-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0e7d4-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="0e7d4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0e7d4-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="0e7d4-114">SSO_INFO_CHANGED_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="0e7d4-114">SSO_INFO_CHANGED_SSO_ADMIN</span></span>                                                                                              |
|  <span data-ttu-id="0e7d4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0e7d4-115">Message Text</span></span>   | <span data-ttu-id="0e7d4-116">Se actualizó la cuenta de administradores de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="0e7d4-116">Updated SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="0e7d4-117">Nuevos administradores de SSO: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0e7d4-117">New SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="0e7d4-118">Administradores de SSO anteriores: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0e7d4-118">Old SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="0e7d4-119">Id. de seguimiento: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0e7d4-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="0e7d4-120">Equipo cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="0e7d4-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="0e7d4-121">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="0e7d4-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e7d4-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="0e7d4-122">Explanation</span></span>  
 <span data-ttu-id="0e7d4-123">Este mensaje de información puede resultar útil para el seguimiento de eventos importantes relacionados con la seguridad que pueden producirse en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="0e7d4-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="0e7d4-124">Este mensaje indica que se ha actualizado la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="0e7d4-124">This message states that the SSO Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e7d4-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0e7d4-125">User Action</span></span>  
 <span data-ttu-id="0e7d4-126">No se requiere ninguna acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e7d4-126">No user action is required.</span></span>