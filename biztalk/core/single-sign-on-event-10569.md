---
title: 'De sesión único: Evento 10569 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25665947921bb316a4d931228016eaf917b4a685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987205"
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="c2eaa-102">De sesión único: Evento 10569</span><span class="sxs-lookup"><span data-stu-id="c2eaa-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="c2eaa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c2eaa-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c2eaa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c2eaa-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="c2eaa-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c2eaa-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="c2eaa-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c2eaa-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="c2eaa-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c2eaa-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="c2eaa-108">10569</span><span class="sxs-lookup"><span data-stu-id="c2eaa-108">10569</span></span>                                                                                                  |
|  <span data-ttu-id="c2eaa-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c2eaa-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="c2eaa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2eaa-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="c2eaa-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c2eaa-111">Component</span></span>    |                                                                                                  <span data-ttu-id="c2eaa-112">N/D</span><span class="sxs-lookup"><span data-stu-id="c2eaa-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="c2eaa-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c2eaa-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="c2eaa-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="c2eaa-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>                                                                                     |
|  <span data-ttu-id="c2eaa-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2eaa-115">Message Text</span></span>   | <span data-ttu-id="c2eaa-116">El administrador de aplicación no puede cambiar la cuenta de administradores de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="c2eaa-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="c2eaa-117">Nombre de la aplicación: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c2eaa-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="c2eaa-118">Administradores de aplicación: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c2eaa-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="c2eaa-119">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="c2eaa-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c2eaa-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="c2eaa-120">Explanation</span></span>  
 <span data-ttu-id="c2eaa-121">El administrador de aplicación no puede cambiar la cuenta de administradores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2eaa-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2eaa-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c2eaa-122">User Action</span></span>  
 <span data-ttu-id="c2eaa-123">Para cambiar la cuenta de administradores de aplicación, debe ser un administrador de aplicación afiliado de SSO o superior.</span><span class="sxs-lookup"><span data-stu-id="c2eaa-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>