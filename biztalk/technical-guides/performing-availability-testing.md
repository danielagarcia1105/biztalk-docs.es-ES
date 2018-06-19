---
title: Realización de las pruebas de disponibilidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298308"
---
# <a name="performing-availability-testing"></a><span data-ttu-id="ea589-102">Realización de las pruebas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="ea589-102">Performing Availability Testing</span></span>
<span data-ttu-id="ea589-103">Debe probar el sistema para la recuperación ante desastres comprobar su capacidad para recuperarse de varios niveles de error, comprendido entre errores a pequeña escala (por ejemplo, un error de tarjeta de red) y la pérdida de un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="ea589-103">You should test your system for disaster recovery to verify its ability to recover from various levels of failure, ranging from small-scale failures (such as a network card failure) to the loss of a production server.</span></span> <span data-ttu-id="ea589-104">Las pruebas de recuperación ante desastres deben incluir los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ea589-104">Your disaster recovery testing should include the following steps:</span></span>  
  
-   <span data-ttu-id="ea589-105">**Error de componente de hardware individual de la prueba.**</span><span class="sxs-lookup"><span data-stu-id="ea589-105">**Test individual hardware component failure.**</span></span>  
  
     <span data-ttu-id="ea589-106">Debe probar la capacidad de recuperarse de un error de componente de hardware individual, como una red o un disco del sistema.</span><span class="sxs-lookup"><span data-stu-id="ea589-106">You should test the ability of the system to recover from an individual hardware component failure, such as a network or disk.</span></span>  
  
-   <span data-ttu-id="ea589-107">**Probar el error de servidor único de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="ea589-107">**Test single BizTalk server failure.**</span></span>  
  
     <span data-ttu-id="ea589-108">En la mayoría [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos de producción, host de procesamiento se reparten entre varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un único grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ea589-108">In most [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] production environments, host processing is spread out among multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a single BizTalk group.</span></span> <span data-ttu-id="ea589-109">¿Qué es la capacidad del grupo de BizTalk para continuar el procesamiento de eventos del host de uno de los servidores del grupo se produce un error?</span><span class="sxs-lookup"><span data-stu-id="ea589-109">What is the ability of the BizTalk group to continue host processing in the event one of the servers in the group fails?</span></span>  
  
-   <span data-ttu-id="ea589-110">**Probar la conmutación por error de nodo de clúster.**</span><span class="sxs-lookup"><span data-stu-id="ea589-110">**Test cluster node failover.**</span></span>  
  
     <span data-ttu-id="ea589-111">Si se utiliza la agrupación en clústeres de Windows para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos o Hosts de BizTalk, debe comprobar la funcionalidad de conmutación por error de nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="ea589-111">If Windows Clustering is used to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or BizTalk Hosts, you should verify cluster node failover functionality.</span></span> <span data-ttu-id="ea589-112">Para obtener más información sobre el uso de clústeres de Windows para proporcionar alta disponibilidad para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [lista de comprobación: proporcionar una alta disponibilidad con tolerancia a errores o equilibrio de carga](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="ea589-112">For more information about using Windows Clustering to provide high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span></span>  
  
-   <span data-ttu-id="ea589-113">**Probar la recuperación de bases de datos de BizTalk Server mediante el trasvase de registros.**</span><span class="sxs-lookup"><span data-stu-id="ea589-113">**Test recovery of BizTalk Server databases using log shipping.**</span></span>  
  
     <span data-ttu-id="ea589-114">Debe comprobar la recuperación de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ea589-114">You should verify the recovery of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="ea589-115">Para obtener más información sobre cómo usar el trasvase de registros para copia de seguridad y restaurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, vea [¿qué es BizTalk Server del trasvase de registros?](../technical-guides/what-is-biztalk-server-log-shipping.md) en esta guía o [del trasvase de registros](http://go.microsoft.com/fwlink/?LinkID=153450) (http://go.microsoft.com/fwlink/?LinkID=153450).</span><span class="sxs-lookup"><span data-stu-id="ea589-115">For more information about using log shipping to back up and restore [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [What Is BizTalk Server Log Shipping?](../technical-guides/what-is-biztalk-server-log-shipping.md) in this guide or [Log Shipping](http://go.microsoft.com/fwlink/?LinkID=153450) (http://go.microsoft.com/fwlink/?LinkID=153450).</span></span>  
  
     <span data-ttu-id="ea589-116">Para una lista de comprobación de los pasos que debe seguir para aumentar la disponibilidad de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres, consulte [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ea589-116">For a checklist of steps that you should follow to increase the availability of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery, see [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea589-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea589-117">See Also</span></span>  
 [<span data-ttu-id="ea589-118">Aumentar la disponibilidad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ea589-118">Increasing Availability for BizTalk Server</span></span>](../technical-guides/increasing-availability-for-biztalk-server.md)