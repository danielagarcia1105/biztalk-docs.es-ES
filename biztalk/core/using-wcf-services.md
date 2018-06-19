---
title: Uso de servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287796"
---
# <a name="using-wcf-services"></a><span data-ttu-id="93056-102">usar los Servicios WCF</span><span class="sxs-lookup"><span data-stu-id="93056-102">Using WCF Services</span></span>
<span data-ttu-id="93056-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad integrada para Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="93056-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Windows Communication Foundation (WCF).</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="93056-104">permite reutilizar y agregar todos los servicios WCF existentes en las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="93056-104"> enables you to reuse and aggregate all your existing WCF services within your orchestrations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="93056-105">También incorpora compatibilidad con adaptadores nativos en servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="93056-105"> also implements support for native adapters in WCF services.</span></span> <span data-ttu-id="93056-106">La compatibilidad con adaptadores nativos proporciona escalabilidad, tolerancia a errores y capacidades de seguimiento para servicios WCF sin tener que escribir código.</span><span class="sxs-lookup"><span data-stu-id="93056-106">Native adapter support provides scalability, fault tolerance, and tracking capabilities for WCF services without requiring you to write code.</span></span> <span data-ttu-id="93056-107">Para obtener información acerca de los adaptadores WCF, vea [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="93056-107">For information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
 <span data-ttu-id="93056-108">Compatibilidad en los servicios WCF [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se divide en dos categorías: publicación o creación de servicios WCF, o una llamada a o consumir servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="93056-108">The WCF services support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] falls into two categories: publishing or creating WCF services, or calling or consuming WCF services.</span></span>  
  
 <span data-ttu-id="93056-109">**Publicar servicios WCF**</span><span class="sxs-lookup"><span data-stu-id="93056-109">**Publishing WCF services**</span></span>  
  
 <span data-ttu-id="93056-110">Puede publicar (exponer) orquestaciones y esquemas como servicios WCF con los adaptadores de WCF para diferenciar la lógica de servicios WCF de la lógica de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="93056-110">You can publish (expose) your orchestrations and schemas as WCF services with the WCF adapters to separate the WCF service logic from the business process logic.</span></span> <span data-ttu-id="93056-111">Para adaptadores aislados de WCF, puede usar el Asistente para publicación de Servicio WCF de BizTalk para crear ubicaciones aisladas de recepción WCF alojadas en aplicaciones Web que se ejecutan en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="93056-111">For isolated WCF adapters, you can use the BizTalk WCF Service Publishing Wizard to create isolated WCF receive locations hosted by Web applications running in Internet Information Services (IIS).</span></span> <span data-ttu-id="93056-112">Para los adaptadores de WCF de tipo En curso, puede publicar metadatos de servicio para cualquier ubicación WCF con el Asistente para publicación de Servicio WCF de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="93056-112">For the in-process WCF adapters, you can publish service metadata for any WCF locations with the BizTalk WCF Service Publishing Wizard.</span></span>  <span data-ttu-id="93056-113">La publicación de metadatos permite la creación de código de cliente mediante la utilidad svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="93056-113">The publishing of metadata allows the creation of client code using the svcutil.exe utility.</span></span>  
  
 <span data-ttu-id="93056-114">**Consumir servicios WCF**</span><span class="sxs-lookup"><span data-stu-id="93056-114">**Consuming WCF services**</span></span>  
  
 <span data-ttu-id="93056-115">Puede usar el Asistente para consumición del Servicio WCF de BizTalk para generar los artefactos de BizTalk, como tipos y orquestaciones de BizTalk, necesarios para consumir un Servicio WCF basado en el documento de metadatos del Servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="93056-115">You can use the BizTalk WCF Service Consuming Wizard to generate the BizTalk artifacts, such as BizTalk orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span> <span data-ttu-id="93056-116">Lo metadatos permiten que un puerto de envío tenga acceso a un servicio externo como cliente.</span><span class="sxs-lookup"><span data-stu-id="93056-116">Metadata allows a send port to access an external service as a client.</span></span> <span data-ttu-id="93056-117">Los metadatos se usan exclusivamente para describir la dirección de extremo, enlace y contrato.</span><span class="sxs-lookup"><span data-stu-id="93056-117">Metadata is used purely for describing the endpoint address, binding, and contract.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93056-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="93056-118">In This Section</span></span>  
  
-   [<span data-ttu-id="93056-119">Publicar servicios WCF</span><span class="sxs-lookup"><span data-stu-id="93056-119">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="93056-120">Consumir servicios WCF</span><span class="sxs-lookup"><span data-stu-id="93056-120">Consuming WCF Services</span></span>](../core/consuming-wcf-services.md)  
  
-   [<span data-ttu-id="93056-121">Especificar el cuerpo del mensaje para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="93056-121">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="93056-122">Tutoriales del adaptador WCF</span><span class="sxs-lookup"><span data-stu-id="93056-122">WCF Adapter Walkthroughs</span></span>](../core/wcf-adapter-walkthroughs.md)