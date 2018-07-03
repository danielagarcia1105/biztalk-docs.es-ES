---
title: 'Tutorial: Integración de BizTalk Server 2013 con Salesforce | Microsoft Docs'
description: Usar Service Bus y BIzTalk Server para integrar con Salesforce
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aecf9bcd1ef29a1324dc1b040388f17a19a71c52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011733"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a><span data-ttu-id="3839f-103">Tutorial: Integración de BizTalk Server 2013 con Salesforce</span><span class="sxs-lookup"><span data-stu-id="3839f-103">Tutorial: Integrating BizTalk Server 2013 with Salesforce</span></span>
<span data-ttu-id="3839f-104">Revisores: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef Ene Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span><span class="sxs-lookup"><span data-stu-id="3839f-104">Reviewers: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef-Jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3839f-105"> introduce a algunos adaptadores nuevos que hacen que una gran cantidad de escenarios híbridos, que implica un entorno local y las tecnologías de Azure ahora es posibles.</span><span class="sxs-lookup"><span data-stu-id="3839f-105"> introduces some new adapters that make a lot of hybrid scenarios, involving on-premises and Azure technologies now possible.</span></span> <span data-ttu-id="3839f-106">En este tutorial, veremos cómo integrar una entidad puramente de nube como Salesforce con un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] local usando algunos de los nuevos adaptadores y [!INCLUDE[winazure](../includes/winazure-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3839f-106">In this tutorial, we see how to integrate a purely cloud entity like Salesforce integrate with an on-premises [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using some of the new adapters and [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="3839f-107">Antes de comenzar, debemos tener claro el objetivo comercial que intentamos alcanzar con la integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con Salesforce.</span><span class="sxs-lookup"><span data-stu-id="3839f-107">Before we start, let’s understand the business objective we try to achieve by integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce.</span></span>  
  
 <span data-ttu-id="3839f-108">También podríamos crear soluciones híbridas que impliquen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y Salesforce con una versión anterior de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; sin embargo, la solución sería mucho más compleja si implica la interacción con Salesforce mediante un servicio Web (SOAP).</span><span class="sxs-lookup"><span data-stu-id="3839f-108">We could also create hybrid solutions involving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce with previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], however the solution would be much more complex involving interaction with Salesforce by consuming a Web service (SOAP).</span></span> <span data-ttu-id="3839f-109">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los nuevos adaptadores, la solución es muy sencilla.</span><span class="sxs-lookup"><span data-stu-id="3839f-109">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the new adapters, the solution is that much easier.</span></span>  
  
## <a name="business-scenario"></a><span data-ttu-id="3839f-110">Escenario de negocio</span><span class="sxs-lookup"><span data-stu-id="3839f-110">Business Scenario</span></span>  
 <span data-ttu-id="3839f-111">Northwind usa el sistema de CRM en línea de Salesforce como solución para mantener un seguimiento de clientes a través de la canalización de ventas.</span><span class="sxs-lookup"><span data-stu-id="3839f-111">Northwind uses the Salesforce online CRM system as their solution for tracking customers through the sales pipeline.</span></span> <span data-ttu-id="3839f-112">Cada vez que se crea una oportunidad de venta en el sistema Salesforce, Northwind quiere que se notifique a sus sistemas locales, como [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para que otros sistemas que siguen en la cadena puedan recopilar datos e iniciar otros procesos relevantes.</span><span class="sxs-lookup"><span data-stu-id="3839f-112">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to be notified so that other down-stream systems can pick up that data and start other relevant processes.</span></span> <span data-ttu-id="3839f-113">Northwind planea implementar esta solución usando los nuevos adaptadores disponibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e incluyendo algunos componentes de [!INCLUDE[winazure](../includes/winazure-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3839f-113">Northwind plans to implement this solution using the new adapters available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and also by including some components of [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="3839f-114">El flujo de datos de un extremo a otro para la solución tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="3839f-114">This is how the end-to-end data flow looks like for the solution:</span></span>  
  
- <span data-ttu-id="3839f-115">Un representante de ventas crea una “oportunidad” en el sistema Salesforce.</span><span class="sxs-lookup"><span data-stu-id="3839f-115">A sales representative creates an “opportunity” in the Salesforce system.</span></span>  
  
- <span data-ttu-id="3839f-116">Cuando el estado de la oportunidad se establece en “Closed Won”, se envía una notificación a un extremo de transmisión hospedado en [!INCLUDE[winazure](../includes/winazure-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3839f-116">When the status of the opportunity is set to “Closed Won”, a notification is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span>  
  
- <span data-ttu-id="3839f-117">Usando el nuevo adaptador WCF-BasicHttpRelay, se pasa la información de notificación al sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] local.</span><span class="sxs-lookup"><span data-stu-id="3839f-117">Using the new WCF-BasicHttpRelay adapter, the notification information is passed on to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system housed on-premise.</span></span>  
  
- <span data-ttu-id="3839f-118">Con la información recibida con la notificación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invoca un extremo REST en Salesforce, usando el nuevo adaptador WCF-WebHttp, para obtener más información acerca de la oportunidad.</span><span class="sxs-lookup"><span data-stu-id="3839f-118">Using the information received as part of the notification, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invokes a REST endpoint in Salesforce, using the new WCF-WebHttp adapter, to get more information about the opportunity.</span></span>  
  
- <span data-ttu-id="3839f-119">Finalmente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la información recibida de Salesforce para crear una entrada de pedido de compra en una tabla de base de datos de SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="3839f-119">Finally, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the information received from Salesforce to create a purchase order entry in an in-house SQL Server database table.</span></span>  
  
  <span data-ttu-id="3839f-120">Estos son los pasos que debe llevar a cabo para alcanzar el objetivo de integración que se explica en esta solución.</span><span class="sxs-lookup"><span data-stu-id="3839f-120">These are the set of steps that you must perform to achieve the integration objective outlined in this solution.</span></span> <span data-ttu-id="3839f-121">Cada uno de estos pasos implica una serie de actividades que iremos viendo conforme avancemos en la creación de la solución.</span><span class="sxs-lookup"><span data-stu-id="3839f-121">Each of these steps involves broad set of activities that we’ll look at as we proceed with creating the solution.</span></span>  
  
  <span data-ttu-id="3839f-122">La siguiente ilustración muestra la solución de integración de un extremo a otro:</span><span class="sxs-lookup"><span data-stu-id="3839f-122">Here’s an illustration that describes the end-to-end integration solution:</span></span>  
  
  <span data-ttu-id="3839f-123">![Escenario de integración de BizTalk Server y Salesforce](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span><span class="sxs-lookup"><span data-stu-id="3839f-123">![BizTalk Server and Salesforce integration scenario](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3839f-124">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3839f-124">Prerequisites</span></span>  
 <span data-ttu-id="3839f-125">El siguiente software debe estar instalado en el equipo donde configure esta solución:</span><span class="sxs-lookup"><span data-stu-id="3839f-125">You must have the following software installed on the computer where you set up this solution:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  <span data-ttu-id="3839f-126">Debe disponer de las siguientes suscripciones a servicios:</span><span class="sxs-lookup"><span data-stu-id="3839f-126">You must have the following service subscriptions:</span></span>  
  
- <span data-ttu-id="3839f-127">Una suscripción a [!INCLUDE[winazure](../includes/winazure-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3839f-127">A [!INCLUDE[winazure](../includes/winazure-md.md)] subscription</span></span>  
  
- <span data-ttu-id="3839f-128">Cuenta de Salesforce Developer Edition</span><span class="sxs-lookup"><span data-stu-id="3839f-128">Salesforce Developer Edition account</span></span>  
  
## <a name="more-resources"></a><span data-ttu-id="3839f-129">Más recursos</span><span class="sxs-lookup"><span data-stu-id="3839f-129">More Resources</span></span>  
 <span data-ttu-id="3839f-130">Además de este tutorial, también puede buscar en los siguientes recursos para obtener más información sobre la integración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con Salesforce usando los nuevos adaptadores introducidos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3839f-130">In addition to this tutorial, you can also look at the following resources to understand more about integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce using the new adapters introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="3839f-131">Un laboratorio virtual que muestra [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y está disponible en la integración de Salesforce [ http://go.microsoft.com/fwlink/?LinkId=290930 ](http://go.microsoft.com/fwlink/?LinkId=290930).</span><span class="sxs-lookup"><span data-stu-id="3839f-131">A virtual lab demonstrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce integration is available at [http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930).</span></span>  
  
- <span data-ttu-id="3839f-132">Un ejemplo basado en este tutorial está disponible para su descarga en [ http://go.microsoft.com/fwlink/?LinkId=290932 ](http://go.microsoft.com/fwlink/?LinkId=290932).</span><span class="sxs-lookup"><span data-stu-id="3839f-132">A sample based on this tutorial is available for download at [http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3839f-133">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3839f-133">Next steps</span></span>
  
-   [<span data-ttu-id="3839f-134">Paso 1: Crear un espacio de nombres de Service Bus</span><span class="sxs-lookup"><span data-stu-id="3839f-134">Step 1: Create a Service Bus Namespace</span></span>](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [<span data-ttu-id="3839f-135">Paso 2: Configurar el sistema de Salesforce</span><span class="sxs-lookup"><span data-stu-id="3839f-135">Step 2: Set up the Salesforce System</span></span>](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [<span data-ttu-id="3839f-136">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3839f-136">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [<span data-ttu-id="3839f-137">Paso 4: Configurar la solución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3839f-137">Step 4: Configure the BizTalk Server Solution</span></span>](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [<span data-ttu-id="3839f-138">Paso 5: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="3839f-138">Step 5: Test the Solution</span></span>](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="3839f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="3839f-139">See Also</span></span>  
 [<span data-ttu-id="3839f-140">Tutoriales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3839f-140">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)