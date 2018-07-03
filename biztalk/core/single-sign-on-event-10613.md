---
title: 'De sesión único: Evento 10613 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 250f113e0cd60b417cee29d32f8e61fbf38632dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023810"
---
# <a name="single-sign-on-event-10613"></a><span data-ttu-id="53403-102">De sesión único: Evento 10613</span><span class="sxs-lookup"><span data-stu-id="53403-102">Single Sign-On: Event 10613</span></span>
## <a name="details"></a><span data-ttu-id="53403-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="53403-103">Details</span></span>  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="53403-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="53403-104">Product Name</span></span>   |                                                   <span data-ttu-id="53403-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="53403-105">Enterprise Single Sign-On</span></span>                                                    |
| <span data-ttu-id="53403-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="53403-106">Product Version</span></span> |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    <span data-ttu-id="53403-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="53403-107">Event ID</span></span>     |                                                             <span data-ttu-id="53403-108">10613</span><span class="sxs-lookup"><span data-stu-id="53403-108">10613</span></span>                                                              |
|  <span data-ttu-id="53403-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="53403-109">Event Source</span></span>   |                                                             <span data-ttu-id="53403-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="53403-110">ENTSSO</span></span>                                                             |
|    <span data-ttu-id="53403-111">Componente</span><span class="sxs-lookup"><span data-stu-id="53403-111">Component</span></span>    |                                                              <span data-ttu-id="53403-112">N/D</span><span class="sxs-lookup"><span data-stu-id="53403-112">N/A</span></span>                                                               |
|  <span data-ttu-id="53403-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="53403-113">Symbolic Name</span></span>  |                                                     <span data-ttu-id="53403-114">SSO_ERROR_RPC_CALLBACK</span><span class="sxs-lookup"><span data-stu-id="53403-114">SSO_ERROR_RPC_CALLBACK</span></span>                                                     |
|  <span data-ttu-id="53403-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="53403-115">Message Text</span></span>   | <span data-ttu-id="53403-116">Acceso denegado al servidor de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="53403-116">SSO server access denied.%r</span></span><br /><br /> <span data-ttu-id="53403-117">Usuario cliente: %1 %r</span><span class="sxs-lookup"><span data-stu-id="53403-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="53403-118">Información de llamada RPC: %2: %3 %r</span><span class="sxs-lookup"><span data-stu-id="53403-118">RPC call information: %2:%3%r</span></span><br /><br /> <span data-ttu-id="53403-119">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="53403-119">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="53403-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="53403-120">Explanation</span></span>  
 <span data-ttu-id="53403-121">Un cliente llamó al servidor de SSO pero no se aceptó la llamada.</span><span class="sxs-lookup"><span data-stu-id="53403-121">A call was made from a client to the SSO Server but was not accepted.</span></span> <span data-ttu-id="53403-122">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.</span><span class="sxs-lookup"><span data-stu-id="53403-122">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53403-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="53403-123">User Action</span></span>  
 <span data-ttu-id="53403-124">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53403-124">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>