---
title: Cómo copiar mensajes controlados en la base de datos de seguimiento de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a><span data-ttu-id="f4d11-102">Cómo copiar mensajes de los que se ha realizado un seguimiento en la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f4d11-102">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>
<span data-ttu-id="f4d11-103">El proceso de archivo y purga puede obtener acceso a las bases de datos de servidores SQL Server diferentes o actualizarlas, por lo que es preciso configurar servidores vinculados entre las instancias implicadas de servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4d11-103">The archiving and purging process potentially accesses and/or updates databases in different SQL servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="f4d11-104">Puede copiar directamente mensajes de los que se ha efectuado un seguimiento del servidor de base de datos de cuadro de mensajes (BizTalkMsgBoxDb) a la base de datos de seguimiento de BizTalk (BizTalkDTADb) a través de un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="f4d11-104">You can directly copy tracked messages from the BizTalk MessageBox (BizTalkMsgBoxDb) database server to your BizTalk Tracking (BizTalkDTADb) database using a linked server.</span></span> <span data-ttu-id="f4d11-105">Debe configurar servidores vinculados entre:</span><span class="sxs-lookup"><span data-stu-id="f4d11-105">You must set up linked servers between:</span></span>  
  
-   <span data-ttu-id="f4d11-106">Cada una de sus bases de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) y la base de datos de seguimiento de BizTalk (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="f4d11-106">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
-   <span data-ttu-id="f4d11-107">La base de datos de seguimiento de BizTalk (BizTalkDTADb) y el servidor de validación para la validación de archivos.</span><span class="sxs-lookup"><span data-stu-id="f4d11-107">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
-   <span data-ttu-id="f4d11-108">Las cuentas de servicio del Agente SQL Server del equipo que aloja la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) deben contar con los permisos db_datareader y db_datawriter para la base de datos de seguimiento de BizTalk (BizTalkDTADb) del servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="f4d11-108">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4d11-109">En el Agente SQL Server, compruebe que el trabajo de copia se ejecuta sin que se produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="f4d11-109">In SQL Server Agent, verify that the copy job runs without errors.</span></span> <span data-ttu-id="f4d11-110">De lo contrario, los errores podrían impedir que los datos se movieran a la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f4d11-110">Otherwise, errors might prevent data from being moved to the tracking database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4d11-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f4d11-111">Prerequisites</span></span>  
 <span data-ttu-id="f4d11-112">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4d11-112">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a><span data-ttu-id="f4d11-113">Para copiar mensajes controlados en la base de datos de seguimiento de BizTalk (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="f4d11-113">To copy tracked messages into the BizTalk Tracking database (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="f4d11-114">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-114">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f4d11-115">En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectar con el servidor SQL server apropiado.</span><span class="sxs-lookup"><span data-stu-id="f4d11-115">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL server.</span></span>  
  
3.  <span data-ttu-id="f4d11-116">En **Microsoft SQL Server Management Studio**, haga doble clic en **Agente SQL Server**y, a continuación, haga clic en **trabajos**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-116">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="f4d11-117">En el panel de detalles, haga clic en **TrackedMessages_Copy_BizTalkMsgBoxDb**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-117">In the details pane, right-click **TrackedMessages_Copy_BizTalkMsgBoxDb**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f4d11-118">En el **propiedades del trabajo - TrackedMessages_Copy_BizTalkMsgBoxDb** cuadro de diálogo **seleccionar una página**, haga clic en **pasos**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-118">In the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="f4d11-119">En **lista de pasos de trabajo**, haga clic en **purgar**y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-119">Under **Job step list**, click **Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="f4d11-120">En el **comando** cuadro, edite los parámetros de los nombres de base de datos según corresponda y el servidor de seguimiento y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-120">In the **Command** box, edit the tracking server and database names parameters as appropriate, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f4d11-121">En el **propiedades del trabajo - TrackedMessages_Copy_BizTalkMsgBoxDb** cuadro de diálogo **seleccionar una página**, haga clic en **General**, seleccione la **habilitado** casilla de verificación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f4d11-121">On the **Job Properties - TrackedMessages_Copy_BizTalkMsgBoxDb** dialog box, under **Select a page**, click **General**,select the **Enabled** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4d11-122">Los mensajes se copiarán de la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) a la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="f4d11-122">The messages will be copied from the BizTalk MessageBox (BizTalkMsgBoxDb) to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4d11-123">Si agrega una nueva base de datos de cuadro de mensajes, tendrá que volver a realizar este procedimiento para ella.</span><span class="sxs-lookup"><span data-stu-id="f4d11-123">If you add a new MessageBox database, you will need to perform this procedure again for the new MessageBox database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d11-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4d11-124">See Also</span></span>  
 [<span data-ttu-id="f4d11-125">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f4d11-125">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)