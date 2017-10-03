---
title: "Establecer propiedades de transporte TIBCO Enterprise Message Service para el puerto de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, setting transport properties
- transport properties, setting for receive port
- setting transport properties, receive port
ms.assetid: bccddf84-d92e-469f-aa6f-4234c91a0be9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94229364e3bed8faaf1407603f17db76c70e6bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a><span data-ttu-id="d7ef0-102">Establecimiento de propiedades de transporte de TIBCO Enterprise Message Service para el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="d7ef0-102">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>
<span data-ttu-id="d7ef0-103">Ubicación de recepción para un sistema TIBCO Enterprise Message (EMS) la **URL** y **Target Namespace** para el sistema TIBCO EMS son los únicos valores de configuración necesarios.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-103">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>  
  
### <a name="to-specify-tibco-ems-transport-properties"></a><span data-ttu-id="d7ef0-104">Para especificar propiedades de transporte de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="d7ef0-104">To specify TIBCO EMS transport properties</span></span>  
  
1.  <span data-ttu-id="d7ef0-105">Expanda el **definición del sistema** y escriba toda la información necesaria para la conexión al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-105">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="d7ef0-106">Expanda **control de mensajes** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-106">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d7ef0-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d7ef0-107">Parameter</span></span>|<span data-ttu-id="d7ef0-108">Description</span><span class="sxs-lookup"><span data-stu-id="d7ef0-108">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d7ef0-109">**Selector de mensajes**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-109">**Message Selector**</span></span>|<span data-ttu-id="d7ef0-110">Los mensajes únicamente se reciben si esta cadena se evalúa en True con el mensaje en el destino.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-110">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="d7ef0-111">Permite que el puerto de recepción recupere únicamente los mensajes que contienen propiedades de encabezado que coincidan con la expresión descrita en este campo.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-111">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="d7ef0-112">La sintaxis de los selectores de mensajes se basa en un subconjunto de la sintaxis de expresiones condicionales de SQL92.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-112">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="d7ef0-113">La sintaxis se describe completamente en la guía del usuario de TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-113">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="d7ef0-114">Por ejemplo, si un mensaje contiene un nombre de propiedad de encabezado NewsType, un puerto de recepción únicamente puede recuperar los elementos que sean de tipo Sports o Editorial.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-114">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="d7ef0-115">**Número de reintentos**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-115">**Retry Count**</span></span>|<span data-ttu-id="d7ef0-116">El número de reintentos para el transporte.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-116">The retry count for the transport.</span></span> <span data-ttu-id="d7ef0-117">Valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-117">Default value is 0.</span></span>|  
    |<span data-ttu-id="d7ef0-118">**Intervalo de reintento**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-118">**Retry Interval**</span></span>|<span data-ttu-id="d7ef0-119">El período de tiempo que el adaptador espera antes de iniciar un reintento.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-119">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="d7ef0-120">El valor predeterminado es cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-120">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="d7ef0-121">Expanda el **definición de conexión de servidor** y escriba toda la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-121">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="d7ef0-122">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d7ef0-122">Parameter</span></span>|<span data-ttu-id="d7ef0-123">Description</span><span class="sxs-lookup"><span data-stu-id="d7ef0-123">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="d7ef0-124">**Destino**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-124">**Destination**</span></span>|<span data-ttu-id="d7ef0-125">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-125">Mandatory setting.</span></span> <span data-ttu-id="d7ef0-126">Define el nombre y tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-126">Defines the name and type of the destination.</span></span> <span data-ttu-id="d7ef0-127">Define la cola o tema con el formato siguiente: Queue[queue.name] o Topic[topic.name].</span><span class="sxs-lookup"><span data-stu-id="d7ef0-127">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="d7ef0-128">**Número de puerto**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-128">**Port Number**</span></span>|<span data-ttu-id="d7ef0-129">Puerto en que escucha el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-129">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="d7ef0-130">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="d7ef0-130">**Server Name**</span></span>|<span data-ttu-id="d7ef0-131">Configuración obligatoria.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-131">Mandatory setting.</span></span> <span data-ttu-id="d7ef0-132">Nombre del sistema que hospeda el servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-132">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="d7ef0-133">Proporcione credenciales mediante el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="d7ef0-133">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="d7ef0-134">Se pueden usar dos métodos para tener acceso al sistema TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-134">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="d7ef0-135">Puede usar las credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-135">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d7ef0-136">Seleccione **Sí** en **usar SSO** usar Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-136">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="d7ef0-137">Seleccione una aplicación afiliada en la lista.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-137">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="d7ef0-138">Una aplicación afiliada, creada por herramientas de inicio de sesión único empresarial, representa una aplicación como TBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-138">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="d7ef0-139">El adaptador de Microsoft BizTalk para TIBCO EMS usa las credenciales de un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-139">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="d7ef0-140">Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-140">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="d7ef0-141">Para obtener más información acerca de cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications5.md).</span><span class="sxs-lookup"><span data-stu-id="d7ef0-141">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="d7ef0-142">Expanda **las credenciales de usuario** y escriba la **nombre de usuario** y **contraseña** para tener acceso al servidor TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-142">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="d7ef0-143">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d7ef0-143">Parameter</span></span>|<span data-ttu-id="d7ef0-144">Description</span><span class="sxs-lookup"><span data-stu-id="d7ef0-144">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="d7ef0-145">La contraseña del usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-145">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d7ef0-146">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-146">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="d7ef0-147">Nombre de un usuario que se usa para comunicar con un demonio TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-147">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="d7ef0-148">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para TIBCO EMS pueda comunicarse con un daemon TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-148">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="d7ef0-149">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-149">Click **Apply**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ef0-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7ef0-150">See Also</span></span>  
 <span data-ttu-id="d7ef0-151">[Creación de puertos de envío](../core/creating-send-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="d7ef0-151">[Creating Send Ports](../core/creating-send-ports1.md) </span></span>  
 [<span data-ttu-id="d7ef0-152">Creación de TIBCO Enterprise Message Service controladores de recepción</span><span class="sxs-lookup"><span data-stu-id="d7ef0-152">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)