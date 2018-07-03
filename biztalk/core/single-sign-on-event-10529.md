---
title: 'De sesión único: Evento 10529 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bc28f01db257c06223e1b1f79268ca63e3ca49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976949"
---
# <a name="single-sign-on-event-10529"></a><span data-ttu-id="d8012-102">De sesión único: Evento 10529</span><span class="sxs-lookup"><span data-stu-id="d8012-102">Single Sign-On: Event 10529</span></span>
## <a name="details"></a><span data-ttu-id="d8012-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8012-103">Details</span></span>  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d8012-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d8012-104">Product Name</span></span>   |                                             <span data-ttu-id="d8012-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="d8012-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="d8012-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d8012-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="d8012-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d8012-107">Event ID</span></span>     |                                                       <span data-ttu-id="d8012-108">10529</span><span class="sxs-lookup"><span data-stu-id="d8012-108">10529</span></span>                                                       |
|  <span data-ttu-id="d8012-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d8012-109">Event Source</span></span>   |                                                      <span data-ttu-id="d8012-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d8012-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="d8012-111">Componente</span><span class="sxs-lookup"><span data-stu-id="d8012-111">Component</span></span>    |                                                        <span data-ttu-id="d8012-112">N\D</span><span class="sxs-lookup"><span data-stu-id="d8012-112">N\A</span></span>                                                        |
|  <span data-ttu-id="d8012-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d8012-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="d8012-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="d8012-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>                                            |
|  <span data-ttu-id="d8012-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d8012-115">Message Text</span></span>   | <span data-ttu-id="d8012-116">Se obtuvo el secreto actual desde el servidor secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="d8012-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="d8012-117">Nombre del servidor secreto: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d8012-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="d8012-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="d8012-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="d8012-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="d8012-119">Explanation</span></span>  
 <span data-ttu-id="d8012-120">Este evento de información indica que SSO obtuvo el secreto principal necesario desde el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d8012-120">This Information event indicates that SSO has the requested master secret from the master secret server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d8012-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d8012-121">User Action</span></span>  

- <span data-ttu-id="d8012-122">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="d8012-122">No user action is necessary.</span></span>  

  <span data-ttu-id="d8012-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d8012-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d8012-124">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="d8012-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="d8012-125">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="d8012-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
