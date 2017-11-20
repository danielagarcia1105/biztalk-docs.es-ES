---
title: "Agrupación en clústeres el servidor BizTalk Server Databases1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 983023ceb88618a540d922481c4cb185a076ae3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-biztalk-server-databases"></a><span data-ttu-id="8f067-102">Agrupar las bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8f067-102">Clustering the BizTalk Server Databases</span></span>
<span data-ttu-id="8f067-103">En esta sección se proporcionan directrices para implementar una solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8f067-103">This section provides guidelines for deploying a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution with high availability.</span></span> <span data-ttu-id="8f067-104">Si la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deja de estar disponible, el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f067-104">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases become unavailable, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment will not function correctly.</span></span> <span data-ttu-id="8f067-105">Para proporcionar una alta disponibilidad, puede crear un clúster de Microsoft SQL Server para las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="8f067-105">To provide high availability, you can create a Microsoft SQL Server cluster for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="8f067-106">![Nivel de base de datos de BizTalk Server](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="8f067-106">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="8f067-107">Para proporcionar alta disponibilidad para el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, debe tener al menos dos equipos que ejecuten SQL Server y una matriz de discos compartidos para su uso por un clúster de conmutación por error de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8f067-107">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must have at least two computers that are running SQL Server and a shared disk array for use by a  Windows Server Failover Cluster.</span></span>  
  
## <a name="procedures-for-clustering-the-databases"></a><span data-ttu-id="8f067-108">Procedimientos para agrupar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="8f067-108">Procedures for Clustering the Databases</span></span>  
  
#### <a name="before-you-start"></a><span data-ttu-id="8f067-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8f067-109">Before you start</span></span>  
  
1.  <span data-ttu-id="8f067-110">Cuando se crean los grupos de dominio para el entorno de BizTalk Server, se deben crear grupos globales de dominios de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f067-110">When you create the domain groups for your BizTalk Server environment, you must create Active Directory domain global groups.</span></span>  
  
2.  <span data-ttu-id="8f067-111">Configure el clúster de SQL Server antes de instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f067-111">Configure the SQL Server cluster before you install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8f067-112">Para obtener más información sobre los clústeres de SQL Server, vea [siempre en Failover Cluster Instances](https://technet.microsoft.com/library/ms189134.aspx).</span><span class="sxs-lookup"><span data-stu-id="8f067-112">For more information about clustering SQL Server, see [Always On Failover Cluster Instances](https://technet.microsoft.com/library/ms189134.aspx).</span></span>  
  
3.  <span data-ttu-id="8f067-113">Si además va a agrupar el servidor secreto principal, configure éste primero.</span><span class="sxs-lookup"><span data-stu-id="8f067-113">If you are also clustering the master secret server, configure that server first.</span></span> <span data-ttu-id="8f067-114">Para obtener más información sobre la alta disponibilidad para Enterprise Single Sign-On, vea [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).</span><span class="sxs-lookup"><span data-stu-id="8f067-114">For more information about high availability for Enterprise Single Sign-On, see [High Availability for Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).</span></span>  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a><span data-ttu-id="8f067-115">Para ejecutar el Asistente para configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8f067-115">To run the BizTalk Server Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="8f067-116">Instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un servidor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f067-116">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a runtime server.</span></span>  
  
2.  <span data-ttu-id="8f067-117">Inicie el programa de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8f067-117">Launch the BizTalk Configuration Program.</span></span> <span data-ttu-id="8f067-118">Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="8f067-118">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3.  <span data-ttu-id="8f067-119">Siga los pasos de [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md) para aplicar una configuración personalizada.</span><span class="sxs-lookup"><span data-stu-id="8f067-119">Follow the steps in [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md) to apply a custom configuration.</span></span> <span data-ttu-id="8f067-120">Para especificar el clúster de SQL Server para las bases de datos de BizTalk, escriba el nombre del clúster de SQL Server en el **bases de datos** cuadro de diálogo del programa de configuración, como se describe en el **editar bases de datos** sección de este tema.</span><span class="sxs-lookup"><span data-stu-id="8f067-120">To specify the SQL Server cluster for the BizTalk databases, enter the name of the SQL Server cluster in the **Databases** dialog of the configuration program as described in the **Editing Databases** section of this topic.</span></span>  
  
4.  <span data-ttu-id="8f067-121">Completar la configuración de BizTalk Server, siga las instrucciones que aparecen en [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="8f067-121">Complete the BizTalk Server configuration by following the instructions in [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f067-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f067-122">See Also</span></span>  
 [<span data-ttu-id="8f067-123">Crear un entorno de alta disponibilidad de servidor de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8f067-123">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)