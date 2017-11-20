---
title: "Uso de un componente de canalización para seleccionar un itinerario existente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b93c5cb6-071f-485d-b0bb-22f95bafa3d0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a733da2348de13120ce37a205b77d2e8194c7790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-select-an-existing-itinerary"></a><span data-ttu-id="9d9e4-102">Uso de un componente de canalización para seleccionar un itinerario existente</span><span class="sxs-lookup"><span data-stu-id="9d9e4-102">Using a Pipeline Component to Select an Existing Itinerary</span></span>
## <a name="esb-itinerary-selector-pipeline-component"></a><span data-ttu-id="9d9e4-103">Componente de canalización de Selector itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="9d9e4-103">ESB Itinerary Selector Pipeline Component</span></span>  
 <span data-ttu-id="9d9e4-104">Mensajes enviados mediante genérico en pendientes itinerarios se envían sin un encabezado de itinerarios.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-104">Messages submitted using generic itinerary on-ramps are submitted without an itinerary header.</span></span> <span data-ttu-id="9d9e4-105">Para resolver el itinerario adecuado y adjuntarlo al mensaje entrante, el aumento debe proporcionar un mecanismo que puede configurarse para tener acceso a los itinerarios desde un repositorio central.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-105">To resolve the appropriate itinerary and attach it to the incoming message, the on-ramp must provide a mechanism that can be configured to access itineraries from a central repository.</span></span>  
  
 <span data-ttu-id="9d9e4-106">El componente de canalización de Selector de itinerario ESB usa una cadena de conexión de la resolución, junto con los solucionadores especializados, para resolver el contenido de un itinerario de servidor almacenado en un repositorio central (de forma predeterminada, SQL Server).</span><span class="sxs-lookup"><span data-stu-id="9d9e4-106">The ESB Itinerary Selector pipeline component uses a resolver connection string, in conjunction with specialized resolvers, to resolve the content of a server-side itinerary stored in a central repository (by default, SQL Server).</span></span>  
  
 <span data-ttu-id="9d9e4-107">Cuando se utiliza el componente de canalización de Selector de itinerario de ESB en WCF pendientes junto con la resolución de itinerario estático, el nombre y la versión de la itinerario solicitado por el cliente (como se representa en el encabezado SOAP) se recupera del contexto del mensaje y se utiliza para seleccionar el itinerario adecuado.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-107">When the ESB Itinerary Selector pipeline component is used in WCF on-ramps in conjunction with the ITINERARY-STATIC resolver, the name and version of the itinerary requested by the client (as represented in the SOAP header) is retrieved from the message context and is used to select the appropriate itinerary.</span></span>  
  
 <span data-ttu-id="9d9e4-108">De forma predeterminada, el componente de canalización de Selector de ESB itinerario se encuentra en las siguientes canalizaciones:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-108">By default, the ESB Itinerary Selector pipeline component resides in the following pipelines:</span></span>  
  
-   <span data-ttu-id="9d9e4-109">ItinerarySelectReceive</span><span class="sxs-lookup"><span data-stu-id="9d9e4-109">ItinerarySelectReceive</span></span>  
  
-   <span data-ttu-id="9d9e4-110">ItinerarySelectReceivePassthrough</span><span class="sxs-lookup"><span data-stu-id="9d9e4-110">ItinerarySelectReceivePassthrough</span></span>  
  
-   <span data-ttu-id="9d9e4-111">ItinerarySelectReceiveXml</span><span class="sxs-lookup"><span data-stu-id="9d9e4-111">ItinerarySelectReceiveXml</span></span>  
  
-   <span data-ttu-id="9d9e4-112">ItinerarySelectSendReceive</span><span class="sxs-lookup"><span data-stu-id="9d9e4-112">ItinerarySelectSendReceive</span></span>  
  
 <span data-ttu-id="9d9e4-113">En las siguientes secciones se describen los pasos realizados por cada componente.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-113">The following sections describe the steps performed by each component.</span></span>  
  
