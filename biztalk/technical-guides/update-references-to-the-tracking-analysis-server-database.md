---
title: "Actualizar las referencias a la base de datos del servidor de análisis de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b85c5c50bc8aeb388d6b7df1591f4b13900998e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a><span data-ttu-id="3cafe-102">Actualizar las referencias a la base de datos del servidor de análisis de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3cafe-102">Update References to the Tracking Analysis Server Database</span></span>
<span data-ttu-id="3cafe-103">La base de datos del servidor de análisis de seguimiento es opcional y contiene los cubos de procesamiento analítico en línea (OLAP).</span><span class="sxs-lookup"><span data-stu-id="3cafe-103">The Tracking Analysis Server database is an optional and contains the online analytical processing (OLAP) cubes.</span></span> <span data-ttu-id="3cafe-104">Estos cubos OLAP son agregaciones de datos contenidos en la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="3cafe-104">These OLAP cubes are aggregations of data contained in the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="3cafe-105">Para restaurar la base de datos del servidor de análisis de seguimiento, use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager para procesar los cubos MessageMetrics y ServiceMetrics.</span><span class="sxs-lookup"><span data-stu-id="3cafe-105">To restore the Tracking Analysis Server database, use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager to process the MessageMetrics and ServiceMetrics cubes.</span></span> <span data-ttu-id="3cafe-106">Para obtener instrucciones, consulte [administrar Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (http://go.microsoft.com/fwlink/?LinkId=130939) en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="3cafe-106">For instructions, see [Managing Backing Up and Restoring (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (http://go.microsoft.com/fwlink/?LinkId=130939) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3cafe-107">Para restaurar la base de datos de seguimiento de Analysis Server en un equipo alternativo, también debe actualizar las referencias al nombre de base de datos en la base de datos de administración de BizTalk mediante el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cafe-107">To restore the Tracking Analysis Server database to an alternate computer, you must also update references to the database name in the BizTalk Management database by using the following procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3cafe-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3cafe-108">Prerequisites</span></span>  
 <span data-ttu-id="3cafe-109">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cafe-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a><span data-ttu-id="3cafe-110">Para actualizar referencias al nombre de base de datos de seguimiento de Analysis Server</span><span class="sxs-lookup"><span data-stu-id="3cafe-110">To update references to the Tracking Analysis Server database name</span></span>  
  
1.  <span data-ttu-id="3cafe-111">En el sistema de destino, haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008**y, a continuación, haga clic en **deSQLServerManagementStudio**.</span><span class="sxs-lookup"><span data-stu-id="3cafe-111">On the destination system, click **Start**, click **Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="3cafe-112">En el **conectar al servidor** cuadro de diálogo, seleccione la **tipo de servidor** como **motor de base de datos**, proporcione un nombre de servidor, proporcione las credenciales para conectarse o el servidor y, a continuación, Haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="3cafe-112">In the **Connect to Server** dialog box, select the **Server type** as **Database Engine**, provide a server name, provide the credentials to connect ot the server, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="3cafe-113">Abra el servidor adecuado haciendo clic en él, haga doble clic en **bases de datos**, haciendo doble clic en **BizTalkMgmtDb**y, a continuación, haga clic en **tablas**.</span><span class="sxs-lookup"><span data-stu-id="3cafe-113">Open the appropriate server by clicking it, double-clicking **Databases**, double-clicking **BizTalkMgmtDb**, and then clicking **Tables**.</span></span>  
  
4.  <span data-ttu-id="3cafe-114">En el panel de detalles, haga clic en **adm_Group**y, a continuación, seleccione **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="3cafe-114">In the details pane, right-click **adm_Group**, and then point to **Open Table**.</span></span>  
  
5.  <span data-ttu-id="3cafe-115">Modifique las columnas que corresponden a la base de datos original para hacer referencia a los valores apropiados de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="3cafe-115">Modify the columns corresponding to the original database to reference the appropriate values for the new database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cafe-116">*\<DBType\>*  DBServerName y  *\<DBType\>*  DBName indican la ubicación de la base de datos, donde  *\<DBType\>*  corresponde al tipo de la base de datos, por ejemplo, TrackingAnalysis.</span><span class="sxs-lookup"><span data-stu-id="3cafe-116">*\<DBType\>* DBServerName and *\<DBType\>* DBName indicate the location of the database, where *\<DBType\>* corresponds to the type of the database, for example, TrackingAnalysis.</span></span>  
  
6.  <span data-ttu-id="3cafe-117">Cierre la tabla para guardar los valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="3cafe-117">Close the table to save the new values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cafe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cafe-118">See Also</span></span>  
 [<span data-ttu-id="3cafe-119">Actualización de referencias de base de datos</span><span class="sxs-lookup"><span data-stu-id="3cafe-119">Updating Database References</span></span>](../technical-guides/updating-database-references.md)