---
title: 'De sesión único: Evento 10509 | Microsoft Docs'
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
ms.openlocfilehash: 12e21d19a4504ecebd14060c784a19f5f7446035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968725"
---
# <a name="single-sign-on-event-10509"></a><span data-ttu-id="c1929-102">De sesión único: Evento 10509</span><span class="sxs-lookup"><span data-stu-id="c1929-102">Single Sign-On: Event 10509</span></span>
## <a name="details"></a><span data-ttu-id="c1929-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c1929-103">Details</span></span>  

|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="c1929-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c1929-104">Product Name</span></span>   |                   <span data-ttu-id="c1929-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c1929-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="c1929-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c1929-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="c1929-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c1929-107">Event ID</span></span>     |                             <span data-ttu-id="c1929-108">10509</span><span class="sxs-lookup"><span data-stu-id="c1929-108">10509</span></span>                              |
|  <span data-ttu-id="c1929-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c1929-109">Event Source</span></span>   |                             <span data-ttu-id="c1929-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c1929-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="c1929-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c1929-111">Component</span></span>    |                              <span data-ttu-id="c1929-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c1929-112">N\A</span></span>                               |
|  <span data-ttu-id="c1929-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c1929-113">Symbolic Name</span></span>  |                 <span data-ttu-id="c1929-114">SSO_INFO_SERVICE_REMOVE_FAILED</span><span class="sxs-lookup"><span data-stu-id="c1929-114">SSO_INFO_SERVICE_REMOVE_FAILED</span></span>                 |
|  <span data-ttu-id="c1929-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c1929-115">Message Text</span></span>   | <span data-ttu-id="c1929-116">No se pudo quitar el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="c1929-116">Failed to remove the SSO service.%r</span></span><br /><br /> <span data-ttu-id="c1929-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="c1929-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c1929-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="c1929-118">Explanation</span></span>  
 <span data-ttu-id="c1929-119">Este evento indica que no se pudo desinstalar el servicio ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="c1929-119">This event indicates that the ENTSSO Service failed to uninstall.</span></span> <span data-ttu-id="c1929-120">Este evento sólo puede ocurrir durante la desinstalación manual de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="c1929-120">This event can only occur during a manual uninstallation of Enterprise Single Sign-On.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c1929-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c1929-121">User Action</span></span>  
 <span data-ttu-id="c1929-122">Para solucionar el evento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1929-122">To resolve this event, do the following:</span></span>  

- <span data-ttu-id="c1929-123">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="c1929-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="c1929-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c1929-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c1929-125">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="c1929-125">Installing SSO</span></span>](../core/installing-sso.md)  

- [<span data-ttu-id="c1929-126">Implementación de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="c1929-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
