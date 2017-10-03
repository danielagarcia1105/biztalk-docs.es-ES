---
title: "Trasvase de registros de supervisión de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eacec106823afc8203e7cce9679cb27cd29d0b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-biztalk-server-log-shipping"></a><span data-ttu-id="3684b-102">Trasvase de registros de supervisión de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3684b-102">Monitoring BizTalk Server Log Shipping</span></span>
<span data-ttu-id="3684b-103">Para determinar el último conjunto de copia de seguridad correcta de las bases de datos de BizTalk Server y los registros que se han restaurado, revise el contenido de la tabla Master.dbo.bts_LogShippingHistory en el destino [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] las instancias.</span><span class="sxs-lookup"><span data-stu-id="3684b-103">To determine the last successful backup set of BizTalk Server databases and logs that have been restored, review the contents of the Master.dbo.bts_LogShippingHistory table on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span> <span data-ttu-id="3684b-104">Esta tabla se rellena con el trabajo de BizTalk Server trasvase obtener copia de seguridad historial de registro y se actualiza mediante el trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="3684b-104">This table is populated by the BizTalk Server Log Shipping Get Backup History job and is updated by the restore job.</span></span> <span data-ttu-id="3684b-105">Cuando una copia de seguridad se restaura correctamente, la columna de restauración se establece en un valor de 1 y RestoredDateTime se establece en la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="3684b-105">When a backup is successfully restored, the Restored column is set to a value of 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="3684b-106">Cuando todas las bases de datos que se restaura en el servidor de un determinado conjunto enumerado en la tabla Master.dbo.bts_LogShippingHistory de copia de seguridad se han restaurado correctamente, el identificador de conjunto de copia de seguridad se escribe en la tabla Master.dbo.bts_LogShippingLastRestoreSet.</span><span class="sxs-lookup"><span data-stu-id="3684b-106">When all of the databases restored to the server from a particular backup set listed in the Master.dbo.bts_LogShippingHistory table have been successfully restored, the backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span> <span data-ttu-id="3684b-107">Esta tabla almacena los últimos conjuntos y es útil para determinar qué conjunto de copia de seguridad de registros se deben restaurar para poner en conexión el grupo de BizTalk de destino después de la aparición de un evento de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="3684b-107">This table stores the last set restored and is useful for determining what backup set of logs need to be restored to bring the destination BizTalk group online after the occurrence of a disaster recovery event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3684b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3684b-108">See Also</span></span>  
 [<span data-ttu-id="3684b-109">Trasvase de registros de configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3684b-109">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)