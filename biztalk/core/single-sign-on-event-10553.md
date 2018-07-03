---
title: 'De sesión único: Evento 10553 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0da8faf-8127-4d2e-a2ef-e5af20aff34f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0103305692cfb978820cd94e9a42a3b384f5ba4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013461"
---
# <a name="single-sign-on-event-10553"></a><span data-ttu-id="760fe-102">De sesión único: Evento 10553</span><span class="sxs-lookup"><span data-stu-id="760fe-102">Single Sign-On: Event 10553</span></span>
## <a name="details"></a><span data-ttu-id="760fe-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="760fe-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="760fe-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="760fe-104">Product Name</span></span>   |                 <span data-ttu-id="760fe-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="760fe-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="760fe-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="760fe-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="760fe-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="760fe-107">Event ID</span></span>     |                           <span data-ttu-id="760fe-108">10553</span><span class="sxs-lookup"><span data-stu-id="760fe-108">10553</span></span>                            |
|  <span data-ttu-id="760fe-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="760fe-109">Event Source</span></span>   |                           <span data-ttu-id="760fe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="760fe-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="760fe-111">Componente</span><span class="sxs-lookup"><span data-stu-id="760fe-111">Component</span></span>    |                            <span data-ttu-id="760fe-112">N/D</span><span class="sxs-lookup"><span data-stu-id="760fe-112">N/A</span></span>                             |
|  <span data-ttu-id="760fe-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="760fe-113">Symbolic Name</span></span>  |           <span data-ttu-id="760fe-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="760fe-114">SSO_ERROR_ADMIN_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="760fe-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="760fe-115">Message Text</span></span>   |               <span data-ttu-id="760fe-116">Acceso denegado al servidor de administración.%r</span><span class="sxs-lookup"><span data-stu-id="760fe-116">Admin server access denied.%r</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="760fe-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="760fe-117">Explanation</span></span>  
 <span data-ttu-id="760fe-118">Un cliente llamó al servidor de administración pero no se aceptó la llamada.</span><span class="sxs-lookup"><span data-stu-id="760fe-118">A call was made from a client to the Admin server but was not accepted.</span></span> <span data-ttu-id="760fe-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.</span><span class="sxs-lookup"><span data-stu-id="760fe-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="760fe-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="760fe-120">User Action</span></span>  
 <span data-ttu-id="760fe-121">Tome nota de la información incluida en el registro de eventos y póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="760fe-121">Note the information in the error log and contact product support services.</span></span>