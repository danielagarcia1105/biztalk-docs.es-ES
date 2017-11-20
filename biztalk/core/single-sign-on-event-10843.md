---
title: "Inicio de sesión único: Evento 10843 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86a39d515858e1cda09317ba6139bc67c95ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10843"></a><span data-ttu-id="86772-102">Inicio de sesión único: Evento 10843</span><span class="sxs-lookup"><span data-stu-id="86772-102">Single Sign-On: Event 10843</span></span>
## <a name="details"></a><span data-ttu-id="86772-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="86772-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86772-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="86772-104">Product Name</span></span>|<span data-ttu-id="86772-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="86772-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="86772-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="86772-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="86772-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="86772-107">Event ID</span></span>|<span data-ttu-id="86772-108">10843</span><span class="sxs-lookup"><span data-stu-id="86772-108">10843</span></span>|  
|<span data-ttu-id="86772-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="86772-109">Event Source</span></span>|<span data-ttu-id="86772-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="86772-110">ENTSSO</span></span>|  
|<span data-ttu-id="86772-111">Componente</span><span class="sxs-lookup"><span data-stu-id="86772-111">Component</span></span>|<span data-ttu-id="86772-112">N/D</span><span class="sxs-lookup"><span data-stu-id="86772-112">N/A</span></span>|  
|<span data-ttu-id="86772-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="86772-113">Symbolic Name</span></span>|<span data-ttu-id="86772-114">ENTSSO_E_NO_SECRET2</span><span class="sxs-lookup"><span data-stu-id="86772-114">ENTSSO_E_NO_SECRET2</span></span>|  
|<span data-ttu-id="86772-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="86772-115">Message Text</span></span>|<span data-ttu-id="86772-116">No se puede realizar la tarea de cifrado o descifrado porque el secreto no está disponible en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="86772-116">Cannot perform encryption or decryption because the secret is not available from the master secret server.</span></span> <span data-ttu-id="86772-117">Consulte el registro de eventos (en el equipo "%1") para ver los errores relacionados.</span><span class="sxs-lookup"><span data-stu-id="86772-117">See the event log (on computer ‘%1’) for related errors.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86772-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="86772-118">Explanation</span></span>  
 <span data-ttu-id="86772-119">Acceso denegado.</span><span class="sxs-lookup"><span data-stu-id="86772-119">Access is denied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86772-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="86772-120">User Action</span></span>  
 <span data-ttu-id="86772-121">El servidor secreto principal está desconectado o le falta el secreto principal necesario.</span><span class="sxs-lookup"><span data-stu-id="86772-121">Either the master secret server is off-line, or the master secret server is missing the required master secret.</span></span> <span data-ttu-id="86772-122">Consulte el registro de eventos en el equipo especificado para ver los errores relacionados.</span><span class="sxs-lookup"><span data-stu-id="86772-122">See the event log on the specified computer for related errors.</span></span>