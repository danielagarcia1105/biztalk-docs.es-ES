---
title: "Publicar una orquestación como servicio Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- orchestrations, Web services
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, prerequisites
- orchestrations, publishing
ms.assetid: f209310d-c265-4c37-8424-c9b287e713ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b6d36f6c56851bfedcd522f96d01a8256232826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-an-orchestration-as-a-web-service"></a><span data-ttu-id="3b86f-102">Publicar una orquestación como un servicio web</span><span class="sxs-lookup"><span data-stu-id="3b86f-102">Publishing an Orchestration as a Web Service</span></span>
<span data-ttu-id="3b86f-103">El Asistente para publicar servicios Web de BizTalk se utiliza para publicar orquestaciones como servicios Web.</span><span class="sxs-lookup"><span data-stu-id="3b86f-103">You use the BizTalk Web Services Publishing Wizard to publish an orchestration as a Web service.</span></span> <span data-ttu-id="3b86f-104">El asistente crea un servicio Web basado en una orquestación en un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3b86f-104">The wizard creates a Web service based on an orchestration in a BizTalk assembly.</span></span> <span data-ttu-id="3b86f-105">El asistente le permite seleccionar las orquestaciones y los puertos de recepción para publicarlos como servicios Web.</span><span class="sxs-lookup"><span data-stu-id="3b86f-105">Using the wizard, you select orchestrations and receive ports to publish Web services.</span></span> <span data-ttu-id="3b86f-106">Puede definir espacios de nombre de destino, requisitos de encabezado SOAP y ubicaciones para el proyecto de servicio Web que el asistente genera.</span><span class="sxs-lookup"><span data-stu-id="3b86f-106">You can define target namespaces, SOAP header requirements, and locations for the Web service project the wizard generates.</span></span>  
  
 <span data-ttu-id="3b86f-107">Antes de ejecutar el asistente, es necesario compilar los ensamblados de BizTalk que contienen las orquestaciones y los esquemas que pretende publicar como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="3b86f-107">Before you run the wizard, you must compile your BizTalk assemblies that contain the orchestrations and schemas that you intend to publish as a Web service.</span></span>  
  
 <span data-ttu-id="3b86f-108">Antes de ejecutar al Asistente para publicación de servicios Web de BizTalk, debe habilitar los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="3b86f-108">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="3b86f-109">Para obtener más información acerca de cómo habilitar los servicios Web para su sistema, consulte [habilitar servicios Web](../core/enabling-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b86f-109">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b86f-110">Debe instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] antes de publicar orquestaciones como servicios Web.</span><span class="sxs-lookup"><span data-stu-id="3b86f-110">You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before you can publish an orchestration as a Web service.</span></span> <span data-ttu-id="3b86f-111">No es necesario instalar Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b86f-111">You don't need to install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b86f-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3b86f-112">In This Section</span></span>  
  
-   [<span data-ttu-id="3b86f-113">Cómo asignar orquestaciones a servicios Web</span><span class="sxs-lookup"><span data-stu-id="3b86f-113">How to Map Orchestrations to Web Services</span></span>](../core/how-to-map-orchestrations-to-web-services.md)  
  
-   [<span data-ttu-id="3b86f-114">Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como servicio Web</span><span class="sxs-lookup"><span data-stu-id="3b86f-114">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)  
  
-   [<span data-ttu-id="3b86f-115">Cómo iniciar excepciones SOAP desde orquestaciones publicadas como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="3b86f-115">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>](../core/how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service.md)