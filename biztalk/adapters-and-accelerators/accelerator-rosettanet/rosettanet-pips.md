---
title: PIP de RosettaNet | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8891979352ce47e18c8cfda80162b3683002c6f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989253"
---
# <a name="rosettanet-pips"></a><span data-ttu-id="e611b-102">PIP de RosettaNet</span><span class="sxs-lookup"><span data-stu-id="e611b-102">RosettaNet PIPs</span></span>
<span data-ttu-id="e611b-103">La organización RosettaNet crea y mantiene los procesos de interfaz de socio (PIP) para proporcionar las definiciones de procesos empresariales comunes para todos los intercambios de mensajes de RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="e611b-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="e611b-104">Cada especificación de PIP proporciona un archivo de definición (DTD) de tipo de documento y un documento de guía de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e611b-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="e611b-105">El archivo DTD define la estructura del mensaje de contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="e611b-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="e611b-106">El documento de instrucciones del mensaje, que es un archivo HTML legible, especifica las restricciones de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="e611b-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="e611b-107">Juntos, proporcionan una definición completa del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="e611b-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="e611b-108">Para obtener más información acerca de las especificaciones de PIP, vea el sitio RosettaNet Web en [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859).</span><span class="sxs-lookup"><span data-stu-id="e611b-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="e611b-109">Contenido PIP</span><span class="sxs-lookup"><span data-stu-id="e611b-109">PIP Contents</span></span>  
 <span data-ttu-id="e611b-110">Una especificación de PIP hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e611b-110">A PIP specification does the following:</span></span>  
  
- <span data-ttu-id="e611b-111">Describe qué modelo de proceso público implementa</span><span class="sxs-lookup"><span data-stu-id="e611b-111">Describes which public process pattern it implements</span></span>  
  
- <span data-ttu-id="e611b-112">Describe cómo configurar el proceso público</span><span class="sxs-lookup"><span data-stu-id="e611b-112">Describes how to configure the public process</span></span>  
  
- <span data-ttu-id="e611b-113">Proporciona referencias a los documentos que se van a intercambiar dentro del PIP</span><span class="sxs-lookup"><span data-stu-id="e611b-113">Provides references to the documents to exchange within the PIP</span></span>  
  
  <span data-ttu-id="e611b-114">Una especificación de PIP incluye tres partes principales: vista operativa de negocio (BOV), vista de servicio funcional (FSV) y una vista de marco de trabajo de implementación (IFV).</span><span class="sxs-lookup"><span data-stu-id="e611b-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="e611b-115">Cada una de estas vistas especifica restricciones de nivel de elemento:</span><span class="sxs-lookup"><span data-stu-id="e611b-115">Each of these views specifies element-level constraints:</span></span>  
  
- <span data-ttu-id="e611b-116">El BOV especifica la semántica de las entidades de datos empresariales y el flujo de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e611b-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="e611b-117">Describe el inicio y estados finales y roles de asociado.</span><span class="sxs-lookup"><span data-stu-id="e611b-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="e611b-118">Describe la interacción entre los roles y detalles de la seguridad, auditoría y controles del proceso.</span><span class="sxs-lookup"><span data-stu-id="e611b-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="e611b-119">Especifica los documentos empresariales y las entidades de datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="e611b-119">It specifies the business documents and business data entities.</span></span>  
  
- <span data-ttu-id="e611b-120">El FSV especifica las interacciones, agentes y servicios de componentes de red.</span><span class="sxs-lookup"><span data-stu-id="e611b-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="e611b-121">Proporciona el diseño del componente de red necesario para ejecutar el PIP y se describen las interacciones del componente de red posible.</span><span class="sxs-lookup"><span data-stu-id="e611b-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
- <span data-ttu-id="e611b-122">El IFV especifica los formatos de mensaje de protocolo de red y los requisitos de comunicación necesarios para ejecutar el PIP.</span><span class="sxs-lookup"><span data-stu-id="e611b-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="e611b-123">Clústeres y segmentos</span><span class="sxs-lookup"><span data-stu-id="e611b-123">Clusters and Segments</span></span>  
 <span data-ttu-id="e611b-124">Clasifique PIP por una función de negocio de alto nivel (clúster) y una subfunción (segmento).</span><span class="sxs-lookup"><span data-stu-id="e611b-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="e611b-125">Clústeres y segmentos de organizan los mensajes empresariales en categorías reconocibles.</span><span class="sxs-lookup"><span data-stu-id="e611b-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="e611b-126">En la tabla siguiente se enumera estos segmentos y clústeres.</span><span class="sxs-lookup"><span data-stu-id="e611b-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="e611b-127">Clusters</span><span class="sxs-lookup"><span data-stu-id="e611b-127">Clusters</span></span>|<span data-ttu-id="e611b-128">Segmentos</span><span class="sxs-lookup"><span data-stu-id="e611b-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="e611b-129">0: soporte técnico de RosettaNet</span><span class="sxs-lookup"><span data-stu-id="e611b-129">0: RosettaNet Support</span></span>|<span data-ttu-id="e611b-130">0a: administrativas</span><span class="sxs-lookup"><span data-stu-id="e611b-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="e611b-131">0c: pruebas</span><span class="sxs-lookup"><span data-stu-id="e611b-131">0C: Testing</span></span>|  
