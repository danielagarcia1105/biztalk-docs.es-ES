---
title: Tutoriales de BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-tutorials"></a><span data-ttu-id="fa698-102">Tutoriales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa698-102">BizTalk Server Tutorials</span></span>
<span data-ttu-id="fa698-103">Tutoriales para aprender a usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa698-103">Tutorials to learn how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>

<span data-ttu-id="fa698-104">Los tutoriales de BizTalk Server contienen escenarios sencillos para que los usuarios nuevos adquieran cierta experiencia en el empleo de una variedad de herramientas de BizTalk, a la vez que crean soluciones de integración compiladas que pueden someterse a prueba.</span><span class="sxs-lookup"><span data-stu-id="fa698-104">The BizTalk Server tutorials contain simple scenarios to give new users an experience of using a variety of BizTalk tools while creating compiled, testable integration solutions.</span></span> <span data-ttu-id="fa698-105">Para los usuarios más avanzados, o los usuarios que diseñan soluciones de BizTalk, consulte [escenarios para soluciones empresariales](../core/scenarios-for-business-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="fa698-105">For more advanced users, or users who are designing BizTalk solutions, see [Scenarios for Business Solutions](../core/scenarios-for-business-solutions.md).</span></span>  
  
## <a name="enterprise-application-integration"></a><span data-ttu-id="fa698-106">Enterprise Application Integration</span><span class="sxs-lookup"><span data-stu-id="fa698-106">Enterprise Application Integration</span></span>
  
[<span data-ttu-id="fa698-107">Tutorial: Integración de aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="fa698-107">Tutorial: Enterprise Application Integration</span></span>](../core/tutorial-1-enterprise-application-integration.md) 

<span data-ttu-id="fa698-108">Implementar una solución de BizTalk que reciba mensajes de solicitud de reposición de inventario de un almacén y evalúe los mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="fa698-108">Implement a BizTalk solution that receives inventory replenishment request messages from a warehouse, and evaluates the request messages.</span></span> <span data-ttu-id="fa698-109">Si la solución rechaza una solicitud, envía un mensaje de rechazo al almacén.</span><span class="sxs-lookup"><span data-stu-id="fa698-109">If the solution denies a request, then it sends a decline message to the warehouse.</span></span> <span data-ttu-id="fa698-110">Si la solución aprueba una solicitud, a continuación, reenvía el mensaje a un sistema de planeamiento de recursos empresariales (ERP).</span><span class="sxs-lookup"><span data-stu-id="fa698-110">If the solution approves a request, then it forwards the message to an Enterprise Resource Planning (ERP) system.</span></span>  

## <a name="create-a-hybrid-application"></a><span data-ttu-id="fa698-111">Crear una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="fa698-111">Create a Hybrid Application</span></span>
[<span data-ttu-id="fa698-112">Tutorial: Crear una aplicación híbrida mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa698-112">Tutorial: Creating a Hybrid Application Using BizTalk Server</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

<span data-ttu-id="fa698-113">Configurar una aplicación de extremo a extremo que usa EDI para generar confirmaciones, Bus de servicio para recibir mensajes, y, a continuación, insertar datos en SQL.</span><span class="sxs-lookup"><span data-stu-id="fa698-113">Set up an end-to-end application that uses EDI to generate acknowledgements, Service Bus to receive messages, and then insert data into SQL.</span></span> 

## <a name="invoke-a-rest-interface"></a><span data-ttu-id="fa698-114">Invocar una interfaz REST</span><span class="sxs-lookup"><span data-stu-id="fa698-114">Invoke a REST Interface</span></span>
[<span data-ttu-id="fa698-115">Tutorial: Invocar una interfaz REST con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa698-115">Tutorial: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

<span data-ttu-id="fa698-116">Usa el adaptador de WCF-WebHttp para utilizar una dirección URL de REST y, a continuación, enviar un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fa698-116">Uses the WCF-WebHttp adapter to use a REST URL, and then send a response message.</span></span> 

## <a name="integrate-biztalk-with-salesforce"></a><span data-ttu-id="fa698-117">Integrar BizTalk con Salesforce</span><span class="sxs-lookup"><span data-stu-id="fa698-117">Integrate BizTalk with Salesforce</span></span>
[<span data-ttu-id="fa698-118">Tutorial: Integrar el servidor BizTalk Server con Salesforce</span><span class="sxs-lookup"><span data-stu-id="fa698-118">Tutorial: Integrating BizTalk Server with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

<span data-ttu-id="fa698-119">Cada vez que se crea una oportunidad de venta en el sistema Salesforce, Northwind quiere que sus sistemas locales, por ejemplo, BizTalk Server, para recibir una notificación para que otros sistemas de nivel inferiores pueden recopilar datos e iniciar otros procesos relevantes.</span><span class="sxs-lookup"><span data-stu-id="fa698-119">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as BizTalk Server, to be notified so that other downstream systems can pick up that data and start other relevant processes.</span></span> 

## <a name="process-json-messages"></a><span data-ttu-id="fa698-120">Procesar mensajes JSON</span><span class="sxs-lookup"><span data-stu-id="fa698-120">Process JSON messages</span></span>
[<span data-ttu-id="fa698-121">Procesamiento de mensajes JSON con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa698-121">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)  

<span data-ttu-id="fa698-122">Configurar una aplicación de BizTalk que recibe un pedido de compra JSON.</span><span class="sxs-lookup"><span data-stu-id="fa698-122">Set up a BizTalk application that receives a JSON purchase order.</span></span> <span data-ttu-id="fa698-123">En la canalización de recepción, un componente de descodificador JSON transforma el mensaje JSON para XML.</span><span class="sxs-lookup"><span data-stu-id="fa698-123">In the receive pipeline, a JSON decoder component transforms the JSON message to XML message.</span></span> <span data-ttu-id="fa698-124">A continuación, utiliza una asignación para transformar el pedido de compra XML en una factura XML.</span><span class="sxs-lookup"><span data-stu-id="fa698-124">Then, uses a map to transform the XML purchase order into an XML invoice.</span></span> <span data-ttu-id="fa698-125">La canalización de envío utiliza un codificador JSON para transformar la factura XML en una factura JSON y, a continuación, envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa698-125">The send pipeline uses a JSON encoder to transform the XML invoice into a JSON invoice, and then sends the message.</span></span>

## <a name="edi-interface-developer"></a><span data-ttu-id="fa698-126">Programadores de la interfaz EDI</span><span class="sxs-lookup"><span data-stu-id="fa698-126">EDI Interface Developer</span></span>
  [<span data-ttu-id="fa698-127">Tutorial: EDI Interface Developer Tutorial</span><span class="sxs-lookup"><span data-stu-id="fa698-127">Tutorial: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
<span data-ttu-id="fa698-128">Un socio comercial envía pedidos de compra con ANSI X12 4010 (un mensaje 850) del conjunto de transacciones 850.</span><span class="sxs-lookup"><span data-stu-id="fa698-128">A trading partner sends purchase orders using the ANSI X12 4010 850 transaction set (an 850 message).</span></span> <span data-ttu-id="fa698-129">Pedidos de compra de un proceso de sistema de orden interno.</span><span class="sxs-lookup"><span data-stu-id="fa698-129">An internal order system processes purchase orders.</span></span>

<span data-ttu-id="fa698-130">Como desarrollador Interfaz responsable de diseñar la interfaz entre el mensaje 850, recibe de su socio comercial y sistema de pedidos interno de su empresa.</span><span class="sxs-lookup"><span data-stu-id="fa698-130">As an interface developer responsible for designing the interface between the 850 message, you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="fa698-131">Su socio comercial requiere una confirmación funcional (997) para cada mensaje 850 que envía.</span><span class="sxs-lookup"><span data-stu-id="fa698-131">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>


## <a name="as2"></a><span data-ttu-id="fa698-132">ENVÍO/RECEPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fa698-132">AS2</span></span>  
[<span data-ttu-id="fa698-133">Tutorial: Tutorial de AS2</span><span class="sxs-lookup"><span data-stu-id="fa698-133">Tutorial: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)

<span data-ttu-id="fa698-134">Configurar una solución que reciba y envíe mensajes con codificación EDIINT/AS2 a través de un transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa698-134">Set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>    


## <a name="do-more"></a><span data-ttu-id="fa698-135">Llevar a cabo más</span><span class="sxs-lookup"><span data-stu-id="fa698-135">Do more</span></span>  
 <span data-ttu-id="fa698-136">Para obtener más información sobre arquitectura y conceptos de BizTalk Server, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa698-136">To learn more about BizTalk Server concepts and architecture, consider the following:</span></span>  
  
[<span data-ttu-id="fa698-137">Introducción</span><span class="sxs-lookup"><span data-stu-id="fa698-137">Get started</span></span>](../core/getting-started-with-biztalk-server.md)
  
[<span data-ttu-id="fa698-138">Planear y diseñar la solución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fa698-138">Plan and architect your BizTalk Server solution</span></span>](../core/plan-and-architect-your-biztalk-server-solution.md)