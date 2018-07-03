---
title: 'De sesión único: Evento 10531 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264941f4-7791-4a1f-a0bf-b992c9ccda64
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74dd7f4e39997e3bbd78ffce8a7bd164968bb358
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006765"
---
# <a name="single-sign-on-event-10531"></a><span data-ttu-id="018cf-102">De sesión único: Evento 10531</span><span class="sxs-lookup"><span data-stu-id="018cf-102">Single Sign-On: Event 10531</span></span>
## <a name="details"></a><span data-ttu-id="018cf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="018cf-103">Details</span></span>  

|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="018cf-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="018cf-104">Product Name</span></span>   |                                                                                    <span data-ttu-id="018cf-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="018cf-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="018cf-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="018cf-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                    |
|    <span data-ttu-id="018cf-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="018cf-107">Event ID</span></span>     |                                                                                              <span data-ttu-id="018cf-108">10531</span><span class="sxs-lookup"><span data-stu-id="018cf-108">10531</span></span>                                                                                               |
|  <span data-ttu-id="018cf-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="018cf-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="018cf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="018cf-110">ENTSSO</span></span>                                                                                              |
|    <span data-ttu-id="018cf-111">Componente</span><span class="sxs-lookup"><span data-stu-id="018cf-111">Component</span></span>    |                                                                                               <span data-ttu-id="018cf-112">N\D</span><span class="sxs-lookup"><span data-stu-id="018cf-112">N\A</span></span>                                                                                                |
|  <span data-ttu-id="018cf-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="018cf-113">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="018cf-114">SSO_ERROR_GET_SECRET_OK</span><span class="sxs-lookup"><span data-stu-id="018cf-114">SSO_ERROR_GET_SECRET_OK</span></span>                                                                                      |
|  <span data-ttu-id="018cf-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="018cf-115">Message Text</span></span>   | <span data-ttu-id="018cf-116">Solicitud de obtención de secreto principal satisfactoria.%r</span><span class="sxs-lookup"><span data-stu-id="018cf-116">A request to get a master secret succeeded.%r</span></span><br /><br /> <span data-ttu-id="018cf-117">Número secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="018cf-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="018cf-118">MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="018cf-118">MSID: %2%r</span></span><br /><br /> <span data-ttu-id="018cf-119">Usuario cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="018cf-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="018cf-120">Equipo cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="018cf-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="018cf-121">Id. de seguimiento: %5</span><span class="sxs-lookup"><span data-stu-id="018cf-121">Tracking ID: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="018cf-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="018cf-122">Explanation</span></span>  
 <span data-ttu-id="018cf-123">Este evento indica que la solicitud de obtención del secreto principal fue satisfactoria.</span><span class="sxs-lookup"><span data-stu-id="018cf-123">This event indicates that a request for master secret has succeeded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="018cf-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="018cf-124">User Action</span></span>  

- <span data-ttu-id="018cf-125">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="018cf-125">No user action is necessary.</span></span>  

  <span data-ttu-id="018cf-126">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="018cf-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="018cf-127">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="018cf-127">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="018cf-128">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="018cf-128">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