|<span data-ttu-id="e611b-132">1: revisión de servicios y productos de asociados</span><span class="sxs-lookup"><span data-stu-id="e611b-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="e611b-133">1a: revisión de asociados</span><span class="sxs-lookup"><span data-stu-id="e611b-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="e611b-134">1b: revisión de servicios y productos</span><span class="sxs-lookup"><span data-stu-id="e611b-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="e611b-135">2: información del producto</span><span class="sxs-lookup"><span data-stu-id="e611b-135">2: Product Information</span></span>|<span data-ttu-id="e611b-136">2a: preparación para la distribución</span><span class="sxs-lookup"><span data-stu-id="e611b-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="e611b-137">2b: notificación de cambio de producto</span><span class="sxs-lookup"><span data-stu-id="e611b-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="e611b-138">2c: información de diseño del producto</span><span class="sxs-lookup"><span data-stu-id="e611b-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="e611b-139">2D: colaboración diseño e ingeniería</span><span class="sxs-lookup"><span data-stu-id="e611b-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="e611b-140">3: administración de pedidos</span><span class="sxs-lookup"><span data-stu-id="e611b-140">3: Order Management</span></span>|<span data-ttu-id="e611b-141">3a: oferta & entrada de pedidos</span><span class="sxs-lookup"><span data-stu-id="e611b-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="e611b-142">3B: transporte de & distribución</span><span class="sxs-lookup"><span data-stu-id="e611b-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="e611b-143">3C: devuelve y finanzas</span><span class="sxs-lookup"><span data-stu-id="e611b-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="e611b-144">3D: configuración del producto</span><span class="sxs-lookup"><span data-stu-id="e611b-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="e611b-145">4: administración del inventario</span><span class="sxs-lookup"><span data-stu-id="e611b-145">4: Inventory Management</span></span>|<span data-ttu-id="e611b-146">4a: previsión de colaboración</span><span class="sxs-lookup"><span data-stu-id="e611b-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="e611b-147">4b: asignación de inventario</span><span class="sxs-lookup"><span data-stu-id="e611b-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="e611b-148">4c: informes de inventario</span><span class="sxs-lookup"><span data-stu-id="e611b-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="e611b-149">4d: la reposición del inventario</span><span class="sxs-lookup"><span data-stu-id="e611b-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="e611b-150">4E: informes de ventas</span><span class="sxs-lookup"><span data-stu-id="e611b-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="e611b-151">4F: protección de precios</span><span class="sxs-lookup"><span data-stu-id="e611b-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="e611b-152">5: administración de la información de marketing</span><span class="sxs-lookup"><span data-stu-id="e611b-152">5: Marketing Information Management</span></span>|<span data-ttu-id="e611b-153">5a: administración de oportunidades de clientes potenciales</span><span class="sxs-lookup"><span data-stu-id="e611b-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="e611b-154">5b: administración de campañas de Marketing</span><span class="sxs-lookup"><span data-stu-id="e611b-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="e611b-155">6: servicio y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e611b-155">6: Service and Support</span></span>|<span data-ttu-id="e611b-156">6a: proporcionar y administrar las garantías, paquetes de servicio y contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="e611b-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="e611b-157">6b: proporcionar y administrar la administración de activos (combinada con 6A)</span><span class="sxs-lookup"><span data-stu-id="e611b-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="e611b-158">6c: soporte técnico y administración de servicios</span><span class="sxs-lookup"><span data-stu-id="e611b-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="e611b-159">7: de fabricación</span><span class="sxs-lookup"><span data-stu-id="e611b-159">7: Manufacturing</span></span>|<span data-ttu-id="e611b-160">7a: transferencia de diseño</span><span class="sxs-lookup"><span data-stu-id="e611b-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="e611b-161">7b: administrar fabricación WO & WIP</span><span class="sxs-lookup"><span data-stu-id="e611b-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="e611b-162">7C: distribuir información de fabricación</span><span class="sxs-lookup"><span data-stu-id="e611b-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="e611b-163">Cada segmento incluye una serie de PIP de mensaje específico.</span><span class="sxs-lookup"><span data-stu-id="e611b-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="e611b-164">Por ejemplo, el PIP de 3A4 es una parte del clúster de administración de pedidos (clúster de 3) y el segmento de oferta y entrada de pedidos (segmento una del clúster de 3).</span><span class="sxs-lookup"><span data-stu-id="e611b-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="e611b-165">Este segmento incluye otros PIP mensajes relacionados, como sigue:</span><span class="sxs-lookup"><span data-stu-id="e611b-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="e611b-166">Clúster de 3: Administración de pedidos</span><span class="sxs-lookup"><span data-stu-id="e611b-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="e611b-167">Segmento r: Quote y entrada de pedidos</span><span class="sxs-lookup"><span data-stu-id="e611b-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="e611b-168">PIP 3A1: oferta de solicitud</span><span class="sxs-lookup"><span data-stu-id="e611b-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="e611b-169">PIP 3A2: solicitud de precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="e611b-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="e611b-170">PIP 3A3: solicitud de transferencia de carro de la compra</span><span class="sxs-lookup"><span data-stu-id="e611b-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="e611b-171">PIP 3A4: administrar pedido de compra</span><span class="sxs-lookup"><span data-stu-id="e611b-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="e611b-172">PIP 3A5: consultar el estado del pedido</span><span class="sxs-lookup"><span data-stu-id="e611b-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="e611b-173">PIP 3A6: distribuir el estado del pedido</span><span class="sxs-lookup"><span data-stu-id="e611b-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="e611b-174">…</span><span class="sxs-lookup"><span data-stu-id="e611b-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e611b-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="e611b-175">See Also</span></span>  
 <span data-ttu-id="e611b-176">[RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="e611b-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="e611b-177">Estándar RNIF</span><span class="sxs-lookup"><span data-stu-id="e611b-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)