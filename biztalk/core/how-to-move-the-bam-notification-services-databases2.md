---
title: "Cómo mover la notificación de BAM servicios Databases2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Notification Services Instance database [BAM]
- migrating, Notification Services database [BAM]
ms.assetid: 4b7f3397-65c9-4c71-8374-8764f4c2e2e3
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 639a326878cd425a951581711c08a0a53127035b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="82c8c-102">Cómo mover las bases de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="82c8c-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="82c8c-103">Este procedimiento se puede utilizar para mover las bases de datos de servicios de notificación de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="82c8c-103">You can use this procedure to move the BAM Notification Services databases to another server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82c8c-104">Es preciso mover conjuntamente la base de datos de la aplicación de servicios de notificación de BAM (BAMAlertsApplication) y la base de datos de instancias de servicios de notificación de BAM (BAMAlertsNSMain).</span><span class="sxs-lookup"><span data-stu-id="82c8c-104">You must move the BAM Notification Services Application (BAMAlertsApplication) database and BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82c8c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82c8c-105">Prerequisites</span></span>  
 <span data-ttu-id="82c8c-106">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82c8c-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-notification-services-databases"></a><span data-ttu-id="82c8c-107">Para mover las bases de datos de servicios de notificación de BAM</span><span class="sxs-lookup"><span data-stu-id="82c8c-107">To move the BAM Notification Services databases</span></span>  
  
1.  <span data-ttu-id="82c8c-108">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="82c8c-108">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="82c8c-109">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="82c8c-110">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="82c8c-110">At the command prompt, navigate to the following directory:</span></span>  
  
         <span data-ttu-id="82c8c-111">**%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking** </span><span class="sxs-lookup"><span data-stu-id="82c8c-111">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
    3.  <span data-ttu-id="82c8c-112">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="82c8c-112">At the command prompt, type:</span></span>  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="82c8c-113">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="82c8c-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="82c8c-114">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="82c8c-114">At the command prompt, type:</span></span>  
  
    ```  
    Net stop NS$BamAlerts  
    ```  
  
3.  <span data-ttu-id="82c8c-115">Siga las instrucciones en libros en pantalla de SQL Server realizar la copia de seguridad de la base de datos en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="82c8c-115">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
4.  <span data-ttu-id="82c8c-116">Copie las bases de datos de servicios de notificación de BAM en el nuevo servidor SQL.</span><span class="sxs-lookup"><span data-stu-id="82c8c-116">Copy the BAM Notification Services databases to the new SQL server.</span></span>  
  
5.  <span data-ttu-id="82c8c-117">Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos en el servidor nuevo.</span><span class="sxs-lookup"><span data-stu-id="82c8c-117">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
6.  <span data-ttu-id="82c8c-118">Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección Alert DeploymentUnit al nombre del nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="82c8c-118">Edit the BAMConfiguration.xml file and change the ServerName in the Alert DeploymentUnit section to the new server name.</span></span>  
  
7.  <span data-ttu-id="82c8c-119">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="82c8c-119">Save and close the BAMConfiguration.xml file.</span></span>  
  
8.  <span data-ttu-id="82c8c-120">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="82c8c-121">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="82c8c-121">At the command prompt, navigate to the following directory:</span></span>  
  
     <span data-ttu-id="82c8c-122">**%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking** </span><span class="sxs-lookup"><span data-stu-id="82c8c-122">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
10. <span data-ttu-id="82c8c-123">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="82c8c-123">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="82c8c-124">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="82c8c-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
11. <span data-ttu-id="82c8c-125">Actualice las referencias a las bases de datos de servicios de notificación de BAM.</span><span class="sxs-lookup"><span data-stu-id="82c8c-125">Update references to the BAM Notification Services databases.</span></span> <span data-ttu-id="82c8c-126">Para obtener más información, consulte [cómo actualizar referencias a las bases de datos de servicios de notificación de BAM](../core/how-to-update-references-to-the-bam-notification-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="82c8c-126">For more information, see [How to Update References to the BAM Notification Services Databases](../core/how-to-update-references-to-the-bam-notification-services-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c8c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="82c8c-127">See Also</span></span>  
 [<span data-ttu-id="82c8c-128">Mover bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82c8c-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)