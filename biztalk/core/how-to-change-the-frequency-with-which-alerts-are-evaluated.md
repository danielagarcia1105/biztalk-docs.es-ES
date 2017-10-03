---
title: "Cómo cambiar la frecuencia con las alertas que se evalúan | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a686c7de8057fdf843ff855da109e77e8ba7b8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a><span data-ttu-id="bfc28-102">Cómo cambiar la frecuencia con la que se evalúan las alertas</span><span class="sxs-lookup"><span data-stu-id="bfc28-102">How to Change the Frequency With Which Alerts Are Evaluated</span></span>
<span data-ttu-id="bfc28-103">Hay casos en los que el generador de SQL Server Notification Services no puede seguir los eventos generados por el proveedor de eventos de BAM cuando se implementa con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bfc28-103">There are cases in which the SQL Notifications services generator may not keep up with events being raised by the BAM event provider when deployed with the default settings.</span></span> <span data-ttu-id="bfc28-104">Se puede aumentar la frecuencia (la duración del cuanto) con la que se evalúan los eventos con respecto a las alertas mediante la modificación del archivo adf.xml de Notification Services.</span><span class="sxs-lookup"><span data-stu-id="bfc28-104">You can increase the frequency (the quantum duration) with which events are evaluated for alerts by modifying the Notification Services adf.xml file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bfc28-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bfc28-105">Prerequisites</span></span>  
 <span data-ttu-id="bfc28-106">Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro de un grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que disponga de permisos para leer y escribir en la base de datos de importación principal. Generalmente, será un grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfc28-106">To perform this procedure you must be logged on as a member of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that has permissions to read and write the Primary Import database, typically this will be a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a><span data-ttu-id="bfc28-107">Para modificar la duración del cuanto del generador de Notification Services</span><span class="sxs-lookup"><span data-stu-id="bfc28-107">To modify the Notification Services generator quantum duration</span></span>  
  
1.  <span data-ttu-id="bfc28-108">Abra el símbolo del sistema de Notification Services.</span><span class="sxs-lookup"><span data-stu-id="bfc28-108">Open the Notification Services Command prompt.</span></span> <span data-ttu-id="bfc28-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **herramientas de configuración**y, a continuación, haga clic en **Símbolo del sistema de notification Services**.</span><span class="sxs-lookup"><span data-stu-id="bfc28-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="bfc28-110">Obtenga el archivo de configuración de Notification Services.</span><span class="sxs-lookup"><span data-stu-id="bfc28-110">Get the Notification Services configuration file.</span></span> <span data-ttu-id="bfc28-111">En el símbolo del sistema, escriba: **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport servidor de base de datos > \< PimaryImport nombre de base de datos >**.</span><span class="sxs-lookup"><span data-stu-id="bfc28-111">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Get config.xml adf.xml \<PimaryImport database server> \< PimaryImport database name>**.</span></span>  
  
3.  <span data-ttu-id="bfc28-112">Modificar o agregar el \<QuantumDuration > elemento bajo el \<ApplicationExecutionSettings > nodo en el en el archivo adf.xml.</span><span class="sxs-lookup"><span data-stu-id="bfc28-112">Modify or add the \<QuantumDuration> element under the \<ApplicationExecutionSettings> node in the in the adf.xml file.</span></span> <span data-ttu-id="bfc28-113">Para obtener más información sobre elemento QuantumDuration, vea [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).</span><span class="sxs-lookup"><span data-stu-id="bfc28-113">For more information on the QuantumDuration element, see [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).</span></span>  
  
4.  <span data-ttu-id="bfc28-114">En el símbolo del sistema, escriba: **cscript ProcessBamNSFiles.vbs-actualizar config.xml adf.xml \<PimaryImport servidor de base de datos > \< PimaryImport nombre de base de datos >.**</span><span class="sxs-lookup"><span data-stu-id="bfc28-114">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Update  config.xml adf.xml  \<PimaryImport database server> \< PimaryImport database name>.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc28-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfc28-115">See Also</span></span>  
 [<span data-ttu-id="bfc28-116">Archivos de configuración de servicios de Script de línea de comandos de BAM para la notificación</span><span class="sxs-lookup"><span data-stu-id="bfc28-116">BAM Command-Line Script for Notification Services Configuration Files</span></span>](../core/bam-command-line-script-for-notification-services-configuration-files.md)