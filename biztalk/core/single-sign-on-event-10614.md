---
title: 'De sesión único: Evento 10614 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cae7c64b5eeff339499f279aa85917211cbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968173"
---
# <a name="single-sign-on-event-10614"></a><span data-ttu-id="3865b-102">De sesión único: Evento 10614</span><span class="sxs-lookup"><span data-stu-id="3865b-102">Single Sign-On: Event 10614</span></span>
## <a name="details"></a><span data-ttu-id="3865b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3865b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3865b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3865b-104">Product Name</span></span>   |                                                                                                        <span data-ttu-id="3865b-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3865b-105">Enterprise Single Sign-On</span></span>                                                                                                        |
| <span data-ttu-id="3865b-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3865b-106">Product Version</span></span> |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    <span data-ttu-id="3865b-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3865b-107">Event ID</span></span>     |                                                                                                                  <span data-ttu-id="3865b-108">10614</span><span class="sxs-lookup"><span data-stu-id="3865b-108">10614</span></span>                                                                                                                  |
|  <span data-ttu-id="3865b-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3865b-109">Event Source</span></span>   |                                                                                                                 <span data-ttu-id="3865b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3865b-110">ENTSSO</span></span>                                                                                                                  |
|    <span data-ttu-id="3865b-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3865b-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="3865b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3865b-112">N/A</span></span>                                                                                                                   |
|  <span data-ttu-id="3865b-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3865b-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="3865b-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3865b-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span></span>                                                                                                     |
|  <span data-ttu-id="3865b-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3865b-115">Message Text</span></span>   | <span data-ttu-id="3865b-116">Valor de tiempo de espera de vale no válido para actualización de información global.%r</span><span class="sxs-lookup"><span data-stu-id="3865b-116">The ticket time-out value is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="3865b-117">Tiempo de espera de vale: %1 minutos %r</span><span class="sxs-lookup"><span data-stu-id="3865b-117">Ticket time-out: %1 minutes%r</span></span><br /><br /> <span data-ttu-id="3865b-118">Tiempo de espera mínimo de vale: %r de 1 minuto</span><span class="sxs-lookup"><span data-stu-id="3865b-118">Minimum ticket time-out: 1 minute%r</span></span><br /><br /> <span data-ttu-id="3865b-119">Tiempo de espera máximo de vale: %2 minutos %r</span><span class="sxs-lookup"><span data-stu-id="3865b-119">Maximum ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="3865b-120">Código de error: %3</span><span class="sxs-lookup"><span data-stu-id="3865b-120">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3865b-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="3865b-121">Explanation</span></span>  
 <span data-ttu-id="3865b-122">El valor de tiempo de espera de vale especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="3865b-122">The ticket time-out value specified is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3865b-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3865b-123">User Action</span></span>  
 <span data-ttu-id="3865b-124">Use la información proporcionada en el mensaje de advertencia para corregir el valor.</span><span class="sxs-lookup"><span data-stu-id="3865b-124">Use the information supplied in the warning message to fix the value.</span></span>