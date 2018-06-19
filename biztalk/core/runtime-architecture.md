---
title: Arquitectura del Runtime | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268996"
---
# <a name="runtime-architecture"></a><span data-ttu-id="a430d-102">Arquitectura en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a430d-102">Runtime Architecture</span></span>
<span data-ttu-id="a430d-103">Antes de revisar información detallada adicional sobre los distintos componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es importante entender cómo encajan los componentes en la arquitectura global del producto.</span><span class="sxs-lookup"><span data-stu-id="a430d-103">Before reviewing more detailed information about the various components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is important that you have an understanding of how the components fit into the overall architecture of the product.</span></span> <span data-ttu-id="a430d-104">El tiempo en ejecución de BizTalk Server está basado en una arquitectura de publicación/suscripción en la que se publica un mensaje en el sistema y, a continuación, éste es recibido por uno o varios suscriptores activos.</span><span class="sxs-lookup"><span data-stu-id="a430d-104">The BizTalk Server runtime is built on a publish/subscribe architecture in which a message is published into the system, and then received by one or more active subscribers.</span></span> <span data-ttu-id="a430d-105">Existen distintos tipos de esta arquitectura, pero a menudo se denomina el modelo implementado en BizTalk Server *basado en contenido de publicación/suscripción*.</span><span class="sxs-lookup"><span data-stu-id="a430d-105">Different flavors of this architecture exist, but the model implemented in BizTalk Server is often called *content-based publish/subscribe*.</span></span>  
  
 <span data-ttu-id="a430d-106">En un modelo de publicación/suscripción basada en contenido, los suscriptores especifican los mensajes que desean recibir con un conjunto de criterios relativos al mensaje.</span><span class="sxs-lookup"><span data-stu-id="a430d-106">In a content-based publish/subscribe model, subscribers specify the messages they want to receive using a set of criteria about the message.</span></span> <span data-ttu-id="a430d-107">El mensaje se evalúa en el momento de su publicación y todos los suscriptores activos con suscripciones coincidentes (indicadas mediante expresiones de filtro) recibirán el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a430d-107">The message is evaluated at the time it is published, and all of the active subscribers with matching subscriptions (indicated by filter expressions), receive the message.</span></span> <span data-ttu-id="a430d-108">Sin embargo, tal y como se aplica a BizTalk Server, la denominación “basada en contenido” resulta algo inapropiada, pues los criterios utilizados para generar suscripciones no tienen que proceder del contenido del mensaje y pueden incluir también información contextual sobre el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a430d-108">As it applies to BizTalk Server, content-based is a bit of a misnomer, however, because the criteria used to build subscriptions do not have to come from the message content, and may include contextual information about the message as well.</span></span> <span data-ttu-id="a430d-109">Para obtener detalles sobre el mecanismo de suscripción, consulte [publicar y arquitectura de suscripción](../core/publish-and-subscribe-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="a430d-109">For details of the subscription mechanism, see [Publish and Subscribe Architecture](../core/publish-and-subscribe-architecture.md).</span></span>  
  
 <span data-ttu-id="a430d-110">En las secciones siguientes se describen los distintos componentes de la arquitectura en tiempo de ejecución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a430d-110">The sections that follow describe the various components of the BizTalk Server runtime architecture.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a430d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a430d-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a430d-112">Mensaje de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a430d-112">The BizTalk Server Message</span></span>](../core/the-biztalk-server-message.md)  
  
-   [<span data-ttu-id="a430d-113">Ciclo de vida de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a430d-113">Lifecycle of a Message</span></span>](../core/lifecycle-of-a-message.md)  
  
-   [<span data-ttu-id="a430d-114">Procesar el mensaje</span><span class="sxs-lookup"><span data-stu-id="a430d-114">Processing the Message</span></span>](../core/processing-the-message.md)  
  
-   [<span data-ttu-id="a430d-115">Mensajería de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="a430d-115">Request-Response Messaging</span></span>](../core/request-response-messaging.md)  
  
-   [<span data-ttu-id="a430d-116">El motor de mensajería</span><span class="sxs-lookup"><span data-stu-id="a430d-116">The Messaging Engine</span></span>](../core/the-messaging-engine.md)  
  
-   [<span data-ttu-id="a430d-117">Entidades</span><span class="sxs-lookup"><span data-stu-id="a430d-117">Entities</span></span>](../core/entities.md)  
  
-   [<span data-ttu-id="a430d-118">Artefactos</span><span class="sxs-lookup"><span data-stu-id="a430d-118">Artifacts</span></span>](../core/artifacts.md)  
  
-   [<span data-ttu-id="a430d-119">Enterprise Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="a430d-119">Enterprise Single Sign-On (SSO)</span></span>](../core/enterprise-single-sign-on-sso.md)  
  
-   [<span data-ttu-id="a430d-120">Motor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="a430d-120">Business Rules Engine</span></span>](../core/business-rules-engine.md)  
  
-   [<span data-ttu-id="a430d-121">Ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a430d-121">BizTalk Assemblies</span></span>](../core/biztalk-assemblies.md)