---
title: Cómo seleccionar un origen de datos activos o archivados | Microsoft Docs
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
ms.openlocfilehash: 83f034a41fffa0c646b0173e8b889c20373760ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967157"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="f16f2-102">Cómo seleccionar un origen de datos activo o archivado</span><span class="sxs-lookup"><span data-stu-id="f16f2-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="f16f2-103">BizTalktracking permite obtener acceso a los datos archivados y dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f16f2-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="f16f2-104">Seleccione un origen de datos activo o archivado en la página principal **administración de BizTalk Server** nodo consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f16f2-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="f16f2-105">El origen predeterminado son los datos activos, que se recuperan de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f16f2-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="f16f2-106">Si decide utilizar datos archivados, deberá seleccionar los servidores y bases de datos apropiados con los que desee trabajar.</span><span class="sxs-lookup"><span data-stu-id="f16f2-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  

-   <span data-ttu-id="f16f2-107">Los datos archivados: analizar datos archivados permite examinar tendencias tanto en su empresa en el sistema, puesto que pueden ser anteriores como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f16f2-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="f16f2-108">Si selecciona datos archivados, debe seleccionar también los correspondientes servidores y bases de datos de SQL Server que contienen los datos archivados.</span><span class="sxs-lookup"><span data-stu-id="f16f2-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  

     <span data-ttu-id="f16f2-109">Los datos archivados se designan al seleccionar **conectarse a una base de datos de seguimiento existente...** .</span><span class="sxs-lookup"><span data-stu-id="f16f2-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  

-   <span data-ttu-id="f16f2-110">Datos en directo: analizar datos activos permite supervisar orquestaciones y canalizaciones, para que pueda identificar y corregir problemas en el desarrollo o entorno de ensayo.</span><span class="sxs-lookup"><span data-stu-id="f16f2-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="f16f2-111">Supervisar datos activos permite también corregir problemas del sistema, tal como por qué se suspenden los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f16f2-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  

     <span data-ttu-id="f16f2-112">Datos activos se designan al seleccionar **conectarse a un grupo existente...** .</span><span class="sxs-lookup"><span data-stu-id="f16f2-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f16f2-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f16f2-113">Prerequisites</span></span>  
 <span data-ttu-id="f16f2-114">Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f16f2-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  

### <a name="to-select-live-data"></a><span data-ttu-id="f16f2-115">Para seleccionar datos activos</span><span class="sxs-lookup"><span data-stu-id="f16f2-115">To select live data</span></span>  

1. <span data-ttu-id="f16f2-116">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f16f2-117">Haga clic en el método main **administración de BizTalk Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="f16f2-117">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="f16f2-118">Haga clic en **conectarse a un grupo existente...**</span><span class="sxs-lookup"><span data-stu-id="f16f2-118">Click **Connect to an existing group…**</span></span>  

4. <span data-ttu-id="f16f2-119">En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f16f2-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="f16f2-120">En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="f16f2-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-121">Click **OK**.</span></span>  

### <a name="to-select-archived-data"></a><span data-ttu-id="f16f2-122">Para seleccionar datos archivados</span><span class="sxs-lookup"><span data-stu-id="f16f2-122">To select archived data</span></span>  

1. <span data-ttu-id="f16f2-123">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f16f2-124">Haga clic en el método main **administración de BizTalk Server** nodo.</span><span class="sxs-lookup"><span data-stu-id="f16f2-124">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="f16f2-125">Haga clic en **conectarse a una base de datos de seguimiento existente...**</span><span class="sxs-lookup"><span data-stu-id="f16f2-125">Click **Connect to an existing tracking database…**</span></span>  

4. <span data-ttu-id="f16f2-126">En el **nombre de SQL Server** , escriba el nombre del servidor que hospeda la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f16f2-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="f16f2-127">En el **nombre de base de datos** cuadro de lista desplegable, seleccione **BizTalkMgmtDb**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="f16f2-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f16f2-128">Click **OK**.</span></span>
