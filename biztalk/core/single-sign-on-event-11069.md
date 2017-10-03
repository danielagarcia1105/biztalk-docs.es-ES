---
title: "Inicio de sesión único: Evento 11069 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66f89a1d273b0ed621cd3b59526714d9cb167bfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11069"></a><span data-ttu-id="4b4b6-102">Inicio de sesión único: Evento 11069</span><span class="sxs-lookup"><span data-stu-id="4b4b6-102">Single Sign-On: Event 11069</span></span>
## <a name="details"></a><span data-ttu-id="4b4b6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4b4b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b4b6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4b4b6-104">Product Name</span></span>|<span data-ttu-id="4b4b6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4b4b6-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4b4b6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4b4b6-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4b4b6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4b4b6-107">Event ID</span></span>|<span data-ttu-id="4b4b6-108">11069</span><span class="sxs-lookup"><span data-stu-id="4b4b6-108">11069</span></span>|  
|<span data-ttu-id="4b4b6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4b4b6-109">Event Source</span></span>|<span data-ttu-id="4b4b6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4b4b6-110">ENTSSO</span></span>|  
|<span data-ttu-id="4b4b6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="4b4b6-111">Component</span></span>|<span data-ttu-id="4b4b6-112">N/D</span><span class="sxs-lookup"><span data-stu-id="4b4b6-112">N/A</span></span>|  
|<span data-ttu-id="4b4b6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4b4b6-113">Symbolic Name</span></span>|<span data-ttu-id="4b4b6-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="4b4b6-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="4b4b6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4b4b6-115">Message Text</span></span>|<span data-ttu-id="4b4b6-116">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.</span><span class="sxs-lookup"><span data-stu-id="4b4b6-116">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span> <span data-ttu-id="4b4b6-117">Use 'ssoconfig -allowPS PCNS yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="4b4b6-117">Use 'ssoconfig -allowPS PCNS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="4b4b6-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4b4b6-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4b4b6-119">Usuario cliente: %2</span><span class="sxs-lookup"><span data-stu-id="4b4b6-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b4b6-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="4b4b6-120">Explanation</span></span>  
 <span data-ttu-id="4b4b6-121">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde PCNS.</span><span class="sxs-lookup"><span data-stu-id="4b4b6-121">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b4b6-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4b4b6-122">User Action</span></span>  
 <span data-ttu-id="4b4b6-123">Para permitir cambios de contraseña de Windows desde PCNS, en la **complemento de servidores**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde PCNS.**</span><span class="sxs-lookup"><span data-stu-id="4b4b6-123">To allow Windows password changes from PCNS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from PCNS.**</span></span>  
  
 <span data-ttu-id="4b4b6-124">Para obtener más información, consulte [cómo utilizar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="4b4b6-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>