---
title: Con los servicios Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288260"
---
# <a name="using-web-services"></a><span data-ttu-id="03429-102">Uso de servicios web</span><span class="sxs-lookup"><span data-stu-id="03429-102">Using Web Services</span></span>
<span data-ttu-id="03429-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad integrada para servicios Web.</span><span class="sxs-lookup"><span data-stu-id="03429-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Web services.</span></span> <span data-ttu-id="03429-104">BizTalk Server permite reutilizar y agregar todos los servicios Web existentes en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="03429-104">BizTalk Server enables the reuse and aggregation of all your existing Web services within your orchestrations.</span></span> <span data-ttu-id="03429-105">Las orquestaciones también se publican o se exponen como servicios Web para diferenciar la lógica de servicios Web de la lógica de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="03429-105">You can also publish (expose) your orchestrations as Web services to separate the Web service logic from the business process logic.</span></span>  
  
 <span data-ttu-id="03429-106">BizTalk Server incorpora la compatibilidad con adaptadores nativos en servicios Web.</span><span class="sxs-lookup"><span data-stu-id="03429-106">BizTalk Server implements support for native adapters in Web services.</span></span> <span data-ttu-id="03429-107">La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios Web sin tener que escribir una sola línea de código.</span><span class="sxs-lookup"><span data-stu-id="03429-107">Native adapter support provides scalability, fault tolerance, and tracking capabilities for Web services without writing a single line of code.</span></span> <span data-ttu-id="03429-108">Para obtener información acerca del adaptador SOAP, vea [adaptador de SOAP](../core/soap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="03429-108">For information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span>  
  
 <span data-ttu-id="03429-109">La compatibilidad de servicios Web de BizTalk Server se divide en dos categorías: consumo o llamada a servicios Web y publicación o creación de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="03429-109">The Web services support in BizTalk Server falls into two categories: consuming or calling Web services and publishing or creating Web services.</span></span>  
  
 <span data-ttu-id="03429-110">Antes de consumir o publicar un servicio Web, debe estar familiarizado con los servicios Web XML en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="03429-110">Before you consume or publish a Web service, you should have an understanding of XML Web services in ASP.NET.</span></span> <span data-ttu-id="03429-111">Para obtener información sobre los conceptos básicos de los servicios Web XML, vea el artículo "XML Web Services Basics" en [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span><span class="sxs-lookup"><span data-stu-id="03429-111">For information about the basics of XML Web services, see the article "XML Web Services Basics" at [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span></span>  
  
 <span data-ttu-id="03429-112">**Consumir servicios Web**</span><span class="sxs-lookup"><span data-stu-id="03429-112">**Consuming Web services**</span></span>  
  
 <span data-ttu-id="03429-113">Se pueden consumir (llamar) servicios Web procedentes de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="03429-113">You can consume (call) Web services from within an orchestration.</span></span> <span data-ttu-id="03429-114">Es posible agregar varios servicios Web a una única orquestación para completar todo un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="03429-114">You can aggregate several Web services into single orchestration to complete an entire business process.</span></span>  
  
 <span data-ttu-id="03429-115">**Publicar servicios Web**</span><span class="sxs-lookup"><span data-stu-id="03429-115">**Publishing Web services**</span></span>  
  
 <span data-ttu-id="03429-116">Se pueden publicar servicios Web mediante el Asistente para publicar servicios Web de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="03429-116">You can publish Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="03429-117">Las orquestaciones y los adaptadores de envío pueden usar estos servicios Web publicados.</span><span class="sxs-lookup"><span data-stu-id="03429-117">Orchestrations and send adapters can use these published Web services.</span></span>  
  
 <span data-ttu-id="03429-118">**Usar encabezados SOAP**</span><span class="sxs-lookup"><span data-stu-id="03429-118">**Using SOAP headers**</span></span>  
  
 <span data-ttu-id="03429-119">BizTalk Server proporciona compatibilidad para encabezados SOAP definidos y desconocidos.</span><span class="sxs-lookup"><span data-stu-id="03429-119">BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="03429-120">BizTalk Server crea una propiedad de contexto para cada encabezado SOAP definido en el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="03429-120">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
 <span data-ttu-id="03429-121">**Estándares de servicios Web**</span><span class="sxs-lookup"><span data-stu-id="03429-121">**Web Services standards**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="03429-122"> debe trabajar con los estándares de servicios web al enviar y recibir.</span><span class="sxs-lookup"><span data-stu-id="03429-122"> should work with any Web Services standards when sending and receiving.</span></span> <span data-ttu-id="03429-123">No todos los estándares se han probado.</span><span class="sxs-lookup"><span data-stu-id="03429-123">Not all standards have been tested.</span></span> <span data-ttu-id="03429-124">Normalmente, los estándares admitidos por WCF también son compatibles con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03429-124">Typically, the standards supported by WCF are also supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="03429-125">Los estándares de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="03429-125">Sample standards include:</span></span>  
  
-   <span data-ttu-id="03429-126">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="03429-126">WS-ReliableMessaging</span></span>  
  
-   <span data-ttu-id="03429-127">WS-Security</span><span class="sxs-lookup"><span data-stu-id="03429-127">WS-Security</span></span>  
  
-   <span data-ttu-id="03429-128">WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="03429-128">WS-SecureConversation</span></span>  
  
-   <span data-ttu-id="03429-129">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="03429-129">WS-Trust</span></span>  
  
-   <span data-ttu-id="03429-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="03429-130">WS-Federation</span></span>  
  
-   <span data-ttu-id="03429-131">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="03429-131">WS-Addressing</span></span>  
  
-   <span data-ttu-id="03429-132">WS-Policy</span><span class="sxs-lookup"><span data-stu-id="03429-132">WS-Policy</span></span>  
  
-   <span data-ttu-id="03429-133">WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="03429-133">WS-MetadataExchange</span></span>  
  
-   <span data-ttu-id="03429-134">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="03429-134">WS-Coordination</span></span>  
  
-   <span data-ttu-id="03429-135">WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="03429-135">WS-Atomic</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03429-136">En esta sección</span><span class="sxs-lookup"><span data-stu-id="03429-136">In This Section</span></span>  
  
-   [<span data-ttu-id="03429-137">Consumir servicios Web</span><span class="sxs-lookup"><span data-stu-id="03429-137">Consuming Web Services</span></span>](../core/consuming-web-services.md)  
  
-   [<span data-ttu-id="03429-138">Publicar servicios Web</span><span class="sxs-lookup"><span data-stu-id="03429-138">Publishing Web Services</span></span>](../core/publishing-web-services.md)  
  
-   [<span data-ttu-id="03429-139">Usar encabezados SOAP</span><span class="sxs-lookup"><span data-stu-id="03429-139">Using SOAP Headers</span></span>](../core/using-soap-headers.md)