---
title: "Cómo recuperar las alertas de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c18265712fa2f0dd1bb2d83d756cc9a9bd1505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-bam-alerts"></a><span data-ttu-id="a0c24-102">Cómo recuperar alertas SAE</span><span class="sxs-lookup"><span data-stu-id="a0c24-102">How to Recover BAM Alerts</span></span>
<span data-ttu-id="a0c24-103">Como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], si se usa Supervisión de la actividad económica (BAM), también será necesario recuperar las alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="a0c24-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], if you are using Business Activity Monitoring (BAM), you must also recover the BAM alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0c24-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a0c24-104">Prerequisites</span></span>  
 <span data-ttu-id="a0c24-105">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0c24-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a><span data-ttu-id="a0c24-106">Para recuperar las alertas de BAM (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="a0c24-106">To recover BAM alerts (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="a0c24-107">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.</span><span class="sxs-lookup"><span data-stu-id="a0c24-107">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="a0c24-108">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="a0c24-108">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a0c24-109">**NSControl register - name BamAlerts-server***\<ServerName >***-service - serviceusername "**  *\<ServiceUserName >* **"- servicepassword"**  *\<ServicePassword >* **"** </span><span class="sxs-lookup"><span data-stu-id="a0c24-109">**nscontrol register -name BamAlerts -server**  *\<ServerName>*  **-service -serviceusername "** *\<ServiceUserName>* **" -servicepassword "** *\<ServicePassword>* **"**</span></span>  
  
     <span data-ttu-id="a0c24-110">Esto habilita los servicios de notificación iniciar sesión en la base de datos correcta (esta información se mantiene en el registro del equipo del servicio NSControl).</span><span class="sxs-lookup"><span data-stu-id="a0c24-110">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service computer by nscontrol).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a0c24-111">Recuerde que debe usar el nuevo servidor de bases de datos de servicios de notificación en el **-server** opción al volver a registrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="a0c24-111">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="a0c24-112">Además, el nombre de usuario que utilice en los nuevos servicios de notificación debería ser el mismo que el que utilizaba en los anteriores.</span><span class="sxs-lookup"><span data-stu-id="a0c24-112">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
3.  <span data-ttu-id="a0c24-113">Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0c24-113">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a0c24-114">En el símbolo del sistema, escriba: **net start NS$ BamAlerts**.</span><span class="sxs-lookup"><span data-stu-id="a0c24-114">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c24-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0c24-115">See Also</span></span>  
 [<span data-ttu-id="a0c24-116">Recuperar un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a0c24-116">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)