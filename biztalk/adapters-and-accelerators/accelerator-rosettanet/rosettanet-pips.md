---
title: PIP de RosettaNet | Documentos de Microsoft
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
ms.openlocfilehash: 1980f7c5e22259dc6c09d4f2d8dba31f3ac04d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210796"
---
# <a name="rosettanet-pips"></a><span data-ttu-id="9b2d3-102">PIP de RosettaNet</span><span class="sxs-lookup"><span data-stu-id="9b2d3-102">RosettaNet PIPs</span></span>
<span data-ttu-id="9b2d3-103">La organización RosettaNet crea y mantiene los procesos de interfaz de socio (PIP) para proporcionar las definiciones de procesos empresariales comunes para todos los intercambios de mensajes de RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="9b2d3-104">Cada especificación de PIP proporciona un archivo de definición (DTD) de tipo de documento y un documento de instrucciones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="9b2d3-105">El archivo DTD define la estructura del mensaje de contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="9b2d3-106">El documento de instrucciones de mensaje, que es un archivo HTML legible, especifica las restricciones de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="9b2d3-107">En conjunto, proporcionan una definición completa del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="9b2d3-108">Para obtener más información acerca de las especificaciones de PIP, vea el sitio RosettaNet Web en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span><span class="sxs-lookup"><span data-stu-id="9b2d3-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="9b2d3-109">Contenido PIP</span><span class="sxs-lookup"><span data-stu-id="9b2d3-109">PIP Contents</span></span>  
 <span data-ttu-id="9b2d3-110">Una especificación de PIP hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b2d3-110">A PIP specification does the following:</span></span>  
  
-   <span data-ttu-id="9b2d3-111">Describe qué modelo de proceso público implementa</span><span class="sxs-lookup"><span data-stu-id="9b2d3-111">Describes which public process pattern it implements</span></span>  
  
-   <span data-ttu-id="9b2d3-112">Describe cómo configurar el proceso público</span><span class="sxs-lookup"><span data-stu-id="9b2d3-112">Describes how to configure the public process</span></span>  
  
-   <span data-ttu-id="9b2d3-113">Proporciona referencias a los documentos que se va a intercambiar en el PIP</span><span class="sxs-lookup"><span data-stu-id="9b2d3-113">Provides references to the documents to exchange within the PIP</span></span>  
  
 <span data-ttu-id="9b2d3-114">Una especificación de PIP incluye tres componentes principales: una vista operativa de negocios (BOV), vista de servicio funcional (FSV) y una vista de marco de trabajo de implementación (IFV).</span><span class="sxs-lookup"><span data-stu-id="9b2d3-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="9b2d3-115">Cada una de estas vistas especifica las restricciones de nivel de elemento:</span><span class="sxs-lookup"><span data-stu-id="9b2d3-115">Each of these views specifies element-level constraints:</span></span>  
  
-   <span data-ttu-id="9b2d3-116">El BOV especifica la semántica de las entidades de datos empresariales y el flujo de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="9b2d3-117">Se describen el inicio y estados finales y roles de asociado.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="9b2d3-118">Describe la interacción entre los roles y detalles de la seguridad, auditoría y controles de proceso.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="9b2d3-119">Especifica los documentos empresariales y entidades de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-119">It specifies the business documents and business data entities.</span></span>  
  
-   <span data-ttu-id="9b2d3-120">El FSV especifica las interacciones, agentes y servicios de componentes de red.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="9b2d3-121">Proporciona el diseño de componentes de red necesario para ejecutar el PIP y describe las interacciones de componente de red posible.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
-   <span data-ttu-id="9b2d3-122">El IFV especifica los formatos de mensaje de protocolo de red y los requisitos de comunicación necesarios para ejecutar el PIP.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="9b2d3-123">Clústeres y segmentos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-123">Clusters and Segments</span></span>  
 <span data-ttu-id="9b2d3-124">Categorizar PIP en una función de negocio de alto nivel (clúster) y una subfunción (segmento).</span><span class="sxs-lookup"><span data-stu-id="9b2d3-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="9b2d3-125">Clústeres y segmentos de organizan los mensajes empresariales en categorías reconocibles.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="9b2d3-126">En la tabla siguiente enumera estos clústeres y segmentos.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="9b2d3-127">Clusters</span><span class="sxs-lookup"><span data-stu-id="9b2d3-127">Clusters</span></span>|<span data-ttu-id="9b2d3-128">Segmentos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="9b2d3-129">0: compatibilidad con RosettaNet</span><span class="sxs-lookup"><span data-stu-id="9b2d3-129">0: RosettaNet Support</span></span>|<span data-ttu-id="9b2d3-130">0a: administrativas</span><span class="sxs-lookup"><span data-stu-id="9b2d3-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="9b2d3-131">0c: prueba</span><span class="sxs-lookup"><span data-stu-id="9b2d3-131">0C: Testing</span></span>|  
