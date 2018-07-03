---
title: Las operaciones que son compatibles con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing by using the adapter
ms.assetid: 800cf44b-357f-4850-8878-f49ceb549adf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3f080cedb74210d02806681b6c9e20656d3d09e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004781"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a><span data-ttu-id="cc203-102">Las operaciones que son compatibles con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="cc203-102">What operations are supported by the Siebel adapter</span></span>
<span data-ttu-id="cc203-103">Los clientes del adaptador pueden realizar operaciones en el sistema de Siebel, ya sea por:</span><span class="sxs-lookup"><span data-stu-id="cc203-103">Adapter clients can perform operations on the Siebel system by either:</span></span>  
  
- <span data-ttu-id="cc203-104">Crear proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cc203-104">Creating BizTalk projects.</span></span>  
  
- <span data-ttu-id="cc203-105">Mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="cc203-105">Using the WCF channel model.</span></span>  
  
- <span data-ttu-id="cc203-106">Mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="cc203-106">Using the WCF service model.</span></span>  
  
  <span data-ttu-id="cc203-107">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cc203-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="cc203-108">Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="cc203-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="cc203-109">Si se requiere una respuesta, se devuelve en un mensaje SOAP a través del canal mismo.</span><span class="sxs-lookup"><span data-stu-id="cc203-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="cc203-110">Para obtener información acerca de la estructura del mensaje y la acción de SOAP asociada con cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="cc203-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>  
  
  <span data-ttu-id="cc203-111">Esta sección proporciona información acerca de las operaciones admitidas en el sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc203-111">This section provides information about the operations supported on the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc203-112">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite la recepción de las llamadas entrantes de un sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="cc203-112">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support receiving inbound calls from a Siebel system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc203-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cc203-113">In This Section</span></span>  
  
-   [<span data-ttu-id="cc203-114">Operaciones en componentes empresariales de Siebel</span><span class="sxs-lookup"><span data-stu-id="cc203-114">Operations on Business Components in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [<span data-ttu-id="cc203-115">Operaciones en servicios empresariales de Siebel</span><span class="sxs-lookup"><span data-stu-id="cc203-115">Operations on Business Services in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc203-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc203-116">See Also</span></span>  
 [<span data-ttu-id="cc203-117">Información general del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel</span><span class="sxs-lookup"><span data-stu-id="cc203-117">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)