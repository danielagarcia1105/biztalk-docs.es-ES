---
title: Operaciones en RFC de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8219a063fed2c940cfcd2658937fde0686542d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015363"
---
# <a name="operations-on-rfcs-in-sap"></a><span data-ttu-id="2812d-102">Operaciones en RFC de SAP</span><span class="sxs-lookup"><span data-stu-id="2812d-102">Operations on RFCs in SAP</span></span>
<span data-ttu-id="2812d-103">Puede usar el[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un cliente RFC y como un servidor RFC.</span><span class="sxs-lookup"><span data-stu-id="2812d-103">You can use the[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] both as an RFC client and as an RFC server.</span></span> <span data-ttu-id="2812d-104">En escenarios de cliente RFC, la aplicación invoca las solicitudes de cambio en el sistema SAP mediante la invocación de operaciones de RFC en la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2812d-104">In RFC client scenarios, your application invokes RFCs on the SAP system by invoking RFC operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2812d-105">En escenarios de servidor RFC SAP sistema invoca las solicitudes de cambio en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], que, a su vez, llamaría a la solicitud de cambio como una operación en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2812d-105">In RFC server scenarios the SAP system invokes RFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], which, in turn, invokes the RFC as an operation on your application.</span></span>  
  
## <a name="rfc-operations"></a><span data-ttu-id="2812d-106">Operaciones de RFC</span><span class="sxs-lookup"><span data-stu-id="2812d-106">RFC Operations</span></span>  
 <span data-ttu-id="2812d-107">RFC aparecen por nombre como operaciones bajo el nodo de categoría de los metadatos RFC mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2812d-107">RFCs are surfaced by name as operations under the RFC metadata category node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="2812d-108">(Se puede examinar o buscar RFC en la **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="2812d-108">(You can browse or search for RFCs under the **RFC** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="2812d-109">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] pueden mostrar solo esas especificaciones RFC para el que puede recuperar metadatos desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can surface only those RFCs for which it can retrieve metadata from the SAP system.</span></span> <span data-ttu-id="2812d-110">El adaptador usa el SDK de RFC para recuperar estos metadatos, por lo que no puede exponer RFC que contienen parámetros con tipos de datos que no son compatibles con el SDK de RFC.</span><span class="sxs-lookup"><span data-stu-id="2812d-110">The adapter uses the RFC SDK to retrieve this metadata, so it cannot surface RFCs that contain parameters with data types that are not supported by the RFC SDK.</span></span> <span data-ttu-id="2812d-111">Por ejemplo, el adaptador no superficie RFC que contienen las estructuras de tipo II de ITAB o tablas.</span><span class="sxs-lookup"><span data-stu-id="2812d-111">For example, the adapter cannot surface RFCs that contain ITAB II type structures or tables.</span></span>  
  
 <span data-ttu-id="2812d-112">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite los siguientes RFC:</span><span class="sxs-lookup"><span data-stu-id="2812d-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on RFCs:</span></span>  
  
- <span data-ttu-id="2812d-113">IMPORTACIÓN de parámetros</span><span class="sxs-lookup"><span data-stu-id="2812d-113">IMPORT parameters</span></span>  
  
- <span data-ttu-id="2812d-114">Parámetros de exportación</span><span class="sxs-lookup"><span data-stu-id="2812d-114">EXPORT parameters</span></span>  
  
