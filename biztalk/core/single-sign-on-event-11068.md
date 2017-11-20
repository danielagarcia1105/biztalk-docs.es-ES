---
title: "Inicio de sesión único: Evento 11068 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be824a9205d81aaaeb9fd87129133b94b4f2e379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11068"></a><span data-ttu-id="f70aa-102">Inicio de sesión único: Evento 11068</span><span class="sxs-lookup"><span data-stu-id="f70aa-102">Single Sign-On: Event 11068</span></span>
## <a name="details"></a><span data-ttu-id="f70aa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f70aa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f70aa-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f70aa-104">Product Name</span></span>|<span data-ttu-id="f70aa-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f70aa-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f70aa-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f70aa-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f70aa-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f70aa-107">Event ID</span></span>|<span data-ttu-id="f70aa-108">11068</span><span class="sxs-lookup"><span data-stu-id="f70aa-108">11068</span></span>|  
|<span data-ttu-id="f70aa-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f70aa-109">Event Source</span></span>|<span data-ttu-id="f70aa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f70aa-110">ENTSSO</span></span>|  
|<span data-ttu-id="f70aa-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f70aa-111">Component</span></span>|<span data-ttu-id="f70aa-112">N/D</span><span class="sxs-lookup"><span data-stu-id="f70aa-112">N/A</span></span>|  
|<span data-ttu-id="f70aa-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f70aa-113">Symbolic Name</span></span>|<span data-ttu-id="f70aa-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span><span class="sxs-lookup"><span data-stu-id="f70aa-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span></span>|  
|<span data-ttu-id="f70aa-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f70aa-115">Message Text</span></span>|<span data-ttu-id="f70aa-116">Acceso denegado al servidor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f70aa-116">Lookup server access denied.</span></span> <span data-ttu-id="f70aa-117">Este servidor de SSO actualmente no está configurado para permitir búsqueda remota.</span><span class="sxs-lookup"><span data-stu-id="f70aa-117">This SSO server is currently not configured to allow remote lookup.</span></span> <span data-ttu-id="f70aa-118">Use 'ssoconfig -remoteLookup yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="f70aa-118">Use 'ssoconfig -remoteLookup yes' or the SSO Administration MMC.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f70aa-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="f70aa-119">Explanation</span></span>  
 <span data-ttu-id="f70aa-120">Se denegó el acceso al servidor de búsqueda porque el servidor de ENTSSO no está configurado para permitir búsqueda remota.</span><span class="sxs-lookup"><span data-stu-id="f70aa-120">Lookup server access has been denied because the ENTSSO server is not configured to allow remote lookup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f70aa-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f70aa-121">User Action</span></span>  
 <span data-ttu-id="f70aa-122">Para permitir búsqueda remota, en la **complemento de servidores**, **avanzadas** ficha, seleccione **Permitir búsqueda remota**.</span><span class="sxs-lookup"><span data-stu-id="f70aa-122">To allow remote lookup, in the **Servers Snap-In**, **Advanced** tab, select **Allow Remote Lookup**.</span></span>  
  
 <span data-ttu-id="f70aa-123">Para obtener más información, consulte [cómo utilizar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="f70aa-123">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>