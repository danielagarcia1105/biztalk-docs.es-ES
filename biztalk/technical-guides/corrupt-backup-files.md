---
title: "Archivos de copia de seguridad esté dañado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="d2b29-102">Archivos de copia de seguridad dañados</span><span class="sxs-lookup"><span data-stu-id="d2b29-102">Corrupt Backup Files</span></span>
<span data-ttu-id="d2b29-103">Un archivo de copia de seguridad quede dañado, está dañado o falta.</span><span class="sxs-lookup"><span data-stu-id="d2b29-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="d2b29-104">Si esto ocurre, no se puede restaurar al menos un archivo.</span><span class="sxs-lookup"><span data-stu-id="d2b29-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="d2b29-105">El trabajo de restauración en el sistema que ha sufrido el error, busca el siguiente conjunto de copia de seguridad completa válido.</span><span class="sxs-lookup"><span data-stu-id="d2b29-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="d2b29-106">En la mayoría de los casos será necesario forzar una copia de seguridad completa del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="d2b29-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="d2b29-107">Si no existe ningún conjunto de este tipo, se produce un error en el trabajo de restauración y cada ejecución subsiguientes también genera un error hasta que se reciba un conjunto de copia de seguridad completa válido.</span><span class="sxs-lookup"><span data-stu-id="d2b29-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="d2b29-108">Si existe un conjunto, se usa para reparar el entorno.</span><span class="sxs-lookup"><span data-stu-id="d2b29-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2b29-109">Debido a la forma en que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] escribe datos de copia de seguridad en un archivo, es posible que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] va a notificar la finalización correcta incluso si la copia de seguridad produce errores durante la escritura real de los datos.</span><span class="sxs-lookup"><span data-stu-id="d2b29-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="d2b29-110">Este escenario se produce principalmente cuando el disco que se escriben en no es local para el equipo y un error de red o se produce la interrupción.</span><span class="sxs-lookup"><span data-stu-id="d2b29-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="d2b29-111">Como medida de precaución general, si se produce un error de red mientras se ejecuta el trabajo de copia de seguridad, forzar una copia de seguridad completa después de que se resuelva el problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="d2b29-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b29-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2b29-112">See Also</span></span>  
 [<span data-ttu-id="d2b29-113">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="d2b29-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)