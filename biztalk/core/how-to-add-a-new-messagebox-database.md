---
title: Cómo agregar una nueva base de datos de cuadro de mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db394722afcdf9e5972a925963b5200b4eba157e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974525"
---
# <a name="how-to-add-a-new-messagebox-database"></a><span data-ttu-id="2451e-102">Cómo agregar una nueva base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="2451e-102">How to Add a New MessageBox Database</span></span>
<span data-ttu-id="2451e-103">Utilice la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para agregar una nueva base de datos de cuadro de mensaje a la implementación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2451e-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to add a new MessageBox database to your BizTalk Server deployment.</span></span> <span data-ttu-id="2451e-104">Las bases de datos de cuadro de mensajes son la base para los elementos de equilibrio de carga de red entre servidores que realizan procesamiento cooperativo.</span><span class="sxs-lookup"><span data-stu-id="2451e-104">MessageBox databases are the basis for load-balancing work items across servers that do cooperative processing.</span></span> <span data-ttu-id="2451e-105">Para aumentar el número de mensajes que puede procesar el sistema, puede ser necesario agregar bases de datos de cuadro de mensajes adicionales.</span><span class="sxs-lookup"><span data-stu-id="2451e-105">To increase the number of messages that your system can process, you may need to add additional MessageBox databases.</span></span>  
  
 <span data-ttu-id="2451e-106">No se puede crear una base de datos de cuadro de mensajes nueva y dar de alta orquestaciones, puertos de envío o grupos de puertos de envío al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="2451e-106">You cannot create a new MessageBox database and have enlisted orchestrations, send ports, or send port groups at the same time.</span></span> <span data-ttu-id="2451e-107">Las orquestaciones, puertos de envío o grupos de puertos de envío dados de alta obtienen acceso a datos que BizTalk Server debe copiar en la nueva base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-107">Enlisted orchestrations, send ports, or send port groups access data that BizTalk Server must copy to the new MessageBox database.</span></span> <span data-ttu-id="2451e-108">Mientras se tiene acceso a estos datos, BizTalk Server no puede copiarlos en la nueva base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-108">While this data is being accessed, BizTalk Server cannot copy it into the new MessageBox database.</span></span>  
  
 <span data-ttu-id="2451e-109">Puede designar bases de datos locales y remotas como bases de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-109">You can designate both local and remote databases as MessageBox databases.</span></span> <span data-ttu-id="2451e-110">Para obtener información acerca de las bases de datos de BizTalk Server, vea [bases de datos de BizTalk Server](../core/databases-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="2451e-110">For information about BizTalk Server databases, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2451e-111">El Agente SQL Server debe estar ejecutándose en todos los servidores SQL a los que desee agregar una nueva base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-111">SQL Server Agent must be running on all of the SQL servers to which you want to add a new MessageBox database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2451e-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2451e-112">Prerequisites</span></span>  
 <span data-ttu-id="2451e-113">Los administradores de las bases de datos de cuadro de mensajes deben tener los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="2451e-113">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="2451e-114">Debe tener los siguientes derechos de usuario para administrar las bases de datos de cuadro de mensajes y deshabilitar la publicación de mensajes nuevos:</span><span class="sxs-lookup"><span data-stu-id="2451e-114">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="2451e-115">Debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2451e-115">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="2451e-116">Debe ser administrador de SQL Server en el equipo donde reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2451e-116">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-add-a-new-messagebox-database"></a><span data-ttu-id="2451e-117">Para agregar una base de datos de cuadro de mensaje nueva</span><span class="sxs-lookup"><span data-stu-id="2451e-117">To add a new MessageBox database</span></span>  
  
1. <span data-ttu-id="2451e-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2451e-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2451e-119">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk y, a continuación, haga clic en **configuración de plataforma**.</span><span class="sxs-lookup"><span data-stu-id="2451e-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then click **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="2451e-120">Haga clic en **cuadros de mensaje**, haga clic en **New**y, a continuación, haga clic en **cuadro de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="2451e-120">Right-click **Message Boxes**, click **New**, and then click **Message Box**.</span></span>  
  
4. <span data-ttu-id="2451e-121">En el **propiedades de cuadro de mensaje** cuadro de diálogo, haga lo siguiente y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="2451e-121">In the **Message Box Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="2451e-122">Use</span><span class="sxs-lookup"><span data-stu-id="2451e-122">Use this</span></span>|<span data-ttu-id="2451e-123">Para</span><span class="sxs-lookup"><span data-stu-id="2451e-123">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="2451e-124">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2451e-124">**SQL Server**</span></span>|<span data-ttu-id="2451e-125">Mostrar el nombre del servidor SQL que aloja la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-125">Displays the name of the SQL server that hosts the MessageBox database.</span></span>|  
   |<span data-ttu-id="2451e-126">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="2451e-126">**Database**</span></span>|<span data-ttu-id="2451e-127">Mostrar el nombre de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2451e-127">Displays the name of the MessageBox database.</span></span>|  
   |<span data-ttu-id="2451e-128">**Cuadro de mensaje de suscripción principal**</span><span class="sxs-lookup"><span data-stu-id="2451e-128">**Master subscription message box**</span></span>|<span data-ttu-id="2451e-129">Indicar si la base de datos de cuadros de mensajes seleccionada es la principal.</span><span class="sxs-lookup"><span data-stu-id="2451e-129">Indicates whether the selected MessageBox database is the master.</span></span> <span data-ttu-id="2451e-130">Si la base de datos de cuadro de mensajes es la principal, esta casilla está activada y no disponible.</span><span class="sxs-lookup"><span data-stu-id="2451e-130">If the current MessageBox database is the master, this check box is selected and unavailable.</span></span> <span data-ttu-id="2451e-131">La primera base de datos de cuadro de mensajes creada cuando se ejecuta el Asistente para Configuración es la principal de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2451e-131">The first MessageBox database created when you run the Configuration Wizard is the master by default.</span></span>|  
   |<span data-ttu-id="2451e-132">**Deshabilitar la publicación de mensajes nuevos**</span><span class="sxs-lookup"><span data-stu-id="2451e-132">**Disable new message publication**</span></span>|<span data-ttu-id="2451e-133">Activar esta casilla para especificar que no desea que esta base de datos de cuadro de mensajes reciba mensajes de activación.</span><span class="sxs-lookup"><span data-stu-id="2451e-133">Select this check box to specify that you do not want this MessageBox database to receive activation messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2451e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2451e-134">See Also</span></span>  
 <span data-ttu-id="2451e-135">[Administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2451e-135">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="2451e-136">[Cómo deshabilitar la publicación de mensajes nuevos](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="2451e-136">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 <span data-ttu-id="2451e-137">[Cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="2451e-137">[How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 <span data-ttu-id="2451e-138">[Copia de seguridad y restaurar bases de datos de BizTalk Server](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2451e-138">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="2451e-139">La base de datos de cuadro de mensajes</span><span class="sxs-lookup"><span data-stu-id="2451e-139">The MessageBox Database</span></span>](../core/the-messagebox-database.md)