---
title: "Inicio de sesión único: Evento 10540 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec48afebfa36411594c28908a233409311e32df9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="960e6-102">Inicio de sesión único: Evento 10540</span><span class="sxs-lookup"><span data-stu-id="960e6-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="960e6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="960e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="960e6-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="960e6-104">Product Name</span></span>|<span data-ttu-id="960e6-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="960e6-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="960e6-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="960e6-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="960e6-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="960e6-107">Event ID</span></span>|<span data-ttu-id="960e6-108">10540</span><span class="sxs-lookup"><span data-stu-id="960e6-108">10540</span></span>|  
|<span data-ttu-id="960e6-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="960e6-109">Event Source</span></span>|<span data-ttu-id="960e6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="960e6-110">ENTSSO</span></span>|  
|<span data-ttu-id="960e6-111">Componente</span><span class="sxs-lookup"><span data-stu-id="960e6-111">Component</span></span>|<span data-ttu-id="960e6-112">CO</span><span class="sxs-lookup"><span data-stu-id="960e6-112">CO</span></span>|  
|<span data-ttu-id="960e6-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="960e6-113">Symbolic Name</span></span>|<span data-ttu-id="960e6-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="960e6-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="960e6-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="960e6-115">Message Text</span></span>|<span data-ttu-id="960e6-116">No se habilitaron vales para la aplicación.%r</span><span class="sxs-lookup"><span data-stu-id="960e6-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="960e6-117">Nombre de la aplicación: %1</span><span class="sxs-lookup"><span data-stu-id="960e6-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="960e6-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="960e6-118">Explanation</span></span>  
 <span data-ttu-id="960e6-119">Este evento de advertencia indica que no se habilitó la característica de vales para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="960e6-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="960e6-120">El uso de vales de SSO es una característica opcional para cada aplicación de SSO.</span><span class="sxs-lookup"><span data-stu-id="960e6-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="960e6-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="960e6-121">User Action</span></span>  
 <span data-ttu-id="960e6-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="960e6-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="960e6-123">Póngase en contacto con el administrador de aplicaciones para habilitar vales para el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="960e6-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="960e6-124">Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).</span><span class="sxs-lookup"><span data-stu-id="960e6-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="960e6-125">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="960e6-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="960e6-126">Vales de SSO</span><span class="sxs-lookup"><span data-stu-id="960e6-126">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="960e6-127">Cómo mostrar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="960e6-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="960e6-128">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="960e6-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)