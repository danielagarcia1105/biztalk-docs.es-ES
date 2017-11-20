---
title: "Acerca de la sesión 2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9d34038acceb0bd52dc598ca48cf5e914d70d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-session-management"></a><span data-ttu-id="8a901-102">Administración de sesiones</span><span class="sxs-lookup"><span data-stu-id="8a901-102">About Session Management</span></span>
<span data-ttu-id="8a901-103">El adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne crea una sesión de conexión para enviar una llamada al servidor J.D. Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="8a901-103">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne creates a connection session to send a call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="8a901-104">Cuando la llamada termina, la sesión se coloca en un grupo para que pueda ser utilizada por una llamada posterior.</span><span class="sxs-lookup"><span data-stu-id="8a901-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="8a901-105">El adaptador crea varias sesiones de conexión para controlar las llamadas concurrentes al servidor J.D. Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="8a901-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="8a901-106">El grupo se limpia regularmente para quitar sesiones que ya no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="8a901-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="8a901-107">El adaptador de Microsoft BizTalk para J.D. Edwards EnterpriseOne proporciona dos propiedades de contexto de mensaje para controlar el momento en que deben tener lugar las llamadas dentro de la misma sesión.</span><span class="sxs-lookup"><span data-stu-id="8a901-107">The Microsoft BizTalk Adapter JD Edwards EnterpriseOne provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="8a901-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="8a901-108">Name</span></span>|<span data-ttu-id="8a901-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a901-109">Type</span></span>|<span data-ttu-id="8a901-110">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="8a901-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="8a901-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="8a901-111">JDE.SessionID</span></span>|<span data-ttu-id="8a901-112">int</span><span class="sxs-lookup"><span data-stu-id="8a901-112">Int</span></span>|<span data-ttu-id="8a901-113">0</span><span class="sxs-lookup"><span data-stu-id="8a901-113">0</span></span>|  
|<span data-ttu-id="8a901-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="8a901-114">JDE.ReserveSession</span></span>|<span data-ttu-id="8a901-115">boolean</span><span class="sxs-lookup"><span data-stu-id="8a901-115">boolean</span></span>|<span data-ttu-id="8a901-116">false</span><span class="sxs-lookup"><span data-stu-id="8a901-116">false</span></span>|  
  
 <span data-ttu-id="8a901-117">La administración de sesiones es innecesaria si la función empresarial requiere una única llamada al servidor J.D. Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="8a901-117">Session management is unnecessary if the business function requires a single call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="8a901-118">El adaptador puede seleccionar cualquier sesión disponible y la sesión permanece disponible para las llamadas siguientes.</span><span class="sxs-lookup"><span data-stu-id="8a901-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="8a901-119">En este escenario, se pueden omitir las propiedades de contexto de mensaje, ya que los valores predeterminados resultan adecuados.</span><span class="sxs-lookup"><span data-stu-id="8a901-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="8a901-120">Alguna funcionalidad de J.D. Edwards EnterpriseOne requiere varias llamadas al servidor J.D. Edwards EnterpriseOne; por ejemplo, la creación de SalesOrder.</span><span class="sxs-lookup"><span data-stu-id="8a901-120">Some JD Edwards EnterpriseOne functionality requires multiple calls to the JD Edwards EnterpriseOne server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="8a901-121">La primera llamada a BeginDoc crea un SalesOrder en blanco.</span><span class="sxs-lookup"><span data-stu-id="8a901-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="8a901-122">Cada llamada posterior a EditLine agrega un elemento de línea a SalesOrder.</span><span class="sxs-lookup"><span data-stu-id="8a901-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="8a901-123">Por último, la llamada a EndDoc cierra SalesOrder.</span><span class="sxs-lookup"><span data-stu-id="8a901-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="8a901-124">Para que no haya errores, todas las llamadas a una SalesOrder deben enviarse en la misma sesión.</span><span class="sxs-lookup"><span data-stu-id="8a901-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="8a901-125">Para ello, asigne propiedades de contexto de mensaje para indicar al adaptador qué hacer con la sesión.</span><span class="sxs-lookup"><span data-stu-id="8a901-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="8a901-126">Para el ejemplo de SalesOrder, éstos son los valores que se asignarían a las propiedades de contexto de mensaje para controlar la sesión de J.D. Edwards EnterpriseOne:</span><span class="sxs-lookup"><span data-stu-id="8a901-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD Edwards EnterpriseOne session:</span></span>  
  
