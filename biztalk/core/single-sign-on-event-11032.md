---
title: 'De sesión único: Evento 11032 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d58cf9d-6806-4580-8014-7eff88d5cc5f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc69ecf447f0917f843a0f80a0a25b1ed0b6e0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022050"
---
# <a name="single-sign-on-event-11032"></a><span data-ttu-id="a9ade-102">De sesión único: Evento 11032</span><span class="sxs-lookup"><span data-stu-id="a9ade-102">Single Sign-On: Event 11032</span></span>
## <a name="details"></a><span data-ttu-id="a9ade-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9ade-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9ade-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a9ade-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="a9ade-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a9ade-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="a9ade-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a9ade-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="a9ade-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a9ade-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="a9ade-108">11032</span><span class="sxs-lookup"><span data-stu-id="a9ade-108">11032</span></span>                                                                                                                                       |
|  <span data-ttu-id="a9ade-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a9ade-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="a9ade-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a9ade-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="a9ade-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a9ade-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="a9ade-112">N/D</span><span class="sxs-lookup"><span data-stu-id="a9ade-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="a9ade-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a9ade-113">Symbolic Name</span></span>  |                                                                                                                     <span data-ttu-id="a9ade-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="a9ade-114">SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED</span></span>                                                                                                                      |
|  <span data-ttu-id="a9ade-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a9ade-115">Message Text</span></span>   | <span data-ttu-id="a9ade-116">Cambio de contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="a9ade-116">Windows password change.</span></span> <span data-ttu-id="a9ade-117">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque está deshabilitada.%r</span><span class="sxs-lookup"><span data-stu-id="a9ade-117">A mapping for this Windows account has been detected but ignored because it is disabled.%r</span></span><br /><br /> <span data-ttu-id="a9ade-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a9ade-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a9ade-119">Cuenta de Windows: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a9ade-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="a9ade-120">Aplicación: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a9ade-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="a9ade-121">Cuenta externa: %4 %r</span><span class="sxs-lookup"><span data-stu-id="a9ade-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="a9ade-122">Usuario cliente: %5</span><span class="sxs-lookup"><span data-stu-id="a9ade-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a9ade-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="a9ade-123">Explanation</span></span>  
 <span data-ttu-id="a9ade-124">Se detectó una asignación para esta cuenta de Windows, pero se la ignoró porque está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a9ade-124">A mapping for this Windows account has been detected but ignored because it is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9ade-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a9ade-125">User Action</span></span>  
  
-   <span data-ttu-id="a9ade-126">Para habilitar la asignación, consulte [cómo habilitar una asignación de usuario](../core/how-to-enable-a-user-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="a9ade-126">To enable the mapping, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>