---
title: 'De sesión único: Evento 10552 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4f78ce40f827e6c06e59e1382aba8faac0337f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001213"
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="4f882-102">De sesión único: Evento 10552</span><span class="sxs-lookup"><span data-stu-id="4f882-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="4f882-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4f882-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="4f882-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4f882-104">Product Name</span></span>   |                 <span data-ttu-id="4f882-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4f882-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="4f882-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4f882-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="4f882-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4f882-107">Event ID</span></span>     |                           <span data-ttu-id="4f882-108">10552</span><span class="sxs-lookup"><span data-stu-id="4f882-108">10552</span></span>                            |
|  <span data-ttu-id="4f882-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4f882-109">Event Source</span></span>   |                           <span data-ttu-id="4f882-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4f882-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="4f882-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4f882-111">Component</span></span>    |                            <span data-ttu-id="4f882-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4f882-112">N/A</span></span>                             |
|  <span data-ttu-id="4f882-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4f882-113">Symbolic Name</span></span>  |          <span data-ttu-id="4f882-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="4f882-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="4f882-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4f882-115">Message Text</span></span>   |              <span data-ttu-id="4f882-116">Acceso denegado al servidor de asignaciones.%r</span><span class="sxs-lookup"><span data-stu-id="4f882-116">Mapping server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="4f882-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="4f882-117">Explanation</span></span>  
 <span data-ttu-id="4f882-118">Un cliente llamó al servidor de asignaciones pero no se aceptó la llamada.</span><span class="sxs-lookup"><span data-stu-id="4f882-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="4f882-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el cliente.</span><span class="sxs-lookup"><span data-stu-id="4f882-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f882-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4f882-120">User Action</span></span>  
 <span data-ttu-id="4f882-121">Tome nota de la información incluida en el registro de eventos y póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f882-121">Note the information in the error log and contact product support services.</span></span>