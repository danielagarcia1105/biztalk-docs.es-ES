---
title: 'Inicio de sesión único: Evento 10507 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02d8dfa-7655-471e-84af-e58d08c3cefd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9f184acaddf64a68b38211c84c86f418af42adf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269932"
---
# <a name="single-sign-on-event-10507"></a><span data-ttu-id="a279e-102">Inicio de sesión único: Evento 10507</span><span class="sxs-lookup"><span data-stu-id="a279e-102">Single Sign-On: Event 10507</span></span>
## <a name="details"></a><span data-ttu-id="a279e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a279e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a279e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="a279e-104">Product Name</span></span>|<span data-ttu-id="a279e-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="a279e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a279e-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="a279e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a279e-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="a279e-107">Event ID</span></span>|<span data-ttu-id="a279e-108">10504</span><span class="sxs-lookup"><span data-stu-id="a279e-108">10504</span></span>|  
|<span data-ttu-id="a279e-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="a279e-109">Event Source</span></span>|<span data-ttu-id="a279e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a279e-110">ENTSSO</span></span>|  
|<span data-ttu-id="a279e-111">Componente</span><span class="sxs-lookup"><span data-stu-id="a279e-111">Component</span></span>|<span data-ttu-id="a279e-112">N\D</span><span class="sxs-lookup"><span data-stu-id="a279e-112">N\A</span></span>|  
|<span data-ttu-id="a279e-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a279e-113">Symbolic Name</span></span>|<span data-ttu-id="a279e-114">SSO_INFO_SERVICE_INSTALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="a279e-114">SSO_INFO_SERVICE_INSTALL_FAILED</span></span>|  
|<span data-ttu-id="a279e-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a279e-115">Message Text</span></span>|<span data-ttu-id="a279e-116">No se pudo instalar el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="a279e-116">Failed to install the SSO service.%r</span></span><br /><br /> <span data-ttu-id="a279e-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="a279e-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a279e-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="a279e-118">Explanation</span></span>  
 <span data-ttu-id="a279e-119">Este evento indica que no se pudo instalar el servicio ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="a279e-119">This event indicates that the ENTSSO Service failed to install.</span></span> <span data-ttu-id="a279e-120">Este evento sólo puede ocurrir durante la instalación manual de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="a279e-120">This event can only occur during a manual installation of Enterprise Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a279e-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a279e-121">User Action</span></span>  
 <span data-ttu-id="a279e-122">Para solucionar el evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a279e-122">To resolve this event, do the following:</span></span>  
  
-   <span data-ttu-id="a279e-123">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="a279e-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="a279e-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a279e-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="a279e-125">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="a279e-125">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="a279e-126">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="a279e-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)