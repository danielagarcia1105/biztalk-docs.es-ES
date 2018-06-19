---
title: Crear TIBCO EMS recibe artefactos | Documentos de Microsoft
description: Crear el puerto de recepción y establecer las propiedades de transporte para usar el adaptador de TIBCO Enterprise Message Service en el servidor BizTalk Server
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
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015379"
---
# <a name="create-tibco-ems-receive-artifacts"></a><span data-ttu-id="db312-103">Crear TIBCO EMS artefactos de recepción</span><span class="sxs-lookup"><span data-stu-id="db312-103">Create TIBCO EMS receive artifacts</span></span>

## <a name="overview"></a><span data-ttu-id="db312-104">Información general</span><span class="sxs-lookup"><span data-stu-id="db312-104">Overview</span></span>
<span data-ttu-id="db312-105">El receptor TIBCO Enterprise Message Service es un servicio de escucha que registra una cola o tema particular y recibe los mensajes relacionados.</span><span class="sxs-lookup"><span data-stu-id="db312-105">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="db312-106">El adaptador de BizTalk para TIBCO Enterprise Message Service se registra primero con TIBCO Enterprise Message Service, mediante la apertura de una nueva sesión y, después, continúa realizando el sondeo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="db312-106">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="db312-107">En esta sección se explica cómo configurar el puerto de recepción para conectarse a TIBCO Enterprise Message Service y cómo incluir XML en la orquestación para interactuar con TIBCO EMS en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="db312-107">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  

## <a name="create-a-receive-port"></a><span data-ttu-id="db312-108">Crear un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="db312-108">Create a receive port</span></span>  
  
1.  <span data-ttu-id="db312-109">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db312-109">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="db312-110">Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.</span><span class="sxs-lookup"><span data-stu-id="db312-110">Right-click **Receive Ports**, select **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="db312-111">En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db312-111">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="db312-112">En el **nombre** , escriba `ReceiveFromTIBCOEMS`.</span><span class="sxs-lookup"><span data-stu-id="db312-112">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="db312-113">En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="db312-113">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="db312-114">Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="db312-114">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="db312-115">En el **ubicaciones de recepción** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db312-115">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="db312-116">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="db312-116">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="db312-117">En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="db312-117">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="db312-118">Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.</span><span class="sxs-lookup"><span data-stu-id="db312-118">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="db312-119">Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="db312-119">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="db312-120">En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.</span><span class="sxs-lookup"><span data-stu-id="db312-120">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="db312-121">Seleccione el **habilitar ventana de servicio** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="db312-121">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="db312-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db312-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="db312-123">En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="db312-123">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="db312-124">En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.</span><span class="sxs-lookup"><span data-stu-id="db312-124">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="db312-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db312-125">Click **OK**.</span></span>  

## <a name="set-the-receive-port-transport-properties"></a><span data-ttu-id="db312-126">Establecer propiedades de transporte del puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="db312-126">Set the receive port transport properties</span></span>
<span data-ttu-id="db312-127">Ubicación de recepción para un sistema TIBCO Enterprise Message (EMS) la **URL** y **Target Namespace** para el sistema TIBCO EMS son los únicos valores de configuración necesarios.</span><span class="sxs-lookup"><span data-stu-id="db312-127">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>    
 
