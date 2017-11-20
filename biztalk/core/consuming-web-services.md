---
title: Consumir servicios Web | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- orchestrations, Web services
- Web services, consuming
- Web services, orchestrations
ms.assetid: 803ba623-86e7-479a-a4b6-5b576fee8825
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 528f61910dfc5e2d24a40b0ed29a23fcf85a72bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="consuming-web-services"></a><span data-ttu-id="aac9c-102">Consumir servicios web</span><span class="sxs-lookup"><span data-stu-id="aac9c-102">Consuming Web Services</span></span>
<span data-ttu-id="aac9c-103">Consumir servicios Web le permite agregar al proceso empresarial servicios Web existentes.</span><span class="sxs-lookup"><span data-stu-id="aac9c-103">Consuming Web services enables you to add existing Web services to your business process.</span></span> <span data-ttu-id="aac9c-104">Es posible agregar varios servicios Web a una orquestación única.</span><span class="sxs-lookup"><span data-stu-id="aac9c-104">You can aggregate several Web services into a single orchestration.</span></span>  
  
 <span data-ttu-id="aac9c-105">Se puede consumir (llamar) un servicio Web procedente de una orquestación usando puertos Web.</span><span class="sxs-lookup"><span data-stu-id="aac9c-105">You can consume (call) a Web service from your orchestration by using Web ports.</span></span> <span data-ttu-id="aac9c-106">Para consumir un servicio Web desde una orquestación, debe crear un puerto Web y construir mensajes Web.</span><span class="sxs-lookup"><span data-stu-id="aac9c-106">To consume a Web service from an orchestration, you create a Web port and construct Web messages.</span></span>  
  
 <span data-ttu-id="aac9c-107">Puede usar los encabezados SOAP con el servicio Web consumido, cambiar el URI de un servicio Web consumido y establecer el URI de forma dinámica para un servicio Web consumido.</span><span class="sxs-lookup"><span data-stu-id="aac9c-107">You can use SOAP headers with the consumed Web service, change the URI of a consumed Web service, and dynamically set the URI for a consumed Web service.</span></span>  
  
 <span data-ttu-id="aac9c-108">Para obtener información acerca de cómo configurar un SOAP el controlador de recepción, vea [cómo configurar un controlador de recepción de SOAP](../core/how-to-configure-a-soap-receive-handler.md).</span><span class="sxs-lookup"><span data-stu-id="aac9c-108">For information about configuring a SOAP receive handler, see [How to Configure a SOAP Receive Handler](../core/how-to-configure-a-soap-receive-handler.md).</span></span> <span data-ttu-id="aac9c-109">Para obtener información acerca de cómo configurar un SOAP ubicación de recepción, consulte [cómo configurar una ubicación de recepción de SOAP](../core/how-to-configure-a-soap-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="aac9c-109">For information about configuring a SOAP receive location, see [How to Configure a SOAP Receive Location](../core/how-to-configure-a-soap-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aac9c-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aac9c-110">In This Section</span></span>  
  
-   [<span data-ttu-id="aac9c-111">Agregar referencias Web</span><span class="sxs-lookup"><span data-stu-id="aac9c-111">Adding Web References</span></span>](../core/adding-web-references.md)  
  
-   [<span data-ttu-id="aac9c-112">Construcción de mensajes Web</span><span class="sxs-lookup"><span data-stu-id="aac9c-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)  
  
-   [<span data-ttu-id="aac9c-113">Creación de puertos Web</span><span class="sxs-lookup"><span data-stu-id="aac9c-113">Creating Web Ports</span></span>](../core/creating-web-ports.md)  
  
-   [<span data-ttu-id="aac9c-114">Consideraciones al consumir servicios Web</span><span class="sxs-lookup"><span data-stu-id="aac9c-114">Considerations When Consuming Web Services</span></span>](../core/considerations-when-consuming-web-services.md)