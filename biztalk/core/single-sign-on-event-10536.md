---
title: "Inicio de sesión único: Evento 10536 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d493a45b-c4ed-40fc-8803-b3ca12f9795b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 273533009d68c36d15f08b7ed106a3e1f7a1b380
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10536"></a><span data-ttu-id="7c9cb-102">Inicio de sesión único: Evento 10536</span><span class="sxs-lookup"><span data-stu-id="7c9cb-102">Single Sign-On: Event 10536</span></span>
## <a name="details"></a><span data-ttu-id="7c9cb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7c9cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c9cb-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="7c9cb-104">Product Name</span></span>|<span data-ttu-id="7c9cb-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="7c9cb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="7c9cb-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="7c9cb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="7c9cb-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="7c9cb-107">Event ID</span></span>|<span data-ttu-id="7c9cb-108">10536</span><span class="sxs-lookup"><span data-stu-id="7c9cb-108">10536</span></span>|  
|<span data-ttu-id="7c9cb-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="7c9cb-109">Event Source</span></span>|<span data-ttu-id="7c9cb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7c9cb-110">ENTSSO</span></span>|  
|<span data-ttu-id="7c9cb-111">Componente</span><span class="sxs-lookup"><span data-stu-id="7c9cb-111">Component</span></span>|<span data-ttu-id="7c9cb-112">CO</span><span class="sxs-lookup"><span data-stu-id="7c9cb-112">CO</span></span>|  
|<span data-ttu-id="7c9cb-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7c9cb-113">Symbolic Name</span></span>|<span data-ttu-id="7c9cb-114">SSO_WARN_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="7c9cb-114">SSO_WARN_API_AUDIT</span></span>|  
|<span data-ttu-id="7c9cb-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7c9cb-115">Message Text</span></span>|<span data-ttu-id="7c9cb-116">AUDITORÍA DE SSO%r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="7c9cb-117">Función: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="7c9cb-118">Id. de seguimiento: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="7c9cb-119">Equipo cliente: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="7c9cb-120">El usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="7c9cb-121">Nombre de la aplicación: %5 %r</span><span class="sxs-lookup"><span data-stu-id="7c9cb-121">Application Name: %5%r</span></span><br /><br /> <span data-ttu-id="7c9cb-122">Código de error: %6</span><span class="sxs-lookup"><span data-stu-id="7c9cb-122">Error Code: %6</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7c9cb-123">Explicación</span><span class="sxs-lookup"><span data-stu-id="7c9cb-123">Explanation</span></span>  
 <span data-ttu-id="7c9cb-124">Este evento de auditoría de advertencia indica que se produjo un evento que cumple con el nivel de auditoría definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-124">This Warning Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="7c9cb-125">Este mensaje de evento incluye:</span><span class="sxs-lookup"><span data-stu-id="7c9cb-125">This event message includes:</span></span>  
  
 <span data-ttu-id="7c9cb-126">**Función:** que se está realizando (función)</span><span class="sxs-lookup"><span data-stu-id="7c9cb-126">**Function:** Function being performed</span></span>  
  
 <span data-ttu-id="7c9cb-127">**Id. de seguimiento:** llama GUID único generado cuando una API de SSO es el primera.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-127">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  
  
 <span data-ttu-id="7c9cb-128">**Equipo cliente:** equipo cliente donde se originó la función.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-128">**Client Computer:** Client computer where the function originated.</span></span>  
  
 <span data-ttu-id="7c9cb-129">**El usuario cliente:** el nombre de la cuenta de usuario que invoca la función.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-129">**Client User:** The name of the user account that invoked the function.</span></span>  
  
 <span data-ttu-id="7c9cb-130">**Nombre de la aplicación:** nombre de SSO afiliadas aplicación asociada a esta función.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-130">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  
  
 <span data-ttu-id="7c9cb-131">**Código de error:** identificador único de error.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-131">**Error Code:** Unique error identifier.</span></span>  
  
 <span data-ttu-id="7c9cb-132">Este tipo de evento se usa para diagnosticar problemas durante el desarrollo, la solución de problemas o la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-132">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="7c9cb-133">La información proporcionada se puede usar para determinar la llamada de API de SSO que se realiza.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-133">Information provided can be used to determine the SSO API call being made.</span></span>  
  
 <span data-ttu-id="7c9cb-134">El nivel de auditoría se puede establecer en 0/1/2/3, donde 0 significa "ninguno", 1 significa "bajo" (muestra errores solamente), 2 significa "medio" (muestra errores y advertencias) y 3 significa "alto" (muestra todos los mensajes de auditoría).</span><span class="sxs-lookup"><span data-stu-id="7c9cb-134">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c9cb-135">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7c9cb-135">User Action</span></span>  
  
-   <span data-ttu-id="7c9cb-136">Compruebe si el registro de eventos contiene mensajes de evento asociados.</span><span class="sxs-lookup"><span data-stu-id="7c9cb-136">Check the event log for associated event messages.</span></span>  
  
 <span data-ttu-id="7c9cb-137">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7c9cb-137">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="7c9cb-138">Cómo auditar SSO</span><span class="sxs-lookup"><span data-stu-id="7c9cb-138">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="7c9cb-139">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="7c9cb-139">Using SSO</span></span>](../core/using-sso.md)