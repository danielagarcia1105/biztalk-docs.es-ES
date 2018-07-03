---
title: Alta disponibilidad del adaptador de MQSeries | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145577ce280595ff959596cff99fd08f334e8993
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008853"
---
# <a name="mqseries-adapter-high-availability"></a><span data-ttu-id="69b38-102">Alta disponibilidad del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="69b38-102">MQSeries Adapter High Availability</span></span>
<span data-ttu-id="69b38-103">Puede mejorar la disponibilidad de las siguientes formas al usar el adaptador:</span><span class="sxs-lookup"><span data-stu-id="69b38-103">You can improve availability in the following ways when you use the adapter:</span></span>  
  
- <span data-ttu-id="69b38-104">Configure un entorno de host de tolerancia a errores para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69b38-104">Set up a fault-tolerant hosting environment for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="69b38-105">Utilice la organización por clústeres de Windows con IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="69b38-105">Use Windows Clustering with IBM WebSphere MQ.</span></span>  
  
  <span data-ttu-id="69b38-106">Para obtener información acerca de la tolerancia a errores y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) y [planear su plataforma para tolerancia a errores](../core/planning-your-platform-for-fault-tolerance.md) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="69b38-106">For information about fault tolerance and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) and [Planning Your Platform for Fault Tolerance](../core/planning-your-platform-for-fault-tolerance.md) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  <span data-ttu-id="69b38-107">Para asegurarse de que el adaptador de MQSeries para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es capaz de comunicarse con una instalación remota del componente MQSAgent, asegúrese de que ha habilitado el acceso de red COM+ en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en el servidor en el que está instalado IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="69b38-107">To ensure that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries Adapter is able to communicate with a remote installation of the MQSAgent component, ensure that you have enabled network COM+ access on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and server where IBM WebSphere MQ is installed.</span></span> <span data-ttu-id="69b38-108">Para obtener más información acerca de cómo habilitar el acceso de red COM +, consulte Microsoft Knowledge Base artículo 817065, "Cómo habilitar el acceso de red COM + en Windows Server 2003," disponible en [ http://go.microsoft.com/fwlink/?LinkId=196580 ](http://go.microsoft.com/fwlink/?LinkId=196580).</span><span class="sxs-lookup"><span data-stu-id="69b38-108">For more information about enabling network COM+ access, see Microsoft Knowledge Base article number 817065, " How to enable network COM+ access in Windows Server 2003," available at [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).</span></span>  
  
  <span data-ttu-id="69b38-109">No es necesario organizar por clústeres la aplicación MQSAgent (MQSAgent2) COM+ que se utiliza con el adaptador de MQSeries para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69b38-109">There is no requirement to cluster the MQSAgent (MQSAgent2) COM+ application that is used with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter.</span></span> <span data-ttu-id="69b38-110">Para proporcionar una alta disponibilidad a este componente, instale el componente en cada nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="69b38-110">To provide high availability for this component, install the component on each cluster node.</span></span> <span data-ttu-id="69b38-111">Si detiene la aplicación COM+, la siguiente llamada del cliente la reiniciará.</span><span class="sxs-lookup"><span data-stu-id="69b38-111">If the COM+ application stops, the next call from the client will start it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b38-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="69b38-112">See Also</span></span>  
 [<span data-ttu-id="69b38-113">Uso del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="69b38-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)