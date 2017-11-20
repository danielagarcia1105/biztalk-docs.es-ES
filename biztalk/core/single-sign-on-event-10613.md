---
title: "Inicio de sesión único: Evento 10613 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7230a0d6400a7265ef9f3cedb6bb47cc23aade
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10613"></a><span data-ttu-id="d3c17-102">Inicio de sesión único: Evento 10613</span><span class="sxs-lookup"><span data-stu-id="d3c17-102">Single Sign-On: Event 10613</span></span>
## <a name="details"></a><span data-ttu-id="d3c17-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d3c17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3c17-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d3c17-104">Product Name</span></span>|<span data-ttu-id="d3c17-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d3c17-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d3c17-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d3c17-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d3c17-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d3c17-107">Event ID</span></span>|<span data-ttu-id="d3c17-108">10613</span><span class="sxs-lookup"><span data-stu-id="d3c17-108">10613</span></span>|  
|<span data-ttu-id="d3c17-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d3c17-109">Event Source</span></span>|<span data-ttu-id="d3c17-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d3c17-110">ENTSSO</span></span>|  
|<span data-ttu-id="d3c17-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d3c17-111">Component</span></span>|<span data-ttu-id="d3c17-112">N/D</span><span class="sxs-lookup"><span data-stu-id="d3c17-112">N/A</span></span>|  
|<span data-ttu-id="d3c17-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d3c17-113">Symbolic Name</span></span>|<span data-ttu-id="d3c17-114">SSO_ERROR_RPC_CALLBACK</span><span class="sxs-lookup"><span data-stu-id="d3c17-114">SSO_ERROR_RPC_CALLBACK</span></span>|  
|<span data-ttu-id="d3c17-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d3c17-115">Message Text</span></span>|<span data-ttu-id="d3c17-116">Acceso denegado al servidor de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="d3c17-116">SSO server access denied.%r</span></span><br /><br /> <span data-ttu-id="d3c17-117">El usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d3c17-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="d3c17-118">Información de llamada RPC: %2: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d3c17-118">RPC call information: %2:%3%r</span></span><br /><br /> <span data-ttu-id="d3c17-119">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="d3c17-119">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d3c17-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="d3c17-120">Explanation</span></span>  
 <span data-ttu-id="d3c17-121">Un cliente llamó al servidor de SSO pero no se aceptó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d3c17-121">A call was made from a client to the SSO Server but was not accepted.</span></span> <span data-ttu-id="d3c17-122">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d3c17-122">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3c17-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d3c17-123">User Action</span></span>  
 <span data-ttu-id="d3c17-124">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con los servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3c17-124">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>