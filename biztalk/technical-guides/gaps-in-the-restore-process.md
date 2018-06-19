---
title: Deficiencias en el proceso de restauración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298100"
---
# <a name="gaps-in-the-restore-process"></a><span data-ttu-id="0dad4-102">Deficiencias en el proceso de restauración</span><span class="sxs-lookup"><span data-stu-id="0dad4-102">Gaps in the Restore Process</span></span>
<span data-ttu-id="0dad4-103">Al revisar los registros en la tabla Master.dbo.bts_LogShippingHistory, quizá observe huecos en los conjuntos restaurados.</span><span class="sxs-lookup"><span data-stu-id="0dad4-103">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may observe gaps in restored sets.</span></span> <span data-ttu-id="0dad4-104">Esto puede ocurrir por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="0dad4-104">This can occur for several reasons.</span></span> <span data-ttu-id="0dad4-105">Sin embargo, se puede restaurar la estabilidad del sistema de destino aunque hayan desaparecido elementos.</span><span class="sxs-lookup"><span data-stu-id="0dad4-105">However, the stability of the destination system can be restored even when gaps have occurred.</span></span> <span data-ttu-id="0dad4-106">Un espacio debe ir seguido de una restauración de una copia de seguridad completa para reparar el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="0dad4-106">A gap must be followed by a restore of a full backup set to repair the destination environment.</span></span> <span data-ttu-id="0dad4-107">Si no está seguido de un espacio restauración de conjunto de copia de seguridad completa, el entorno de destino no es estable y no se puede restaurar en un estado coherente.</span><span class="sxs-lookup"><span data-stu-id="0dad4-107">If a gap is not followed by a full backup set restore, the destination environment is not stable and cannot be restored in a consistent state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dad4-108">Las copias de seguridad completas tan sólo se restauran para crear inicialmente la base de datos y para reparar problemas en la cadena de copias de seguridad del historial de registros.</span><span class="sxs-lookup"><span data-stu-id="0dad4-108">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="0dad4-109">Siempre que un problema no se produce con una restauración, no se restauran conjuntos de copia de seguridad completa, ya no participan en la cadena de copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="0dad4-109">As long as a problem does not occur with a restore, full backup sets are not restored, because they do not participate in the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dad4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dad4-110">See Also</span></span>  
 [<span data-ttu-id="0dad4-111">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="0dad4-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)