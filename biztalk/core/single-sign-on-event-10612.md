---
title: 'De sesión único: Evento 10612 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fdc86dd2143bf8b2b4c27dab66cc4c06ddff5ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973021"
---
# <a name="single-sign-on-event-10612"></a><span data-ttu-id="cccd7-102">De sesión único: Evento 10612</span><span class="sxs-lookup"><span data-stu-id="cccd7-102">Single Sign-On: Event 10612</span></span>
## <a name="details"></a><span data-ttu-id="cccd7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cccd7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cccd7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cccd7-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="cccd7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="cccd7-105">Enterprise Single Sign-On</span></span>                                                                                                                            |
| <span data-ttu-id="cccd7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cccd7-106">Product Version</span></span> |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="cccd7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cccd7-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="cccd7-108">10612</span><span class="sxs-lookup"><span data-stu-id="cccd7-108">10612</span></span>                                                                                                                                      |
|  <span data-ttu-id="cccd7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cccd7-109">Event Source</span></span>   |                                                                                                                                     <span data-ttu-id="cccd7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cccd7-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="cccd7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="cccd7-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="cccd7-112">N/D</span><span class="sxs-lookup"><span data-stu-id="cccd7-112">N/A</span></span>                                                                                                                                       |
|  <span data-ttu-id="cccd7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cccd7-113">Symbolic Name</span></span>  |                                                                                                                          <span data-ttu-id="cccd7-114">SSO_WARN_TRANSACTION_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cccd7-114">SSO_WARN_TRANSACTION_TIMEOUT</span></span>                                                                                                                           |
|  <span data-ttu-id="cccd7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cccd7-115">Message Text</span></span>   | <span data-ttu-id="cccd7-116">El tiempo de espera de transacción supera el máximo recomendado para la operación.</span><span class="sxs-lookup"><span data-stu-id="cccd7-116">The transaction time-out exceeds the recommended maximum for this operation.</span></span> <span data-ttu-id="cccd7-117">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="cccd7-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="cccd7-118">Id. de transacción: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cccd7-118">Transaction ID: %1%r</span></span><br /><br /> <span data-ttu-id="cccd7-119">Tiempo de espera de transacción: minutos %2 (cero indica un tiempo de espera infinito) %r</span><span class="sxs-lookup"><span data-stu-id="cccd7-119">Transaction time-out: %2 minutes (zero indicates an infinite time-out)%r</span></span><br /><br /> <span data-ttu-id="cccd7-120">Máximo recomendado: %3 minutos</span><span class="sxs-lookup"><span data-stu-id="cccd7-120">Recommended maximum: %3 minutes</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cccd7-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="cccd7-121">Explanation</span></span>  
 <span data-ttu-id="cccd7-122">El sistema recibió una transacción con un valor de tiempo de espera extremadamente grande.</span><span class="sxs-lookup"><span data-stu-id="cccd7-122">A transaction has entered the system with an exceedingly large timeout value.</span></span> <span data-ttu-id="cccd7-123">Si el sistema ENTSSO sondea la base de datos de SSO mientras está bloqueada por una transacción de larga duración, el sistema finalmente se desconectará.</span><span class="sxs-lookup"><span data-stu-id="cccd7-123">If the ENTSSO system polls the SSO database while it’s locked by a long-running transaction, the system will eventually go offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cccd7-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cccd7-124">User Action</span></span>  
 <span data-ttu-id="cccd7-125">No se requiere ninguna acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="cccd7-125">No user action is required.</span></span>