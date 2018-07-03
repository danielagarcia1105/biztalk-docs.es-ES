---
title: 'De sesión único: Evento 10749 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf82eb2fc8312874947af3c035dc13bb8e39a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010979"
---
# <a name="single-sign-on-event-10749"></a><span data-ttu-id="e85e6-102">De sesión único: Evento 10749</span><span class="sxs-lookup"><span data-stu-id="e85e6-102">Single Sign-On: Event 10749</span></span>
## <a name="details"></a><span data-ttu-id="e85e6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e85e6-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e85e6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e85e6-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="e85e6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="e85e6-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="e85e6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e85e6-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="e85e6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e85e6-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="e85e6-108">10749</span><span class="sxs-lookup"><span data-stu-id="e85e6-108">10749</span></span>                                                                                                                                |
|  <span data-ttu-id="e85e6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e85e6-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="e85e6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e85e6-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="e85e6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="e85e6-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="e85e6-112">N\D</span><span class="sxs-lookup"><span data-stu-id="e85e6-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="e85e6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e85e6-113">Symbolic Name</span></span>  |                                                                                                                       <span data-ttu-id="e85e6-114">SSO_WARN_PS_CLIENT_PING</span><span class="sxs-lookup"><span data-stu-id="e85e6-114">SSO_WARN_PS_CLIENT_PING</span></span>                                                                                                                       |
|  <span data-ttu-id="e85e6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e85e6-115">Message Text</span></span>   | <span data-ttu-id="e85e6-116">No se pudo establecer la conexión con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="e85e6-116">Could not contact the destination SSO server.</span></span><br /><br /> <span data-ttu-id="e85e6-117">Compruebe si el servicio SSO está en ejecución en ese servidor y si se puede establecer la conexión con éste.%r</span><span class="sxs-lookup"><span data-stu-id="e85e6-117">Check that the SSO service is running on that server and that it can be contacted.%r</span></span><br /><br /> <span data-ttu-id="e85e6-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e85e6-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e85e6-119">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e85e6-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="e85e6-120">Nombre del servidor SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e85e6-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="e85e6-121">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="e85e6-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="e85e6-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="e85e6-122">Explanation</span></span>  
 <span data-ttu-id="e85e6-123">Este evento de advertencia indica que la sincronización de contraseñas de SSO no pudo establecer la comunicación con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="e85e6-123">This Warning event indicates that SSO Password Sync could not contact the specified destination SSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e85e6-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e85e6-124">User Action</span></span>  
 <span data-ttu-id="e85e6-125">Para solucionar la advertencia, realice una o varias de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e85e6-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="e85e6-126">Use el complemento de servidores de ENTSSO para comprobar el servidor.</span><span class="sxs-lookup"><span data-stu-id="e85e6-126">Use the ENTSSO Servers Snap-In to check the server.</span></span>  

- <span data-ttu-id="e85e6-127">Inicie el servicio de inicio de sesión único empresarial si no está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="e85e6-127">Start the Enterprise Single Sign-On Service if it is not running.</span></span>  

- <span data-ttu-id="e85e6-128">Compruebe la conexión de red con el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="e85e6-128">Check the network connection to the destination SSO server.</span></span>  

- <span data-ttu-id="e85e6-129">Compruebe el firewall en el servidor de SSO de destino.</span><span class="sxs-lookup"><span data-stu-id="e85e6-129">Check firewall on the destination SSO Server.</span></span>  

  <span data-ttu-id="e85e6-130">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e85e6-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="e85e6-131">Cómo usar el complemento de servidores</span><span class="sxs-lookup"><span data-stu-id="e85e6-131">How to Use the Servers Snap-in</span></span>](../core/how-to-use-the-servers-snap-in.md)
