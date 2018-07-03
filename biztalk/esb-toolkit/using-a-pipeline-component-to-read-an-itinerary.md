---
title: Uso de un componente de canalización para leer un itinerario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e3b40c7-0f17-4d33-a26f-f51346a98be5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03e4e48b125d7a8236c66ce36e458dd2d51a6f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991133"
---
# <a name="using-a-pipeline-component-to-read-an-itinerary"></a><span data-ttu-id="39a0f-102">Uso de un componente de canalización para leer un itinerario</span><span class="sxs-lookup"><span data-stu-id="39a0f-102">Using a Pipeline Component to Read an Itinerary</span></span>
<span data-ttu-id="39a0f-103">Un mensaje que llega en una canalización de recepción puede contener metadatos en el encabezado SOAP que define sus requisitos de procesamiento (itinerario del lado cliente).</span><span class="sxs-lookup"><span data-stu-id="39a0f-103">A message that arrives in a receive pipeline can contain metadata in its SOAP header that defines its processing requirements (client-side itinerary).</span></span> <span data-ttu-id="39a0f-104">Figura 1 ilustra el uso de los componentes de canalización de distribuidor de ESB e itinerarios de ESB.</span><span class="sxs-lookup"><span data-stu-id="39a0f-104">Figure 1 illustrates the use of the ESB Itinerary and ESB Dispatcher pipeline components.</span></span>  

 <span data-ttu-id="39a0f-105">![Lectura del componente de canalización](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span><span class="sxs-lookup"><span data-stu-id="39a0f-105">![Pipeline Component Read](../esb-toolkit/media/ch4-pipelinecomponentread.gif "Ch4-PipelineComponentRead")</span></span>  

 <span data-ttu-id="39a0f-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="39a0f-106">**Figure 1**</span></span>  

 <span data-ttu-id="39a0f-107">**Ejemplo de un componente de canalización de itinerarios de ESB**</span><span class="sxs-lookup"><span data-stu-id="39a0f-107">**Example of an ESB Itinerary pipeline component**</span></span>  

 <span data-ttu-id="39a0f-108">Un componente de canalización de itinerarios de ESB puede usarse para capturar los metadatos de un mensaje como propiedades de contexto que se pueden definir la transformación aplicada por el ESB.</span><span class="sxs-lookup"><span data-stu-id="39a0f-108">An ESB Itinerary pipeline component can be used to capture the metadata from a message as context properties that can define the processing applied by the ESB.</span></span>  

 <span data-ttu-id="39a0f-109">Las secciones siguientes describen los pasos realizados por cada componente.</span><span class="sxs-lookup"><span data-stu-id="39a0f-109">The following sections describe the steps performed by each component.</span></span>  

## <a name="esb-itinerary-pipeline-component-process-steps"></a><span data-ttu-id="39a0f-110">Pasos del proceso de componente de canalización itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="39a0f-110">ESB Itinerary Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="39a0f-111">En el ejemplo que se muestra en la figura 1, el componente de canalización de itinerarios de ESB ejecuta los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="39a0f-111">In the example shown in Figure 1, the ESB Itinerary pipeline component executes the following steps:</span></span>  

- <span data-ttu-id="39a0f-112">Lee el encabezado SOAP de itinerario.</span><span class="sxs-lookup"><span data-stu-id="39a0f-112">It reads the itinerary SOAP header.</span></span> <span data-ttu-id="39a0f-113">La entidad envía establece el itinerario rellenando el encabezado SOAP cuando se envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="39a0f-113">The submitting party sets the itinerary by populating the SOAP header when he or she submits the message.</span></span> <span data-ttu-id="39a0f-114">Una serie de propiedades de contexto del mensaje de BizTalk representan el encabezado SOAP; Estas propiedades varían según el tipo de adaptador del servicio Web que se usa.</span><span class="sxs-lookup"><span data-stu-id="39a0f-114">A series of BizTalk message context properties represent the SOAP header; these properties vary, depending on the type of Web service adapter that is used.</span></span> <span data-ttu-id="39a0f-115">Estos son los adaptadores de servicio Web pertinentes:</span><span class="sxs-lookup"><span data-stu-id="39a0f-115">The following are the relevant Web service adapters:</span></span>  

  - <span data-ttu-id="39a0f-116">**Adaptador de WCF.**</span><span class="sxs-lookup"><span data-stu-id="39a0f-116">**WCF adapter.**</span></span> <span data-ttu-id="39a0f-117">Este adaptador analiza los encabezados SOAP y rellena las propiedades de contexto de mensaje de BizTalk aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="39a0f-117">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  


    |                                  <span data-ttu-id="39a0f-118">Propiedades</span><span class="sxs-lookup"><span data-stu-id="39a0f-118">Properties</span></span>                                  |
    |------------------------------------------------------------------------------|
    |                             <span data-ttu-id="39a0f-119">**Nombre = itinerario**</span><span class="sxs-lookup"><span data-stu-id="39a0f-119">**Name = Itinerary**</span></span>                             |
    | <span data-ttu-id="39a0f-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span><span class="sxs-lookup"><span data-stu-id="39a0f-120">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary**</span></span> |

    > [!NOTE]
    >  <span data-ttu-id="39a0f-121">De forma predeterminada, el adaptador de Windows Communication Foundation (WCF) utiliza el nombre raíz del esquema denominado ItineraryDescription.xsd (este esquema se usa para generar el encabezado SOAP de itinerarios de ESB) como el contexto de BizTalk **nombre** argumento, y usa el espacio de nombres de destino del esquema como el contexto de BizTalk **Namespace** argumento.</span><span class="sxs-lookup"><span data-stu-id="39a0f-121">By default, the Windows Communication Foundation (WCF) adapter uses the root name of the schema named ItineraryDescription.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the target namespace of the schema as the BizTalk context **Namespace** argument.</span></span>  

  - <span data-ttu-id="39a0f-122">**Adaptador de SOAP.**</span><span class="sxs-lookup"><span data-stu-id="39a0f-122">**SOAP adapter.**</span></span> <span data-ttu-id="39a0f-123">Este adaptador analiza los encabezados SOAP y rellena las propiedades de contexto de mensaje de BizTalk aparece en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="39a0f-123">This adapter parses the SOAP headers and populates the BizTalk message context properties listed in the following table.</span></span>  


    |                              <span data-ttu-id="39a0f-124">Propiedades</span><span class="sxs-lookup"><span data-stu-id="39a0f-124">Properties</span></span>                              |
    |----------------------------------------------------------------------|
    |                         <span data-ttu-id="39a0f-125">**Nombre = itinerario**</span><span class="sxs-lookup"><span data-stu-id="39a0f-125">**Name = Itinerary**</span></span>                         |
    | <span data-ttu-id="39a0f-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span><span class="sxs-lookup"><span data-stu-id="39a0f-126">**Namespace = http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**</span></span> |

    > [!NOTE]
    >  <span data-ttu-id="39a0f-127">De forma predeterminada, el adaptador de SOAP utiliza el nombre raíz del esquema denominado Itinerary.xsd (este esquema se usa para generar el encabezado SOAP de itinerarios de ESB) como el contexto de BizTalk **nombre** argumento y utiliza el espacio de nombres del encabezado SOAP como el Contexto de BizTalk **Namespace** argumento.</span><span class="sxs-lookup"><span data-stu-id="39a0f-127">By default, the SOAP Adapter uses the root name of the schema named Itinerary.xsd (this schema is used to generate the ESB Itinerary SOAP header) as the BizTalk context **Name** argument, and it uses the namespace of the SOAP header as the BizTalk context **Namespace** argument.</span></span>  

- <span data-ttu-id="39a0f-128">Quita el valor original de itinerarios el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="39a0f-128">It removes the original itinerary value from the message context.</span></span>  

- <span data-ttu-id="39a0f-129">Valida el itinerario y establece propiedades específicas para preestablecer valores predeterminados si son null en el itinerario; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39a0f-129">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  

  - <span data-ttu-id="39a0f-130">Si el recuento de servicio es menor que 1, el componente produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="39a0f-130">If Service count is less than 1, the component throws an exception.</span></span>  

  - <span data-ttu-id="39a0f-131">El componente establece los atributos de itinerarios raíz con los valores para la cuenta de servicio, el identificador (**Uuid**), la hora de inicio (**BeginTime**), y si se trata de una solicitud unidireccional o bidireccional (**IsRequestResponse**).</span><span class="sxs-lookup"><span data-stu-id="39a0f-131">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  

  - <span data-ttu-id="39a0f-132">El componente valida los servicios, Establece los identificadores, Establece la instancia de servicio actual (el servicio para procesar a continuación) y valida los solucionadores asociados.</span><span class="sxs-lookup"><span data-stu-id="39a0f-132">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  

  - <span data-ttu-id="39a0f-133">El componente define el segmento de BizTalk del itinerario mediante las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="39a0f-133">The component sets the BizTalk Segment of the itinerary using the following properties:</span></span>  

    -   <span data-ttu-id="39a0f-134">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="39a0f-134">**correlationToken**</span></span>  

    -   <span data-ttu-id="39a0f-135">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="39a0f-135">**reqRespTransmitPipelineID**</span></span>  

    -   <span data-ttu-id="39a0f-136">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="39a0f-136">**interchangeId**</span></span>  

    -   <span data-ttu-id="39a0f-137">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="39a0f-137">**receiveInstanceId**</span></span>  

    -   <span data-ttu-id="39a0f-138">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="39a0f-138">**epmRRCorrelationToken**</span></span>  

  - <span data-ttu-id="39a0f-139">El componente escribe el itinerario modificado las propiedades de contexto de mensaje de BizTalk aparece en la siguiente tabla con las propiedades definidas en el esquema del sistema-Properties.xsd.</span><span class="sxs-lookup"><span data-stu-id="39a0f-139">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  


    |                                           <span data-ttu-id="39a0f-140">Propiedades</span><span class="sxs-lookup"><span data-stu-id="39a0f-140">Properties</span></span>                                           |
    |------------------------------------------------------------------------------------------------|
    |                                   <span data-ttu-id="39a0f-141">**Nombre = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="39a0f-141">**Name = ItineraryHeader**</span></span>                                   |
    | <span data-ttu-id="39a0f-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="39a0f-142">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span> |


  - <span data-ttu-id="39a0f-143">El componente promociona las cuatro propiedades de contexto de BizTalk aparece en la tabla siguiente con los valores definidos en el esquema del sistema-Properties.xsd.</span><span class="sxs-lookup"><span data-stu-id="39a0f-143">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  

    |<span data-ttu-id="39a0f-144">Property</span><span class="sxs-lookup"><span data-stu-id="39a0f-144">Property</span></span>|<span data-ttu-id="39a0f-145">Valor</span><span class="sxs-lookup"><span data-stu-id="39a0f-145">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="39a0f-146">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="39a0f-146">**ServiceName**</span></span>|<span data-ttu-id="39a0f-147">El nombre de la instancia actual del servicio definido en el itinerario.</span><span class="sxs-lookup"><span data-stu-id="39a0f-147">The name of the current service instance defined in the itinerary.</span></span>|  
    |<span data-ttu-id="39a0f-148">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="39a0f-148">**ServiceType**</span></span>|<span data-ttu-id="39a0f-149">Establecer en **orquestación** o **mensajería**</span><span class="sxs-lookup"><span data-stu-id="39a0f-149">Set to either **Orchestration** or **Messaging**</span></span>|  
    |<span data-ttu-id="39a0f-150">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="39a0f-150">**IsRequestResponse**</span></span>|<span data-ttu-id="39a0f-151">Establecer en **True** o **False**</span><span class="sxs-lookup"><span data-stu-id="39a0f-151">Set to either **True** or **False**</span></span>|  
    |<span data-ttu-id="39a0f-152">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="39a0f-152">**ServiceState**</span></span>|<span data-ttu-id="39a0f-153">Establecido en **pendiente**</span><span class="sxs-lookup"><span data-stu-id="39a0f-153">Set to **Pending**</span></span>|  

## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="39a0f-154">Pasos de proceso de componente de canalización ESB distribuidor</span><span class="sxs-lookup"><span data-stu-id="39a0f-154">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="39a0f-155">En el ejemplo que se muestra en la figura 1, el componente de canalización de distribuidor de ESB ejecuta los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="39a0f-155">In the example shown in Figure 1, the ESB Dispatcher pipeline component executes the following steps:</span></span>  

- <span data-ttu-id="39a0f-156">Administra la ejecución de todos los pasos de itinerarios de tipo **mensajería** y hace avanzar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="39a0f-156">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="39a0f-157">El componente de distribuidor de ESB es con reconocimiento de ubicación y ejecuta la lógica basada en su ubicación en el ciclo de procesamiento de mensajería, lo que sería **recepción entrante, enviar transmitir**, **enviar entrada**, o **Recepción saliente**.</span><span class="sxs-lookup"><span data-stu-id="39a0f-157">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound, Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="39a0f-158">El componente de canalización de distribuidor de ESB invoca servicios de mensajería itinerarios de ESB especificados en el archivo Esb.config.</span><span class="sxs-lookup"><span data-stu-id="39a0f-158">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="39a0f-159">De forma predeterminada, las propiedades de configuración de este componente para el enrutamiento y transformación están asociadas con los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="39a0f-159">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  

  - <span data-ttu-id="39a0f-160">**Microsoft.Practices.ESB.Services.Transform.**</span><span class="sxs-lookup"><span data-stu-id="39a0f-160">**Microsoft.Practices.ESB.Services.Transform.**</span></span> <span data-ttu-id="39a0f-161">Este servicio ejecuta asignaciones de BizTalk en la carga de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="39a0f-161">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="39a0f-162">El servicio valida los requisitos de transformación y actualiza las propiedades de contexto de BizTalk que contienen el nombre de la especificación de documento y el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39a0f-162">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="39a0f-163">El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de transformación, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="39a0f-163">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  

  - <span data-ttu-id="39a0f-164"><strong>Microsoft.Practices.ESB.Services.Routing.</strong> Este servicio utiliza la resolución y el marco de proveedores de adaptador para establecer la información de enrutamiento de punto de conexión adecuado.</span><span class="sxs-lookup"><span data-stu-id="39a0f-164"><strong>Microsoft.Practices.ESB.Services.Routing.</strong>This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="39a0f-165">El distribuidor de ESB este servicio se ejecuta sólo si éste es el nombre del servicio de enrutamiento, tal como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="39a0f-165">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>
