---
title: Cómo conectarse a un grupo existente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942093faa4a556f31d090de97b3feff4eb7a9a45
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-connect-to-an-existing-group"></a><span data-ttu-id="62069-102">Cómo efectuar una conexión a un grupo existente</span><span class="sxs-lookup"><span data-stu-id="62069-102">How to Connect to an Existing Group</span></span>
<span data-ttu-id="62069-103">La consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede usarse en cualquier equipo de la empresa para administrar de forma remota uno o varios grupos de BizTalk Server en ella, siempre y cuando estos grupos se encuentre en equipos del mismo dominio o en dominios de confianza.</span><span class="sxs-lookup"><span data-stu-id="62069-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console on any computer in your enterprise to remotely manage one or more BizTalk Server groups within your enterprise, as long as these groups are located on computers within the same domain or within trusted domains.</span></span>  
  
 <span data-ttu-id="62069-104">El nodo de administración de BizTalk Server en la consola de administración de BizTalk Server es el nodo de nivel más alto para todos los grupos de BizTalk y es el nivel que utiliza cuando se agrega un grupo de BizTalk Server existente a la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="62069-104">The BizTalk Server Administration node in the BizTalk Server Administration console is the highest-level node for all BizTalk groups, and is the level that you use when adding an existing BizTalk Server group to the BizTalk Server Administration console.</span></span> <span data-ttu-id="62069-105">Al agregar un grupo, es preciso especificar un servidor existente y una base de datos de administración de BizTalk con la cual se desea efectuar la conexión.</span><span class="sxs-lookup"><span data-stu-id="62069-105">When you add a group, you must specify an existing server and BizTalk Management database to which you want to connect.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="62069-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="62069-106">Prerequisites</span></span>  
 <span data-ttu-id="62069-107">Para llevar a cabo este procedimiento, debe iniciar sesión como miembro del grupo de operadores de BizTalk Server o de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="62069-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group or as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-connect-to-an-existing-group"></a><span data-ttu-id="62069-108">Para efectuar una conexión a un grupo existente</span><span class="sxs-lookup"><span data-stu-id="62069-108">To connect to an existing group</span></span>  
  
1.  <span data-ttu-id="62069-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="62069-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="62069-110">En el árbol de consola, haga clic en **administración de BizTalk Server**y, a continuación, haga clic en **conectar a grupo existente**.</span><span class="sxs-lookup"><span data-stu-id="62069-110">In the console tree, right-click **BizTalk Server Administration**, and then click **Connect to Existing Group**.</span></span>  
  
3.  <span data-ttu-id="62069-111">En el **conectarse a base de configuración de servidor de BizTalk existente** cuadro de diálogo, en la **nombre de SQL Server** lista desplegable, seleccione el nombre de la instancia de Microsoft SQL Server que hospeda el BizTalk Base de datos de administración (conocido también como la base de datos de configuración).</span><span class="sxs-lookup"><span data-stu-id="62069-111">In the **Connect to Existing BizTalk Server Configuration Database** dialog box, in the **SQL Server name** drop-down list box, select the name of the Microsoft SQL Server instance that hosts the BizTalk Management database (also referred to as the Configuration database).</span></span> <span data-ttu-id="62069-112">Al seleccionar la instancia de servidor SQL Server, BizTalk Server intenta detectar automáticamente las bases de datos de BizTalk Server del equipo.</span><span class="sxs-lookup"><span data-stu-id="62069-112">When you select the instance of SQL Server, BizTalk Server automatically attempts to detect BizTalk Server databases on that computer.</span></span>  
  
4.  <span data-ttu-id="62069-113">En el **nombre de base de datos** lista desplegable, seleccione la base de datos de administración de BizTalk Server (**BizTalkMgmtDb**) al que desea conectarse y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="62069-113">In the **Database name** drop-down list box, select the BizTalk Server Management database (**BizTalkMgmtDb**) to which you want to connect, and then click **OK**.</span></span>  
  
     <span data-ttu-id="62069-114">La consola de administración de BizTalk Server agrega el grupo de BizTalk Server en el árbol de consola.</span><span class="sxs-lookup"><span data-stu-id="62069-114">The BizTalk Server Administration console adds the BizTalk Server group to the console tree.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62069-115">Si la base de datos de administración de BizTalk Server se aloja en un clúster de SQL Server y éste lleva a cabo una conmutación por error, es posible que aparezca un error similar al siguiente cuando se intenta efectuar la conexión con la base de datos de administración:</span><span class="sxs-lookup"><span data-stu-id="62069-115">If the BizTalk Server Management database is housed on a SQL Server cluster and the cluster is in the process of failing over then you may receive an error similar to the following when you attempt to connect to the Management database:</span></span>  
    >   
    >  <span data-ttu-id="62069-116">No se pudo cargar el grupo [\<servername\>:\<base de datos de administración\>] proveedores de datos.</span><span class="sxs-lookup"><span data-stu-id="62069-116">Failed to load Group [\<servername\>:\<management database\>] data providers.</span></span>  
    >   
    >  <span data-ttu-id="62069-117">And</span><span class="sxs-lookup"><span data-stu-id="62069-117">And</span></span>  
    >   
    >  <span data-ttu-id="62069-118">INFORMACIÓN ADICIONAL:</span><span class="sxs-lookup"><span data-stu-id="62069-118">ADDITIONAL INFORMATION:</span></span>  
    >   
    >  <span data-ttu-id="62069-119">No se encuentra la instancia de la clase WMI.</span><span class="sxs-lookup"><span data-stu-id="62069-119">Instance of the WMI class is not found.</span></span> <span data-ttu-id="62069-120">(WinMgmt)</span><span class="sxs-lookup"><span data-stu-id="62069-120">(WinMgmt)</span></span>  
    >   
    >  <span data-ttu-id="62069-121">Este error puede producirse a causa de la falta de disponibilidad de las bases de datos de BizTalk mientras se efectúa la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="62069-121">This error can occur because the BizTalk databases are not available while they are being failed over.</span></span> <span data-ttu-id="62069-122">Para solucionar este problema, espere a que la instancia en clúster de servidores SQL Server se encuentre en línea antes de intentar conectarla a la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="62069-122">To workaround this issue, wait until after the clustered instance of SQL Server is online before attempting to connect to it with the BizTalk Server Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62069-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="62069-123">See Also</span></span>  
 <span data-ttu-id="62069-124">[Administración de grupos](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="62069-124">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="62069-125">Grupos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="62069-125">BizTalk Groups</span></span>](../core/biztalk-groups.md)