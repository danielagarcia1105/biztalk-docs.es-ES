---
title: "Cómo habilitar servicios de notificación en más equipos en un grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9787c5ac1371f6743285a151e5666d12b592a300
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a><span data-ttu-id="bc878-102">Cómo habilitar servicios de notificación en equipos adicionales en un grupo</span><span class="sxs-lookup"><span data-stu-id="bc878-102">How to Enable Notifications Services on Additional Computers In A Group</span></span>
<span data-ttu-id="bc878-103">Al ejecutar BAM en un entorno de varios equipos, debe habilitar Notification Services en cada equipo en el que va a ejecutar la utilidad de administración de BAM para implementar una actividad.</span><span class="sxs-lookup"><span data-stu-id="bc878-103">When running BAM in a multi-computer environment, you must enable Notification Services on each computer on which you will run the BAM Management Utility to deploy an activity.</span></span>  
  
 <span data-ttu-id="bc878-104">Considere el caso siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc878-104">Consider the following scenario:</span></span>  
  
-   <span data-ttu-id="bc878-105">Grupo A consta de los siguientes equipos:</span><span class="sxs-lookup"><span data-stu-id="bc878-105">Group A consists of the following computers:</span></span>  
  
    -   <span data-ttu-id="bc878-106">El equipo 1 se utiliza como equipo de administración de BAM.</span><span class="sxs-lookup"><span data-stu-id="bc878-106">Computer 1 is used as a BAM administration computer.</span></span>  
  
    -   <span data-ttu-id="bc878-107">El equipo 2 aloja las tablas de importación principal (PIT) y la base de datos de esquema de estrella de BAM.</span><span class="sxs-lookup"><span data-stu-id="bc878-107">Computer 2 hosts the BAM PIT and Star Schema database.</span></span>  
  
    -   <span data-ttu-id="bc878-108">El equipo 3 aloja las bases de datos de archivo y análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="bc878-108">Computer 3 hosts the BAM Archive and Analysis databases.</span></span>  
  
    -   <span data-ttu-id="bc878-109">El equipo 4 aloja la base de datos de alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="bc878-109">Computer 4 hosts the BAM Alerts database.</span></span>  
  
    -   <span data-ttu-id="bc878-110">El equipo 5 aloja el resto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bc878-110">Computer 5 hosts the rest of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
-   <span data-ttu-id="bc878-111">Grupo B:</span><span class="sxs-lookup"><span data-stu-id="bc878-111">Group B:</span></span>  
  
    -   <span data-ttu-id="bc878-112">El equipo 6 se utiliza como equipo de administración de BAM en el que todas las bases de datos se comparten con el grupo A.</span><span class="sxs-lookup"><span data-stu-id="bc878-112">Computer 6 is used as a BAM administration computer on which all the databases are shared with Group A.</span></span>  
  
 <span data-ttu-id="bc878-113">Para poder implementar una actividad en las bases de datos en un grupo desde el equipo en el grupo B, primero debe registrar los servicios de notificación con el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hospeda los servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="bc878-113">To be able to deploy an activity to the databases in group A from the computer in group B, you must first register the Notification Services with the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hosting the notifications services.</span></span> <span data-ttu-id="bc878-114">Si no se registra, aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="bc878-114">If the Notification Services are not registered, you will receive the following error:</span></span>  
  
 <span data-ttu-id="bc878-115">Deploying Alert… (Implementando alerta...) ERROR: Error en la implementación de BAM.</span><span class="sxs-lookup"><span data-stu-id="bc878-115">Deploying Alert... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="bc878-116">Las alertas no se implementaron.</span><span class="sxs-lookup"><span data-stu-id="bc878-116">The alerts were not deployed.</span></span>  
  
 <span data-ttu-id="bc878-117">Se produjo una excepción en el destino de la invocación.</span><span class="sxs-lookup"><span data-stu-id="bc878-117">Exception has been thrown by the target of an invocation.</span></span>  
  
 <span data-ttu-id="bc878-118">No se encontraron las entradas de Registro de la instancia especificada de Notification Services.</span><span class="sxs-lookup"><span data-stu-id="bc878-118">The registry entries for the specified instance of Notification Services could not be found.</span></span>  
  
### <a name="to-register-notifications-services-additional-computers"></a><span data-ttu-id="bc878-119">Procedimiento para registrar equipos adicionales de servicios de notificaciones</span><span class="sxs-lookup"><span data-stu-id="bc878-119">To register notifications services additional computers</span></span>  
  
1.  <span data-ttu-id="bc878-120">En el equipo del grupo adicional, haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **deherramientasdeconfiguración**y, a continuación, haga clic en **comandos de Notification Services**.</span><span class="sxs-lookup"><span data-stu-id="bc878-120">On the computer in the additional group, click **Start**, point to **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="bc878-121">En el símbolo del sistema, escriba: **nscontrol register - nombre \<NS prefijo nombre elegido en config\> -server \<sql server de ns db\>**.</span><span class="sxs-lookup"><span data-stu-id="bc878-121">At the command prompt, type: **nscontrol register -name \<NS Prefix name chosen at config\> -server \<ns db sql server\>**.</span></span> <span data-ttu-id="bc878-122">Esto permite que los servicios de notificación inicien sesión en la base de datos correcta (nscontrol mantiene esta información en el Registro del equipo de servicio).</span><span class="sxs-lookup"><span data-stu-id="bc878-122">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc878-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc878-123">See Also</span></span>  
 <span data-ttu-id="bc878-124">[Cambiar la configuración de tiempo de ejecución BAM](../core/changing-bam-runtime-settings.md) </span><span class="sxs-lookup"><span data-stu-id="bc878-124">[Changing BAM Runtime Settings](../core/changing-bam-runtime-settings.md) </span></span>  
 [<span data-ttu-id="bc878-125">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="bc878-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)