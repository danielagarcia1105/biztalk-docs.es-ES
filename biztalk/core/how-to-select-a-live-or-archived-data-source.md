---
title: Cómo seleccionar un origen de datos activos o archivados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7172a822a71e2b0d7dc621e6c1e11b055b723bd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255292"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="e7ebd-102">Cómo seleccionar un origen de datos activo o archivado</span><span class="sxs-lookup"><span data-stu-id="e7ebd-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="e7ebd-103">BizTalktracking permite obtener acceso a los datos archivados y dinámicos.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="e7ebd-104">Seleccione un origen de datos activos o archivados en la página principal **administración de BizTalk Server** nodo consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="e7ebd-105">El origen predeterminado son los datos activos, que se recuperan de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="e7ebd-106">Si decide utilizar datos archivados, deberá seleccionar los servidores y bases de datos apropiados con los que desee trabajar.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  
  
-   <span data-ttu-id="e7ebd-107">Los datos archivados: analizar datos archivados permite examinar tendencias tanto en su empresa como en el sistema, puesto que pueden ser anteriores como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="e7ebd-108">Si selecciona datos archivados, debe seleccionar también los correspondientes servidores y bases de datos de SQL Server que contienen los datos archivados.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  
  
     <span data-ttu-id="e7ebd-109">Los datos archivados se designan al seleccionar **conectar a una base de datos de seguimiento existente...** .</span><span class="sxs-lookup"><span data-stu-id="e7ebd-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  
  
-   <span data-ttu-id="e7ebd-110">Datos activos: analizar datos activos permite supervisar orquestaciones y canalizaciones, para que pueda identificar y corregir problemas en el desarrollo o el entorno de ensayo.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="e7ebd-111">Supervisar datos activos permite también corregir problemas del sistema, tal como por qué se suspenden los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  
  
     <span data-ttu-id="e7ebd-112">Datos activos se designan al seleccionar **conectar a un grupo existente...** .</span><span class="sxs-lookup"><span data-stu-id="e7ebd-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7ebd-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e7ebd-113">Prerequisites</span></span>  
 <span data-ttu-id="e7ebd-114">Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-select-live-data"></a><span data-ttu-id="e7ebd-115">Para seleccionar datos activos</span><span class="sxs-lookup"><span data-stu-id="e7ebd-115">To select live data</span></span>  
  
1.  <span data-ttu-id="e7ebd-116">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e7ebd-117">Haga clic en el método main **administración de BizTalk Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-117">Click the main  **BizTalk Server Administration** node.</span></span>  
  
3.  <span data-ttu-id="e7ebd-118">Haga clic en **conectar a un grupo existente...**</span><span class="sxs-lookup"><span data-stu-id="e7ebd-118">Click **Connect to an existing group…**</span></span>  
  
4.  <span data-ttu-id="e7ebd-119">En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  
  
5.  <span data-ttu-id="e7ebd-120">En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  
  
6.  <span data-ttu-id="e7ebd-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-121">Click **OK**.</span></span>  
  
### <a name="to-select-archived-data"></a><span data-ttu-id="e7ebd-122">Para seleccionar datos archivados</span><span class="sxs-lookup"><span data-stu-id="e7ebd-122">To select archived data</span></span>  
  
1.  <span data-ttu-id="e7ebd-123">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e7ebd-124">Haga clic en el método main **administración de BizTalk Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-124">Click the main  **BizTalk Server Administration** node.</span></span>  
  
3.  <span data-ttu-id="e7ebd-125">Haga clic en **conectar a una base de datos de seguimiento existente...**</span><span class="sxs-lookup"><span data-stu-id="e7ebd-125">Click **Connect to an existing tracking database…**</span></span>  
  
4.  <span data-ttu-id="e7ebd-126">En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  
  
5.  <span data-ttu-id="e7ebd-127">En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  
  
6.  <span data-ttu-id="e7ebd-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7ebd-128">Click **OK**.</span></span>