## <a name="esb-itinerary-selector-pipeline-component-processing-steps"></a><span data-ttu-id="9d9e4-114">Pasos de procesamiento de componente de canalización de Selector itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="9d9e4-114">ESB Itinerary Selector Pipeline Component Processing Steps</span></span>  
 <span data-ttu-id="9d9e4-115">El componente de canalización de Selector de itinerario ESB ejecuta los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-115">The ESB Itinerary Selector pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="9d9e4-116">La entidad envía envía un mensaje para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-116">The submitting party submits a message for processing.</span></span> <span data-ttu-id="9d9e4-117">El componente de Selector de itinerario utiliza a un solucionador especificado como una cadena de conexión de la propiedad, configurada por el programador, para determinar y seleccione el itinerario adecuado en el almacén itinerario, según el contenido del mensaje o contexto.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-117">The Itinerary Selector component uses a resolver specified as a property connection string, configured by the developer, to determine and select the appropriate itinerary from the itinerary store, based on message content or context.</span></span>  
  
-   <span data-ttu-id="9d9e4-118">Valida el itinerario y establece las propiedades específicas para preestablecer valores predeterminados si son null en el itinerario; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-118">It validates the itinerary and sets specific properties to preset default values if they are null in the itinerary; for example:</span></span>  
  
    -   <span data-ttu-id="9d9e4-119">Si el recuento de servicio es menor que 1, el componente produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-119">If Service count is less than 1, the component throws an exception.</span></span>  
  
    -   <span data-ttu-id="9d9e4-120">El componente establece los atributos de raíz itinerarios utilizando los valores para la cuenta de servicio, el identificador (**Uuid**), la hora de inicio (**BeginTime**), y si se trata de una solicitud unidireccional o bidireccional (**IsRequestResponse**).</span><span class="sxs-lookup"><span data-stu-id="9d9e4-120">The component sets the itinerary root attributes using the values for the Service count, the identifier (**Uuid**), the start time (**BeginTime**), and whether this is a one-way or two-way request (**IsRequestResponse**).</span></span>  
  
    -   <span data-ttu-id="9d9e4-121">El componente valida los servicios, Establece los identificadores, Establece la instancia de servicio actual (el servicio para procesar a continuación) y valida los solucionadores asociados.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-121">The component validates the services, sets the identifiers, sets the current service instance (the service to process next), and validates any associated resolvers.</span></span>  
  
    -   <span data-ttu-id="9d9e4-122">El componente establece el segmento de Microsoft BizTalk Server de la itinerario con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-122">The component sets the Microsoft BizTalk Server segment of the itinerary using the following properties:</span></span>  
  
        -   <span data-ttu-id="9d9e4-123">**correlationToken**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-123">**correlationToken**</span></span>  
  
        -   <span data-ttu-id="9d9e4-124">**reqRespTransmitPipelineID**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-124">**reqRespTransmitPipelineID**</span></span>  
  
        -   <span data-ttu-id="9d9e4-125">**interchangeId**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-125">**interchangeId**</span></span>  
  
        -   <span data-ttu-id="9d9e4-126">**receiveInstanceId**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-126">**receiveInstanceId**</span></span>  
  
        -   <span data-ttu-id="9d9e4-127">**epmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-127">**epmRRCorrelationToken**</span></span>  
  
    -   <span data-ttu-id="9d9e4-128">El componente escribe el itinerario modificado las propiedades de contexto de mensaje de BizTalk aparece en la siguiente tabla con las propiedades definidas en el esquema del sistema-Properties.xsd.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-128">The component writes the modified itinerary to the BizTalk message context properties listed in the following table using the properties defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="9d9e4-129">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9d9e4-129">Properties</span></span>|  
        |----------------|  
        |<span data-ttu-id="9d9e4-130">**Nombre = ItineraryHeader**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-130">**Name = ItineraryHeader**</span></span>|  
        |<span data-ttu-id="9d9e4-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-131">**Namespace = http://schemas.microsoft.biztalk.practices.esb.com/itinerary/system-properties**</span></span>|  
  
    -   <span data-ttu-id="9d9e4-132">El componente promociona las cuatro propiedades de contexto de BizTalk aparece en la tabla siguiente con los valores definidos en el esquema del sistema-Properties.xsd.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-132">The component promotes the four BizTalk context properties listed in the following table using the values defined in the System-Properties.xsd schema.</span></span>  
  
        |<span data-ttu-id="9d9e4-133">Propiedad</span><span class="sxs-lookup"><span data-stu-id="9d9e4-133">Property</span></span>|<span data-ttu-id="9d9e4-134">Valor</span><span class="sxs-lookup"><span data-stu-id="9d9e4-134">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="9d9e4-135">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-135">**ServiceName**</span></span>|<span data-ttu-id="9d9e4-136">El nombre de la instancia actual de servicio definido en el itinerario.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-136">The name of the current service instance defined in the itinerary.</span></span>|  
        |<span data-ttu-id="9d9e4-137">**ServiceType**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-137">**ServiceType**</span></span>|<span data-ttu-id="9d9e4-138">Establecido en **orquestación** o **mensajería**.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-138">Set to either **Orchestration** or **Messaging**.</span></span>|  
        |<span data-ttu-id="9d9e4-139">**IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-139">**IsRequestResponse**</span></span>|<span data-ttu-id="9d9e4-140">Establecido en **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-140">Set to either **True** or **False**.</span></span>|  
        |<span data-ttu-id="9d9e4-141">**ServiceState**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-141">**ServiceState**</span></span>|<span data-ttu-id="9d9e4-142">Establecido en **pendiente**.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-142">Set to **Pending**.</span></span>|  
  
