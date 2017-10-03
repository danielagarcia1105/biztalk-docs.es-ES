---
title: "Inicio de sesión único: Evento 10745 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="f49ad-102">Inicio de sesión único: Evento 10745</span><span class="sxs-lookup"><span data-stu-id="f49ad-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="f49ad-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f49ad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f49ad-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f49ad-104">Product Name</span></span>|<span data-ttu-id="f49ad-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="f49ad-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f49ad-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f49ad-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f49ad-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f49ad-107">Event ID</span></span>|<span data-ttu-id="f49ad-108">10745</span><span class="sxs-lookup"><span data-stu-id="f49ad-108">10745</span></span>|  
|<span data-ttu-id="f49ad-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f49ad-109">Event Source</span></span>|<span data-ttu-id="f49ad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f49ad-110">ENTSSO</span></span>|  
|<span data-ttu-id="f49ad-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f49ad-111">Component</span></span>|<span data-ttu-id="f49ad-112">N\D</span><span class="sxs-lookup"><span data-stu-id="f49ad-112">N\A</span></span>|  
|<span data-ttu-id="f49ad-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f49ad-113">Symbolic Name</span></span>|<span data-ttu-id="f49ad-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f49ad-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>|  
|<span data-ttu-id="f49ad-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f49ad-115">Message Text</span></span>|<span data-ttu-id="f49ad-116">Adaptador desconectado.%r</span><span class="sxs-lookup"><span data-stu-id="f49ad-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="f49ad-117">Id. de seguimiento: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f49ad-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f49ad-118">Adaptador: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f49ad-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f49ad-119">Mensaje de error: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f49ad-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="f49ad-120">Código de error: %4</span><span class="sxs-lookup"><span data-stu-id="f49ad-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f49ad-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="f49ad-121">Explanation</span></span>  
 <span data-ttu-id="f49ad-122">Este evento de error indica que el adaptador especificado está desconectado.</span><span class="sxs-lookup"><span data-stu-id="f49ad-122">This Error event indicates that the specified adapter is offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f49ad-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f49ad-123">User Action</span></span>  
 <span data-ttu-id="f49ad-124">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f49ad-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="f49ad-125">Compruebe si en los registros de eventos del sistema y la aplicación existen errores asociados.</span><span class="sxs-lookup"><span data-stu-id="f49ad-125">Check the system and application event logs for associated errors.</span></span>  
  
-   <span data-ttu-id="f49ad-126">Compruebe si el adaptador externo presenta errores.</span><span class="sxs-lookup"><span data-stu-id="f49ad-126">Check the external adapter for errors.</span></span>  
  
 <span data-ttu-id="f49ad-127">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f49ad-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="f49ad-128">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="f49ad-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)