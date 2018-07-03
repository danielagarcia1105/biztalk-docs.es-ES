---
title: Características para los clientes del adaptador SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 411ae3a1b044b89a0ef5390a0f0ad26430909bcb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984637"
---
# <a name="features-for-sap-adapter-clients"></a><span data-ttu-id="990d0-102">Características para los clientes del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="990d0-102">Features for SAP adapter clients</span></span>
<span data-ttu-id="990d0-103">Además de las características se tratan en los temas de [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md), el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="990d0-103">In addition to the features discussed throughout the topics of [Architecture overview of BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md), the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also provides the following features that are useful for adapter clients.</span></span>  
  
- <span data-ttu-id="990d0-104">**Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**.</span><span class="sxs-lookup"><span data-stu-id="990d0-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="990d0-105">Pueden configurar los clientes del adaptador el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] especificando ciertas propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="990d0-105">Adapter clients can configure the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="990d0-106">Por ejemplo, los clientes pueden configurar el adaptador para especificar el número máximo de conexiones de grupo de conexiones del adaptador especificando un valor para el **MaxConnectionsPerSystem** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="990d0-106">For example, clients can configure the adapter to specify the maximum number of connections in the adapter's connection pool by specifying a value for the **MaxConnectionsPerSystem** binding property.</span></span> <span data-ttu-id="990d0-107">Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="990d0-107">For more information, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
- <span data-ttu-id="990d0-108">**Compatibilidad con puertos dinámicos en BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="990d0-108">**Support for dynamic ports in BizTalk Server**.</span></span> <span data-ttu-id="990d0-109">A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="990d0-109">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="990d0-110">Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="990d0-110">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md).</span></span>
  
- <span data-ttu-id="990d0-111">**Compatibilidad con versiones de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="990d0-111">**Support for message versioning**.</span></span> <span data-ttu-id="990d0-112">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite mensajes de control de versiones para habilitar la compatibilidad con esquemas de mensaje diferente en las versiones futuras de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="990d0-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports message versioning to enable support for different message schemas in future releases of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="990d0-113">Para obtener más información, consulte [compatibilidad de versiones de mensaje](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md).</span><span class="sxs-lookup"><span data-stu-id="990d0-113">For more information, see [Message Versioning Support](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="990d0-114">Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.</span><span class="sxs-lookup"><span data-stu-id="990d0-114">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
- <span data-ttu-id="990d0-115">**Compatibilidad con contadores de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="990d0-115">**Support for performance counters**.</span></span> <span data-ttu-id="990d0-116">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los contadores de rendimiento basados en WCF para su uso por los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="990d0-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="990d0-117">Para obtener más información sobre los contadores de rendimiento, consulte [usar contadores de rendimiento con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="990d0-117">For more information about performance counters, see [Use Performance Counters with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990d0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="990d0-118">See Also</span></span>  
 [<span data-ttu-id="990d0-119">Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="990d0-119">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)