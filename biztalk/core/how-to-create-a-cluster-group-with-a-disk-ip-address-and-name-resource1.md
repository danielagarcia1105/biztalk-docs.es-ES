---
title: "Cómo crear un grupo de clústeres con un disco, dirección IP y el nombre Resource1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a><span data-ttu-id="363e6-102">Cómo crear un grupo de clústeres con un disco, una dirección IP y un recurso de nombre</span><span class="sxs-lookup"><span data-stu-id="363e6-102">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>
<span data-ttu-id="363e6-103">Para en clúster [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] componentes y dependencias para ser accesibles a través de la red a través de NetBIOS, un clúster **nombre de red** recurso debe crearse en el mismo grupo de clústeres.</span><span class="sxs-lookup"><span data-stu-id="363e6-103">For clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components and dependencies to be accessible over the network via NetBIOS, a clustered **Network Name** resource must be created in same cluster group.</span></span> <span data-ttu-id="363e6-104">Para un recurso de nombre de red agrupado esté accesible a través del protocolo TCP/IP, un **dirección IP** recurso debe crearse en el mismo grupo de clúster.</span><span class="sxs-lookup"><span data-stu-id="363e6-104">For a clustered Network Name resource to be accessible via the TCP/IP protocol, an **IP Address** resource must be created in the same cluster group as well.</span></span> <span data-ttu-id="363e6-105">Algunos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencias también requieren el uso de un clúster **disco físico** recurso para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="363e6-105">Some [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencies also require the use of a clustered **Physical Disk** resource to function correctly.</span></span> <span data-ttu-id="363e6-106">Para crear un grupo de clúster con una **disco físico**, **dirección IP** y **nombre de red** recursos siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="363e6-106">To create a cluster group with a **Physical Disk**, **IP Address** and **Network Name** resource follow these steps:</span></span>  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a><span data-ttu-id="363e6-107">Para crear un servicio o una apliación con un recurso Disco físico, Dirección IP y Nombre de red</span><span class="sxs-lookup"><span data-stu-id="363e6-107">To create a service or application with a Physical Disk, IP Address, and Network Name resource</span></span>  
  
1.  <span data-ttu-id="363e6-108">En Windows, haga clic en **iniciar**, **programas**, **herramientas administrativas**y, a continuación, **administración de clúster de conmutación por error** para iniciar la conmutación por error Programa de administración de clúster.</span><span class="sxs-lookup"><span data-stu-id="363e6-108">In Windows, click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
2.  <span data-ttu-id="363e6-109">Conmute por error todos los servicios y las aplicaciones al nodo de clúster en el que ejecuta Administración de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="363e6-109">Fail over all services and applications to the cluster node that you are running Failover Cluster Management on.</span></span> <span data-ttu-id="363e6-110">Para conmutar por error un servicio o aplicación, haga clic con el servicio o aplicación en el panel izquierdo de administración de clúster de conmutación por error, seleccione **mover este servicio o aplicación a otro nodo** y haga clic para seleccionar el nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="363e6-110">To fail over a service or application, right click the service or application in the left pane of Failover Cluster Management, point to **Move this service or application to another node** and click to select the destination node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="363e6-111">El nodo de clúster que hospeda los recursos de clúster de ejecución también es conocido como el **active** nodo.</span><span class="sxs-lookup"><span data-stu-id="363e6-111">The cluster node that hosts running cluster resources is also known as the **active** node.</span></span> <span data-ttu-id="363e6-112">El nodo de clúster que hospeda los recursos de clúster no están en ejecución es también conocido como el **pasivo** nodo.</span><span class="sxs-lookup"><span data-stu-id="363e6-112">The cluster node that hosts non-running cluster resources is also known as the **passive** node.</span></span>  
  
3.  <span data-ttu-id="363e6-113">En el panel izquierdo, haga clic en **servicios y aplicaciones**, haga clic en **configurar un servicio o aplicación** para iniciar el Asistente para alta disponibilidad y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="363e6-113">In the left-hand pane, right-click **Services and Applications**, click **Configure a Service or Application** to launch the High Availability Wizard, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="363e6-114">Haga clic para seleccionar **servidor de archivos** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="363e6-114">Click to select **File Server** and click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="363e6-115">Seleccionar **servidor de archivos** en este punto se realiza como una manera sencilla de crear un grupo de clústeres con un recurso de disco.</span><span class="sxs-lookup"><span data-stu-id="363e6-115">Selecting **File Server** at this point is done as a straightforward way to create a cluster group with a disk resource.</span></span>  
  
5.  <span data-ttu-id="363e6-116">En el **punto de acceso de cliente** página del Asistente para alta disponibilidad escriba un nombre de red único en la **nombre** cuadro, por ejemplo *BizTalkCluster*, escriba una dirección IP disponible dirección en **dirección**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="363e6-116">On the **Client Access Point** page of the High Availability Wizard enter a unique network name into the **Name** box, for example *BizTalkCluster*, enter an available IP address under **Address**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="363e6-117">En el **Seleccionar almacenamiento** página, haga clic para seleccionar un recurso de disco disponible y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="363e6-117">On the **Select Storage** page, click to select an available disk resource and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="363e6-118">En el **confirmación** página haga clic en **siguiente** para crear el grupo de clúster.</span><span class="sxs-lookup"><span data-stu-id="363e6-118">On the **Confirmation** page click **Next** to create the cluster group.</span></span>  
  
8.  <span data-ttu-id="363e6-119">En el **resumen** página haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="363e6-119">On the **Summary** page click **Finish**.</span></span>