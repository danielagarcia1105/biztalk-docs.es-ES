---
title: Cómo desactivar el seguimiento Global | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e6ea49766bbb433c7fd142ee3c66ae1ee331292
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020580"
---
# <a name="how-to-turn-off-global-tracking"></a><span data-ttu-id="9cff0-102">Cómo desactivar el seguimiento global</span><span class="sxs-lookup"><span data-stu-id="9cff0-102">How to Turn Off Global Tracking</span></span>
<span data-ttu-id="9cff0-103">De forma predeterminada, el seguimiento global se habilita cuando se instala BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9cff0-103">By default, global tracking is enabled when you install BizTalk Server.</span></span> <span data-ttu-id="9cff0-104">La base de datos de seguimiento de BizTalk (BizTalkDTADb) aumenta de tamaño a medida que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa los datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9cff0-104">The BizTalk Tracking (BizTalkDTADb) database grows in size as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes data on your system.</span></span> <span data-ttu-id="9cff0-105">Si el rendimiento del disco es deficiente a causa del tamaño de la base de datos de seguimiento de BizTalk, puede purgar los datos de la misma.</span><span class="sxs-lookup"><span data-stu-id="9cff0-105">If the size of the BizTalk Tracking database causes poor disk performance, you can purge the data from the Tracking database.</span></span> <span data-ttu-id="9cff0-106">Si están surgiendo problemas de rendimiento que se solucionan de manera momentánea mediante la purga de la base de datos de seguimiento de BizTalk, y desea configurar BizTalk para que no recopile más información de seguimiento, considere la posibilidad de desactivar el seguimiento global.</span><span class="sxs-lookup"><span data-stu-id="9cff0-106">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span>  
  
 <span data-ttu-id="9cff0-107">Es importante tener en cuenta que, al desactivar el seguimiento global, se deshabilitan los interceptores de seguimiento de todo el grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cff0-107">It is important to understand that turning off global tracking disables the tracking interceptors for the entire [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="9cff0-108">Es decir, BizTalk no realizará un seguimiento de los eventos en las tablas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9cff0-108">This means that BizTalk will not track events in its tracking tables.</span></span> <span data-ttu-id="9cff0-109">Como alternativa, puede desactivar el seguimiento de los eventos individuales.</span><span class="sxs-lookup"><span data-stu-id="9cff0-109">Alternatively, you can turn off tracking for individual events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cff0-110">Si utiliza Supervisión de la actividad económica (BAM), debe mantener un host de seguimiento dedicado, incluso si deshabilita el seguimiento global,</span><span class="sxs-lookup"><span data-stu-id="9cff0-110">If you are using Business Activity Monitoring (BAM), you should maintain a dedicated tracking host, even if you disable global tracking.</span></span> <span data-ttu-id="9cff0-111">ya que los eventos de BAM usan el Servicio de descodificación de datos de seguimiento (TDDS).</span><span class="sxs-lookup"><span data-stu-id="9cff0-111">This is because BAM events use the Tracking Data Decode Service (TDDS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9cff0-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9cff0-112">Prerequisites</span></span>  
 <span data-ttu-id="9cff0-113">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9cff0-113">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a><span data-ttu-id="9cff0-114">Para desactivar el seguimiento global (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="9cff0-114">To turn off global tracking (SQL Server 2008)</span></span>  
  
1. <span data-ttu-id="9cff0-115">En el servidor SQL server que hospeda la base de datos de seguimiento de BizTalk (BizTalkDTADb), haga clic en **iniciar**, haga clic en **programas**, haga clic en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en  **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-115">On the SQL server that hosts the BizTalk Tracking (BizTalkDTADb) database, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="9cff0-116">En el **conectar al servidor** cuadro de diálogo, compruebe el nombre del servidor y la autenticación y, a continuación, haga clic en **Connect**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-116">In the **Connect to Server** dialog box, verify the server name and authentication, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="9cff0-117">En Microsoft SQL Server Management Studio, en **Explorador de objetos**, expanda \< *nombre_equipo*\>, expanda **bases de datos**, expanda  **BizTalkMgmtDb**, expanda **tablas**, haga clic en **adm_Group**y, a continuación, haga clic en **Abrir tabla**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-117">In Microsoft SQL Server Management Studio, in **Object Explorer**, expand \<*computer name*\>, expand **Databases**, expand **BizTalkMgmtDb**, expand **Tables**, right-click **adm_Group**, and then click **Open Table**.</span></span>  
  
4. <span data-ttu-id="9cff0-118">En el Visor de tablas, desplácese horizontalmente hasta que encuentre **GlobalTrackingOption**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-118">In the table viewer, scroll horizontally until you find **GlobalTrackingOption**.</span></span>  
  
5. <span data-ttu-id="9cff0-119">En el **GlobalTrackingOption** columna, cambie el valor de 1 a 0 para desactivar esta característica y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9cff0-119">In the **GlobalTrackingOption** column, change the value from 1 to 0, to turn off this feature, and then press ENTER.</span></span>  
  
6. <span data-ttu-id="9cff0-120">Cierre Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9cff0-120">Close Microsoft SQL Server Management Studio.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9cff0-121">Deberá reiniciar los hosts de BizTalk para que el cambio surta efecto.</span><span class="sxs-lookup"><span data-stu-id="9cff0-121">You must restart your BizTalk hosts for the change to take effect.</span></span>  
  
7. <span data-ttu-id="9cff0-122">Haga clic en **iniciar**, haga clic en **programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-122">Click **Start**, click **Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8. <span data-ttu-id="9cff0-123">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Las instancias de host**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-123">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
9. <span data-ttu-id="9cff0-124">En el panel de detalles, haga clic en cada host y, a continuación, haga clic en **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="9cff0-124">In the details pane, right-click each host, and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cff0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cff0-125">See Also</span></span>  
 <span data-ttu-id="9cff0-126">[Archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="9cff0-126">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="9cff0-127">[Cómo purgar datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="9cff0-127">[How to Purge Data from the BizTalk Tracking Database](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span></span>  
 [<span data-ttu-id="9cff0-128">Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9cff0-128">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)