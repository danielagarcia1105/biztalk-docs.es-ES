---
title: 'De sesión único: Evento 10555 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a44b3c72659cec8295e7a6625e7b6d94259283c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000309"
---
# <a name="single-sign-on-event-10555"></a><span data-ttu-id="05f82-102">De sesión único: Evento 10555</span><span class="sxs-lookup"><span data-stu-id="05f82-102">Single Sign-On: Event 10555</span></span>
## <a name="details"></a><span data-ttu-id="05f82-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="05f82-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="05f82-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="05f82-104">Product Name</span></span>   |                 <span data-ttu-id="05f82-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="05f82-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="05f82-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="05f82-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="05f82-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="05f82-107">Event ID</span></span>     |                           <span data-ttu-id="05f82-108">10555</span><span class="sxs-lookup"><span data-stu-id="05f82-108">10555</span></span>                            |
|  <span data-ttu-id="05f82-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="05f82-109">Event Source</span></span>   |                           <span data-ttu-id="05f82-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="05f82-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="05f82-111">Componente</span><span class="sxs-lookup"><span data-stu-id="05f82-111">Component</span></span>    |                            <span data-ttu-id="05f82-112">N/D</span><span class="sxs-lookup"><span data-stu-id="05f82-112">N/A</span></span>                             |
|  <span data-ttu-id="05f82-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="05f82-113">Symbolic Name</span></span>  |          <span data-ttu-id="05f82-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="05f82-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="05f82-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="05f82-115">Message Text</span></span>   | <span data-ttu-id="05f82-116">Acceso denegado al servidor secreto.%r</span><span class="sxs-lookup"><span data-stu-id="05f82-116">Secret server access denied.%r</span></span><br /><br /> <span data-ttu-id="05f82-117">Usuario cliente: %1</span><span class="sxs-lookup"><span data-stu-id="05f82-117">Client User: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="05f82-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="05f82-118">Explanation</span></span>  
 <span data-ttu-id="05f82-119">Se envió un mensaje al servidor pero se bloqueó la respuesta.</span><span class="sxs-lookup"><span data-stu-id="05f82-119">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="05f82-120">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="05f82-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05f82-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="05f82-121">User Action</span></span>  
 <span data-ttu-id="05f82-122">Tome nota de la información incluida en el registro de eventos y póngase en contacto con los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05f82-122">Note the information in the error log and contact product support services.</span></span>