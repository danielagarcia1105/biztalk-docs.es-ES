---
title: Limpiar el entorno de destino | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4023492bf79223b3ba6b1db5cedebadf88feb9c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299868"
---
# <a name="cleaning-the-destination-environment"></a><span data-ttu-id="c1923-102">Limpiar el entorno de destino</span><span class="sxs-lookup"><span data-stu-id="c1923-102">Cleaning the Destination Environment</span></span>
<span data-ttu-id="c1923-103">Si el trabajo de restauración encuentra con condiciones de error que no se puede resolver, limpie el entorno de destino para que pueda iniciar desde un entorno vacío.</span><span class="sxs-lookup"><span data-stu-id="c1923-103">If the restore job encounters error conditions that cannot be resolved, clean the destination environment so that it can start from an empty environment.</span></span> <span data-ttu-id="c1923-104">Ejecuta el procedimiento almacenado **sp_LogShippingClean** ubicado en la base de datos maestra en el destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia se "limpia" el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="c1923-104">Running the stored procedure **sp_LogShippingClean** located in the master database on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance will “clean” the destination environment.</span></span> <span data-ttu-id="c1923-105">Este procedimiento quita todas las bases de datos y elimina el último conjunto de datos restaurado para el origen especificado.</span><span class="sxs-lookup"><span data-stu-id="c1923-105">This procedure drops all databases and deletes the last restored data set for the specified source.</span></span>  
  
 <span data-ttu-id="c1923-106">Antes de ejecutar este procedimiento, deshabilite la **envío de registro BTS - Restaurar bases de datos** trabajo (el trabajo de copia de seguridad del historial de get puede continuar la ejecución).</span><span class="sxs-lookup"><span data-stu-id="c1923-106">Before running this procedure, disable the **BTS Log Shipping - Restore Databases** job (the get backup history job may continue running).</span></span> <span data-ttu-id="c1923-107">Para obtener más información acerca de cómo deshabilitar el **envío de registro BTS - Restaurar bases de datos** trabajo vea [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span><span class="sxs-lookup"><span data-stu-id="c1923-107">For more information about disabling the **BTS Log Shipping - Restore Databases** job see [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="c1923-108">Después de la **sp_LogShippingClean** se ejecuta el procedimiento, la próxima vez que se ejecuta el trabajo de restauración se encontrará la copia de seguridad completa más reciente con un conjunto de copia de seguridad de registros subsiguientes válido.</span><span class="sxs-lookup"><span data-stu-id="c1923-108">After the **sp_LogShippingClean** procedure is run, the next time the restore job runs it will find the most recent full backup set with a valid subsequent log backup set.</span></span> <span data-ttu-id="c1923-109">Si este conjunto ya se ha restaurado, el trabajo de restauración borra la **restaurados** columna para el conjunto y la posterior establece y, a continuación, continúa con la restauración del conjunto.</span><span class="sxs-lookup"><span data-stu-id="c1923-109">If this set has already been restored, the restore job clears the **Restored** column for the set and all subsequent sets and then proceeds with restoring the set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1923-110">Dado que el trabajo busca la copia de seguridad completa más reciente establecer después de que se ha limpiado el entorno, forzar una copia de seguridad completa en el sistema de origen después de ejecutar este procedimiento, pero antes de ejecutar el trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="c1923-110">Because the job looks for the most recent full backup set after the environment has been cleaned, force a full backup on the source system after running this procedure but before running the restore job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1923-111">El **sp_LogShippingClean** procedimiento debe repetirse en todos los servidores que se va a restaurar las bases de datos para un sistema de origen especificado con el fin de mantener sincronizados entre sí en términos que se han aplicado los conjuntos de los diferentes servidores.</span><span class="sxs-lookup"><span data-stu-id="c1923-111">The **sp_LogShippingClean** procedure must be repeated on all servers that are restoring databases for a given source system in order to keep the different servers in synch with each other in terms of which sets have been applied.</span></span>  
  
 <span data-ttu-id="c1923-112">Para ejecutar el **sp_LogShippingClean** procedimiento, conéctese a la base de datos maestra en todos los [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias que forman parte de la recuperación ante desastres de sitio y ejecute el siguiente comando en el **nueva consulta** opción disponible en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio para cada [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia:</span><span class="sxs-lookup"><span data-stu-id="c1923-112">To run the **sp_LogShippingClean** procedure, connect to the master database on all [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances that are part of the disaster recovery site and execute the following command in the **New Query** option available in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio for each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance:</span></span>  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 <span data-ttu-id="c1923-113">donde **SourceID** corresponde al valor del identificador configurado en la producción [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias.</span><span class="sxs-lookup"><span data-stu-id="c1923-113">where **SourceID** corresponds to the identifier configured on the production [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1923-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1923-114">See Also</span></span>  
 [<span data-ttu-id="c1923-115">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="c1923-115">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)