---
title: Aspectos destacados de la implementación del servicio en la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257756"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a><span data-ttu-id="f3e8d-102">Aspectos destacados de la implementación del servicio en la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f3e8d-102">Implementation Highlights of the Service Oriented Solution</span></span>
<span data-ttu-id="f3e8d-103">Una solución resuelve un problema concreto en un contexto específico.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-103">A solution solves a particular problem in a specific context.</span></span> <span data-ttu-id="f3e8d-104">La solución orientada a servicios no es una excepción y es específica para Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el escenario.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-104">The Service Oriented solution is no exception and is specific to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the scenario.</span></span> <span data-ttu-id="f3e8d-105">Para obtener más información acerca del escenario de Woodgrove Bank, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).</span><span class="sxs-lookup"><span data-stu-id="f3e8d-105">For more information about the Woodgrove Bank scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="f3e8d-106">Durante el desarrollo del escenario, varias áreas resultaron ser cuellos de botella al reducir los tiempos de respuesta a un nivel aceptable.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-106">While developing the scenario, several areas proved to be bottlenecks in reducing response times to an acceptable level.</span></span> <span data-ttu-id="f3e8d-107">El envío de mensajes a los sistemas de servidor mediante adaptadores provoca una notable latencia en la obtención de respuestas.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-107">Sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="f3e8d-108">En general, los adaptadores de por sí ofrecen una latencia muy baja.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-108">In general, adapters by themselves offer very low latency.</span></span> <span data-ttu-id="f3e8d-109">Sin embargo, la arquitectura distribuida de BizTalk requiere que los adaptadores se comuniquen con las instancias de host de las orquestaciones mediante el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-109">However, the distributed architecture of BizTalk requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="f3e8d-110">Esto produce acciones de ida y vuelta a la base de datos y afecta a los tiempos de latencia.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-110">This introduces round trips to the database and affects latency times.</span></span> <span data-ttu-id="f3e8d-111">Por este motivo, la versión en línea de la solución (la versión más rápida) hace que la funcionalidad del adaptador de la propia orquestación llame directamente a los sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-111">For this reason, the inline version of the solution (the fastest version) builds the adapter functionality in the orchestration itself calls the back-end systems directly.</span></span> <span data-ttu-id="f3e8d-112">Es decir, con tres sistemas de servidor diferentes, potencialmente hay tres mecanismos distintos para comunicarse con los sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-112">With three different back-end systems, that means potentially three different mechanisms to communicate with the back-end systems.</span></span>  
  
 <span data-ttu-id="f3e8d-113">Otra área que mostraba problemas de rendimiento era la recuperación de datos de configuración desde el inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-113">Another area that proved a performance problem was retrieving configuration data from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="f3e8d-114">Para conservar la comodidad y la universalidad de SSO a la vez que se acelera el tiempo de recuperación, la solución emplea una caché local para los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-114">To retain the convenience and universality of SSO while speeding up retrieval time, the solution uses a local cache for configuration values.</span></span> <span data-ttu-id="f3e8d-115">El uso de SSO también permite realizar una administración más fácil de los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-115">Using SSO also allows easier management of the configuration data.</span></span> <span data-ttu-id="f3e8d-116">Con la agregación de más instancias de host para satisfacer los requisitos de latencia y de rendimiento no es necesario cambiar valores en el servidor que ejecuta la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-116">Adding additional host instances to meet latency and performance requirements does not require changing settings on the server running the host instance.</span></span>  
  
 <span data-ttu-id="f3e8d-117">Otro elemento inusual de la solución es la llamada a las canalizaciones directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-117">Another unusual element of the solution is calling pipelines directly from code.</span></span> <span data-ttu-id="f3e8d-118">Esto permite volver a utilizar los componentes de canalización personalizados.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-118">This allows reuse of the custom pipeline components.</span></span>  
  
 <span data-ttu-id="f3e8d-119">Por último, hay varios valores de BizTalk Server que se pueden modificar para obtener el último resquicio de velocidad de la solución.</span><span class="sxs-lookup"><span data-stu-id="f3e8d-119">Finally, there are several BizTalk Server settings that you can change to squeeze out the last bit of speed from the solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3e8d-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f3e8d-120">In This Section</span></span>  
  
-   [<span data-ttu-id="f3e8d-121">La inclusión de Back-end invocación</span><span class="sxs-lookup"><span data-stu-id="f3e8d-121">Inlining Back-end Invocation</span></span>](../core/inlining-back-end-invocation.md)  
  
-   [<span data-ttu-id="f3e8d-122">Usar SSO de forma eficaz en el servicio de solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f3e8d-122">Using SSO Efficiently in the Service Oriented Solution</span></span>](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="f3e8d-123">Uso de canalizaciones desde el servicio solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f3e8d-123">Using Pipelines from the Service Oriented Solution</span></span>](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="f3e8d-124">Ajustar la solución orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="f3e8d-124">Tuning the Service Oriented Solution</span></span>](../core/tuning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="f3e8d-125">Separar tipo de transporte y procesamiento</span><span class="sxs-lookup"><span data-stu-id="f3e8d-125">Decoupling Transport Type and Processing</span></span>](../core/decoupling-transport-type-and-processing.md)