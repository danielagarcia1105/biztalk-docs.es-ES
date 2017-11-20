---
title: "Inicio de sesión único: Evento 10705 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41db0b3aeba4e3c71da3193af807f881bb4ae586
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10705"></a><span data-ttu-id="beb22-102">Inicio de sesión único: Evento 10705</span><span class="sxs-lookup"><span data-stu-id="beb22-102">Single Sign-On: Event 10705</span></span>
## <a name="details"></a><span data-ttu-id="beb22-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="beb22-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="beb22-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="beb22-104">Product Name</span></span>|<span data-ttu-id="beb22-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="beb22-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="beb22-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="beb22-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="beb22-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="beb22-107">Event ID</span></span>|<span data-ttu-id="beb22-108">10705</span><span class="sxs-lookup"><span data-stu-id="beb22-108">10705</span></span>|  
|<span data-ttu-id="beb22-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="beb22-109">Event Source</span></span>|<span data-ttu-id="beb22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="beb22-110">ENTSSO</span></span>|  
|<span data-ttu-id="beb22-111">Componente</span><span class="sxs-lookup"><span data-stu-id="beb22-111">Component</span></span>|<span data-ttu-id="beb22-112">N\D</span><span class="sxs-lookup"><span data-stu-id="beb22-112">N\A</span></span>|  
|<span data-ttu-id="beb22-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="beb22-113">Symbolic Name</span></span>|<span data-ttu-id="beb22-114">SSO_WARN_PS_NOT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="beb22-114">SSO_WARN_PS_NOT_ADAPTER</span></span>|  
|<span data-ttu-id="beb22-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="beb22-115">Message Text</span></span>|<span data-ttu-id="beb22-116">El adaptador especificado no es una aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="beb22-116">The specified adapter is not an adapter application.</span></span> <span data-ttu-id="beb22-117">Compruebe el tipo de aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="beb22-117">Check the application type.%r</span></span><br /><br /> <span data-ttu-id="beb22-118">Adaptador: %1</span><span class="sxs-lookup"><span data-stu-id="beb22-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="beb22-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="beb22-119">Explanation</span></span>  
 <span data-ttu-id="beb22-120">Este evento de advertencia indica que el adaptador especificado no es una aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="beb22-120">This Warning event indicates that the specified adapter is not an adapter application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="beb22-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="beb22-121">User Action</span></span>  
 <span data-ttu-id="beb22-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="beb22-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="beb22-123">Use el complemento MMC de administración de SSO, haga clic con el botón secundario en el adaptador especificado y, a continuación, haga clic en Propiedades para determinar el tipo de aplicación o bien, use las herramientas de línea de comandos "ssops -list" y "ssops -display" para determinarlo.</span><span class="sxs-lookup"><span data-stu-id="beb22-123">Use the SSO Admin MMC Snap-In, right click the specified adapter, and then click Properties to determine the application type or use the command line tool  ssops -list and ssops -display to determine the application type.</span></span>  
  
-   <span data-ttu-id="beb22-124">Use el complemento MMC de administración de SSO o "ssops -addapp" para establecer la aplicación de adaptador.</span><span class="sxs-lookup"><span data-stu-id="beb22-124">Use the SSO Admin MMC Snap-In or ssops -addapp to set the adapter application.</span></span>  
  
 <span data-ttu-id="beb22-125">Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="beb22-125">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="beb22-126">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="beb22-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)