---
title: 'De sesión único: Evento 10817 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979197"
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="926a4-102">De sesión único: Evento 10817</span><span class="sxs-lookup"><span data-stu-id="926a4-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="926a4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="926a4-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="926a4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="926a4-104">Product Name</span></span>   |                 <span data-ttu-id="926a4-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="926a4-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="926a4-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="926a4-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="926a4-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="926a4-107">Event ID</span></span>     |                           <span data-ttu-id="926a4-108">10817</span><span class="sxs-lookup"><span data-stu-id="926a4-108">10817</span></span>                            |
|  <span data-ttu-id="926a4-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="926a4-109">Event Source</span></span>   |                           <span data-ttu-id="926a4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="926a4-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="926a4-111">Componente</span><span class="sxs-lookup"><span data-stu-id="926a4-111">Component</span></span>    |                            <span data-ttu-id="926a4-112">N/D</span><span class="sxs-lookup"><span data-stu-id="926a4-112">N/A</span></span>                             |
|  <span data-ttu-id="926a4-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="926a4-113">Symbolic Name</span></span>  |              <span data-ttu-id="926a4-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="926a4-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>               |
|  <span data-ttu-id="926a4-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="926a4-115">Message Text</span></span>   |         <span data-ttu-id="926a4-116">No se encuentra la notificación especificada.</span><span class="sxs-lookup"><span data-stu-id="926a4-116">The specified notification was not found.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="926a4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="926a4-117">Explanation</span></span>  
 <span data-ttu-id="926a4-118">El cambio de contraseña especificó un GUID de notificación que no se puede encontrar.</span><span class="sxs-lookup"><span data-stu-id="926a4-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="926a4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="926a4-119">User Action</span></span>  
 <span data-ttu-id="926a4-120">Para determinar el GUID adecuado de la notificación, consulte la configuración del adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="926a4-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>