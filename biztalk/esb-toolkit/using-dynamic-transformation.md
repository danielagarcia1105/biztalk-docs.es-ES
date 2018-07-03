---
title: Mediante la transformación dinámica | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb83c4dc90a513367d2c914dc546eb0fd931d67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006139"
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="61bd2-102">Uso de la transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="61bd2-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="61bd2-103">Información general</span><span class="sxs-lookup"><span data-stu-id="61bd2-103">Overview</span></span>  
 <span data-ttu-id="61bd2-104">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite tres mecanismos para la transformación dinámica:</span><span class="sxs-lookup"><span data-stu-id="61bd2-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
- <span data-ttu-id="61bd2-105">Un agente de la transformación dinámica implementado como una orquestación</span><span class="sxs-lookup"><span data-stu-id="61bd2-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
- <span data-ttu-id="61bd2-106">Un servicio Web de la transformación dinámica que incluye con el núcleo de servicios Web</span><span class="sxs-lookup"><span data-stu-id="61bd2-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
- <span data-ttu-id="61bd2-107">Transformaciones que se ejecutan los componentes de canalización ESB</span><span class="sxs-lookup"><span data-stu-id="61bd2-107">Transformations executed by ESB pipeline components</span></span>  
  
  <span data-ttu-id="61bd2-108">En esta sección se centra en el agente de transformación que se implementa como una orquestación.</span><span class="sxs-lookup"><span data-stu-id="61bd2-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="61bd2-109">Para obtener información acerca de la transformación del servicio Web, consulte [mediante los servicios Web de BizTalk ESB Toolkit](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="61bd2-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="61bd2-110">Para obtener información acerca de los componentes de canalización del distribuidor de ESB, consulte [mediante los componentes de soporte técnico de canalización](../esb-toolkit/using-the-pipeline-support-components.md).</span><span class="sxs-lookup"><span data-stu-id="61bd2-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="61bd2-111">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="61bd2-111">How It Works</span></span>  
 <span data-ttu-id="61bd2-112">El agente de entrega de la transformación es una orquestación que se suscribe a mensajes donde la **nombre** atributo del elemento actual **ServiceInstance** es el elemento en el itinerario  **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="61bd2-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="61bd2-113">El agente realiza la siguiente secuencia de operaciones:</span><span class="sxs-lookup"><span data-stu-id="61bd2-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="61bd2-114">Recibe un mensaje sin tipo (System.Xml.XmlDocument).</span><span class="sxs-lookup"><span data-stu-id="61bd2-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="61bd2-115">Si el nombre de la asignación está disponible como un valor estático en el itinerario, el agente intenta resolver el nombre de la asignación mediante el Administrador de resolución.</span><span class="sxs-lookup"><span data-stu-id="61bd2-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="61bd2-116">Aplica la asignación adecuada para el mensaje de origen de entrada.</span><span class="sxs-lookup"><span data-stu-id="61bd2-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="61bd2-117">Publica la salida de mapa en la base de datos de cuadro de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="61bd2-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="61bd2-118">Cómo configurar la transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="61bd2-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="61bd2-119">Para obtener más información sobre cómo configurar la transformación dinámica con el Diseñador de itinerario, consulte [crear itinerarios usar diseñador de itinerario](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span><span class="sxs-lookup"><span data-stu-id="61bd2-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="61bd2-120">Errores de transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="61bd2-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="61bd2-121">El mecanismo de transformación dinámica creará y publicará un mensaje de error ESB en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="61bd2-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
- <span data-ttu-id="61bd2-122">El componente de resolución no puede determinar que se asignan a aplicar.</span><span class="sxs-lookup"><span data-stu-id="61bd2-122">The resolver component cannot determine which map to apply.</span></span>  
  
- <span data-ttu-id="61bd2-123">La asignación especificada no está disponible (por ejemplo, ha especificado un tipo de asignación incorrecta o un mapa no ha implementado todavía en BizTalk Server 2009).</span><span class="sxs-lookup"><span data-stu-id="61bd2-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
- <span data-ttu-id="61bd2-124">Se produce un error durante la asignación (por ejemplo, el documento de origen no es del tipo de origen correctos o las referencias de mapa no se implementa una función personalizada en un ensamblado externo a BizTalk).</span><span class="sxs-lookup"><span data-stu-id="61bd2-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
- <span data-ttu-id="61bd2-125">Se produce una excepción durante la resolución de just-in-time (JIT) del tipo de mapa.</span><span class="sxs-lookup"><span data-stu-id="61bd2-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
- <span data-ttu-id="61bd2-126">No existe ningún suscriptor para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="61bd2-126">No subscriber exists for the output message.</span></span>  
  
- <span data-ttu-id="61bd2-127">Se produce cualquier excepción del sistema.</span><span class="sxs-lookup"><span data-stu-id="61bd2-127">Any system exception occurs.</span></span>  
  
  <span data-ttu-id="61bd2-128">Es responsabilidad del desarrollador para proporcionar la información de contexto utilizada para rellenar los mensajes de excepción y crear controladores para reaccionar a la excepción.</span><span class="sxs-lookup"><span data-stu-id="61bd2-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="61bd2-129">Está disponible automáticamente algunos de los datos y un controlador genérico recogerá el mensaje de excepción si no hay ningún controlador de destino está especificado o disponible.</span><span class="sxs-lookup"><span data-stu-id="61bd2-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="61bd2-130">Para obtener más información sobre el control de excepciones de la transformación dinámica, consulte [usando administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).</span><span class="sxs-lookup"><span data-stu-id="61bd2-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>