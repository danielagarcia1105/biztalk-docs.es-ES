---
title: Creación de TIBCO EMS artefactos de recepción | Microsoft Docs
description: Crear el puerto de recepción y establecer las propiedades de transporte para usar el adaptador de TIBCO Enterprise Message Service en BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27dd4ff3e317f178c2b9085cf531a6b963aafc7f
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "24015379"
---
# <a name="create-tibco-ems-receive-artifacts"></a><span data-ttu-id="a1832-103">Creación de TIBCO EMS artefactos de recepción</span><span class="sxs-lookup"><span data-stu-id="a1832-103">Create TIBCO EMS receive artifacts</span></span>

## <a name="overview"></a><span data-ttu-id="a1832-104">Información general</span><span class="sxs-lookup"><span data-stu-id="a1832-104">Overview</span></span>
<span data-ttu-id="a1832-105">El receptor TIBCO Enterprise Message Service es un servicio de escucha que registra una cola o tema particular y recibe los mensajes relacionados.</span><span class="sxs-lookup"><span data-stu-id="a1832-105">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="a1832-106">El adaptador de BizTalk para TIBCO Enterprise Message Service se registra primero con TIBCO Enterprise Message Service, mediante la apertura de una nueva sesión y, después, continúa realizando el sondeo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1832-106">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="a1832-107">En esta sección se explica cómo configurar el puerto de recepción para conectarse a TIBCO Enterprise Message Service y cómo incluir XML en la orquestación para interactuar con TIBCO EMS en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a1832-107">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  

## <a name="create-a-receive-port"></a><span data-ttu-id="a1832-108">Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="a1832-108">Create a receive port</span></span>  
  
