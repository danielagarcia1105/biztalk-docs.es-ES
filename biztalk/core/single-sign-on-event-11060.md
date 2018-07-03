---
title: 'De sesión único: Evento 11060 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74fd521f2b2dab27a3a408e8459d5bb4113252d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022738"
---
# <a name="single-sign-on-event-11060"></a><span data-ttu-id="10d42-102">De sesión único: Evento 11060</span><span class="sxs-lookup"><span data-stu-id="10d42-102">Single Sign-On: Event 11060</span></span>
## <a name="details"></a><span data-ttu-id="10d42-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="10d42-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="10d42-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="10d42-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="10d42-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="10d42-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="10d42-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="10d42-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="10d42-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="10d42-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="10d42-108">11060</span><span class="sxs-lookup"><span data-stu-id="10d42-108">11060</span></span>                                                                                                         |
|  <span data-ttu-id="10d42-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="10d42-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="10d42-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="10d42-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="10d42-111">Componente</span><span class="sxs-lookup"><span data-stu-id="10d42-111">Component</span></span>    |                                                                                                          <span data-ttu-id="10d42-112">N/D</span><span class="sxs-lookup"><span data-stu-id="10d42-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="10d42-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="10d42-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="10d42-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="10d42-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span></span>                                                                                             |
|  <span data-ttu-id="10d42-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="10d42-115">Message Text</span></span>   | <span data-ttu-id="10d42-116">Los cambios de contraseña de Windows de MIIS sólo se aceptarán desde una cuenta de servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="10d42-116">Windows password changes from MIIS will only be accepted from the SSO service account.%r</span></span><br /><br /> <span data-ttu-id="10d42-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="10d42-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="10d42-118">Usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="10d42-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="10d42-119">Cuenta de servicio SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="10d42-119">SSO Service Account: %3%r</span></span><br /><br /> <span data-ttu-id="10d42-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="10d42-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="10d42-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="10d42-121">Explanation</span></span>  
 <span data-ttu-id="10d42-122">El servidor de ENTSSO recibió un cambio de contraseña de Microsoft Identity Integration Server (MIIS).</span><span class="sxs-lookup"><span data-stu-id="10d42-122">A password change has been received by the ENTSSO server from Microsoft Identity Integration Server (MIIS).</span></span> <span data-ttu-id="10d42-123">No obstante, el servidor de ENTSSO sólo aceptará cambios de contraseña de MIIS si el usuario del cliente (usuario que llama) es la misma cuenta que la cuenta de servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="10d42-123">However, the ENTSSO server will only accept password changes from MIIS if the Client User (the caller) is the same account as the SSO service account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10d42-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="10d42-124">User Action</span></span>  
 <span data-ttu-id="10d42-125">Compruebe la configuración del usuario que llama para sincronización de contraseñas de MIIS.</span><span class="sxs-lookup"><span data-stu-id="10d42-125">Check the configuration of the caller for password sync in MIIS.</span></span> <span data-ttu-id="10d42-126">Para obtener más información, consulte [cómo configurar ENTSSO para la sincronización de contraseñas de MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md).</span><span class="sxs-lookup"><span data-stu-id="10d42-126">For more information, see [How to Configure ENTSSO for MIIS Password Sync](../core/how-to-configure-entsso-for-miis-password-sync.md).</span></span>