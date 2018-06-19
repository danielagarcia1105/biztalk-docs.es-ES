---
title: 'Inicio de sesión único: Evento 10560 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d630dccdd21aaade843d4aa8fd7026d05fd71da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271388"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="0d9b2-102">Inicio de sesión único: Evento 10560</span><span class="sxs-lookup"><span data-stu-id="0d9b2-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="0d9b2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0d9b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d9b2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="0d9b2-104">Product Name</span></span>|<span data-ttu-id="0d9b2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="0d9b2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0d9b2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="0d9b2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0d9b2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="0d9b2-107">Event ID</span></span>|<span data-ttu-id="0d9b2-108">10560</span><span class="sxs-lookup"><span data-stu-id="0d9b2-108">10560</span></span>|  
|<span data-ttu-id="0d9b2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="0d9b2-109">Event Source</span></span>|<span data-ttu-id="0d9b2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0d9b2-110">ENTSSO</span></span>|  
|<span data-ttu-id="0d9b2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="0d9b2-111">Component</span></span>|<span data-ttu-id="0d9b2-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0d9b2-112">N/A</span></span>|  
|<span data-ttu-id="0d9b2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0d9b2-113">Symbolic Name</span></span>|<span data-ttu-id="0d9b2-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="0d9b2-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>|  
|<span data-ttu-id="0d9b2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0d9b2-115">Message Text</span></span>|<span data-ttu-id="0d9b2-116">No se pudo realizar la copia de seguridad del secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="0d9b2-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="0d9b2-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0d9b2-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="0d9b2-118">MSID actual: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0d9b2-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="0d9b2-119">MSID anterior: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0d9b2-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="0d9b2-120">El usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="0d9b2-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="0d9b2-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="0d9b2-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0d9b2-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="0d9b2-122">Explanation</span></span>  
 <span data-ttu-id="0d9b2-123">Error al intentar realizar una copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="0d9b2-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="0d9b2-124">Es posible que los permisos, la ruta de acceso o el directorio del usuario que intenta realizar esta copia de seguridad tenga sean incorrectos.</span><span class="sxs-lookup"><span data-stu-id="0d9b2-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d9b2-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0d9b2-125">User Action</span></span>  
 <span data-ttu-id="0d9b2-126">Para obtener información sobre la copia de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b2-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>