---
title: 'De sesión único: Evento 10530 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38eb770f795d23286b2a057a428e3bfec73e1674
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974885"
---
# <a name="single-sign-on-event-10530"></a><span data-ttu-id="5eda2-102">De sesión único: Evento 10530</span><span class="sxs-lookup"><span data-stu-id="5eda2-102">Single Sign-On: Event 10530</span></span>
## <a name="details"></a><span data-ttu-id="5eda2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5eda2-103">Details</span></span>  

|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5eda2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5eda2-104">Product Name</span></span>   |                                             <span data-ttu-id="5eda2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5eda2-105">Enterprise Single Sign-On</span></span>                                              |
| <span data-ttu-id="5eda2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5eda2-106">Product Version</span></span> |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="5eda2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5eda2-107">Event ID</span></span>     |                                                       <span data-ttu-id="5eda2-108">10530</span><span class="sxs-lookup"><span data-stu-id="5eda2-108">10530</span></span>                                                        |
|  <span data-ttu-id="5eda2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5eda2-109">Event Source</span></span>   |                                                       <span data-ttu-id="5eda2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5eda2-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="5eda2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5eda2-111">Component</span></span>    |                                                        <span data-ttu-id="5eda2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="5eda2-112">N\A</span></span>                                                         |
|  <span data-ttu-id="5eda2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5eda2-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="5eda2-114">SSO_INFO_GOT_PREVIOUS_SECRET</span><span class="sxs-lookup"><span data-stu-id="5eda2-114">SSO_INFO_GOT_PREVIOUS_SECRET</span></span>                                            |
|  <span data-ttu-id="5eda2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5eda2-115">Message Text</span></span>   | <span data-ttu-id="5eda2-116">Se obtuvo el secreto anterior desde el servidor secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="5eda2-116">Got the previous secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="5eda2-117">Nombre del servidor secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5eda2-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="5eda2-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="5eda2-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="5eda2-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="5eda2-119">Explanation</span></span>  
 <span data-ttu-id="5eda2-120">Este evento de información indica que SSO cuenta con el secreto principal anterior.</span><span class="sxs-lookup"><span data-stu-id="5eda2-120">This Information event indicates that SSO has the previous master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5eda2-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5eda2-121">User Action</span></span>  

- <span data-ttu-id="5eda2-122">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5eda2-122">No user action is necessary.</span></span>  

  <span data-ttu-id="5eda2-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5eda2-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5eda2-124">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="5eda2-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="5eda2-125">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="5eda2-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
