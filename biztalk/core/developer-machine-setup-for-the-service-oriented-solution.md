---
title: "Solución orientada a servicios de configuración del equipo del desarrollador del servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb3407dbccbc4dccc902892cf04fa71991b8d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a><span data-ttu-id="14e96-102">Configuración del equipo del programador para la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="14e96-102">Developer Machine Setup for the Service Oriented Solution</span></span>
<span data-ttu-id="14e96-103">La arquitectura orientada a servicios (SOA) es un enfoque para la generación de sistemas distribuidos.</span><span class="sxs-lookup"><span data-stu-id="14e96-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="14e96-104">La solución orientada a servicios demuestra cómo varios sistemas servidor con protocolos distintos se pueden integrar en un único servicio que pueden consumir los clientes.</span><span class="sxs-lookup"><span data-stu-id="14e96-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="14e96-105">Esta solución integra servicios con un enfoque que garantiza características de entrega y rendimiento para los acuerdos de nivel de servicio que tiene que satisfacer.</span><span class="sxs-lookup"><span data-stu-id="14e96-105">This solution integrates services with an approach that guarantees delivery and performance characteristics for the service level agreement that you need to satisfy.</span></span>  
  
 <span data-ttu-id="14e96-106">La solución orientada a servicios basa su modelo en un escenario de contrato de nivel de servicio en el que BizTalk Server y los servidores de la aplicación de la unidad de negocio conectados a éste disponen de tres segundos para responder a una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="14e96-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="14e96-107">Uno de estos tres segundos puede ser utilizado por el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="14e96-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="14e96-108">Hay tres versiones de la solución orientada a servicios: adaptador, en línea y el código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="14e96-108">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="14e96-109">Para obtener más información acerca de las diferencias entre las tres versiones de la solución orientada a servicios, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="14e96-109">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span> <span data-ttu-id="14e96-110">Como un programador, obtiene que se esté ejecutando el escenario utilizando la versión de código auxiliar del escenario.</span><span class="sxs-lookup"><span data-stu-id="14e96-110">As a developer, you get the scenario running by using the stub version of the scenario.</span></span> <span data-ttu-id="14e96-111">Esta versión no requiere ningún servidor LOB para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="14e96-111">This version does not require any LOB back-end servers in order to run.</span></span> <span data-ttu-id="14e96-112">Después, podrá utilizar la versión del adaptador del escenario para conocer cómo pueden integrarse y configurarse varios adaptadores y servidores para responder mediante los servidores de BizTalk Server como un único servicio.</span><span class="sxs-lookup"><span data-stu-id="14e96-112">After this you can use the adapter version of the scenario to learn how various adapters and back-end servers can be integrated and configured to respond using the BizTalk servers as a single service.</span></span> <span data-ttu-id="14e96-113">A continuación, puede medir la latencia inducida por BizTalk Server y sus adaptadores.</span><span class="sxs-lookup"><span data-stu-id="14e96-113">You can then measure the latency induced by BizTalk Server and its adapters.</span></span>  
  
 <span data-ttu-id="14e96-114">Si existe un exceso de latencia de BizTalk Server en sus requisitos de servicios, puede omitir los puntos de persistencia del adaptador LOB mediante la instalación y ejecución de la versión en línea de SOA.</span><span class="sxs-lookup"><span data-stu-id="14e96-114">If the latency for the BizTalk server is in excess of its service requirement, you can bypass the LOB adapter persistence points by installing and running the SOA in-line version.</span></span> <span data-ttu-id="14e96-115">Esta versión omite los adaptadores y, en consecuencia, sus contribuciones de latencia debido al punto de persistencia del cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="14e96-115">This version bypasses the adapters and subsequently their latency contributions due to the MessageBox persistence point.</span></span> <span data-ttu-id="14e96-116">En su lugar, la versión en línea se comunica de inmediato con los servidores a través de mecanismos de autenticación de llamadas a procedimiento remoto (RPC) como DCOM.</span><span class="sxs-lookup"><span data-stu-id="14e96-116">Instead, the inline version talks straight to the back-end servers through Remote Procedure Calls (RPC) mechanisms such as DCOM.</span></span>  
  
 <span data-ttu-id="14e96-117">Para obtener más información sobre el punto de persistencia de cuadro de mensajes, vea [persistencia y el motor de orquestaciones](../core/persistence-and-the-orchestration-engine.md).</span><span class="sxs-lookup"><span data-stu-id="14e96-117">For more information about the MessageBox persistence point, see [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span>  
  
 <span data-ttu-id="14e96-118">Esta guía de implementación describe el modo de instalación y prueba de las tres versiones de la solución orientada a servicios en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="14e96-118">This deployment guide describes how to install and test the three versions of the service-oriented solution on a single computer.</span></span>  
  
 <span data-ttu-id="14e96-119">Para obtener más información acerca de la solución orientada a servicios, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="14e96-119">For more information about the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14e96-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="14e96-120">In This Section</span></span>  
  
-   [<span data-ttu-id="14e96-121">Antes de instalar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="14e96-121">Before Installing the Service Oriented Solution</span></span>](../core/before-installing-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="14e96-122">Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="14e96-122">How to Install the Stub Version of the Service Oriented Solution</span></span>](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="14e96-123">Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="14e96-123">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="14e96-124">Cómo ejecutar el servicio de la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="14e96-124">How to Run the Service Oriented Solution</span></span>](../core/how-to-run-the-service-oriented-solution.md)