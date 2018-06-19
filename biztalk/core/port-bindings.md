---
title: Enlaces de puerto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, warnings
- ports, bindings
- bindings, Web ports
- bindings, design time
- Web ports, port bindings
- bindings, ports
- bindings, direct
- bindings, warnings
- bindings, deployment
- bindings, dynamic
ms.assetid: b61c725a-0082-42d3-b88a-533583161734
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943cbbaa6db9413ffad15bfcf3302d2216e3ab17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265204"
---
# <a name="port-bindings"></a><span data-ttu-id="f8d5b-102">Enlaces de puerto</span><span class="sxs-lookup"><span data-stu-id="f8d5b-102">Port Bindings</span></span>
<span data-ttu-id="f8d5b-103">Un enlace de puerto es la información de configuración que determina dónde y cómo se enviará o recibirá un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-103">A port binding is the configuration information that determines where and how a message will be sent or received.</span></span> <span data-ttu-id="f8d5b-104">Según el tipo, es posible que un enlace de puerto haga referencia a ubicaciones físicas, canalizaciones u otras orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-104">Depending on its type, a port binding might refer to physical locations, pipelines, or other orchestrations.</span></span>  
  
 <span data-ttu-id="f8d5b-105">Hay tres tipos de enlaces de puertos para puertos que reciben mensajes:</span><span class="sxs-lookup"><span data-stu-id="f8d5b-105">There are three types of port binding for ports that receive messages:</span></span>  
  
-   <span data-ttu-id="f8d5b-106">Especificar ahora</span><span class="sxs-lookup"><span data-stu-id="f8d5b-106">Specify now</span></span>  
  
-   <span data-ttu-id="f8d5b-107">Especificar más tarde</span><span class="sxs-lookup"><span data-stu-id="f8d5b-107">Specify later</span></span>  
  
-   <span data-ttu-id="f8d5b-108">Directo</span><span class="sxs-lookup"><span data-stu-id="f8d5b-108">Direct</span></span>  
  
 <span data-ttu-id="f8d5b-109">Hay cuatro tipos de enlaces de puertos para puertos que envían mensajes:</span><span class="sxs-lookup"><span data-stu-id="f8d5b-109">There are four types of port binding for ports that send messages:</span></span>  
  
-   <span data-ttu-id="f8d5b-110">Especificar ahora</span><span class="sxs-lookup"><span data-stu-id="f8d5b-110">Specify now</span></span>  
  
-   <span data-ttu-id="f8d5b-111">Especificar más tarde</span><span class="sxs-lookup"><span data-stu-id="f8d5b-111">Specify later</span></span>  
  
-   <span data-ttu-id="f8d5b-112">Directo</span><span class="sxs-lookup"><span data-stu-id="f8d5b-112">Direct</span></span>  
  
-   <span data-ttu-id="f8d5b-113">Dinámica</span><span class="sxs-lookup"><span data-stu-id="f8d5b-113">Dynamic</span></span>  
  
## <a name="binding-at-deployment-time"></a><span data-ttu-id="f8d5b-114">Enlace en tiempo de implementación</span><span class="sxs-lookup"><span data-stu-id="f8d5b-114">Binding at Deployment Time</span></span>  
 <span data-ttu-id="f8d5b-115">Puede enlazar el puerto con una ubicación de recepción o con un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-115">You can bind your port to a receive location or to a send port.</span></span> <span data-ttu-id="f8d5b-116">Si no tiene toda la información que se debe especificar una ubicación física, puede seleccionar la **especificar más tarde** opción de enlace de puerto en el Diseñador de orquestaciones y solo hay que especificar el tipo de puerto que describe el puerto.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-116">If you do not have all of the information you need to specify a physical location, you can select the **Specify later** port binding option in Orchestration Designer, and you only need to specify the port type that describes the port.</span></span> <span data-ttu-id="f8d5b-117">Una vez que se ha implementado la aplicación, puede especificar la información acerca de la ubicación mediante el uso de la Consola de administración de BizTalk o puede configurar la información de configuración mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-117">After the application has been deployed, you can specify information about the location by using the BizTalk Server Administration console, or you can configure the location information programmatically.</span></span>  
  
## <a name="binding-at-design-time"></a><span data-ttu-id="f8d5b-118">Enlace en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="f8d5b-118">Binding at Design Time</span></span>  
 <span data-ttu-id="f8d5b-119">Puede seleccionar la **especificar ahora** puerto opción de enlace en el Diseñador de orquestaciones para especificar el transporte y la canalización en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-119">You can select the **Specify now** port binding option in Orchestration Designer to specify the transport and pipeline at design time.</span></span> <span data-ttu-id="f8d5b-120">Al especificar el puerto para la recepción de mensajes, solo están disponibles los transportes HTTP, SOAP y FILE en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-120">When specifying the port for receiving messages, only HTTP, SOAP, and FILE transports are available from the drop-down list.</span></span> <span data-ttu-id="f8d5b-121">Al especificar el puerto para el envío de mensajes, solo están disponibles los transportes HTTP, FILE y SMTP en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-121">When specifying the port for sending messages, only HTTP, FILE, and SMTP transports are available from the drop-down list.</span></span> <span data-ttu-id="f8d5b-122">Esta opción es útil si conoce previamente el origen o el destino de los mensajes transmitidos.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-122">This option is useful if you know in advance the source or destination of transmitted messages.</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="f8d5b-123">Enlace directo</span><span class="sxs-lookup"><span data-stu-id="f8d5b-123">Direct Binding</span></span>  
 <span data-ttu-id="f8d5b-124">Los puertos de enlace directo son puertos lógicos unidireccionales y bidireccionales en las orquestaciones que no están enlazadas expresamente a ningún puerto físico.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-124">Direct bound ports are logical one-way or two-way ports in your orchestrations that are not explicitly bound to any physical ports.</span></span> <span data-ttu-id="f8d5b-125">Los puertos de enlace directo permiten tener distintos patrones de comunicación entre los servicios.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-125">Direct bound ports allow you to have different communication patterns among your services.</span></span> <span data-ttu-id="f8d5b-126">Para implementar el enlace directo, seleccione la **directa** puerto opción de enlace en el Diseñador de orquestaciones en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-126">To implement direct binding, select the **Direct** port binding option in Orchestration Designer at design time.</span></span>  
  
 <span data-ttu-id="f8d5b-127">Hay tres tipos de puertos de enlace directo:</span><span class="sxs-lookup"><span data-stu-id="f8d5b-127">There are three types of direct bound ports:</span></span>  
  
