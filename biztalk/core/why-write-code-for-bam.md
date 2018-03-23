---
title: ¿Por qué escribir código para BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10b8ccb29d95daf8ccdf80d67faef3e50495af04
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="why-write-code-for-bam"></a><span data-ttu-id="b68cf-103">¿Por qué escribir código para BAM?</span><span class="sxs-lookup"><span data-stu-id="b68cf-103">Why Write Code For BAM?</span></span>
<span data-ttu-id="b68cf-104">En la mayoría de las circunstancias puede usar las herramientas de BAM sin que sea necesario escribir su propio código para realizar funciones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b68cf-104">In most circumstances you can use the BAM tools without writing your own code to perform your tracking functions.</span></span> <span data-ttu-id="b68cf-105">Estas herramientas son el complemento de BAM para Excel, la utilidad de administración de BAM y el Editor de perfiles de seguimiento (TPE).</span><span class="sxs-lookup"><span data-stu-id="b68cf-105">These tools are the BAM Add-in for Excel, the BAM Management utility, and the Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="b68cf-106">BAM en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona interceptores para las orquestaciones y componentes de mensajería de BizTalk (canalizaciones y puertos).</span><span class="sxs-lookup"><span data-stu-id="b68cf-106">BAM in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides interceptors for BizTalk orchestrations and messaging components (pipelines and ports).</span></span> <span data-ttu-id="b68cf-107">Un interceptor es software que instrumenta una aplicación para que pueda recopilar datos de un modo genérico basado en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b68cf-107">An interceptor is software that instruments an application so that it can collect data in a generic way based on a configuration file.</span></span> <span data-ttu-id="b68cf-108">Puede instrumentar la aplicación para que use estos interceptores mediante el Editor de perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b68cf-108">You can instrument your application to use these interceptors by using the Tracking Profile Editor.</span></span> <span data-ttu-id="b68cf-109">Para obtener más información sobre el Editor de perfiles de seguimiento, vea [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b68cf-109">For more information about the Tracking Profile Editor, see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
 <span data-ttu-id="b68cf-110">Sin embargo, hay dos escenarios principales en los que le resultará ventajoso instrumentar su aplicación mediante las API de BAM:</span><span class="sxs-lookup"><span data-stu-id="b68cf-110">There are two primary scenarios, however, in which you will find it advantageous to instrument your application using the BAM APIs:</span></span>  
  
-   <span data-ttu-id="b68cf-111">No existe un interceptor de BAM para el host que pretende supervisar.</span><span class="sxs-lookup"><span data-stu-id="b68cf-111">There is no BAM interceptor for the host you intend to monitor.</span></span>  
  
-   <span data-ttu-id="b68cf-112">El interceptor integrado no permite la complejidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b68cf-112">The built-in interceptor does not allow for the complexity of your application.</span></span>  
  
 <span data-ttu-id="b68cf-113">Cuando no hay ningún interceptor integrado, puede usar el BAM **EventStream** API para capturar los eventos de interés.</span><span class="sxs-lookup"><span data-stu-id="b68cf-113">When there is no built-in interceptor, you can use the BAM **EventStream** APIs to capture the events of interest.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b68cf-114">Puede combinar **EventStream** las clases con el **BAMInterceptor** clase para crear su propio interceptor.</span><span class="sxs-lookup"><span data-stu-id="b68cf-114">You can combine **EventStream** classes with the **BAMInterceptor** class to create your own interceptor.</span></span> <span data-ttu-id="b68cf-115">El ejemplo de SDK de API de BAM ilustra un interceptor genérico simple que puede extender.</span><span class="sxs-lookup"><span data-stu-id="b68cf-115">The BAM API SDK sample illustrates a simple generic interceptor that you can extend.</span></span> <span data-ttu-id="b68cf-116">Al construir su propio interceptor, puede instrumentar varios procesos similares sin tener que escribir código nuevo para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="b68cf-116">By constructing your own interceptor you can instrument a number of similar processes without writing new code for each application.</span></span> <span data-ttu-id="b68cf-117">Para ver el ejemplo de SDK de API de BAM, consulte [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b68cf-117">To view the BAM API SDK sample, see [BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68cf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b68cf-118">See Also</span></span>  
 [<span data-ttu-id="b68cf-119">Implementar soluciones de BAM</span><span class="sxs-lookup"><span data-stu-id="b68cf-119">Implementing BAM Solutions</span></span>](../core/implementing-bam-solutions.md)