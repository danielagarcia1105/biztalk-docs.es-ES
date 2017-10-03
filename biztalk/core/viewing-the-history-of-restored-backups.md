---
title: Ver el historial de restaura las copias de seguridad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa5a7fbe2b0e731920880570b0555402ba162c7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-the-history-of-restored-backups"></a><span data-ttu-id="a00dd-102">Ver el historial de las copias de seguridad restauradas</span><span class="sxs-lookup"><span data-stu-id="a00dd-102">Viewing the History of Restored Backups</span></span>
<span data-ttu-id="a00dd-103">Para determinar el último conjunto de copias de seguridad restaurado correctamente, revise el contenido de la tabla Master.dbo.bts_LogShippingHistory.</span><span class="sxs-lookup"><span data-stu-id="a00dd-103">To determine the last successful backup set restored, review the contents of the Master.dbo.bts_LogShippingHistory table.</span></span> <span data-ttu-id="a00dd-104">El trabajo Obtener historial de copias de seguridad rellena esta tabla, mientras que el trabajo Restaurar bases de datos efectúa su actualización.</span><span class="sxs-lookup"><span data-stu-id="a00dd-104">This table is populated by the Get Backup History job and updated by the Restore Databases job.</span></span> <span data-ttu-id="a00dd-105">Cuando una copia de seguridad se restaura correctamente, la columna de restauración se establece como 1, y RestoredDateTime se define con la hora y fecha actuales.</span><span class="sxs-lookup"><span data-stu-id="a00dd-105">When a backup is successfully restored, the Restored column is set to 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="a00dd-106">Cuando todas las bases de datos que se están restaurando en el servidor a partir de un conjunto particular de copias de seguridad culminan correctamente el proceso de restauración, se escribe el Id. del conjunto de copias de seguridad en la tabla Master.dbo.bts_LogShippingLastRestoreSet.</span><span class="sxs-lookup"><span data-stu-id="a00dd-106">When all of the databases being restored to the server from a particular backup set have been successfully restored, that backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span>  
  
## <a name="gaps-in-the-restore-process"></a><span data-ttu-id="a00dd-107">Desapariciones en el proceso de restauración</span><span class="sxs-lookup"><span data-stu-id="a00dd-107">Gaps in the restore process</span></span>  
 <span data-ttu-id="a00dd-108">Al revisar los registros de la tabla Master.dbo.bts_LogShippingHistory, es posible que se haya producido alguna desaparición en los conjuntos restaurados.</span><span class="sxs-lookup"><span data-stu-id="a00dd-108">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may find gaps in the sets restored.</span></span> <span data-ttu-id="a00dd-109">Esto puede ocurrir por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="a00dd-109">This can occur for several reasons.</span></span> <span data-ttu-id="a00dd-110">No obstante, aunque hayan desaparecido elementos, aún podrá recuperar la estabilidad del sistema de destino (es decir, de los equipos de copia de seguridad).</span><span class="sxs-lookup"><span data-stu-id="a00dd-110">However, you can still recover the stability of your destination system (which are your backup computers), even when gaps have occurred.</span></span> <span data-ttu-id="a00dd-111">Para reparar el sistema de destino, es preciso restaurar un conjunto completo de copias de seguridad después de que se produzca la desaparición.</span><span class="sxs-lookup"><span data-stu-id="a00dd-111">A gap must be followed by a restore of a full backup set to repair the destination system.</span></span> <span data-ttu-id="a00dd-112">De lo contrario, el entorno de destino no será estable.</span><span class="sxs-lookup"><span data-stu-id="a00dd-112">If a gap is not followed by a full backup set restore, the destination environment is not stable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a00dd-113">Las copias de seguridad completas tan sólo se restauran para crear inicialmente la base de datos y para reparar problemas en la cadena de copias de seguridad del historial de registros.</span><span class="sxs-lookup"><span data-stu-id="a00dd-113">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="a00dd-114">En la mayoría de casos, no se restauran conjuntos completos de copias de seguridad, puesto que no forman parte de la cadena de copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="a00dd-114">In most cases full backup sets are not restored, as they are not part of the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00dd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a00dd-115">See Also</span></span>  
 [<span data-ttu-id="a00dd-116">Información avanzada sobre la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="a00dd-116">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)