---
title: Cómo las bases de datos de marca el servidor BizTalk Server para la supervisión personalizada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea069140b9dd89fafa13fe57be9eefa17eceb790
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023714"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="cd5c6-102">Cómo marcar bases de datos de BizTalk Server para la supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="cd5c6-102">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>
<span data-ttu-id="cd5c6-103">Si ha instalado Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración, puede personalizar la forma [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se supervisan las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-103">If you have installed the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack, you can customize the way [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are monitored.</span></span> <span data-ttu-id="cd5c6-104">Esto garantiza que el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] módulo de administración supervisa los siguientes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos:</span><span class="sxs-lookup"><span data-stu-id="cd5c6-104">This ensures that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack monitors the following [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases:</span></span>  
  
-   <span data-ttu-id="cd5c6-105">Base de datos de archivo de BAM (BAMArchive)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-105">BAM Archive (BAMArchive) database</span></span>  
  
-   <span data-ttu-id="cd5c6-106">Base de datos de importación principal de BAM BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="cd5c6-106">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="cd5c6-107">Base de datos de esquema de estrella (BAMStarSchema)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-107">BAM Star Schema (BAMStarSchema) database</span></span>  
  
-   <span data-ttu-id="cd5c6-108">Base de datos de seguimiento de BizTalk (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-108">BizTalk Tracking (BizTalkDTADb) database</span></span>  
  
-   <span data-ttu-id="cd5c6-109">Base de datos de administración de BizTalk  (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-109">BizTalk Management (BizTalkMgmtDb) database</span></span>  
  
-   <span data-ttu-id="cd5c6-110">Base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-110">BizTalk MessageBox (BizTalkMsgBoxDb) database</span></span>  
  
-   <span data-ttu-id="cd5c6-111">Base de datos del motor de reglas (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-111">Rule Engine (BizTalkRuleEngineDb) database</span></span>  
  
-   <span data-ttu-id="cd5c6-112">Base de datos de inicio de sesión único empresarial (SSODB)</span><span class="sxs-lookup"><span data-stu-id="cd5c6-112">Enterprise Single Sign-On (SSODB) database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd5c6-113">Debe haber iniciado sesión como un miembro del rol de Operations Manager Advanced Operator o [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] grupo de administración.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-113">You must be logged on as a member of the Operations Manager Advanced Operator role or [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] Management Group.</span></span>  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="cd5c6-114">Para marcar las bases de datos de BizTalk Server para la supervisión personalizada</span><span class="sxs-lookup"><span data-stu-id="cd5c6-114">To mark BizTalk Server databases for customized monitoring</span></span>  
  
1. <span data-ttu-id="cd5c6-115">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **System Center Operations Manager 2007**y, a continuación, haga clic en **consola del operador**.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-115">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007**, and then click **Operations Console**.</span></span>  
  
2. <span data-ttu-id="cd5c6-116">En la consola del operador, haga clic en el **Authoring** botón.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-116">In the Operations console, click the **Authoring** button.</span></span>  
  
3. <span data-ttu-id="cd5c6-117">En el **Authoring** panel, expanda **objetos del módulo de administración**y, a continuación, haga clic en **detecciones de objetos**.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-117">In the **Authoring** pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
4. <span data-ttu-id="cd5c6-118">Para buscar una detección para SQL Server, en la barra de herramientas de la consola de operador, haga clic en **buscar**y en el **buscar** cuadro de texto escriba **SQL 2008** para buscar SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-118">To locate a discovery for SQL Server, on the Operations console toolbar click **Find**, and in the **Look for** text box enter **SQL 2008** to search for SQL Server 2008.</span></span>  
  
5. <span data-ttu-id="cd5c6-119">En el **tipo detectado: SQL 2008 DB** categoría, seleccione **detectar bases de datos de un motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-119">Under the **Discovered Type: SQL 2008 DB** category, select **Discover Databases for a Database Engine**.</span></span>  
  
6. <span data-ttu-id="cd5c6-120">En la barra de herramientas de la consola de operaciones, haga clic en **invalida** y, a continuación, elija **invalidar la detección de objetos**.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-120">On the Operations console toolbar, click **Overrides** and then point to **Override the Object Discovery**.</span></span> <span data-ttu-id="cd5c6-121">Puede elegir invalidar la detección para los objetos de un tipo específico o para todos los objetos dentro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-121">You can choose to override the discovery for objects of a specific type or for all objects within a group.</span></span> <span data-ttu-id="cd5c6-122">Después de elegir qué grupo de tipo de objeto va a invalidar, el **propiedades de invalidación** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-122">After you choose which group of object type to override, the **Override Properties** dialog box opens.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="cd5c6-123">Si el **invalida** botón no está disponible, asegúrese de que ha seleccionado un monitor y no un objeto contenedor en el panel monitores.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-123">If the **Overrides** button is not available, make sure you have selected a monitor and not a container object in the Monitors pane.</span></span>  
  
7. <span data-ttu-id="cd5c6-124">Active la casilla situada en la **invalidar** columna junto a la **lista de exclusión** parámetro y en el **Reemplazar valor** columna, escriba el nombre de la base de datos que desea excluir de la supervisión.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-124">Select the check box in the **Override** column next to the **Exclude List** parameter, and in the **Override Value** column, type the name of the database that you want to exclude from monitoring.</span></span> <span data-ttu-id="cd5c6-125">Asegúrese de que el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no aparecen en las bases de datos que desea supervisar el **Reemplazar valor** columna.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-125">Make sure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that you want to monitor are not listed in the **Override Value** column.</span></span>  
  
   > [!TIP]  
   >  <span data-ttu-id="cd5c6-126">Puede usar las detecciones de objeto modificado para crear un nuevo módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-126">You can use the modified object discoveries to create a new management pack.</span></span> <span data-ttu-id="cd5c6-127">En la parte inferior del panel, el **Seleccionar módulo de administración de destino** desplegable muestra un valor predeterminado de **módulo de administración predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-127">At the bottom of the pane, the **Select destination management pack** drop-down shows a default value of **Default Management Pack**.</span></span> <span data-ttu-id="cd5c6-128">Haga clic en **New** para crear un nuevo módulo de administración con las detecciones de objeto modificado.</span><span class="sxs-lookup"><span data-stu-id="cd5c6-128">Click **New** to create a new management pack using the modified object discoveries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5c6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd5c6-129">See Also</span></span>  
 [<span data-ttu-id="cd5c6-130">Supervisión de servidores SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd5c6-130">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)