---
title: "Arquitecturas de ejemplo para pequeñas &amp; medianas empresas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a><span data-ttu-id="e7635-102">Arquitecturas de ejemplo para pequeñas &amp; medianas empresas</span><span class="sxs-lookup"><span data-stu-id="e7635-102">Sample Architectures for Small &amp; Medium-Sized Companies</span></span>
<span data-ttu-id="e7635-103">Esta sección ofrece una arquitectura de ejemplo en la que Microsoft BizTalk Server se implementa para proteger los activos de una pequeña o mediana empresa.</span><span class="sxs-lookup"><span data-stu-id="e7635-103">This section provides a sample architecture to deploy Microsoft BizTalk Server when you want to help to protect the assets in a small or medium-sized company.</span></span> <span data-ttu-id="e7635-104">Aunque estas arquitecturas fomentan la protección en profundidad y la separación de servicios para minimizar el impacto de un ataque, dan por sentadas las magnitudes de hardware, software y recursos humanos que normalmente tienen a su disposición las grandes compañías.</span><span class="sxs-lookup"><span data-stu-id="e7635-104">While these architectures encourage defense in depth and separation of services to minimize the impact of an attack, they assume quantities of hardware, software, and human resources that are generally available to large companies.</span></span>  
  
 <span data-ttu-id="e7635-105">No obstante, las pequeñas y medianas empresas (o las grandes organizaciones con pequeñas implementaciones de BizTalk Server) también deben preocuparse de proteger sus entornos.</span><span class="sxs-lookup"><span data-stu-id="e7635-105">However, small and medium-sized companies (or large companies with small BizTalk Server deployments) should also be concerned with how to protect their environments.</span></span> <span data-ttu-id="e7635-106">Una vez que hemos observado cómo las empresas implementan (o pretenden implementar) las soluciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], hemos desarrollado una arquitectura de ejemplo para pequeñas y medianas empresas que mantiene un equilibrio entre los recursos disponibles y la mayor seguridad posible.</span><span class="sxs-lookup"><span data-stu-id="e7635-106">After we looked at how companies deployed or plan to deploy their [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions, we derived a sample architecture for small and medium-sized companies that balances available resources with the greatest possible security.</span></span> <span data-ttu-id="e7635-107">Utilice la información de esta sección como guía para planear su propia implementación.</span><span class="sxs-lookup"><span data-stu-id="e7635-107">You should use the information in this section to help you plan your own deployment.</span></span> <span data-ttu-id="e7635-108">Puede que, después de evaluar sus activos y necesidades empresariales, decida adoptar otra arquitectura para su implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7635-108">After you evaluate your business needs and assets you might decide on a different architecture for your BizTalk Server deployment.</span></span>  
  
 <span data-ttu-id="e7635-109">Para que resulte más fácil ver el aspecto que tendría la arquitectura, esta sección proporciona arquitecturas de ejemplo basadas en varios adaptadores que podría usar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e7635-109">To make it easier to see how your architecture would look, this section provides sample architectures based on various adapters that you might use in your environment.</span></span> <span data-ttu-id="e7635-110">Las ilustraciones muestran los componentes de la topología que son independientes de los adaptadores y los que dependen del adaptador que se usa en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7635-110">The figures show you which components of the topology are adapter-independent, and which components depend on the adapter you use in your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="e7635-111">Además, se examinan escenarios de uso basados en algunos de los adaptadores que se pueden utilizar en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7635-111">We also examine usage scenarios based on some of the adapters you can use with BizTalk Server.</span></span> <span data-ttu-id="e7635-112">Para ayudarle a planear y diseñar su propia arquitectura, le ofrecemos un análisis de modelo de amenaza de esta arquitectura de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e7635-112">To help you as you plan and design your own architecture, we provide a threat model analysis of this sample architecture.</span></span> <span data-ttu-id="e7635-113">Este análisis ofrece un examen más profundo de los problemas de seguridad que pueden afectar a su empresa según los adaptadores que use para comunicarse con sus asociados.</span><span class="sxs-lookup"><span data-stu-id="e7635-113">This analysis gives you a deeper look at the potential security issues that might affect your company, depending on the adapters you use to communicate with your partners.</span></span>  
  
 <span data-ttu-id="e7635-114">Aunque esta sección contiene información para ayudarle a diseñar una implementación segura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], para mejorar la seguridad de su entorno, debería considerar la posibilidad de proteger la comunicación entre los servidores del entorno.</span><span class="sxs-lookup"><span data-stu-id="e7635-114">While this section gives you information to help you design a secure deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to increase the security in your environment you should also consider securing the communication between the servers in the environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7635-115">En esta sección se supone que no está usando la supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="e7635-115">This section assumes that you are not using Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="e7635-116">Esta característica necesita que se tengan en cuenta temas de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="e7635-116">This feature requires additional security considerations.</span></span> <span data-ttu-id="e7635-117">Esto se explica en [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).</span><span class="sxs-lookup"><span data-stu-id="e7635-117">This is discussed in [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7635-118">Para obtener más información acerca de los adaptadores no se describe en este documento, consulte el centro de desarrollo de BizTalk Server ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span><span class="sxs-lookup"><span data-stu-id="e7635-118">For more information about adapters not described in this document, see the BizTalk Server Developer Center ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7635-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e7635-119">In This Section</span></span>  
  
-   [<span data-ttu-id="e7635-120">Arquitectura de ejemplo: Servidor BizTalk Server Base</span><span class="sxs-lookup"><span data-stu-id="e7635-120">Sample Architecture: Base BizTalk Server</span></span>](../core/sample-architecture-base-biztalk-server.md)  
  
-   [<span data-ttu-id="e7635-121">Arquitectura de ejemplo: Los adaptadores SOAP y HTTP</span><span class="sxs-lookup"><span data-stu-id="e7635-121">Sample Architecture: HTTP and SOAP Adapters</span></span>](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="e7635-122">Arquitectura de ejemplo: Message Queue Server de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e7635-122">Sample Architecture: BizTalk Message Queuing</span></span>](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [<span data-ttu-id="e7635-123">Arquitectura de ejemplo: Adaptador de FTP de</span><span class="sxs-lookup"><span data-stu-id="e7635-123">Sample Architecture: FTP Adapter</span></span>](../core/sample-architecture-ftp-adapter.md)  
  
-   [<span data-ttu-id="e7635-124">Arquitectura de ejemplo: Adaptador de archivo de</span><span class="sxs-lookup"><span data-stu-id="e7635-124">Sample Architecture: File Adapter</span></span>](../core/sample-architecture-file-adapter.md)