## <a name="esb-dispatcher-pipeline-component-process-steps"></a><span data-ttu-id="9d9e4-143">Pasos de proceso de componente de canalización de distribuidor ESB</span><span class="sxs-lookup"><span data-stu-id="9d9e4-143">ESB Dispatcher Pipeline Component Process Steps</span></span>  
 <span data-ttu-id="9d9e4-144">El componente de canalización de distribuidor de ESB ejecuta los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-144">The ESB Dispatcher pipeline component executes the following steps:</span></span>  
  
-   <span data-ttu-id="9d9e4-145">Administra la ejecución de todos los pasos itinerarios de tipo **mensajería** y hace avanzar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-145">It manages the execution of any itinerary steps of type **Messaging** and advances the itinerary.</span></span> <span data-ttu-id="9d9e4-146">El componente de distribuidor de ESB está con reconocimiento de ubicación y ejecuta la lógica basada en su ubicación en el ciclo de procesamiento de mensajería, lo que sería **recibir entrada**, **enviar transmitir**, **enviar Entrada**, o **recibir salida**.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-146">The ESB Dispatcher component is location-aware and executes logic based on its location in the messaging processing cycle, which could be **Receive Inbound**, **Send Transmit**, **Send Inbound**, or **Receive Outbound**.</span></span> <span data-ttu-id="9d9e4-147">Servicios de mensajería itinerarios de ESB especificados en el archivo Esb.config, invoca el componente de canalización de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-147">The ESB Dispatcher pipeline component invokes ESB itinerary messaging services specified in the Esb.config file.</span></span> <span data-ttu-id="9d9e4-148">De forma predeterminada, las propiedades de configuración de este componente para el enrutamiento y la transformación se asocian con los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="9d9e4-148">By default, the configuration properties of this component for routing and transformation are associated with the following services:</span></span>  
  
    -   <span data-ttu-id="9d9e4-149">**Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-149">**Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="9d9e4-150">Este servicio ejecuta asignaciones de BizTalk en la carga de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-150">This service executes BizTalk maps against the payload of an inbound message.</span></span> <span data-ttu-id="9d9e4-151">El servicio valida los requisitos de transformación y actualiza las propiedades de contexto de BizTalk que contienen el nombre de la especificación de documento y el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-151">The service validates transform requirements and updates the BizTalk context properties that contain the document specification name and the message type.</span></span> <span data-ttu-id="9d9e4-152">El distribuidor de ESB solo se ejecuta este servicio si este es el nombre del servicio en la transformación, tal y como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-152">The ESB Dispatcher executes this service only if this is the name of the transform service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>  
  
    -   <span data-ttu-id="9d9e4-153">**Microsoft.Practices.ESB.Services.Routing.**</span><span class="sxs-lookup"><span data-stu-id="9d9e4-153">**Microsoft.Practices.ESB.Services.Routing.**</span></span> <span data-ttu-id="9d9e4-154">Este servicio utiliza la resolución y el marco de proveedores de adaptador para establecer la información de enrutamiento de punto de conexión adecuado.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-154">This service uses the Resolver and Adapter Provider Framework to set the appropriate endpoint routing information.</span></span> <span data-ttu-id="9d9e4-155">El distribuidor de ESB solo se ejecuta este servicio si este es el nombre del servicio de enrutamiento, tal y como aparece en la propiedad correspondiente del componente de canalización de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="9d9e4-155">The ESB Dispatcher executes this service only if this is the name of the routing service as it appears in the corresponding property of the ESB Dispatcher pipeline component.</span></span>