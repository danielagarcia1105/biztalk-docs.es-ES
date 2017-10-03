---
title: "Inicio de sesión único: Evento 11008 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88d2dfa2cfb71d66b43cfaa77b24b1dfce70fd7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="ec9c3-102">Inicio de sesión único: Evento 11008</span><span class="sxs-lookup"><span data-stu-id="ec9c3-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="ec9c3-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ec9c3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec9c3-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ec9c3-104">Product Name</span></span>|<span data-ttu-id="ec9c3-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="ec9c3-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ec9c3-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ec9c3-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ec9c3-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ec9c3-107">Event ID</span></span>|<span data-ttu-id="ec9c3-108">11008</span><span class="sxs-lookup"><span data-stu-id="ec9c3-108">11008</span></span>|  
|<span data-ttu-id="ec9c3-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ec9c3-109">Event Source</span></span>|<span data-ttu-id="ec9c3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ec9c3-110">ENTSSO</span></span>|  
|<span data-ttu-id="ec9c3-111">Componente</span><span class="sxs-lookup"><span data-stu-id="ec9c3-111">Component</span></span>|<span data-ttu-id="ec9c3-112">N/D</span><span class="sxs-lookup"><span data-stu-id="ec9c3-112">N/A</span></span>|  
|<span data-ttu-id="ec9c3-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ec9c3-113">Symbolic Name</span></span>|<span data-ttu-id="ec9c3-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="ec9c3-114">SSO_WARN_CHECK_GROUP</span></span>|  
|<span data-ttu-id="ec9c3-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec9c3-115">Message Text</span></span>|<span data-ttu-id="ec9c3-116">Error al comprobar pertenencia a grupos.%r</span><span class="sxs-lookup"><span data-stu-id="ec9c3-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="ec9c3-117">Nombre de grupo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ec9c3-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="ec9c3-118">Nombre de cuenta: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ec9c3-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="ec9c3-119">Datos adicionales: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ec9c3-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="ec9c3-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="ec9c3-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec9c3-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="ec9c3-121">Explanation</span></span>  
 <span data-ttu-id="ec9c3-122">Las causas más probables del error son problemas de red, uso entre dominios o nivel combinado de controladores de dominio (por ejemplo, si el sistema usa controladores de dominio de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ec9c3-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec9c3-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ec9c3-123">User Action</span></span>  
 <span data-ttu-id="ec9c3-124">Consulte al administrador de red para saber si existen problemas de red o si el sistema tiene uso entre dominios o nivel combinado de controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="ec9c3-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>