|<span data-ttu-id="9b2d3-132">1: producto de socios comerciales y revisión de servicio</span><span class="sxs-lookup"><span data-stu-id="9b2d3-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="9b2d3-133">1a: revisión de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="9b2d3-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="9b2d3-134">1b: producto y revisión de servicio</span><span class="sxs-lookup"><span data-stu-id="9b2d3-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="9b2d3-135">2: obtener información de producto</span><span class="sxs-lookup"><span data-stu-id="9b2d3-135">2: Product Information</span></span>|<span data-ttu-id="9b2d3-136">2a: preparación para la distribución</span><span class="sxs-lookup"><span data-stu-id="9b2d3-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="9b2d3-137">2b: notificación de cambio de producto</span><span class="sxs-lookup"><span data-stu-id="9b2d3-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="9b2d3-138">2c: información de diseño del producto</span><span class="sxs-lookup"><span data-stu-id="9b2d3-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="9b2d3-139">2D: colaboración diseño e ingeniería</span><span class="sxs-lookup"><span data-stu-id="9b2d3-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="9b2d3-140">3: administración de pedidos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-140">3: Order Management</span></span>|<span data-ttu-id="9b2d3-141">3a: oferta & de entrada de pedidos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="9b2d3-142">3B: transporte & distribución</span><span class="sxs-lookup"><span data-stu-id="9b2d3-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="9b2d3-143">3C: devuelve el identificador & Finanzas</span><span class="sxs-lookup"><span data-stu-id="9b2d3-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="9b2d3-144">3D: configuración del producto</span><span class="sxs-lookup"><span data-stu-id="9b2d3-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="9b2d3-145">4: administración de inventario</span><span class="sxs-lookup"><span data-stu-id="9b2d3-145">4: Inventory Management</span></span>|<span data-ttu-id="9b2d3-146">4a: previsión colaboración</span><span class="sxs-lookup"><span data-stu-id="9b2d3-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="9b2d3-147">4b: asignación de inventario</span><span class="sxs-lookup"><span data-stu-id="9b2d3-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="9b2d3-148">4c: informes de inventario</span><span class="sxs-lookup"><span data-stu-id="9b2d3-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="9b2d3-149">4d: la reposición del inventario</span><span class="sxs-lookup"><span data-stu-id="9b2d3-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="9b2d3-150">4E: informes de ventas</span><span class="sxs-lookup"><span data-stu-id="9b2d3-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="9b2d3-151">4F: protección de precios</span><span class="sxs-lookup"><span data-stu-id="9b2d3-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="9b2d3-152">5: administración de la información de marketing</span><span class="sxs-lookup"><span data-stu-id="9b2d3-152">5: Marketing Information Management</span></span>|<span data-ttu-id="9b2d3-153">5a: gestión de oportunidad de clientes potenciales</span><span class="sxs-lookup"><span data-stu-id="9b2d3-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="9b2d3-154">5b: administración de campañas de Marketing</span><span class="sxs-lookup"><span data-stu-id="9b2d3-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="9b2d3-155">6: servicio y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9b2d3-155">6: Service and Support</span></span>|<span data-ttu-id="9b2d3-156">6a: proporcionar y administrar garantías, paquetes de servicio y un contrato de servicios</span><span class="sxs-lookup"><span data-stu-id="9b2d3-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="9b2d3-157">6b: proporcionar y administrar la administración de activos (combinado con 6A)</span><span class="sxs-lookup"><span data-stu-id="9b2d3-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="9b2d3-158">6c: administración del servicio y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="9b2d3-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="9b2d3-159">7: fabricación</span><span class="sxs-lookup"><span data-stu-id="9b2d3-159">7: Manufacturing</span></span>|<span data-ttu-id="9b2d3-160">7a: transferencia de diseño</span><span class="sxs-lookup"><span data-stu-id="9b2d3-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="9b2d3-161">7b: administrar fabricación WO & WIP</span><span class="sxs-lookup"><span data-stu-id="9b2d3-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="9b2d3-162">7C: distribuir información de fabricación</span><span class="sxs-lookup"><span data-stu-id="9b2d3-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="9b2d3-163">Cada segmento incluye un número de mensaje específico PIP.</span><span class="sxs-lookup"><span data-stu-id="9b2d3-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="9b2d3-164">Por ejemplo, el PIP 3A4 pertenece el grupo de administración de pedidos (clúster 3) y el segmento de oferta y Order Entry (segmento A de clúster 3).</span><span class="sxs-lookup"><span data-stu-id="9b2d3-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="9b2d3-165">Este segmento incluye otros PIP mensaje relacionado, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9b2d3-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="9b2d3-166">Grupo 3: Administración de pedidos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="9b2d3-167">Oferta de segmento r: y entrada de pedidos</span><span class="sxs-lookup"><span data-stu-id="9b2d3-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="9b2d3-168">PIP 3A1: oferta de solicitud</span><span class="sxs-lookup"><span data-stu-id="9b2d3-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="9b2d3-169">PIP 3A2: solicitud de precio y disponibilidad</span><span class="sxs-lookup"><span data-stu-id="9b2d3-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="9b2d3-170">PIP 3A3: solicitud de transferencia de carro de la compra</span><span class="sxs-lookup"><span data-stu-id="9b2d3-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="9b2d3-171">PIP 3A4: administrar el pedido de compra</span><span class="sxs-lookup"><span data-stu-id="9b2d3-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="9b2d3-172">PIP 3A5: consultar el estado del pedido</span><span class="sxs-lookup"><span data-stu-id="9b2d3-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="9b2d3-173">PIP 3A6: distribuir el estado del pedido</span><span class="sxs-lookup"><span data-stu-id="9b2d3-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="9b2d3-174">…</span><span class="sxs-lookup"><span data-stu-id="9b2d3-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2d3-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b2d3-175">See Also</span></span>  
 <span data-ttu-id="9b2d3-176">[RosettaNet y CIDX estándares de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="9b2d3-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="9b2d3-177">Estándar RNIF</span><span class="sxs-lookup"><span data-stu-id="9b2d3-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)