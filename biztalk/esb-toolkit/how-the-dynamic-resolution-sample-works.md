---
title: "Cómo funciona el ejemplo de resolución dinámica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="85229-102">Cómo funciona el ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="85229-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="85229-103">El ejemplo de resolución dinámica utiliza el componente de canalización de desensamblador de distribuidor de ESB para todos los ejemplos de mensajes que se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="85229-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  
  
 <span data-ttu-id="85229-104">Para escenarios de mensajería unidireccionales, en el ejemplo se resuelve el extremo utilizando el BRE, IP estática o resolución de XPATH y establece el protocolo de archivo al archivo, FTP o MQSeries.</span><span class="sxs-lookup"><span data-stu-id="85229-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  
  
 <span data-ttu-id="85229-105">Para escenarios de mensajería bidireccionales, el ejemplo resuelve el extremo utilizando la IP estática, BRE, UDDI o resolución de XPATH y establece el protocolo de SOAP en SOAP o WCF-BasicHttp.</span><span class="sxs-lookup"><span data-stu-id="85229-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="85229-106">Además, los ejemplos de resolverán y ejecutan mediante el solucionador BRE, que usa los hechos contenidos en las propiedades de contexto de mensaje y el cuerpo del mensaje para determinar el resultado de la resolución de asignaciones de BizTalk de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85229-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  
  
 <span data-ttu-id="85229-107">El resultado del proceso de resolución es que todos los ejemplos bidireccionales envía su mensaje a ESB. Servicio de CanadianServices Web situado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span><span class="sxs-lookup"><span data-stu-id="85229-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="85229-108">Además, según el resultado de la resolución, el ejemplo ejecuta el **submitOrder** o **submitPurchase** acción.</span><span class="sxs-lookup"><span data-stu-id="85229-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="85229-109">Además, el componente de canalización de desensamblador de distribuidor de ESB ejecuta dinámicamente una asignación de BizTalk, función especificado o la acción resuelta.</span><span class="sxs-lookup"><span data-stu-id="85229-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  
  
 <span data-ttu-id="85229-110">La figura 1 muestra la que ubicación de recepción de las canalizaciones configuradas para el DynamicResolutionReqResp_SOAP.</span><span class="sxs-lookup"><span data-stu-id="85229-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  
  
 <span data-ttu-id="85229-111">![Canalizaciones de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="85229-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  
  
 <span data-ttu-id="85229-112">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="85229-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="85229-113">**Las canalizaciones configuradas de la DynamicResolutionReqResp_SOAP ubicación de recepción de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="85229-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="85229-114">Figura 2 muestra las propiedades de cada instancia del componente ESBReceiveXML que utiliza el Desensamblador de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="85229-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  
  
 <span data-ttu-id="85229-115">![XML de recepción de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="85229-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  
  
 <span data-ttu-id="85229-116">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="85229-116">**Figure 2**</span></span>  
  
 <span data-ttu-id="85229-117">**Las propiedades de cada instancia de los componentes de la canalización de ESBReceiveXML de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="85229-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="85229-118">Las siguientes propiedades se muestran en la figura 2:</span><span class="sxs-lookup"><span data-stu-id="85229-118">The following properties are shown in Figure 2:</span></span>  
  
-   <span data-ttu-id="85229-119">**Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="85229-119">**Enabled**.</span></span> <span data-ttu-id="85229-120">Esta propiedad determina si la canalización está activa.</span><span class="sxs-lookup"><span data-stu-id="85229-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="85229-121">Si se establece en **False**, mensajes atraviesan sin procesar.</span><span class="sxs-lookup"><span data-stu-id="85229-121">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="85229-122">**Punto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="85229-122">**Endpoint**.</span></span> <span data-ttu-id="85229-123">Esta propiedad es la cadena de conexión utilizada para determinar qué resolución que se debe cargar y especifica la configuración del extremo.</span><span class="sxs-lookup"><span data-stu-id="85229-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  
  
-   <span data-ttu-id="85229-124">**Nombredemapa**.</span><span class="sxs-lookup"><span data-stu-id="85229-124">**MapName**.</span></span> <span data-ttu-id="85229-125">Esta propiedad es la cadena de conexión que se usa para determinar qué resolución que se debe cargar y qué asignación de BizTalk a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="85229-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="85229-126">Puede ser el nombre completo de un mapa en lugar de una cadena de conexión de resolución.</span><span class="sxs-lookup"><span data-stu-id="85229-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  
  
-   <span data-ttu-id="85229-127">**Validar**.</span><span class="sxs-lookup"><span data-stu-id="85229-127">**Validate**.</span></span> <span data-ttu-id="85229-128">Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en el mapa se resuelva y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="85229-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  
  
 <span data-ttu-id="85229-129">La figura 3 muestra las propiedades de cada instancia del componente ESBSendPassthrough que usa el distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="85229-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  
  
 <span data-ttu-id="85229-130">![Resolución dinámica enviar Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="85229-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  
  
 <span data-ttu-id="85229-131">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="85229-131">**Figure 3**</span></span>  
  
 <span data-ttu-id="85229-132">**Las propiedades de cada instancia de los componentes de la canalización de ESBSendPassthrough de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="85229-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="85229-133">Las siguientes propiedades se muestran en la figura 3:</span><span class="sxs-lookup"><span data-stu-id="85229-133">The following properties are shown in Figure 3:</span></span>  
  
-   <span data-ttu-id="85229-134">**Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="85229-134">**Enabled**.</span></span> <span data-ttu-id="85229-135">Esta propiedad determina si la canalización está activa.</span><span class="sxs-lookup"><span data-stu-id="85229-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="85229-136">Si se establece en **False**, mensajes atraviesan sin procesar.</span><span class="sxs-lookup"><span data-stu-id="85229-136">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="85229-137">**Punto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="85229-137">**Endpoint**.</span></span> <span data-ttu-id="85229-138">Esta propiedad es la cadena de conexión utilizada para determinar a qué resolución se cargue y la configuración de extremo.</span><span class="sxs-lookup"><span data-stu-id="85229-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  
  
-   <span data-ttu-id="85229-139">**Nombredemapa**.</span><span class="sxs-lookup"><span data-stu-id="85229-139">**MapName**.</span></span> <span data-ttu-id="85229-140">Esta propiedad es la cadena de conexión que se usa para determinar qué resolución que se debe cargar y qué asignación de BizTalk a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="85229-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="85229-141">Un nombre completo de un mapa puede usarse en lugar de la cadena de conexión de una resolución.</span><span class="sxs-lookup"><span data-stu-id="85229-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  
  
-   <span data-ttu-id="85229-142">**Validar**.</span><span class="sxs-lookup"><span data-stu-id="85229-142">**Validate**.</span></span> <span data-ttu-id="85229-143">Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en el mapa se resuelva y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="85229-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>