---
title: Cómo purgar datos manualmente desde la base de datos de cuadro de mensajes en un entorno de prueba | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 398991a9-344a-487a-a817-dfc97d48ebe6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6d5f8b232e31a140ee4786b87d2bb270505f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254060"
---
# <a name="how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment"></a><span data-ttu-id="92c9e-102">Purga manual de datos de la base de datos de cuadro de mensaje en un entorno de prueba</span><span class="sxs-lookup"><span data-stu-id="92c9e-102">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>
<span data-ttu-id="92c9e-103">Al ejecutar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de desarrollo o prueba, los datos almacenados en la base de datos de cuadro de mensajes no son normalmente datos económicos importantes "activos", por lo cual pueden eliminarse.</span><span class="sxs-lookup"><span data-stu-id="92c9e-103">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a development or test environment, data that is stored in the MessageBox database is not usually business critical "live" data and therefore may be deleted.</span></span> <span data-ttu-id="92c9e-104">En estos casos, es posible que necesite un método "rápido y sucio" para depurar datos desde la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="92c9e-104">In these scenarios, you may need a "quick and dirty" method for purging data from the MessageBox database.</span></span> <span data-ttu-id="92c9e-105">Siga los procedimientos de este tema para depurar datos manualmente desde la base de datos de cuadro de mensajes usando el procedimiento almacenado bts_CleanupMsgbox.</span><span class="sxs-lookup"><span data-stu-id="92c9e-105">Follow the procedures in this topic to manually purge data from the MessageBox database using the bts_CleanupMsgbox stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92c9e-106">solo debe realizar estos pasos en un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="92c9e-106">You should only perform these steps in a test environment.</span></span> <span data-ttu-id="92c9e-107">No se admite la depuración manual de la base de datos de cuadro de mensajes de BizTalk en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="92c9e-107">Manually purging the BizTalk MessageBox database in a production environment is not supported.</span></span>  
  
### <a name="to-stop-biztalk-services"></a><span data-ttu-id="92c9e-108">Procedimiento para detener los servicios de BizTalk</span><span class="sxs-lookup"><span data-stu-id="92c9e-108">To stop BizTalk services</span></span>  
  
1.  <span data-ttu-id="92c9e-109">Detenga cualquier instancia del servicio de BizTalk desde la consola Servicios.</span><span class="sxs-lookup"><span data-stu-id="92c9e-109">Stop any instances of the BizTalk service from the Services console.</span></span>  
  
2.  <span data-ttu-id="92c9e-110">Si está ejecutando adaptadores en hosts aislados (por ejemplo, HTTP, SOAP o WCF), reinicie IIS ejecutando IISRESET desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="92c9e-110">If you are running any adapters in isolated hosts (for example HTTP, SOAP, or WCF), restart IIS by running the IISRESET from a command prompt.</span></span>  
  
3.  <span data-ttu-id="92c9e-111">Cierre cualquier adaptador aislado personalizado que esté en ejecución.</span><span class="sxs-lookup"><span data-stu-id="92c9e-111">Shut down any custom Isolated Adapters that are running.</span></span>  
  
### <a name="to-create-and-execute-the-btscleanupmsgbox-stored-procedure-using-sql-server-2008"></a><span data-ttu-id="92c9e-112">Para crear y ejecutar el procedimiento almacenado bts_CleanupMsgbox con SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="92c9e-112">To create and execute the bts_CleanupMsgbox stored procedure using SQL Server 2008</span></span>  
  
