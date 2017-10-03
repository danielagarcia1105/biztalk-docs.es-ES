---
title: "Cómo crear un puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.procedure.createreceiveport
helpviewer_keywords:
- receive ports, creating
- managing [receive ports], creating
- creating, receive ports
ms.assetid: 23fae441-be80-4759-b3d6-74787a40e65b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdecbc36962d3e4e45d35171747ff4c450959a83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-receive-port"></a><span data-ttu-id="9e25c-102">Cómo crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="9e25c-102">How to Create a Receive Port</span></span>
<span data-ttu-id="9e25c-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e25c-103">This topic describes how to use the BizTalk Server Administration console to create a receive port.</span></span> <span data-ttu-id="9e25c-104">Un puerto de recepción es una agrupación lógica de ubicaciones de recepción similares a través de los cuales los servicios interactúan con los socios comerciales externos mediante la recepción de datos.</span><span class="sxs-lookup"><span data-stu-id="9e25c-104">A receive port is a logical grouping of similar receive locations through which services interact with external partners by receiving data.</span></span>  
  
 <span data-ttu-id="9e25c-105">Puede crear los siguientes tipos de puertos de recepción:</span><span class="sxs-lookup"><span data-stu-id="9e25c-105">You can create the following types of receive ports:</span></span>  
  
-   <span data-ttu-id="9e25c-106">Unidireccionales: se utilizan para aplicaciones que entregan un mensaje sin esperar una respuesta de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="9e25c-106">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  
  
