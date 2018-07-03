---
title: 'De sesión único: Evento 10525 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cba8ef4-4e48-44a7-b791-bab7dc4b9cc0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae350ce6b1688d908dedb3961007401300d8d2fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968197"
---
# <a name="single-sign-on-event-10525"></a><span data-ttu-id="99755-102">De sesión único: Evento 10525</span><span class="sxs-lookup"><span data-stu-id="99755-102">Single Sign-On: Event 10525</span></span>
## <a name="details"></a><span data-ttu-id="99755-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="99755-103">Details</span></span>  

|                 |                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="99755-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="99755-104">Product Name</span></span>   |                                                                      <span data-ttu-id="99755-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="99755-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="99755-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="99755-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="99755-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="99755-107">Event ID</span></span>     |                                                                                <span data-ttu-id="99755-108">10525</span><span class="sxs-lookup"><span data-stu-id="99755-108">10525</span></span>                                                                                 |
|  <span data-ttu-id="99755-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="99755-109">Event Source</span></span>   |                                                                                <span data-ttu-id="99755-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="99755-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="99755-111">Componente</span><span class="sxs-lookup"><span data-stu-id="99755-111">Component</span></span>    |                                                                                 <span data-ttu-id="99755-112">N\D</span><span class="sxs-lookup"><span data-stu-id="99755-112">N\A</span></span>                                                                                  |
|  <span data-ttu-id="99755-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="99755-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="99755-114">SSO_INFO_GENERATE_SECRET_OK</span><span class="sxs-lookup"><span data-stu-id="99755-114">SSO_INFO_GENERATE_SECRET_OK</span></span>                                                                      |
|  <span data-ttu-id="99755-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="99755-115">Message Text</span></span>   | <span data-ttu-id="99755-116">El nuevo secreto principal se generó correctamente.%r</span><span class="sxs-lookup"><span data-stu-id="99755-116">A new master secret was successfully generated.%r</span></span><br /><br /> <span data-ttu-id="99755-117">MSID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="99755-117">MSID: %1%r</span></span><br /><br /> <span data-ttu-id="99755-118">Usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="99755-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="99755-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="99755-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="99755-120">Id. de seguimiento: %4</span><span class="sxs-lookup"><span data-stu-id="99755-120">Tracking ID: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="99755-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="99755-121">Explanation</span></span>  
 <span data-ttu-id="99755-122">Este evento de información indica que se generó un nuevo secreto principal correctamente.</span><span class="sxs-lookup"><span data-stu-id="99755-122">This Information event indicates that a new master secret was successfully generated.</span></span>  

## <a name="user-action"></a><span data-ttu-id="99755-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="99755-123">User Action</span></span>  

- <span data-ttu-id="99755-124">No es necesario que el usuario realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="99755-124">No user action is necessary.</span></span>  

  <span data-ttu-id="99755-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="99755-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="99755-126">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="99755-126">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="99755-127">Administración del secreto maestro</span><span class="sxs-lookup"><span data-stu-id="99755-127">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
