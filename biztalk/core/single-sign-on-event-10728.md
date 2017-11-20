---
title: "Inicio de sesión único: Evento 10728 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f579189c-c9a5-4d2c-a3d5-f0ba03c5a3ef
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5052d03713808754abf04e8c2ba1590800e6cf9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10728"></a><span data-ttu-id="085cd-102">Inicio de sesión único: Evento 10728</span><span class="sxs-lookup"><span data-stu-id="085cd-102">Single Sign-On: Event 10728</span></span>
## <a name="details"></a><span data-ttu-id="085cd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="085cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="085cd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="085cd-104">Product Name</span></span>|<span data-ttu-id="085cd-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="085cd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="085cd-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="085cd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="085cd-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="085cd-107">Event ID</span></span>|<span data-ttu-id="085cd-108">10728</span><span class="sxs-lookup"><span data-stu-id="085cd-108">10728</span></span>|  
|<span data-ttu-id="085cd-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="085cd-109">Event Source</span></span>|<span data-ttu-id="085cd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="085cd-110">ENTSSO</span></span>|  
|<span data-ttu-id="085cd-111">Componente</span><span class="sxs-lookup"><span data-stu-id="085cd-111">Component</span></span>|<span data-ttu-id="085cd-112">N\D</span><span class="sxs-lookup"><span data-stu-id="085cd-112">N\A</span></span>|  
|<span data-ttu-id="085cd-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="085cd-113">Symbolic Name</span></span>|<span data-ttu-id="085cd-114">SSO_ERROR_VERSION</span><span class="sxs-lookup"><span data-stu-id="085cd-114">SSO_ERROR_VERSION</span></span>|  
|<span data-ttu-id="085cd-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="085cd-115">Message Text</span></span>|<span data-ttu-id="085cd-116">Esta versión de servidor de SSO no es compatible con la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="085cd-116">This version of the SSO server is not compatible with the SSO database.</span></span> <span data-ttu-id="085cd-117">Actualice el servidor secreto principal.%r</span><span class="sxs-lookup"><span data-stu-id="085cd-117">Please upgrade your master secret server.%r</span></span><br /><br /> <span data-ttu-id="085cd-118">Nombre SQL Server: %1 %r</span><span class="sxs-lookup"><span data-stu-id="085cd-118">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="085cd-119">Nombre de la base de datos SSO: %2 %r</span><span class="sxs-lookup"><span data-stu-id="085cd-119">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="085cd-120">Versión de la base de datos SSO: %3 %r</span><span class="sxs-lookup"><span data-stu-id="085cd-120">SSO Database Version: %3%r</span></span><br /><br /> <span data-ttu-id="085cd-121">Versión requerida: %4</span><span class="sxs-lookup"><span data-stu-id="085cd-121">Required Version: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="085cd-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="085cd-122">Explanation</span></span>  
 <span data-ttu-id="085cd-123">Este evento de error indica que la versión de servidor de SSO es más reciente que la base de datos de SSO (versión que la creó originalmente).</span><span class="sxs-lookup"><span data-stu-id="085cd-123">This Error event indicates that the SSO server version is more recent than (the version that originally created) the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="085cd-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="085cd-124">User Action</span></span>  
 <span data-ttu-id="085cd-125">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="085cd-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="085cd-126">Actualice el servidor secreto principal de SSO para que coincida con la versión actual de este servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="085cd-126">Upgrade the SSO master secret server to match the current version of this SSO server.</span></span> <span data-ttu-id="085cd-127">De este modo, se actualizará la base de datos de SSO a la versión actual.</span><span class="sxs-lookup"><span data-stu-id="085cd-127">This will upgrade the SSO database to the current version.</span></span>  
  
 <span data-ttu-id="085cd-128">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="085cd-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="085cd-129">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="085cd-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)