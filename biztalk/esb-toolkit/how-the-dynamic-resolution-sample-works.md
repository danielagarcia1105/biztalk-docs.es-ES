---
title: Cómo funciona el ejemplo de resolución dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab7a46a02dc080fa27b9df2b30614bc8a45c6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976437"
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="83641-102">Cómo funciona el ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="83641-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="83641-103">El ejemplo de resolución dinámica utiliza el componente de canalización de desensamblador de distribuidor de ESB para todos los ejemplos de mensajes que se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="83641-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  

 <span data-ttu-id="83641-104">Para escenarios de mensajería unidireccionales, en el ejemplo se resuelve como el punto de conexión mediante la estática, el BRE o resolución de XPATH y negocia el protocolo de archivo para el archivo, FTP o MQSeries.</span><span class="sxs-lookup"><span data-stu-id="83641-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  

 <span data-ttu-id="83641-105">Para escenarios de mensajería bidireccionales, el ejemplo se resuelve como el punto de conexión mediante estático, BRE, UDDI o resolución de XPATH y negocia el protocolo de SOAP en SOAP o WCF-BasicHttp.</span><span class="sxs-lookup"><span data-stu-id="83641-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="83641-106">Además, los ejemplos de resolverán y ejecutan mediante la resolución del BRE, que usa los datos contenidos en las propiedades de contexto de mensaje y el cuerpo del mensaje para determinar el resultado de la resolución de asignaciones de BizTalk de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83641-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  

 <span data-ttu-id="83641-107">El resultado del proceso de resolución es que todos los ejemplos bidireccionales enviar su mensaje a ESB. Servicio CanadianServices Web ubicado en http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span><span class="sxs-lookup"><span data-stu-id="83641-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="83641-108">Además, según el resultado de la resolución, el ejemplo ejecuta el **submitOrder** o **submitPurchase** acción.</span><span class="sxs-lookup"><span data-stu-id="83641-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="83641-109">Además, el componente de canalización de desensamblador de distribuidor de ESB ejecuta dinámicamente según especificado o la acción resolver una asignación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83641-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  

 <span data-ttu-id="83641-110">Figura 1 muestra la que ubicación de recepción de las canalizaciones configuradas para el DynamicResolutionReqResp_SOAP.</span><span class="sxs-lookup"><span data-stu-id="83641-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  

 <span data-ttu-id="83641-111">![Canalizaciones de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="83641-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  

 <span data-ttu-id="83641-112">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="83641-112">**Figure 1**</span></span>  

 <span data-ttu-id="83641-113">**Las canalizaciones configuradas de la DynamicResolutionReqResp_SOAP recepción la ubicación de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="83641-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="83641-114">Figura 2 muestra las propiedades de cada instancia del componente ESBReceiveXML que utiliza el Desensamblador de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="83641-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  

 <span data-ttu-id="83641-115">![XML de recepción de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="83641-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  

 <span data-ttu-id="83641-116">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="83641-116">**Figure 2**</span></span>  

 <span data-ttu-id="83641-117">**Las propiedades de cada instancia de los componentes de la canalización ESBReceiveXML de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="83641-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="83641-118">Las siguientes propiedades se muestran en la figura 2:</span><span class="sxs-lookup"><span data-stu-id="83641-118">The following properties are shown in Figure 2:</span></span>  

- <span data-ttu-id="83641-119">**Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="83641-119">**Enabled**.</span></span> <span data-ttu-id="83641-120">Esta propiedad determina si la canalización está activa.</span><span class="sxs-lookup"><span data-stu-id="83641-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="83641-121">Si se establece en **False**, los mensajes pasan a través sin procesamiento.</span><span class="sxs-lookup"><span data-stu-id="83641-121">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="83641-122">**Punto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="83641-122">**Endpoint**.</span></span> <span data-ttu-id="83641-123">Esta propiedad es la cadena de conexión utilizada para determinar qué resolución para cargar y especifica la configuración de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="83641-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  

- <span data-ttu-id="83641-124">**Nombredemapa**.</span><span class="sxs-lookup"><span data-stu-id="83641-124">**MapName**.</span></span> <span data-ttu-id="83641-125">Esta propiedad es la cadena de conexión que se usa para determinar qué resolución para cargar y qué asignación de BizTalk a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="83641-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="83641-126">Puede ser el nombre completo de un mapa en lugar de una cadena de conexión de la resolución.</span><span class="sxs-lookup"><span data-stu-id="83641-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  

- <span data-ttu-id="83641-127">**Validar**.</span><span class="sxs-lookup"><span data-stu-id="83641-127">**Validate**.</span></span> <span data-ttu-id="83641-128">Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en la asignación que se va resolver y la ejecutará.</span><span class="sxs-lookup"><span data-stu-id="83641-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  

  <span data-ttu-id="83641-129">Figura 3 muestra las propiedades de cada instancia del componente ESBSendPassthrough que utiliza el distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="83641-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  

  <span data-ttu-id="83641-130">![Paso a través de envío de resolución dinámica](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="83641-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  

  <span data-ttu-id="83641-131">**Figura 3**</span><span class="sxs-lookup"><span data-stu-id="83641-131">**Figure 3**</span></span>  

  <span data-ttu-id="83641-132">**Las propiedades de cada instancia de los componentes de la canalización ESBSendPassthrough de la aplicación de ejemplo de resolución dinámica**</span><span class="sxs-lookup"><span data-stu-id="83641-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  

  <span data-ttu-id="83641-133">Las siguientes propiedades se muestran en la figura 3:</span><span class="sxs-lookup"><span data-stu-id="83641-133">The following properties are shown in Figure 3:</span></span>  

- <span data-ttu-id="83641-134">**Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="83641-134">**Enabled**.</span></span> <span data-ttu-id="83641-135">Esta propiedad determina si la canalización está activa.</span><span class="sxs-lookup"><span data-stu-id="83641-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="83641-136">Si se establece en **False**, los mensajes pasan a través sin procesamiento.</span><span class="sxs-lookup"><span data-stu-id="83641-136">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="83641-137">**Punto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="83641-137">**Endpoint**.</span></span> <span data-ttu-id="83641-138">Esta propiedad es la cadena de conexión utilizada para determinar a qué resolución para carga y la configuración de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="83641-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  

- <span data-ttu-id="83641-139">**Nombredemapa**.</span><span class="sxs-lookup"><span data-stu-id="83641-139">**MapName**.</span></span> <span data-ttu-id="83641-140">Esta propiedad es la cadena de conexión que se usa para determinar qué resolución para cargar y qué asignación de BizTalk a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="83641-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="83641-141">Un nombre completo de un mapa puede usarse en lugar de la cadena de conexión de una resolución.</span><span class="sxs-lookup"><span data-stu-id="83641-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  

- <span data-ttu-id="83641-142">**Validar**.</span><span class="sxs-lookup"><span data-stu-id="83641-142">**Validate**.</span></span> <span data-ttu-id="83641-143">Cuando se establece en **True** (valor predeterminado), el Desensamblador de distribuidor de ESB componente indica al servicio de transformación de ESB para validar el mensaje de origen con respecto al esquema de origen definido en la asignación que se va resolver y la ejecutará.</span><span class="sxs-lookup"><span data-stu-id="83641-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>
