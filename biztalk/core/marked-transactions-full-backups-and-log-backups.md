---
title: Transacciones marcadas, copias de seguridad completas y diferenciales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff71cbe7eb910c66530dee3264822eae121c0ce2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="marked-transactions-full-backups-and-log-backups"></a><span data-ttu-id="6c02e-102">Copias de seguridad de registros, copias de seguridad completas y transacciones marcadas</span><span class="sxs-lookup"><span data-stu-id="6c02e-102">Marked Transactions, Full Backups, and Log Backups</span></span>
<span data-ttu-id="6c02e-103">El trabajo de copia de seguridad de BizTalk Server crea copias de seguridad sincronizadas de todas las bases de datos de BizTalk Server mediante el uso de las copias de seguridad completa de la base de datos y copias de seguridad de registro de transacciones, junto con un tipo de transacción que se conoce como un *transacción marcada*.</span><span class="sxs-lookup"><span data-stu-id="6c02e-103">The Backup BizTalk Server Job creates synchronized backups of all BizTalk Server databases by using full database backups and transaction log backups, in conjunction with a type of transaction known as a *marked transaction*.</span></span> <span data-ttu-id="6c02e-104">Las transacciones marcadas son transacciones que colocan una marca en el registro de transacciones de todas las bases de datos que participan en la transacción.</span><span class="sxs-lookup"><span data-stu-id="6c02e-104">Marked transactions are transactions that place a mark into the transaction log of all databases participating in the transaction.</span></span> <span data-ttu-id="6c02e-105">La transacción marcada bloquea el inicio de nuevas transacciones distribuidas, espera a que se completen las transacciones distribuidas que están actualmente en ejecución y, seguidamente, efectúa la ejecución para colocar la marca.</span><span class="sxs-lookup"><span data-stu-id="6c02e-105">The marked transaction blocks new distributed transactions from starting, waits for the distributed transactions that are currently running to complete, and then executes to place the mark.</span></span>  
  
 <span data-ttu-id="6c02e-106">La marca representa un punto de transacción coherente en todas las bases de datos y que puede utilizarse con sucesivas copias de seguridad de registros para restaurar las bases de datos en ese punto.</span><span class="sxs-lookup"><span data-stu-id="6c02e-106">The mark represents a transaction point that is consistent across all databases; you can use the mark with subsequent log backups to restore your databases to that point.</span></span>  
  
 <span data-ttu-id="6c02e-107">Para cada una de las bases de datos de BizTalk Server, el trabajo de copia de seguridad de BizTalk Server crea una copia de seguridad de registros de transacciones marcada cada vez que se ejecuta; asimismo, crea una copia de seguridad completa en función de un periodo especificado.</span><span class="sxs-lookup"><span data-stu-id="6c02e-107">For each BizTalk Server database, the Backup BizTalk Server job creates a marked transaction log backup every time it runs, and it creates a full backup based on a time period that you specify.</span></span>  
  
## <a name="full-backups"></a><span data-ttu-id="6c02e-108">Copias de seguridad completas</span><span class="sxs-lookup"><span data-stu-id="6c02e-108">Full backups</span></span>  
 <span data-ttu-id="6c02e-109">Cuando se ejecuta el trabajo de copia de seguridad de BizTalk Server ejecuta el primer proceso de copia de seguridad, *BackupFull*, una vez cada periodo (y no cada vez que se ejecuta el trabajo).</span><span class="sxs-lookup"><span data-stu-id="6c02e-109">When you run the Backup BizTalk Server job it runs the first backup process, *BackupFull*, once every period (not every time the job runs).</span></span> <span data-ttu-id="6c02e-110">Para obtener más información sobre cómo programar el trabajo de copia de seguridad de BizTalk Server, vea [cómo programar el trabajo de copia de seguridad de BizTalk Server](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span><span class="sxs-lookup"><span data-stu-id="6c02e-110">For more information about how to schedule the Backup BizTalk Server job, see [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
 <span data-ttu-id="6c02e-111">La primera vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server durante un nuevo periodo, lleva a cabo una copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="6c02e-111">The first time the Backup BizTalk Server job runs during a new period, it performs a full backup.</span></span> <span data-ttu-id="6c02e-112">Por ejemplo, si programa el trabajo para que se ejecute una vez cada hora, pero configura el periodo como diario, el trabajo de copia de seguridad de BizTalk Server efectúa una copia de seguridad la primera vez que se ejecuta y, posteriormente, una vez al día (a medianoche).</span><span class="sxs-lookup"><span data-stu-id="6c02e-112">For example, if you schedule the job to run every hour but configure the period to be daily, the Backup BizTalk Server job performs a full backup the first time it runs, and then every day at midnight.</span></span>  
  
## <a name="transaction-log-backups"></a><span data-ttu-id="6c02e-113">Copias de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="6c02e-113">Transaction log backups</span></span>  
 <span data-ttu-id="6c02e-114">Es el segundo proceso que realiza el trabajo de copia de seguridad de BizTalk Server *MarkAndBackupLog*.</span><span class="sxs-lookup"><span data-stu-id="6c02e-114">The second process that the Backup BizTalk Server job performs is *MarkAndBackupLog*.</span></span> <span data-ttu-id="6c02e-115">Este proceso coloca una marca en todas las bases de datos de BizTalk Server y realiza una copia de seguridad de registros de transacciones cada vez que se ejecuta el trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c02e-115">This process places a mark in all BizTalk Server databases and performs a transaction log backup every time the job executes.</span></span>  
  
 <span data-ttu-id="6c02e-116">La marca es la cadena creada mediante el uso de  *\<ServerName\>*_*\<DatabaseName\>*_Log\_  *\<LogMarkName\>*\_*\<Timestamp\>*.bak, donde el  *\<nombre de la marca de registro\>*  está configurado en el trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6c02e-116">The mark is the string created by using *\<ServerName\>*_*\<DatabaseName\>*_Log\_*\<LogMarkName\>*\_*\<Timestamp\>*.bak, where the *\<Log Mark Name\>* is configured in the SQL Server Agent job.</span></span> <span data-ttu-id="6c02e-117">Esta marca se debe utilizar al restaurar el último registro en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c02e-117">This mark must be used when restoring the last log to each database.</span></span>  
  
 <span data-ttu-id="6c02e-118">Para obtener más información, vea las secciones que tratan de las copias de seguridad de registros de transacciones, y de la copia de seguridad de las bases de datos relacionadas y de su restauración, en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6c02e-118">For more information, see "Transaction Log Backups" and "Backup and Recovery of Related Databases" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c02e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c02e-119">See Also</span></span>  
 [<span data-ttu-id="6c02e-120">Información avanzada sobre copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="6c02e-120">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)