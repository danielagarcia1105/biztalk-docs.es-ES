---
title: Archivos de copia de seguridad dañados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5947b527dea1206255daf52f128569fd7a4f659c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987917"
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="37966-102">Archivos de copia de seguridad dañados</span><span class="sxs-lookup"><span data-stu-id="37966-102">Corrupt Backup Files</span></span>
<span data-ttu-id="37966-103">Una copia de seguridad puede quedar dañado, dañado o faltan.</span><span class="sxs-lookup"><span data-stu-id="37966-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="37966-104">Si esto ocurre, no puede restaurarse al menos un archivo.</span><span class="sxs-lookup"><span data-stu-id="37966-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="37966-105">Busca el siguiente conjunto de copia de seguridad completa válido en el trabajo de restauración en el sistema que ha había sufrido el error.</span><span class="sxs-lookup"><span data-stu-id="37966-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="37966-106">En la mayoría de los casos será necesario forzar una copia de seguridad completa del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="37966-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="37966-107">Si no existe tal conjunto, se produce un error en el trabajo de restauración y cada ejecución posterior también genera un error hasta que llegue un conjunto de copia de seguridad completa válido.</span><span class="sxs-lookup"><span data-stu-id="37966-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="37966-108">Si existe un conjunto, sirve para reparar el entorno.</span><span class="sxs-lookup"><span data-stu-id="37966-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37966-109">Debido a la manera en que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] escribe los datos de copia de seguridad en un archivo, es posible que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] informará correctamente incluso si la copia de seguridad dado error durante la escritura de los datos real.</span><span class="sxs-lookup"><span data-stu-id="37966-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="37966-110">Este escenario se produce principalmente cuando el disco que se escriben en no es local para el equipo y un error de red o se produce la interrupción.</span><span class="sxs-lookup"><span data-stu-id="37966-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="37966-111">Como medida de precaución general, si se produce un error de red mientras se ejecuta el trabajo de copia de seguridad, fuerce una copia de seguridad completa después de resolver el problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="37966-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37966-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="37966-112">See Also</span></span>  
 [<span data-ttu-id="37966-113">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="37966-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)