- <span data-ttu-id="2812d-115">Parámetros de variación</span><span class="sxs-lookup"><span data-stu-id="2812d-115">CHANGING parameters</span></span>  
  
  <span data-ttu-id="2812d-116">Para obtener más información acerca de las estructuras de mensajes y las acciones de SOAP utilizadas para las solicitudes de cambio por el adaptador, vea [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-116">For more information about the message structures and SOAP actions used for RFCs by the adapter, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="invoking-rfcs-on-an-sap-system"></a><span data-ttu-id="2812d-117">Invocar RFC en un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="2812d-117">Invoking RFCs on an SAP System</span></span>  
 <span data-ttu-id="2812d-118">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] presenta las solicitudes de cambio como las operaciones individuales que toman el nombre de la solicitud de cambio en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-118">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces RFCs as individual operations that take the name of the RFC on the SAP system.</span></span> <span data-ttu-id="2812d-119">Para invocar una solicitud de cambio en el sistema SAP, se invoca la operación de RFC con el nombre adecuado en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="2812d-119">To invoke an RFC on the SAP system, you invoke the appropriately named RFC operation on the adapter.</span></span>  
  
 <span data-ttu-id="2812d-120">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="2812d-120">For more information about:</span></span>  
  
-   <span data-ttu-id="2812d-121">Invocar una RFC mediante BizTalk Server, consulte [invocar RFC utilizando BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-121">Invoking an RFC using BizTalk Server, see [Invoke RFCs by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="2812d-122">Invocar una RFC mediante el modelo de servicio WCF, vea [invocar RFC de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-122">Invoking an RFC using the WCF service model, see [Invoke RFCs in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="2812d-123">Invocar una RFC mediante el modelo de canal WCF, vea [invocar operaciones en el sistema de SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-123">Invoking an RFC using the WCF channel model, see [Invoke Operations on the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a><span data-ttu-id="2812d-124">Recibir llamadas RFC de entrada desde un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="2812d-124">Receiving Inbound RFC Calls from an SAP System</span></span>  
 <span data-ttu-id="2812d-125">Es posible que SAP actuar como cliente e invocar los módulos de función en un servidor externo de RFC.</span><span class="sxs-lookup"><span data-stu-id="2812d-125">It is possible for SAP to act as a client and invoke function modules on an external RFC server.</span></span> <span data-ttu-id="2812d-126">Esta funcionalidad permite:</span><span class="sxs-lookup"><span data-stu-id="2812d-126">This functionality enables:</span></span>  
  
- <span data-ttu-id="2812d-127">Aplicación de SAP para notificaciones de inserción a sistemas externos sin la necesidad de sondear continuamente SAP para las notificaciones mediante una llamada a las solicitudes de cambio de sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="2812d-127">SAP to push notifications to external systems without the external systems having to continuously poll SAP for notifications by calling RFCs.</span></span>  
  
- <span data-ttu-id="2812d-128">La implementación de lógica de negocios fuera del sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-128">The implementation of business logic outside the SAP system.</span></span> <span data-ttu-id="2812d-129">El sistema SAP, a continuación, puede llamar al programa externo en el servidor RFC.</span><span class="sxs-lookup"><span data-stu-id="2812d-129">The SAP system can then call the external program on the RFC server.</span></span>  
  
  <span data-ttu-id="2812d-130">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede actuar como un servidor RFC para recibir dichas llamadas RFC entrantes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-130">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can act as an RFC server to receive such inbound RFC calls from the SAP system.</span></span> <span data-ttu-id="2812d-131">Cuando el adaptador recibe una llamada de RFC de SAP, invoca esa operación RFC en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2812d-131">When the adapter receives an RFC call from SAP, it invokes that RFC operation on your application.</span></span>  
  
  <span data-ttu-id="2812d-132">Para el adaptador funcionar como un servidor RFC:</span><span class="sxs-lookup"><span data-stu-id="2812d-132">For the adapter to perform as an RFC server:</span></span>  
  
- <span data-ttu-id="2812d-133">La solicitud de cambio se debe declarar en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-133">The RFC must be declared on the SAP system.</span></span> <span data-ttu-id="2812d-134">Esto es para que el adaptador pueda recuperar los metadatos que describen la solicitud de cambio desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-134">This is so the adapter can retrieve metadata that describes the RFC from the SAP system.</span></span> <span data-ttu-id="2812d-135">La solicitud de cambio se implementa realmente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2812d-135">The RFC is actually implemented in your application.</span></span>  
  
- <span data-ttu-id="2812d-136">El adaptador debe registrarse con un destino de RFC en una puerta de enlace SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-136">The adapter must register with an RFC destination on an SAP gateway.</span></span> <span data-ttu-id="2812d-137">El registro se basa en un nombre lógico que se llama a un identificador de programa.</span><span class="sxs-lookup"><span data-stu-id="2812d-137">The registration is based on a logical name called a program ID.</span></span> <span data-ttu-id="2812d-138">Proporcione los parámetros en el URI para especificar el identificador de programa, la puerta de enlace SAP y SAP de servidor para este registro de conexión.</span><span class="sxs-lookup"><span data-stu-id="2812d-138">You supply parameters in the connection URI to specify the PROGRAM ID, SAP gateway, and SAP server for this registration.</span></span>  
  
  <span data-ttu-id="2812d-139">El ejemplo siguiente muestra el código ABAP necesario para invocar una RFC mediante el identificador de programa, MYDEST.</span><span class="sxs-lookup"><span data-stu-id="2812d-139">The following example shows the ABAP code required to invoke an RFC through the PROGRAM ID, MYDEST.</span></span>  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 <span data-ttu-id="2812d-140">Para obtener más información acerca de:</span><span class="sxs-lookup"><span data-stu-id="2812d-140">For more information about:</span></span>  
  
-   <span data-ttu-id="2812d-141">Recibir una llamada de servidor RFC mediante BizTalk Server, consulte [recibir llamadas de RFC de entrada por mediante BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-141">Receiving an RFC server call using BizTalk Server, see [Receive Inbound RFC Calls by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="2812d-142">Recibir una llamada de servidor RFC mediante el modelo de servicio WCF, vea [recibir llamadas de RFC de entrada de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-142">Receiving an RFC server call using the WCF service model, see [Receive  Inbound RFC Calls in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="2812d-143">Recibir una llamada de servidor RFC mediante el modelo de canal WCF, vea [recibir operaciones de entrada desde el sistema SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-143">Receiving an RFC server call using the WCF channel model, see [Receive Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="special-rfc-operations"></a><span data-ttu-id="2812d-144">Operaciones de RFC especiales</span><span class="sxs-lookup"><span data-stu-id="2812d-144">Special RFC Operations</span></span>  
 <span data-ttu-id="2812d-145">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también se puede realizar determinadas operaciones de RFC especiales en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="2812d-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can also perform certain special RFC operations on the SAP system.</span></span> <span data-ttu-id="2812d-146">Una operación de este tipo es RfcGetAttributes.</span><span class="sxs-lookup"><span data-stu-id="2812d-146">One such operation is RfcGetAttributes.</span></span>  
  
- <span data-ttu-id="2812d-147">**RfcGetAttributes**.</span><span class="sxs-lookup"><span data-stu-id="2812d-147">**RfcGetAttributes**.</span></span> <span data-ttu-id="2812d-148">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa esta operación para obtener información acerca de los parámetros de conexión RFC como identificador del sistema, página de códigos del socio y lenguaje.</span><span class="sxs-lookup"><span data-stu-id="2812d-148">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses this operation to get information about the RFC connection parameters such as system ID, partner code page, and language.</span></span> <span data-ttu-id="2812d-149">Esta operación está disponible en el **RFC** nodo cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2812d-149">This operation is available under the **RFC** node when using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
  <span data-ttu-id="2812d-150">Para obtener más información acerca de la estructura y mensajes de acción SOAP para invocar una operación RfcGetAttributes en el sistema SAP, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span><span class="sxs-lookup"><span data-stu-id="2812d-150">For more information about message structure and SOAP action for invoking an RfcGetAttributes operation on the SAP system, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2812d-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="2812d-151">See Also</span></span>  
 <span data-ttu-id="2812d-152">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="2812d-152">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>