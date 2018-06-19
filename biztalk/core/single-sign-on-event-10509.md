---
title: 'Inicio de sesión único: Evento 10509 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4d61cbb7af195aa88c36b64149366334c835b80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270356"
---
# <a name="single-sign-on-event-10509"></a><span data-ttu-id="6cac2-102">Inicio de sesión único: Evento 10509</span><span class="sxs-lookup"><span data-stu-id="6cac2-102">Single Sign-On: Event 10509</span></span>
## <a name="details"></a><span data-ttu-id="6cac2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6cac2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cac2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6cac2-104">Product Name</span></span>|<span data-ttu-id="6cac2-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="6cac2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6cac2-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6cac2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6cac2-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6cac2-107">Event ID</span></span>|<span data-ttu-id="6cac2-108">10509</span><span class="sxs-lookup"><span data-stu-id="6cac2-108">10509</span></span>|  
|<span data-ttu-id="6cac2-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6cac2-109">Event Source</span></span>|<span data-ttu-id="6cac2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6cac2-110">ENTSSO</span></span>|  
|<span data-ttu-id="6cac2-111">Componente</span><span class="sxs-lookup"><span data-stu-id="6cac2-111">Component</span></span>|<span data-ttu-id="6cac2-112">N\D</span><span class="sxs-lookup"><span data-stu-id="6cac2-112">N\A</span></span>|  
|<span data-ttu-id="6cac2-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6cac2-113">Symbolic Name</span></span>|<span data-ttu-id="6cac2-114">SSO_INFO_SERVICE_REMOVE_FAILED</span><span class="sxs-lookup"><span data-stu-id="6cac2-114">SSO_INFO_SERVICE_REMOVE_FAILED</span></span>|  
|<span data-ttu-id="6cac2-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6cac2-115">Message Text</span></span>|<span data-ttu-id="6cac2-116">No se pudo quitar el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="6cac2-116">Failed to remove the SSO service.%r</span></span><br /><br /> <span data-ttu-id="6cac2-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="6cac2-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6cac2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="6cac2-118">Explanation</span></span>  
 <span data-ttu-id="6cac2-119">Este evento indica que no se pudo desinstalar el servicio ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="6cac2-119">This event indicates that the ENTSSO Service failed to uninstall.</span></span> <span data-ttu-id="6cac2-120">Este evento sólo puede ocurrir durante la desinstalación manual de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6cac2-120">This event can only occur during a manual uninstallation of Enterprise Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cac2-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6cac2-121">User Action</span></span>  
 <span data-ttu-id="6cac2-122">Para solucionar el evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cac2-122">To resolve this event, do the following:</span></span>  
  
-   <span data-ttu-id="6cac2-123">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="6cac2-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="6cac2-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6cac2-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6cac2-125">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="6cac2-125">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="6cac2-126">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="6cac2-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)