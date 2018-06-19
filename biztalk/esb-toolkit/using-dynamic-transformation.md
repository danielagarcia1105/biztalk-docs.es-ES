---
title: Mediante la transformación dinámica | Documentos de Microsoft
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
ms.openlocfilehash: 1d7f6bc57d009e558188950d9bcb0387f808f835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295412"
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="cd858-102">Usar la transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="cd858-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="cd858-103">Información general</span><span class="sxs-lookup"><span data-stu-id="cd858-103">Overview</span></span>  
 <span data-ttu-id="cd858-104">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es compatible con tres mecanismos para la transformación dinámica:</span><span class="sxs-lookup"><span data-stu-id="cd858-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
-   <span data-ttu-id="cd858-105">Un agente de transformación dinámica que se implementa como una orquestación</span><span class="sxs-lookup"><span data-stu-id="cd858-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
-   <span data-ttu-id="cd858-106">Un servicio Web de transformación dinámica que incluye con el núcleo de servicios Web</span><span class="sxs-lookup"><span data-stu-id="cd858-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
-   <span data-ttu-id="cd858-107">Transformaciones que se ejecuta por componentes de canalización ESB</span><span class="sxs-lookup"><span data-stu-id="cd858-107">Transformations executed by ESB pipeline components</span></span>  
  
 <span data-ttu-id="cd858-108">En esta sección se centra en el agente de transformación que se implementa como una orquestación.</span><span class="sxs-lookup"><span data-stu-id="cd858-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="cd858-109">Para obtener información acerca de la transformación del servicio Web, consulte [mediante los servicios Web de BizTalk ESB Toolkit](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd858-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="cd858-110">Para obtener información acerca de los componentes de canalización de distribuidor de ESB, consulte [con los componentes de compatibilidad de canalización](../esb-toolkit/using-the-pipeline-support-components.md).</span><span class="sxs-lookup"><span data-stu-id="cd858-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="cd858-111">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="cd858-111">How It Works</span></span>  
 <span data-ttu-id="cd858-112">El agente de entrega de la transformación es una orquestación que se suscribe a mensajes donde la **nombre** atributo del elemento actual **ServiceInstance** elemento en el itinerario es  **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="cd858-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="cd858-113">El agente realiza la siguiente secuencia de operaciones:</span><span class="sxs-lookup"><span data-stu-id="cd858-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="cd858-114">Recibe un mensaje sin tipo (System.Xml.XmlDocument).</span><span class="sxs-lookup"><span data-stu-id="cd858-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="cd858-115">Si el nombre de la asignación está disponible como un valor estático en el itinerario, el agente intenta resolver el nombre de la asignación mediante el Administrador de resolución.</span><span class="sxs-lookup"><span data-stu-id="cd858-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="cd858-116">Aplica la asignación correspondiente al mensaje de origen de entrada.</span><span class="sxs-lookup"><span data-stu-id="cd858-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="cd858-117">La salida de mapa publica en la base de datos de cuadro de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cd858-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="cd858-118">Cómo configurar la transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="cd858-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="cd858-119">Para obtener más información sobre cómo configurar la transformación dinámica con el Diseñador de itinerario, consulte [crear itinerarios utilizando Diseñador de itinerario](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span><span class="sxs-lookup"><span data-stu-id="cd858-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="cd858-120">Errores de transformación dinámica</span><span class="sxs-lookup"><span data-stu-id="cd858-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="cd858-121">El mecanismo de transformación dinámica creará y publicar un mensaje de error ESB en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd858-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="cd858-122">El componente de resolución no puede determinar que se asignan a aplicar.</span><span class="sxs-lookup"><span data-stu-id="cd858-122">The resolver component cannot determine which map to apply.</span></span>  
  
-   <span data-ttu-id="cd858-123">La asignación especificada no está disponible (por ejemplo, ha especificado un tipo de asignación incorrecta o un mapa que aún no se ha implementado en BizTalk Server 2009).</span><span class="sxs-lookup"><span data-stu-id="cd858-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
-   <span data-ttu-id="cd858-124">Se produce un error durante la asignación (por ejemplo, el documento de origen no es del tipo de fuente correcto o las referencias de asignación no se ha implementado una función personalizada en un ensamblado externo a BizTalk).</span><span class="sxs-lookup"><span data-stu-id="cd858-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
-   <span data-ttu-id="cd858-125">Se produce una excepción durante la resolución de just-in-time (JIT) del tipo de mapa.</span><span class="sxs-lookup"><span data-stu-id="cd858-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
-   <span data-ttu-id="cd858-126">No existe ningún suscriptor para el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="cd858-126">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="cd858-127">Se produce cualquier excepción del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd858-127">Any system exception occurs.</span></span>  
  
 <span data-ttu-id="cd858-128">Es responsabilidad del desarrollador para proporcionar la información de contexto que se usan para rellenar los mensajes de excepción y crear controladores para reaccionar ante la excepción.</span><span class="sxs-lookup"><span data-stu-id="cd858-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="cd858-129">Algunos de los datos está disponible automáticamente, y un controlador genérico recogerá el mensaje de excepción si no hay ningún controlador de destino está especificado o está disponible.</span><span class="sxs-lookup"><span data-stu-id="cd858-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="cd858-130">Para obtener más información sobre el control de excepciones de la transformación dinámica, consulte [utilizando Administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).</span><span class="sxs-lookup"><span data-stu-id="cd858-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>