-   <span data-ttu-id="9e25c-107">Solicitud-respuesta: se utilizan con aplicaciones que requieren una respuesta a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e25c-107">Request-response — used with applications that require a response to a message</span></span>  
  
 <span data-ttu-id="9e25c-108">Además de la configuración descrita en este tema, también puede especificar opciones de seguimiento de los mensajes administrados por un puerto de recepción, como se describe en [cómo configurar seguimiento para un puerto de recepción](../core/how-to-configure-tracking-for-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="9e25c-108">In addition to the configuration described in this topic, you can also specify tracking options for the messages handled by a receive port, as described in [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e25c-109">Si va a crear un puerto de recepción en un equipo remoto y ese equipo no tiene acceso de red DTC habilitado, tendrá que reiniciar el equipo remoto después de crear el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e25c-109">If you are creating a receive port on a remote computer and that computer does not have network DTC enabled, you will have to reboot the remote computer after creating the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e25c-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e25c-110">Prerequisites</span></span>  
 <span data-ttu-id="9e25c-111">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9e25c-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9e25c-112">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="9e25c-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="9e25c-113">Para crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="9e25c-113">To create a receive port</span></span>  
  
1.  <span data-ttu-id="9e25c-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9e25c-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9e25c-115">En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para la que desee crear un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e25c-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="9e25c-116">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional** o **puerto de recepción de solicitud-respuesta**, función para el tipo de puerto que desea crear.</span><span class="sxs-lookup"><span data-stu-id="9e25c-116">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port** or **Request Response Receive Port**, according to the type of port you want to create.</span></span>  
  
4.  <span data-ttu-id="9e25c-117">En el **propiedades de puerto de recepción** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e25c-117">In the **Receive Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="9e25c-118">Use</span><span class="sxs-lookup"><span data-stu-id="9e25c-118">Use this</span></span>|<span data-ttu-id="9e25c-119">Para</span><span class="sxs-lookup"><span data-stu-id="9e25c-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e25c-120">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9e25c-120">**Name**</span></span>|<span data-ttu-id="9e25c-121">Escribir el nombre del puerto.</span><span class="sxs-lookup"><span data-stu-id="9e25c-121">Type the name of the port.</span></span>|  
    |<span data-ttu-id="9e25c-122">**Sin autenticación**</span><span class="sxs-lookup"><span data-stu-id="9e25c-122">**No authentication**</span></span>|<span data-ttu-id="9e25c-123">Haga clic en esta opción para deshabilitar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9e25c-123">Click this option to disable authentication.</span></span> <span data-ttu-id="9e25c-124">Ésta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9e25c-124">This is the default.</span></span>|  
    |<span data-ttu-id="9e25c-125">**Eliminar mensajes si hay errores de autenticación**</span><span class="sxs-lookup"><span data-stu-id="9e25c-125">**Drop messages if authentication fails**</span></span>|<span data-ttu-id="9e25c-126">Haga clic en esta opción para habilitar la autenticación y eliminar los mensajes no autenticados.</span><span class="sxs-lookup"><span data-stu-id="9e25c-126">Click this option to enable authentication but to drop unauthenticated messages.</span></span>|  
    |<span data-ttu-id="9e25c-127">**Conservar mensajes si hay errores de autenticación**</span><span class="sxs-lookup"><span data-stu-id="9e25c-127">**Keep messages if authentication fails**</span></span>|<span data-ttu-id="9e25c-128">Habilitar la autenticación y mantener los mensajes no autenticados.</span><span class="sxs-lookup"><span data-stu-id="9e25c-128">Click this option to enable authentication and keep unauthenticated messages.</span></span>|  
    |<span data-ttu-id="9e25c-129">**Habilitar enrutamiento para mensajes con errores**</span><span class="sxs-lookup"><span data-stu-id="9e25c-129">**Enable routing for failed messages**</span></span>|<span data-ttu-id="9e25c-130">Activar esta casilla para intentar enrutar cualquier mensaje que genere un error de procesamiento a una aplicación de suscripción (por ejemplo, otro puerto de recepción o programación de orquestación).</span><span class="sxs-lookup"><span data-stu-id="9e25c-130">Select this check box to attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="9e25c-131">Desactive la casilla para suspender los mensajes con error y generar una confirmación negativa (NACK).</span><span class="sxs-lookup"><span data-stu-id="9e25c-131">Clear the check box to suspend failed messages and generate a negative acknowledgment (NACK).</span></span> <span data-ttu-id="9e25c-132">Esta opción está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9e25c-132">The default value is cleared.</span></span> <span data-ttu-id="9e25c-133">Para obtener más información, consulte [cómo habilitar enrutamiento para mensajes de error para un puerto de recepción](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="9e25c-133">For more information, see [How to Enable Routing for Failed Messages for a Receive Port](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).</span></span>|  
  
5.  <span data-ttu-id="9e25c-134">En el panel izquierdo, haga clic en **ubicaciones de recepción**y crear una nueva ubicación de recepción de este puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="9e25c-134">In the left pane, click **Receive Locations**, and create a new receive location for this receive port.</span></span> <span data-ttu-id="9e25c-135">Para obtener instrucciones, consulte [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="9e25c-135">For instructions, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
6.  <span data-ttu-id="9e25c-136">En el panel izquierdo, haga clic en **asignaciones de entrada**, y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e25c-136">In the left pane, click **Inbound Maps**, and do the following:</span></span>  
  
    |<span data-ttu-id="9e25c-137">Use</span><span class="sxs-lookup"><span data-stu-id="9e25c-137">Use this</span></span>|<span data-ttu-id="9e25c-138">Para</span><span class="sxs-lookup"><span data-stu-id="9e25c-138">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e25c-139">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="9e25c-139">**Source Document**</span></span>|<span data-ttu-id="9e25c-140">Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-140">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="9e25c-141">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="9e25c-141">**Map**</span></span>|<span data-ttu-id="9e25c-142">Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-142">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="9e25c-143">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="9e25c-143">**Target Document**</span></span>|<span data-ttu-id="9e25c-144">Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-144">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
7.  <span data-ttu-id="9e25c-145">Si va a crear una respuesta de solicitud de puerto de recepción, a continuación, en el panel izquierdo, haga clic en **asignaciones de salida**, y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e25c-145">If you are creating a request-response receive port, then in the left pane, click **Outbound Maps**, and do the following:</span></span>  
  
    |<span data-ttu-id="9e25c-146">Use</span><span class="sxs-lookup"><span data-stu-id="9e25c-146">Use this</span></span>|<span data-ttu-id="9e25c-147">Para</span><span class="sxs-lookup"><span data-stu-id="9e25c-147">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9e25c-148">**Documento de origen**</span><span class="sxs-lookup"><span data-stu-id="9e25c-148">**Source Document**</span></span>|<span data-ttu-id="9e25c-149">Seleccionar el esquema de origen para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-149">From the drop-down list, select the source schema to use with this port.</span></span>|  
    |<span data-ttu-id="9e25c-150">**Mapa**</span><span class="sxs-lookup"><span data-stu-id="9e25c-150">**Map**</span></span>|<span data-ttu-id="9e25c-151">Seleccionar la asignación que desea asociar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-151">From the drop-down list, select the map you want to associate with this port.</span></span>|  
    |<span data-ttu-id="9e25c-152">**Documento de destino**</span><span class="sxs-lookup"><span data-stu-id="9e25c-152">**Target Document**</span></span>|<span data-ttu-id="9e25c-153">Seleccionar el esquema de destino para usar con este puerto en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e25c-153">From the drop-down list, select the destination schema to use with this port.</span></span>|  
  
8.  <span data-ttu-id="9e25c-154">Cuando termine de configurar el puerto de recepción, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e25c-154">When finished configuring the receive port, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e25c-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e25c-155">See Also</span></span>  
 [<span data-ttu-id="9e25c-156">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="9e25c-156">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)