1.  <span data-ttu-id="92c9e-113">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="92c9e-113">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="92c9e-114">En el **conectar con SQL Server** cuadro de diálogo, seleccione el servidor SQL server y el método de autenticación adecuado y, a continuación, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="92c9e-114">In the **Connect to SQL Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="92c9e-115">En el **bases de datos disponibles** lista desplegable, seleccione la base de datos de BizTalk Messagebox (**BizTalkMsgBoxDB** de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="92c9e-115">In the **Available databases** drop-down list, select the BizTalk Messagebox database (**BizTalkMsgBoxDB** by default).</span></span>  
  
4.  <span data-ttu-id="92c9e-116">Haga clic en el **nueva consulta** icono en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="92c9e-116">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="92c9e-117">Abra la **msgbox_cleanup_logic.sql** archivo desde SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="92c9e-117">Open the **msgbox_cleanup_logic.sql** file from SQL Server Management Studio.</span></span> <span data-ttu-id="92c9e-118">El archivo msgbox_cleanup_logic.sql se encuentra en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ del equipo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="92c9e-118">The msgbox_cleanup_logic.sql file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\ directory of the BizTalk Server computer.</span></span>  
  
6.  <span data-ttu-id="92c9e-119">Haga clic en el **Ejecutar consulta** icono en la barra de herramientas para ejecutar el script para crear el bts_CleanupMsgbox procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="92c9e-119">Click the **Execute Query** icon on the toolbar to run the script to create the bts_CleanupMsgbox stored procedure.</span></span> <span data-ttu-id="92c9e-120">El procedimiento almacenado bts_CleanupMsgbox puede verse a continuación en la lista de procedimientos almacenados como dbo.bts_CleanupMsgbox.</span><span class="sxs-lookup"><span data-stu-id="92c9e-120">The bts_CleanupMsgbox stored procedure can then be viewed in the list of stored procedures as dbo.bts_CleanupMsgbox.</span></span>  
  
7.  <span data-ttu-id="92c9e-121">Haga clic en el **nueva consulta** icono en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="92c9e-121">Click the **New Query** icon on the toolbar.</span></span>  
  
8.  <span data-ttu-id="92c9e-122">Pegue el siguiente comando en la nueva ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="92c9e-122">Paste the following command into the new query window:</span></span>  
  
    ```  
    exec bts_CleanupMsgbox  
    ```  
  
9. <span data-ttu-id="92c9e-123">Haga clic en el **Ejecutar consulta** icono en la barra de herramientas para ejecutar la bts_CleanupMsgbox procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="92c9e-123">Click the **Execute Query** icon on the toolbar to run the bts_CleanupMsgbox stored procedure.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="92c9e-124">No ejecute el procedimiento almacenado bts_CleanupMsgbox en un servidor de producción que esté ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92c9e-124">Do not run the bts_CleanupMsgbox stored procedure on a production server that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="92c9e-125">solo debe ejecutar el procedimiento almacenado bts_CleanupMsgbox en un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="92c9e-125">You should only run the bts_CleanupMsgbox stored procedure in a test environment.</span></span> <span data-ttu-id="92c9e-126">No se admite la ejecución del procedimiento almacenado bts_CleanupMsgbox en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="92c9e-126">Running the bts_CleanupMsgbox stored procedure in a production environment is not supported.</span></span>  
  
10. <span data-ttu-id="92c9e-127">Reinicie los servicios de BizTalk según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="92c9e-127">Restart BizTalk services as needed.</span></span>  
  
## <a name="considerations-when-running-the-btscleanupmsgbox-stored-procedure"></a><span data-ttu-id="92c9e-128">Consideraciones al ejecutar el procedimiento almacenado bts_CleanupMsgbox</span><span class="sxs-lookup"><span data-stu-id="92c9e-128">Considerations when running the bts_CleanupMsgbox stored procedure</span></span>  
 <span data-ttu-id="92c9e-129">Las siguientes consideraciones se aplican al ejecutar el procedimiento almacenado bts_CleanupMsgbox:</span><span class="sxs-lookup"><span data-stu-id="92c9e-129">The following considerations apply when running the bts_CleanupMsgbox stored procedure:</span></span>  
  
1.  <span data-ttu-id="92c9e-130">Si instala una revisión de seguridad en el sistema de prueba que actualiza los esquemas de base de datos de BizTalk, la revisión de seguridad podría sobrescribir el procedimiento almacenado bts_CleanupMsgbox con una versión vacía de dicho procedimiento.</span><span class="sxs-lookup"><span data-stu-id="92c9e-130">If you install a hot fix onto your test system that updates the BizTalk database schemas, the hot fix may overwrite the bts_CleanupMsgbox stored procedure with an empty version of this stored procedure.</span></span> <span data-ttu-id="92c9e-131">En tal caso, deberá seguir los procedimientos descritos en este tema para volver a crear el procedimiento almacenado bts_CleanupMsgbox.</span><span class="sxs-lookup"><span data-stu-id="92c9e-131">In this case, you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
2.  <span data-ttu-id="92c9e-132">Si crea una nueva base de datos MessageBox, el procedimiento almacenado bts_CleanupMsgbox se vaciará y deberá seguir los procedimientos descritos en este tema para volver a crear el procedimiento almacenado bts_CleanupMsgbox.</span><span class="sxs-lookup"><span data-stu-id="92c9e-132">If you create a new MessageBox database, the bts_CleanupMsgbox stored procedure will be empty and you will need to follow the procedures outlined in this topic to recreate the bts_CleanupMsgbox stored procedure.</span></span>  
  
3.  <span data-ttu-id="92c9e-133">Uso del procedimiento almacenado bts_CleanupMsgbox es **no admite** en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="92c9e-133">Use of the bts_CleanupMsgbox stored procedure is **not supported** on a production system.</span></span> <span data-ttu-id="92c9e-134">Este procedimiento almacenado eliminará todos los datos de su base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="92c9e-134">This stored procedure will delete all of the data in your MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c9e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="92c9e-135">See Also</span></span>  
 [<span data-ttu-id="92c9e-136">Cómo purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="92c9e-136">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)