1.  <span data-ttu-id="db312-128">Expanda el **definición del sistema** y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-128">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="db312-129">Expanda **control de mensajes** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="db312-129">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="db312-130">Parámetro</span><span class="sxs-lookup"><span data-stu-id="db312-130">Parameter</span></span>|<span data-ttu-id="db312-131">Description</span><span class="sxs-lookup"><span data-stu-id="db312-131">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="db312-132">**Selector de mensajes**</span><span class="sxs-lookup"><span data-stu-id="db312-132">**Message Selector**</span></span>|<span data-ttu-id="db312-133">Los mensajes únicamente se reciben si esta cadena se evalúa en True con el mensaje en el destino.</span><span class="sxs-lookup"><span data-stu-id="db312-133">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="db312-134">Permite que el puerto de recepción recupere únicamente los mensajes que contienen propiedades de encabezado que coincidan con la expresión descrita en este campo.</span><span class="sxs-lookup"><span data-stu-id="db312-134">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="db312-135">La sintaxis de los selectores de mensajes se basa en un subconjunto de la sintaxis de expresiones condicionales de SQL92.</span><span class="sxs-lookup"><span data-stu-id="db312-135">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="db312-136">La sintaxis se describe completamente en la guía del usuario de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-136">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="db312-137">Por ejemplo, si un mensaje contiene un nombre de propiedad de encabezado NewsType, un puerto de recepción únicamente puede recuperar los elementos que sean de tipo Sports o Editorial.</span><span class="sxs-lookup"><span data-stu-id="db312-137">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="db312-138">**Número de reintentos**</span><span class="sxs-lookup"><span data-stu-id="db312-138">**Retry Count**</span></span>|<span data-ttu-id="db312-139">El número de reintentos para el transporte.</span><span class="sxs-lookup"><span data-stu-id="db312-139">The retry count for the transport.</span></span> <span data-ttu-id="db312-140">Valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="db312-140">Default value is 0.</span></span>|  
    |<span data-ttu-id="db312-141">**Intervalo de reintento**</span><span class="sxs-lookup"><span data-stu-id="db312-141">**Retry Interval**</span></span>|<span data-ttu-id="db312-142">El período de tiempo que el adaptador espera antes de iniciar un reintento.</span><span class="sxs-lookup"><span data-stu-id="db312-142">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="db312-143">El valor predeterminado es cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="db312-143">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="db312-144">Expanda el **definición de conexión de servidor** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="db312-144">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="db312-145">Parámetro</span><span class="sxs-lookup"><span data-stu-id="db312-145">Parameter</span></span>|<span data-ttu-id="db312-146">Description</span><span class="sxs-lookup"><span data-stu-id="db312-146">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="db312-147">**Destino**</span><span class="sxs-lookup"><span data-stu-id="db312-147">**Destination**</span></span>|<span data-ttu-id="db312-148">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="db312-148">Mandatory setting.</span></span> <span data-ttu-id="db312-149">Define el nombre y tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="db312-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="db312-150">Define la cola o tema con el formato siguiente: Queue[queue.name] o Topic[topic.name].</span><span class="sxs-lookup"><span data-stu-id="db312-150">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="db312-151">**Número de puerto**</span><span class="sxs-lookup"><span data-stu-id="db312-151">**Port Number**</span></span>|<span data-ttu-id="db312-152">Puerto en que escucha el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-152">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="db312-153">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="db312-153">**Server Name**</span></span>|<span data-ttu-id="db312-154">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="db312-154">Mandatory setting.</span></span> <span data-ttu-id="db312-155">Nombre del sistema que hospeda el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-155">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="db312-156">Proporcione credenciales mediante el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="db312-156">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="db312-157">Se pueden usar dos métodos para tener acceso al sistema TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-157">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="db312-158">Puede usar las credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="db312-158">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="db312-159">Seleccione **Sí** en **usar SSO** usar Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="db312-159">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="db312-160">Seleccione una aplicación afiliada en la lista.</span><span class="sxs-lookup"><span data-stu-id="db312-160">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="db312-161">Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-161">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="db312-162">El adaptador de Microsoft BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db312-162">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="db312-163">Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.</span><span class="sxs-lookup"><span data-stu-id="db312-163">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="db312-164">Para obtener más información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="db312-164">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="db312-165">Expanda **las credenciales de usuario** y escriba la **nombre de usuario** y **contraseña** para tener acceso al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-165">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="db312-166">Parámetro</span><span class="sxs-lookup"><span data-stu-id="db312-166">Parameter</span></span>|<span data-ttu-id="db312-167">Description</span><span class="sxs-lookup"><span data-stu-id="db312-167">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="db312-168">La contraseña del usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-168">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="db312-169">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-169">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="db312-170">Nombre de un usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-170">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="db312-171">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="db312-171">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="db312-172">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db312-172">Click **Apply**, and then click **OK**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="db312-173">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="db312-173">Next steps</span></span>
[<span data-ttu-id="db312-174">Propiedades de contexto del mensaje de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="db312-174">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)