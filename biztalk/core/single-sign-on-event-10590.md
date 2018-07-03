---
title: 'De sesión único: Evento 10590 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2ac48ecf1279c1a8347e8f1ab3bcd1367854ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006775"
---
# <a name="single-sign-on-event-10590"></a><span data-ttu-id="57047-102">De sesión único: Evento 10590</span><span class="sxs-lookup"><span data-stu-id="57047-102">Single Sign-On: Event 10590</span></span>
## <a name="details"></a><span data-ttu-id="57047-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="57047-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="57047-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="57047-104">Product Name</span></span>   |                 <span data-ttu-id="57047-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="57047-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="57047-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="57047-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="57047-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="57047-107">Event ID</span></span>     |                           <span data-ttu-id="57047-108">10590</span><span class="sxs-lookup"><span data-stu-id="57047-108">10590</span></span>                            |
|  <span data-ttu-id="57047-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="57047-109">Event Source</span></span>   |                           <span data-ttu-id="57047-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="57047-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="57047-111">Componente</span><span class="sxs-lookup"><span data-stu-id="57047-111">Component</span></span>    |                            <span data-ttu-id="57047-112">N/D</span><span class="sxs-lookup"><span data-stu-id="57047-112">N/A</span></span>                             |
|  <span data-ttu-id="57047-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="57047-113">Symbolic Name</span></span>  |                  <span data-ttu-id="57047-114">SSO_ERROR_OUT_OF_SERVICE</span><span class="sxs-lookup"><span data-stu-id="57047-114">SSO_ERROR_OUT_OF_SERVICE</span></span>                  |
|  <span data-ttu-id="57047-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="57047-115">Message Text</span></span>   |        <span data-ttu-id="57047-116">Inicio de sesión único empresarial se está desconectando.</span><span class="sxs-lookup"><span data-stu-id="57047-116">Enterprise Single Sign-On is going offline.</span></span>         |
  
## <a name="explanation"></a><span data-ttu-id="57047-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="57047-117">Explanation</span></span>  
 <span data-ttu-id="57047-118">Por lo general, el sistema ENTSSO comprueba si existen actualizaciones en la base de datos de ENTSSO cada 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="57047-118">The ENTSSO system usually checks for updates on the ENTSSO database every 30 seconds.</span></span> <span data-ttu-id="57047-119">Si la base de datos no está disponible durante un período especificado (normalmente cinco minutos), el sistema se desconecta solo.</span><span class="sxs-lookup"><span data-stu-id="57047-119">If the database is unavailable for a specified time (usually five minutes), the system itself goes offline.</span></span> <span data-ttu-id="57047-120">Si se encuentra en este estado, el sistema no responde a solicitudes de credenciales.</span><span class="sxs-lookup"><span data-stu-id="57047-120">In this state the system will not respond to requests for credentials.</span></span> <span data-ttu-id="57047-121">No obstante, es posible llevar a cabo algunas actividades administrativas y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="57047-121">Some offline and administrative activities are still possible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57047-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="57047-122">User Action</span></span>  
 <span data-ttu-id="57047-123">Este error indica que la base de datos de ENTSSO está desconectada.</span><span class="sxs-lookup"><span data-stu-id="57047-123">This error indicates that the ENTSSO database is offline.</span></span> <span data-ttu-id="57047-124">Investigue la causa de inmediato.</span><span class="sxs-lookup"><span data-stu-id="57047-124">You should investigate immediately.</span></span>