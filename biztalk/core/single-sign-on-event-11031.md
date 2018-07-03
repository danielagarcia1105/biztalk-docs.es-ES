---
title: 'De sesión único: Evento 11031 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f90be8f631bbd9503de3401bc84d27af32aa991a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015085"
---
# <a name="single-sign-on-event-11031"></a><span data-ttu-id="13f53-102">De sesión único: Evento 11031</span><span class="sxs-lookup"><span data-stu-id="13f53-102">Single Sign-On: Event 11031</span></span>
## <a name="details"></a><span data-ttu-id="13f53-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="13f53-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="13f53-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="13f53-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="13f53-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="13f53-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="13f53-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="13f53-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="13f53-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="13f53-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="13f53-108">11031</span><span class="sxs-lookup"><span data-stu-id="13f53-108">11031</span></span>                                                                                                                                          |
|  <span data-ttu-id="13f53-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="13f53-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="13f53-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13f53-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="13f53-111">Componente</span><span class="sxs-lookup"><span data-stu-id="13f53-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="13f53-112">N/D</span><span class="sxs-lookup"><span data-stu-id="13f53-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="13f53-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="13f53-113">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="13f53-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span><span class="sxs-lookup"><span data-stu-id="13f53-114">SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING</span></span>                                                                                                                          |
|  <span data-ttu-id="13f53-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="13f53-115">Message Text</span></span>   | <span data-ttu-id="13f53-116">Cambio de contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="13f53-116">Windows password change.</span></span> <span data-ttu-id="13f53-117">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque ya no es válida.%r</span><span class="sxs-lookup"><span data-stu-id="13f53-117">A mapping for this Windows account has been detected but ignored because it is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="13f53-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="13f53-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="13f53-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="13f53-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="13f53-120">Aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="13f53-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="13f53-121">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="13f53-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="13f53-122">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="13f53-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="13f53-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="13f53-123">Explanation</span></span>  
 <span data-ttu-id="13f53-124">Es posible que la cuenta de Windows exista y sea válida, pero no es la cuenta de usuarios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="13f53-124">It may be that the Windows account exists and is valid, but is not in the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13f53-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="13f53-125">User Action</span></span>  
 <span data-ttu-id="13f53-126">Elimine la asignación e intente crearla nuevamente.</span><span class="sxs-lookup"><span data-stu-id="13f53-126">Delete the mapping and try to recreate it.</span></span>