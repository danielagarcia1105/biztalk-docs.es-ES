---
title: Características para los clientes del adaptador de Oracle EBS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974f75eaa2416ae11572a1b29eb682d6bc7c0172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968885"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a><span data-ttu-id="9c70e-102">Características para los clientes del adaptador de Oracle EBS</span><span class="sxs-lookup"><span data-stu-id="9c70e-102">Features for Oracle EBS adapter clients</span></span>
<span data-ttu-id="9c70e-103">Además de las características se tratan en los temas de [información general sobre el adaptador de BizTalk para Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] también proporciona las siguientes características que son útiles para los clientes del adaptador:</span><span class="sxs-lookup"><span data-stu-id="9c70e-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="9c70e-104">**Compatibilidad con la configuración de los adaptadores que usan propiedades de enlace**.</span><span class="sxs-lookup"><span data-stu-id="9c70e-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="9c70e-105">Pueden configurar los clientes del adaptador el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] especificando ciertas propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="9c70e-105">Adapter clients can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="9c70e-106">Por ejemplo, los clientes pueden configurar el adaptador para usar la agrupación de conexiones ODP.NET estableciendo el **UseOracleConnectionPool** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9c70e-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="9c70e-107">Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9c70e-107">For more information, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
- <span data-ttu-id="9c70e-108">**Compatibilidad con valores null para los parámetros de operación**.</span><span class="sxs-lookup"><span data-stu-id="9c70e-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="9c70e-109">Los clientes del adaptador pueden proporcionar valores nulos para parámetros de operación mediante el atributo "nil" en el XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="9c70e-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
- <span data-ttu-id="9c70e-110">**Compatibilidad con puertos dinámicos en BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="9c70e-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="9c70e-111">A través de BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con un puerto dinámico que permite el enrutamiento dinámico de los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] basándose en las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9c70e-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="9c70e-112">Para obtener más información, consulte [configurar los puertos dinámicos en el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9c70e-112">For more information, see [Configure Dynamic Ports in the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c70e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c70e-113">See Also</span></span>  
[<span data-ttu-id="9c70e-114">El adaptador de BizTalk para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="9c70e-114">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)