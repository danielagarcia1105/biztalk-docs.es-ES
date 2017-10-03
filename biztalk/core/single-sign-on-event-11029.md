---
title: "Inicio de sesión único: Evento 11029 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f24cee6fcbe7db5ce0b4f31d458a5a29118c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11029"></a><span data-ttu-id="08819-102">Inicio de sesión único: Evento 11029</span><span class="sxs-lookup"><span data-stu-id="08819-102">Single Sign-On: Event 11029</span></span>
## <a name="details"></a><span data-ttu-id="08819-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="08819-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08819-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="08819-104">Product Name</span></span>|<span data-ttu-id="08819-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="08819-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="08819-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="08819-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="08819-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="08819-107">Event ID</span></span>|<span data-ttu-id="08819-108">11029</span><span class="sxs-lookup"><span data-stu-id="08819-108">11029</span></span>|  
|<span data-ttu-id="08819-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="08819-109">Event Source</span></span>|<span data-ttu-id="08819-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="08819-110">ENTSSO</span></span>|  
|<span data-ttu-id="08819-111">Componente</span><span class="sxs-lookup"><span data-stu-id="08819-111">Component</span></span>|<span data-ttu-id="08819-112">N/D</span><span class="sxs-lookup"><span data-stu-id="08819-112">N/A</span></span>|  
|<span data-ttu-id="08819-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="08819-113">Symbolic Name</span></span>|<span data-ttu-id="08819-114">SSO_INFO_CASE_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="08819-114">SSO_INFO_CASE_SENSITIVE</span></span>|  
|<span data-ttu-id="08819-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="08819-115">Message Text</span></span>|<span data-ttu-id="08819-116">La base de datos de SSO distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="08819-116">The SSO database is case sensitive.</span></span> <span data-ttu-id="08819-117">El servidor de SSO se ejecutará en modo de distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="08819-117">The SSO server will run in case sensitive mode.</span></span> <span data-ttu-id="08819-118">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="08819-118">See documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08819-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="08819-119">Explanation</span></span>  
 <span data-ttu-id="08819-120">De forma predeterminada, el servidor de SSO no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="08819-120">By default the SSO server is not case-sensitive.</span></span> <span data-ttu-id="08819-121">No obstante, la base de datos de SSO de SQL Server se configuró para que distinga mayúsculas de minúsculas, de manera que el servidor de SSO también se ejecutará en este modo.</span><span class="sxs-lookup"><span data-stu-id="08819-121">However, the SQL Server SSO database has been configured to be case-sensitive, so the SSO Server will also run in case sensitive mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08819-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="08819-122">User Action</span></span>  
 <span data-ttu-id="08819-123">Tenga presente esto al especificar nombres de aplicación y de cuentas externas dado que ahora distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="08819-123">Be aware of this when specifying application names and external account names as they are now case-sensitive.</span></span> <span data-ttu-id="08819-124">Para obtener más información, consulte [servidor de SSO](../core/sso-server.md).</span><span class="sxs-lookup"><span data-stu-id="08819-124">For more information, see [SSO Server](../core/sso-server.md).</span></span>