1.  <span data-ttu-id="a1832-109">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1832-109">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="a1832-110">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="a1832-110">Right-click **Receive Ports**, select **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="a1832-111">En el **propiedades de puerto de recepción** ventana, en el **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1832-111">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="a1832-112">En el **nombre** , escriba `ReceiveFromTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="a1832-112">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="a1832-113">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="a1832-113">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="a1832-114">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="a1832-114">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="a1832-115">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1832-115">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="a1832-116">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a1832-116">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="a1832-117">En el **ubicaciones de recepción** ventana, en el **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="a1832-117">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="a1832-118">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="a1832-118">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="a1832-119">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="a1832-119">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="a1832-120">En el **programación** página, seleccione el **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="a1832-120">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="a1832-121">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="a1832-121">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="a1832-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1832-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a1832-123">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar los documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a1832-123">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="a1832-124">En el **seguimiento** , seleccione el seguimiento de cuerpos de mensaje deseado y las propiedades de mensaje de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a1832-124">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="a1832-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1832-125">Click **OK**.</span></span>  

## <a name="set-the-receive-port-transport-properties"></a><span data-ttu-id="a1832-126">Establecer propiedades de transporte del puerto de la recepción</span><span class="sxs-lookup"><span data-stu-id="a1832-126">Set the receive port transport properties</span></span>
<span data-ttu-id="a1832-127">Ubicación de recepción para un sistema TIBCO Enterprise Message (EMS) la **URL** y **Target Namespace** al sistema TIBCO EMS son los únicos valores de configuración necesarios.</span><span class="sxs-lookup"><span data-stu-id="a1832-127">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>    
 
1.  <span data-ttu-id="a1832-128">Expanda el **definición del sistema** y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-128">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="a1832-129">Expanda **de mensajes** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="a1832-129">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="a1832-130">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a1832-130">Parameter</span></span>|<span data-ttu-id="a1832-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1832-131">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="a1832-132">**Selector de mensajes**</span><span class="sxs-lookup"><span data-stu-id="a1832-132">**Message Selector**</span></span>|<span data-ttu-id="a1832-133">Los mensajes únicamente se reciben si esta cadena se evalúa en True con el mensaje en el destino.</span><span class="sxs-lookup"><span data-stu-id="a1832-133">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="a1832-134">Permite que el puerto de recepción recupere únicamente los mensajes que contienen propiedades de encabezado que coincidan con la expresión descrita en este campo.</span><span class="sxs-lookup"><span data-stu-id="a1832-134">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="a1832-135">La sintaxis de los selectores de mensajes se basa en un subconjunto de la sintaxis de expresiones condicionales de SQL92.</span><span class="sxs-lookup"><span data-stu-id="a1832-135">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="a1832-136">La sintaxis se describe completamente en la guía del usuario de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-136">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="a1832-137">Por ejemplo, si un mensaje contiene un nombre de propiedad de encabezado NewsType, un puerto de recepción únicamente puede recuperar los elementos que sean de tipo Sports o Editorial.</span><span class="sxs-lookup"><span data-stu-id="a1832-137">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="a1832-138">**Número de reintentos**</span><span class="sxs-lookup"><span data-stu-id="a1832-138">**Retry Count**</span></span>|<span data-ttu-id="a1832-139">El número de reintentos para el transporte.</span><span class="sxs-lookup"><span data-stu-id="a1832-139">The retry count for the transport.</span></span> <span data-ttu-id="a1832-140">Valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="a1832-140">Default value is 0.</span></span>|  
    |<span data-ttu-id="a1832-141">**Intervalo de reintento**</span><span class="sxs-lookup"><span data-stu-id="a1832-141">**Retry Interval**</span></span>|<span data-ttu-id="a1832-142">El período de tiempo que el adaptador espera antes de iniciar un reintento.</span><span class="sxs-lookup"><span data-stu-id="a1832-142">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="a1832-143">El valor predeterminado es cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a1832-143">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="a1832-144">Expanda el **definición de conexión de servidor** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="a1832-144">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="a1832-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a1832-145">Parameter</span></span>|<span data-ttu-id="a1832-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1832-146">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="a1832-147">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a1832-147">**Destination**</span></span>|<span data-ttu-id="a1832-148">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="a1832-148">Mandatory setting.</span></span> <span data-ttu-id="a1832-149">Define el nombre y tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="a1832-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="a1832-150">Define la cola o tema con el formato siguiente: Queue[nombre.cola] o Topic[nombre.tema].</span><span class="sxs-lookup"><span data-stu-id="a1832-150">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="a1832-151">**Número de puerto**</span><span class="sxs-lookup"><span data-stu-id="a1832-151">**Port Number**</span></span>|<span data-ttu-id="a1832-152">Puerto en que escucha el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-152">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="a1832-153">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="a1832-153">**Server Name**</span></span>|<span data-ttu-id="a1832-154">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="a1832-154">Mandatory setting.</span></span> <span data-ttu-id="a1832-155">Nombre del sistema que hospeda el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-155">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="a1832-156">Proporcione credenciales mediante el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="a1832-156">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="a1832-157">Se pueden usar dos métodos para tener acceso al sistema TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-157">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="a1832-158">Puede usar las credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="a1832-158">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="a1832-159">Seleccione **Sí** en **usar SSO** utilizar inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="a1832-159">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="a1832-160">Seleccione una aplicación afiliada en la lista.</span><span class="sxs-lookup"><span data-stu-id="a1832-160">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="a1832-161">Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-161">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="a1832-162">El adaptador de Microsoft BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1832-162">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="a1832-163">Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.</span><span class="sxs-lookup"><span data-stu-id="a1832-163">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="a1832-164">Para obtener más información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="a1832-164">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="a1832-165">Expanda **las credenciales de usuario** y escriba el **nombre de usuario** y **contraseña** para acceder al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-165">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="a1832-166">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a1832-166">Parameter</span></span>|<span data-ttu-id="a1832-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1832-167">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="a1832-168">La contraseña del usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-168">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="a1832-169">Si no seleccionó **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-169">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="a1832-170">Nombre de un usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-170">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="a1832-171">Si no seleccionó **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a1832-171">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="a1832-172">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1832-172">Click **Apply**, and then click **OK**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a1832-173">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1832-173">Next steps</span></span>
[<span data-ttu-id="a1832-174">Propiedades de contexto del mensaje de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="a1832-174">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)