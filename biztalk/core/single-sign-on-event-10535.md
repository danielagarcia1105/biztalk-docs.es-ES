---
title: 'Inicio de sesión único: Evento 10535 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f96032c8176a251090453e493487a97d9cf0fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270084"
---
# <a name="single-sign-on-event-10535"></a><span data-ttu-id="3448f-102">Inicio de sesión único: Evento 10535</span><span class="sxs-lookup"><span data-stu-id="3448f-102">Single Sign-On: Event 10535</span></span>
## <a name="details"></a><span data-ttu-id="3448f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3448f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3448f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3448f-104">Product Name</span></span>|<span data-ttu-id="3448f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="3448f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3448f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3448f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3448f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3448f-107">Event ID</span></span>|<span data-ttu-id="3448f-108">10535</span><span class="sxs-lookup"><span data-stu-id="3448f-108">10535</span></span>|  
|<span data-ttu-id="3448f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3448f-109">Event Source</span></span>|<span data-ttu-id="3448f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3448f-110">ENTSSO</span></span>|  
|<span data-ttu-id="3448f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="3448f-111">Component</span></span>|<span data-ttu-id="3448f-112">CO</span><span class="sxs-lookup"><span data-stu-id="3448f-112">CO</span></span>|  
|<span data-ttu-id="3448f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3448f-113">Symbolic Name</span></span>|<span data-ttu-id="3448f-114">SSO_INFO_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="3448f-114">SSO_INFO_API_AUDIT</span></span>|  
|<span data-ttu-id="3448f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3448f-115">Message Text</span></span>|<span data-ttu-id="3448f-116">AUDITORÍA DE SSO%r</span><span class="sxs-lookup"><span data-stu-id="3448f-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="3448f-117">Función: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3448f-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="3448f-118">Id. de seguimiento: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3448f-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="3448f-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3448f-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="3448f-120">El usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="3448f-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="3448f-121">Nombre de la aplicación: %5</span><span class="sxs-lookup"><span data-stu-id="3448f-121">Application Name: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3448f-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="3448f-122">Explanation</span></span>  
 <span data-ttu-id="3448f-123">Este evento de auditoría de información indica que se produjo un evento que cumple con el nivel de auditoría definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3448f-123">This Information Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="3448f-124">Este mensaje de evento incluye:</span><span class="sxs-lookup"><span data-stu-id="3448f-124">This event message includes:</span></span>  
  
 <span data-ttu-id="3448f-125">**Función:** que se está realizando (función)</span><span class="sxs-lookup"><span data-stu-id="3448f-125">**Function:** Function being performed</span></span>  
  
 <span data-ttu-id="3448f-126">**Id. de seguimiento:** llama GUID único generado cuando una API de SSO es el primera.</span><span class="sxs-lookup"><span data-stu-id="3448f-126">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  
  
 <span data-ttu-id="3448f-127">**Equipo cliente:** equipo cliente donde se originó la función.</span><span class="sxs-lookup"><span data-stu-id="3448f-127">**Client Computer:** Client computer where the function originated.</span></span>  
  
 <span data-ttu-id="3448f-128">**El usuario cliente:** el nombre de la cuenta de usuario que invoca la función.</span><span class="sxs-lookup"><span data-stu-id="3448f-128">**Client User:** The name of the user account that invoked the function.</span></span>  
  
 <span data-ttu-id="3448f-129">**Nombre de la aplicación:** nombre de SSO afiliadas aplicación asociada a esta función.</span><span class="sxs-lookup"><span data-stu-id="3448f-129">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  
  
 <span data-ttu-id="3448f-130">Este tipo de evento se usa para diagnosticar problemas durante el desarrollo, la solución de problemas o la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3448f-130">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="3448f-131">La información proporcionada se puede usar para determinar la llamada de API de SSO que se realiza.</span><span class="sxs-lookup"><span data-stu-id="3448f-131">Information provided can be used to determine the SSO API call being made.</span></span>  
  
 <span data-ttu-id="3448f-132">El nivel de auditoría se puede establecer en 0/1/2/3, donde 0 significa "ninguno", 1 significa "bajo" (muestra errores solamente), 2 significa "medio" (muestra errores y advertencias) y 3 significa "alto" (muestra todos los mensajes de auditoría).</span><span class="sxs-lookup"><span data-stu-id="3448f-132">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3448f-133">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3448f-133">User Action</span></span>  
  
-   <span data-ttu-id="3448f-134">Compruebe si el registro de eventos contiene mensajes de evento asociados.</span><span class="sxs-lookup"><span data-stu-id="3448f-134">Check the event log for associated event messages.</span></span>  
  
 <span data-ttu-id="3448f-135">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3448f-135">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="3448f-136">Cómo auditar SSO</span><span class="sxs-lookup"><span data-stu-id="3448f-136">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="3448f-137">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="3448f-137">Using SSO</span></span>](../core/using-sso.md)