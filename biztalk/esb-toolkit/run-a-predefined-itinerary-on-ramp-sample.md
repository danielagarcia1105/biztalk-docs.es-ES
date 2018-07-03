---
title: Ejecutar un ejemplo de rampa de itinerario predefinido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e428a9106582e5bad3408cfb6643cc5da21ac74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996589"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a><span data-ttu-id="ac08e-102">Ejecutar un ejemplo de rampa de itinerario predefinido</span><span class="sxs-lookup"><span data-stu-id="ac08e-102">Run a Predefined Itinerary On-Ramp Sample</span></span>
<span data-ttu-id="ac08e-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye 20 casos de uso de itinerario predefinidos que puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ac08e-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes 20 predefined Itinerary use cases you can execute.</span></span> <span data-ttu-id="ac08e-104">Para obtener una lista de estos casos de uso, vea [los escenarios de itinerarios de ejemplo](../esb-toolkit/the-sample-itinerary-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="ac08e-104">For a list of these use cases, see [The Sample Itinerary Scenarios](../esb-toolkit/the-sample-itinerary-scenarios.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac08e-105">Antes de ejecutar cualquiera de los ejemplos, debe importar manualmente el archivo de enlace de itinerarios adecuado desde la carpeta \Source\Samples\Itinerary\Install\Binding en la aplicación de GlobalBank.ESB BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ac08e-105">Before you run any of the samples, you must manually import the appropriate itinerary binding file from the \Source\Samples\Itinerary\Install\Binding folder into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="ac08e-106">Este archivo de enlace restablece las propiedades en los dos puertos de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="ac08e-106">This binding file resets the properties on the two dynamic send ports.</span></span> <span data-ttu-id="ac08e-107">Importe el archivo de enlace denominado GlobalBank.ESB.Itinerary_Bindings.xml.</span><span class="sxs-lookup"><span data-stu-id="ac08e-107">Import the binding file named GlobalBank.ESB.Itinerary_Bindings.xml.</span></span>  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a><span data-ttu-id="ac08e-108">Para ejecutar uno de los ejemplos de rampa de itinerario predefinido</span><span class="sxs-lookup"><span data-stu-id="ac08e-108">To run one of the pre-defined Itinerary On-Ramp samples</span></span>  
  
1. <span data-ttu-id="ac08e-109">Si aún no se está ejecutando la aplicación GlobalBank.ESB, utilice la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="ac08e-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="ac08e-110">En el Explorador de Windows, abra el \Source\Samples\Itinerary\Source\ESB subcarpeta. Itinerary.Test\bin\Debug donde instaló los ejemplos del Kit de herramientas de ESB de BizTalk y, a continuación, inicie la aplicación denominada Esb.Itinerary.Test.exe.</span><span class="sxs-lookup"><span data-stu-id="ac08e-110">In Windows Explorer, open the subfolder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug where you installed the BizTalk ESB Toolkit samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="ac08e-111">Haga clic en el **LoadItinerary** y, a continuación, seleccione el itinerario de ejemplo denominado TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml desde la carpeta \Source\Samples\Itinerary\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="ac08e-111">Click the **LoadItinerary** button, and then select the sample itinerary named TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml from the \Source\Samples\Itinerary\Itineraries folder.</span></span>  
  
4. <span data-ttu-id="ac08e-112">En el **opciones del servicio Web** sección, seleccione el **servicio bidireccional** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="ac08e-112">In the **Web Service Options** section, select the **Two-Way Service** check box.</span></span> <span data-ttu-id="ac08e-113">Esto indica al cliente de prueba para realizar una operación de servicio de itinerarios de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac08e-113">This instructs the test client to perform a request-response itinerary service operation.</span></span>  
  
