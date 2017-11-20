---
title: "Inicio de sesión único: Evento 11063 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82581dafd58a07ed217a5e9062aa91057a84aed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11063"></a><span data-ttu-id="07227-102">Inicio de sesión único: Evento 11063</span><span class="sxs-lookup"><span data-stu-id="07227-102">Single Sign-On: Event 11063</span></span>
## <a name="details"></a><span data-ttu-id="07227-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="07227-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07227-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="07227-104">Product Name</span></span>|<span data-ttu-id="07227-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="07227-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="07227-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="07227-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="07227-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="07227-107">Event ID</span></span>|<span data-ttu-id="07227-108">11063</span><span class="sxs-lookup"><span data-stu-id="07227-108">11063</span></span>|  
|<span data-ttu-id="07227-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="07227-109">Event Source</span></span>|<span data-ttu-id="07227-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07227-110">ENTSSO</span></span>|  
|<span data-ttu-id="07227-111">Componente</span><span class="sxs-lookup"><span data-stu-id="07227-111">Component</span></span>|<span data-ttu-id="07227-112">N/D</span><span class="sxs-lookup"><span data-stu-id="07227-112">N/A</span></span>|  
|<span data-ttu-id="07227-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="07227-113">Symbolic Name</span></span>|<span data-ttu-id="07227-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="07227-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="07227-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="07227-115">Message Text</span></span>|<span data-ttu-id="07227-116">Acceso denegado al servidor de sincronización de contraseñas (para MIIS).%r</span><span class="sxs-lookup"><span data-stu-id="07227-116">Password sync server (for MIIS) access denied.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07227-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="07227-117">Explanation</span></span>  
 <span data-ttu-id="07227-118">Se denegó el acceso a la devolución de llamada de MIIS.</span><span class="sxs-lookup"><span data-stu-id="07227-118">MIIS Callback access has been denied.</span></span> <span data-ttu-id="07227-119">La causa más probable de este error es que no se pudo usar la autenticación Kerberos entre el sistema ENTSSO y MIIS.</span><span class="sxs-lookup"><span data-stu-id="07227-119">The most likely cause of this error is failure to use the Kerberos authentication between the ENTSSO system and MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07227-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="07227-120">User Action</span></span>  
 <span data-ttu-id="07227-121">Confirme si el sistema ENTSSO usa la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="07227-121">Confirm that your ENTSSO system is using Kerberos authentication.</span></span> <span data-ttu-id="07227-122">Para obtener más información, consulte [recomendaciones de seguridad de SSO](../core/sso-security-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="07227-122">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>