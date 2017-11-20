---
title: "Inicio de sesión único: Evento 11070 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb0d2a868d5c8bf47cbcb5389bf2d16dadf4010a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11070"></a><span data-ttu-id="3c324-102">Inicio de sesión único: Evento 11070</span><span class="sxs-lookup"><span data-stu-id="3c324-102">Single Sign-On: Event 11070</span></span>
## <a name="details"></a><span data-ttu-id="3c324-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c324-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c324-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3c324-104">Product Name</span></span>|<span data-ttu-id="3c324-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3c324-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3c324-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3c324-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3c324-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3c324-107">Event ID</span></span>|<span data-ttu-id="3c324-108">11070</span><span class="sxs-lookup"><span data-stu-id="3c324-108">11070</span></span>|  
|<span data-ttu-id="3c324-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3c324-109">Event Source</span></span>|<span data-ttu-id="3c324-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c324-110">ENTSSO</span></span>|  
|<span data-ttu-id="3c324-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3c324-111">Component</span></span>|<span data-ttu-id="3c324-112">N/D</span><span class="sxs-lookup"><span data-stu-id="3c324-112">N/A</span></span>|  
|<span data-ttu-id="3c324-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c324-113">Symbolic Name</span></span>|<span data-ttu-id="3c324-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="3c324-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="3c324-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c324-115">Message Text</span></span>|<span data-ttu-id="3c324-116">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS.</span><span class="sxs-lookup"><span data-stu-id="3c324-116">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span> <span data-ttu-id="3c324-117">Use 'ssoconfig -allowPS MIIS yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="3c324-117">Use 'ssoconfig -allowPS MIIS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="3c324-118">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3c324-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3c324-119">Usuario cliente: %2</span><span class="sxs-lookup"><span data-stu-id="3c324-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c324-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c324-120">Explanation</span></span>  
 <span data-ttu-id="3c324-121">Este servidor de SSO actualmente no está configurado para permitir cambios de contraseña de Windows desde MIIS.</span><span class="sxs-lookup"><span data-stu-id="3c324-121">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c324-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c324-122">User Action</span></span>  
 <span data-ttu-id="3c324-123">Para permitir cambios de contraseña de Windows desde MIIS, en la **complemento de servidores**, **propiedades de sincronización de contraseña** ficha, seleccione **Permitir sincronización de contraseñas desde MIIS.**</span><span class="sxs-lookup"><span data-stu-id="3c324-123">To allow Windows password changes from MIIS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from MIIS.**</span></span>  
  
 <span data-ttu-id="3c324-124">Para obtener más información, consulte [cómo utilizar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="3c324-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>