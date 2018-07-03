---
title: 'De sesión único: Evento 10560 | Microsoft Docs'
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
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967757"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="9fc76-102">De sesión único: Evento 10560</span><span class="sxs-lookup"><span data-stu-id="9fc76-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="9fc76-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9fc76-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9fc76-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9fc76-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="9fc76-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9fc76-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="9fc76-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9fc76-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="9fc76-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9fc76-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="9fc76-108">10560</span><span class="sxs-lookup"><span data-stu-id="9fc76-108">10560</span></span>                                                                                            |
|  <span data-ttu-id="9fc76-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9fc76-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="9fc76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9fc76-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="9fc76-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9fc76-111">Component</span></span>    |                                                                                             <span data-ttu-id="9fc76-112">N/D</span><span class="sxs-lookup"><span data-stu-id="9fc76-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="9fc76-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9fc76-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="9fc76-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="9fc76-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>                                                                                |
|  <span data-ttu-id="9fc76-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9fc76-115">Message Text</span></span>   | <span data-ttu-id="9fc76-116">No se pudo realizar la copia de seguridad del secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="9fc76-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="9fc76-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9fc76-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="9fc76-118">MSID actual: %2 %r</span><span class="sxs-lookup"><span data-stu-id="9fc76-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="9fc76-119">MSID anterior: %3 %r</span><span class="sxs-lookup"><span data-stu-id="9fc76-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="9fc76-120">Usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="9fc76-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="9fc76-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="9fc76-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9fc76-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="9fc76-122">Explanation</span></span>  
 <span data-ttu-id="9fc76-123">Error al intentar realizar una copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="9fc76-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="9fc76-124">Es posible que los permisos, la ruta de acceso o el directorio del usuario que intenta realizar esta copia de seguridad tenga sean incorrectos.</span><span class="sxs-lookup"><span data-stu-id="9fc76-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9fc76-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9fc76-125">User Action</span></span>  
 <span data-ttu-id="9fc76-126">Para obtener información sobre copias de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="9fc76-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>