|<span data-ttu-id="8a901-127">Función</span><span class="sxs-lookup"><span data-stu-id="8a901-127">Function</span></span>|<span data-ttu-id="8a901-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="8a901-128">SessionID</span></span>|<span data-ttu-id="8a901-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="8a901-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="8a901-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8a901-130">BeginDoc</span></span>|<span data-ttu-id="8a901-131">0</span><span class="sxs-lookup"><span data-stu-id="8a901-131">0</span></span>|<span data-ttu-id="8a901-132">true</span><span class="sxs-lookup"><span data-stu-id="8a901-132">true</span></span>|  
|<span data-ttu-id="8a901-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="8a901-133">EditLine</span></span>|<span data-ttu-id="8a901-134">Se copia de la respuesta BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8a901-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="8a901-135">true</span><span class="sxs-lookup"><span data-stu-id="8a901-135">true</span></span>|  
|<span data-ttu-id="8a901-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="8a901-136">EditLine</span></span>|<span data-ttu-id="8a901-137">Se copia de la respuesta BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8a901-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="8a901-138">true</span><span class="sxs-lookup"><span data-stu-id="8a901-138">true</span></span>|  
|<span data-ttu-id="8a901-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="8a901-139">EndDoc</span></span>|<span data-ttu-id="8a901-140">Copia de la respuesta BeginDoc</span><span class="sxs-lookup"><span data-stu-id="8a901-140">Copied from  BeginDoc reply</span></span>|<span data-ttu-id="8a901-141">false</span><span class="sxs-lookup"><span data-stu-id="8a901-141">false</span></span>|  
  
-   <span data-ttu-id="8a901-142">Para la primera llamada, el adaptador puede elegir cualquier sesión disponible (porque el valor de SessionID es cero).</span><span class="sxs-lookup"><span data-stu-id="8a901-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
-   <span data-ttu-id="8a901-143">El adaptador devuelve el valor de SessionID usado en la respuesta BeginDoc.</span><span class="sxs-lookup"><span data-stu-id="8a901-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
-   <span data-ttu-id="8a901-144">La propiedad ReserveSession indica al adaptador que reserve esta sesión para las llamadas siguientes que soliciten de forma explícita esta sesión.</span><span class="sxs-lookup"><span data-stu-id="8a901-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="8a901-145">Ninguna otra llamada puede reutilizar accidentalmente la sesión porque está reservada.</span><span class="sxs-lookup"><span data-stu-id="8a901-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
-   <span data-ttu-id="8a901-146">Las llamadas posteriores solicitan la sesión al establecer SessionID con el valor devuelto en BeginDoc.</span><span class="sxs-lookup"><span data-stu-id="8a901-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
-   <span data-ttu-id="8a901-147">La propiedad ReserveSession está establecida como True, al menos hasta la última llamada de la serie.</span><span class="sxs-lookup"><span data-stu-id="8a901-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
-   <span data-ttu-id="8a901-148">La última llamada establece ReserveSession como False para que la sesión esté disponible para cualquier llamada siguiente.</span><span class="sxs-lookup"><span data-stu-id="8a901-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="8a901-149">No obstante, la orquestación puede optar por conservar la sesión para más llamadas.</span><span class="sxs-lookup"><span data-stu-id="8a901-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
 <span data-ttu-id="8a901-150">Si la sesión no se usa durante un tiempo, el grupo la eliminará aunque la sesión siga reservada por error.</span><span class="sxs-lookup"><span data-stu-id="8a901-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
 <span data-ttu-id="8a901-151">Para obtener información detallada sobre las propiedades de contexto de mensaje, vea la documentación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8a901-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a901-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a901-152">See Also</span></span>  
 [<span data-ttu-id="8a901-153">Usar propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="8a901-153">Using Message Context Properties</span></span>](../core/using-message-context-properties1.md)