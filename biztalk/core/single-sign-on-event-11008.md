---
title: 'De sesión único: Evento 11008 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3a77dcfb89a3040cf6c1acb71a053d57393591
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983733"
---
# <a name="single-sign-on-event-11008"></a><span data-ttu-id="11c14-102">De sesión único: Evento 11008</span><span class="sxs-lookup"><span data-stu-id="11c14-102">Single Sign-On: Event 11008</span></span>
## <a name="details"></a><span data-ttu-id="11c14-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="11c14-103">Details</span></span>  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="11c14-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="11c14-104">Product Name</span></span>   |                                                                 <span data-ttu-id="11c14-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="11c14-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="11c14-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="11c14-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="11c14-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="11c14-107">Event ID</span></span>     |                                                                           <span data-ttu-id="11c14-108">11008</span><span class="sxs-lookup"><span data-stu-id="11c14-108">11008</span></span>                                                                           |
|  <span data-ttu-id="11c14-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="11c14-109">Event Source</span></span>   |                                                                          <span data-ttu-id="11c14-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="11c14-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="11c14-111">Componente</span><span class="sxs-lookup"><span data-stu-id="11c14-111">Component</span></span>    |                                                                            <span data-ttu-id="11c14-112">N/D</span><span class="sxs-lookup"><span data-stu-id="11c14-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="11c14-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="11c14-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="11c14-114">SSO_WARN_CHECK_GROUP</span><span class="sxs-lookup"><span data-stu-id="11c14-114">SSO_WARN_CHECK_GROUP</span></span>                                                                    |
|  <span data-ttu-id="11c14-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="11c14-115">Message Text</span></span>   | <span data-ttu-id="11c14-116">Error al comprobar pertenencia a grupos.%r</span><span class="sxs-lookup"><span data-stu-id="11c14-116">Check group membership failed.%r</span></span><br /><br /> <span data-ttu-id="11c14-117">Nombre del grupo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="11c14-117">Group Name: %1%r</span></span><br /><br /> <span data-ttu-id="11c14-118">Nombre de cuenta: %2 %r</span><span class="sxs-lookup"><span data-stu-id="11c14-118">Account Name: %2%r</span></span><br /><br /> <span data-ttu-id="11c14-119">Datos adicionales: %3 %r</span><span class="sxs-lookup"><span data-stu-id="11c14-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="11c14-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="11c14-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="11c14-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="11c14-121">Explanation</span></span>  
 <span data-ttu-id="11c14-122">Las causas más probables del error son problemas de red, uso entre dominios o nivel combinado de controladores de dominio (por ejemplo, si el sistema usa controladores de dominio de [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="11c14-122">This is most likely caused by network issues, cross-domain use, or a mixed level of domain controllers (for example, if your system uses domain controllers from both [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11c14-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="11c14-123">User Action</span></span>  
 <span data-ttu-id="11c14-124">Consulte al administrador de red para saber si existen problemas de red o si el sistema tiene uso entre dominios o nivel combinado de controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="11c14-124">Check with your network administrator to see if there are any network issues, or if your system has any cross-domain use or mixed level of domain controllers.</span></span>