5. <span data-ttu-id="ac08e-114">(Opcional) Seleccione el **usar servicio de WCF** casilla de verificación si desea que la aplicación para usar el OnRamp.Itinerary.Response.WCF la ubicación de recepción en lugar del predeterminado OnRamp.Itinerary.Response.SOAP ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="ac08e-114">(Optional) Select the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6. <span data-ttu-id="ac08e-115">Haga clic en el **LoadMessage** botón y, a continuación, seleccione el mensaje de ejemplo NAOrderDoc.xml desde la carpeta \Source\Samples\Itinerary\Test\Data.</span><span class="sxs-lookup"><span data-stu-id="ac08e-115">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="ac08e-116">Haga clic en el **SubmitRequest** botón para enviar la solicitud al servicio de rampa de itinerario.</span><span class="sxs-lookup"><span data-stu-id="ac08e-116">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="ac08e-117">Figura 1 muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="ac08e-117">Figure 1 shows the result.</span></span>  
  
   <span data-ttu-id="ac08e-118">![Itinerario en rampa](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span><span class="sxs-lookup"><span data-stu-id="ac08e-118">![Itinerary On Ramp](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")</span></span>  
  
   <span data-ttu-id="ac08e-119">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="ac08e-119">**Figure 1**</span></span>  
  
   <span data-ttu-id="ac08e-120">**La aplicación de cliente de itinerario en rampa ejecutando uno de los ejemplos de itinerario en rampa**</span><span class="sxs-lookup"><span data-stu-id="ac08e-120">**The Itinerary On-Ramp client application running one of the Itinerary On-Ramp samples**</span></span>  
  
   <span data-ttu-id="ac08e-121">El nombre del servicio especificado en la definición de itinerarios corresponde directamente a la **ServiceName** propiedad del servicio al que se suscribe el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac08e-121">The name of the service specified in the itinerary definition corresponds directly to the **ServiceName** property of the service to which the sample subscribes.</span></span> <span data-ttu-id="ac08e-122">En el ejemplo de itinerario ejecutado en el procedimiento anterior (TwoWay OrchTransform-OrchRoutingGroup OrchTwoWayCustom.xml), el primer servicio que se ejecuta es un servicio basado en la orquestación que realiza una transformación.</span><span class="sxs-lookup"><span data-stu-id="ac08e-122">In the itinerary sample executed in the previous procedure (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml), the first service executed is an orchestration-based service that performs a transformation.</span></span> <span data-ttu-id="ac08e-123">La siguiente sección del itinerario especifica este servicio.</span><span class="sxs-lookup"><span data-stu-id="ac08e-123">The following section of the itinerary specifies this service.</span></span>  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 <span data-ttu-id="ac08e-124">El servicio de orquestación en este **\<servicio\>** elemento especifica la orquestación de enlace directo que tiene las propiedades de filtro se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="ac08e-124">The orchestration service in this **\<Service\>** element specifies the direct-bound orchestration that has the filter properties shown in Figure 2.</span></span> <span data-ttu-id="ac08e-125">Tenga en cuenta que la orquestación se suscribe solo a los mensajes que tienen el valor **Microsoft.Practices.ESB.Services.Transform** para el **ServiceName** propiedad de contexto, el valor  **Pendiente** para el **ServiceState** propiedad de contexto y el valor de la orquestación para la **ServiceType** propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="ac08e-125">Notice that the orchestration subscribes only to messages that have the value **Microsoft.Practices.ESB.Services.Transform** for the **ServiceName** context property, the value **Pending** for the **ServiceState** context property, and the value Orchestration for the **ServiceType** context property.</span></span>  
  
 <span data-ttu-id="ac08e-126">![Expresión de filtro](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span><span class="sxs-lookup"><span data-stu-id="ac08e-126">![Filter Expression](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")</span></span>  
  
 <span data-ttu-id="ac08e-127">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="ac08e-127">**Figure 2**</span></span>  
  
 <span data-ttu-id="ac08e-128">**La expresión de filtro para la orquestación de enlace directo usada en el ejemplo de rampa de itinerario**</span><span class="sxs-lookup"><span data-stu-id="ac08e-128">**The filter expression for the direct-bound orchestration used in the Itinerary On-Ramp sample**</span></span>