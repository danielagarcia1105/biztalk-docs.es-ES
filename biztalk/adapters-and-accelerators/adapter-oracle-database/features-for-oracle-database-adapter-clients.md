---
title: Características para los clientes del adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce283c3fd63f72d67e31806e86bf9caa08555dd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976181"
---
# <a name="features-for-oracle-database-adapter-clients"></a><span data-ttu-id="f5687-102">Características para los clientes del adaptador de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="f5687-102">Features for Oracle Database adapter clients</span></span>
<span data-ttu-id="f5687-103">Además de las características se tratan en los temas de [información general del adaptador de BizTalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador:</span><span class="sxs-lookup"><span data-stu-id="f5687-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="f5687-104">**Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**.</span><span class="sxs-lookup"><span data-stu-id="f5687-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="f5687-105">Pueden configurar los clientes del adaptador el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] especificando ciertas propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="f5687-105">Adapter clients can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="f5687-106">Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo el **UseOracleConnectionPool** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f5687-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="f5687-107">Para obtener más información, consulte [configurar las propiedades de enlace para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="f5687-107">For more information, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
- <span data-ttu-id="f5687-108">**Compatibilidad con valores null para los parámetros de operación**.</span><span class="sxs-lookup"><span data-stu-id="f5687-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="f5687-109">Los clientes del adaptador pueden proporcionar valores nulos para parámetros de operación mediante el atributo "nil" en el XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5687-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
- <span data-ttu-id="f5687-110">**Compatibilidad con puertos dinámicos en BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="f5687-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="f5687-111">A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f5687-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="f5687-112">Para obtener más información, consulte [configurar puertos dinámicos](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f5687-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).</span></span>  
  
- <span data-ttu-id="f5687-113">**Compatibilidad con contadores de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="f5687-113">**Support for performance counters**.</span></span> <span data-ttu-id="f5687-114">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con los contadores de rendimiento basados en WCF para su uso por los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="f5687-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="f5687-115">Para obtener más información sobre los contadores de rendimiento, consulte [los contadores de rendimiento](../../core/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="f5687-115">For more information about performance counters, see [Performance Counters](../../core/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5687-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5687-116">See Also</span></span>  
 [<span data-ttu-id="f5687-117">Información general sobre el adaptador de BizTalk para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="f5687-117">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)