-   <span data-ttu-id="f8d5b-128">Puerto de enlace directo de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="f8d5b-128">MessageBox direct bound port</span></span>  
  
-   <span data-ttu-id="f8d5b-129">Puerto de enlace directo de autocorrelación</span><span class="sxs-lookup"><span data-stu-id="f8d5b-129">Self-correlating direct bound port</span></span>  
  
-   <span data-ttu-id="f8d5b-130">Puerto de enlace directo de orquestación de socio</span><span class="sxs-lookup"><span data-stu-id="f8d5b-130">Partner orchestration direct bound port</span></span>  
  
 <span data-ttu-id="f8d5b-131">Para obtener más información sobre cómo trabajar con puertos de enlace directo, vea [trabajar con puertos de enlace directo en orquestaciones](../core/working-with-direct-bound-ports-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-131">For more information about how to work with direct bound ports, see [Working with Direct Bound Ports in Orchestrations](../core/working-with-direct-bound-ports-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8d5b-132">Si utiliza el enlace directo, no podrá intercambiar mensajes entre un puerto de solicitud-respuesta y dos puertos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-132">When you use direct binding, you cannot exchange messages between one request-response port and two one-way ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8d5b-133">El enlace directo no es compatible con los estándares del Lenguaje de ingeniería de procesos empresariales para servicios Web (BPEL4WS).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-133">Direct binding is not compliant with the standards of the Business Process Engineering Language for Web Services (BPEL4WS).</span></span> <span data-ttu-id="f8d5b-134">Si necesita compatibilidad con BPEL4WS, use otro tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-134">If you require BPEL4WS compliance, use another kind of binding.</span></span>  
  
## <a name="dynamic-binding"></a><span data-ttu-id="f8d5b-135">Enlace dinámico</span><span class="sxs-lookup"><span data-stu-id="f8d5b-135">Dynamic Binding</span></span>  
 <span data-ttu-id="f8d5b-136">Si no conocerá el destino de una comunicación hasta el tiempo de ejecución, puede usar el enlace dinámico para un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-136">If you will not know the destination of a communication until run time, you can use dynamic binding for a send port.</span></span> <span data-ttu-id="f8d5b-137">La ubicación podría, por ejemplo, se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8d5b-137">The location might, for example, be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following code:</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
```  
  
 <span data-ttu-id="f8d5b-138">Para obtener información acerca de cómo asignar dinámicamente los valores a puertos, consulte [cómo asignar valores a puertos dinámicos](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-138">For information about how to dynamically assign values to ports, see [How to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md).</span></span>  
  
## <a name="web-ports"></a><span data-ttu-id="f8d5b-139">Puertos Web</span><span class="sxs-lookup"><span data-stu-id="f8d5b-139">Web Ports</span></span>  
 <span data-ttu-id="f8d5b-140">Si el proyecto contiene una referencia a un servicio Web, el Diseñador de orquestaciones lo detectará y hará que esté disponible un tipo de puerto Web apropiado.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-140">If your project contains a reference to a Web service, Orchestration Designer will detect it and will make available a corresponding Web port type.</span></span> <span data-ttu-id="f8d5b-141">Para crear un puerto Web, solo tiene que agregar un puerto a la orquestación y asignarle un tipo de puerto Web existente.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-141">To create a Web port, you simply add a port to your orchestration and assign it an existing Web port type.</span></span> <span data-ttu-id="f8d5b-142">Para obtener más información, consulte [crear puertos Web](../core/creating-web-ports.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-142">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d5b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8d5b-143">See Also</span></span>  
 <span data-ttu-id="f8d5b-144">[Cómo trabajar con tipos de puerto](../core/how-to-work-with-port-types.md) </span><span class="sxs-lookup"><span data-stu-id="f8d5b-144">[How to Work with Port Types](../core/how-to-work-with-port-types.md) </span></span>  
 <span data-ttu-id="f8d5b-145">[Patrón de comunicación](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="f8d5b-145">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="f8d5b-146">[Dirección de comunicación](../core/communication-direction.md) </span><span class="sxs-lookup"><span data-stu-id="f8d5b-146">[Communication Direction](../core/communication-direction.md) </span></span>  
 <span data-ttu-id="f8d5b-147">[Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f8d5b-147">[Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md) </span></span>  
 <span data-ttu-id="f8d5b-148">[Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="f8d5b-148">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="f8d5b-149">Consumir servicios Web</span><span class="sxs-lookup"><span data-stu-id="f8d5b-149">Consuming Web Services</span></span>](../core/consuming-web-services.md)