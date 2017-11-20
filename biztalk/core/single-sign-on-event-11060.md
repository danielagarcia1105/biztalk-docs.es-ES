---
title: "Inicio de sesión único: Evento 11060 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1423b7385e6c0b8f78fb815ec48b749556cd291f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11060"></a><span data-ttu-id="4f792-102">Inicio de sesión único: Evento 11060</span><span class="sxs-lookup"><span data-stu-id="4f792-102">Single Sign-On: Event 11060</span></span>
## <a name="details"></a><span data-ttu-id="4f792-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4f792-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f792-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4f792-104">Product Name</span></span>|<span data-ttu-id="4f792-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4f792-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4f792-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4f792-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4f792-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4f792-107">Event ID</span></span>|<span data-ttu-id="4f792-108">11060</span><span class="sxs-lookup"><span data-stu-id="4f792-108">11060</span></span>|  
|<span data-ttu-id="4f792-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4f792-109">Event Source</span></span>|<span data-ttu-id="4f792-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4f792-110">ENTSSO</span></span>|  
|<span data-ttu-id="4f792-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4f792-111">Component</span></span>|<span data-ttu-id="4f792-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4f792-112">N/A</span></span>|  
|<span data-ttu-id="4f792-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4f792-113">Symbolic Name</span></span>|<span data-ttu-id="4f792-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="4f792-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="4f792-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4f792-115">Message Text</span></span>|<span data-ttu-id="4f792-116">Los cambios de contraseña de Windows de MIIS sólo se aceptarán desde una cuenta de servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4f792-116">Windows password changes from MIIS will only be accepted from the SSO service account.%r</span></span><br /><br /> <span data-ttu-id="4f792-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4f792-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4f792-118">El usuario cliente: %2 %r</span><span class="sxs-lookup"><span data-stu-id="4f792-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="4f792-119">Cuenta de servicio SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="4f792-119">SSO Service Account: %3%r</span></span><br /><br /> <span data-ttu-id="4f792-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="4f792-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4f792-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="4f792-121">Explanation</span></span>  
 <span data-ttu-id="4f792-122">El servidor de ENTSSO recibió un cambio de contraseña de Microsoft Identity Integration Server (MIIS).</span><span class="sxs-lookup"><span data-stu-id="4f792-122">A password change has been received by the ENTSSO server from Microsoft Identity Integration Server (MIIS).</span></span> <span data-ttu-id="4f792-123">No obstante, el servidor de ENTSSO sólo aceptará cambios de contraseña de MIIS si el usuario del cliente (usuario que llama) es la misma cuenta que la cuenta de servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="4f792-123">However, the ENTSSO server will only accept password changes from MIIS if the Client User (the caller) is the same account as the SSO service account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f792-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4f792-124">User Action</span></span>  
 <span data-ttu-id="4f792-125">Compruebe la configuración del usuario que llama para sincronización de contraseñas de MIIS.</span><span class="sxs-lookup"><span data-stu-id="4f792-125">Check the configuration of the caller for password sync in MIIS.</span></span> <span data-ttu-id="4f792-126">Para obtener más información, consulte [cómo configurar ENTSSO para la sincronización de contraseña de MIIS](../core/how-to-configure-entsso-for-miis-password-sync.md).</span><span class="sxs-lookup"><span data-stu-id="4f792-126">For more information, see [How to Configure ENTSSO for MIIS Password Sync](../core/how-to-configure-entsso-for-miis-password-sync.md).</span></span>