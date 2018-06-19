---
title: Distributed problemas del sistema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297756"
---
# <a name="distributed-system-problems"></a><span data-ttu-id="cc63e-102">Problemas de sistemas distribuidos</span><span class="sxs-lookup"><span data-stu-id="cc63e-102">Distributed System Problems</span></span>
<span data-ttu-id="cc63e-103">En un sistema de destino distribuida, los trabajos de restauración no son conscientes de los errores o problemas en los demás equipos.</span><span class="sxs-lookup"><span data-stu-id="cc63e-103">In a distributed destination system the restore jobs are not aware of errors or problems on the other computers.</span></span> <span data-ttu-id="cc63e-104">Por ejemplo, suponga que el equipo A restaurar la base de datos de administración de BizTalk y la base de datos de seguimiento de BizTalk y el equipo B está restaurando la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="cc63e-104">For example, suppose that computer A is restoring the BizTalk Management database and the BizTalk Tracking database, and computer B is restoring the BizTalk MessageBox database.</span></span> <span data-ttu-id="cc63e-105">Ambos equipos restauración correctamente los conjuntos de copia de seguridad 1 y 25.</span><span class="sxs-lookup"><span data-stu-id="cc63e-105">Both computers successfully restore backup sets 1 through 25.</span></span> <span data-ttu-id="cc63e-106">Conjunto de 26, sin embargo, tiene un archivo de copia de seguridad de registro dañado de la base de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="cc63e-106">Set 26, however, has a corrupted log backup file of the BizTalk MessageBox database.</span></span> <span data-ttu-id="cc63e-107">El equipo A sus bases de datos restaura correctamente pero se produce un error en el equipo B restaurar el archivo dañado.</span><span class="sxs-lookup"><span data-stu-id="cc63e-107">Computer A restores its databases correctly but computer B fails to restore the corrupted file.</span></span>  
  
 <span data-ttu-id="cc63e-108">En este caso, forzar una copia de seguridad completa en el sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="cc63e-108">In this situation, force a full backup on the source system.</span></span> <span data-ttu-id="cc63e-109">Siguiendo con el ejemplo anterior, se supone que se ha diagnosticado el problema y se creó una copia de seguridad completa para el conjunto de 35.</span><span class="sxs-lookup"><span data-stu-id="cc63e-109">Continuing the example above, assume that the problem was diagnosed and a full backup was created for set 35.</span></span> <span data-ttu-id="cc63e-110">El equipo A, a continuación, restauraciones conjuntos 26 a 34, porque no es consciente del problema en el equipo B. equipo B se producirá un error hasta que ve 35 de conjunto de copia de seguridad completa y copia de seguridad de registros subsiguientes conjunto 36 (Recuerde que debe siempre ser una copia de seguridad de registros completa subsiguientes para un conjunto sea restauración d).</span><span class="sxs-lookup"><span data-stu-id="cc63e-110">Computer A then restores sets 26 to 34, because it is not aware of the problem on Computer B. Computer B will fail until it sees full backup set 35 and subsequent log backup set 36 (remember that there must always be one subsequent complete log backup for a set to be restored).</span></span> <span data-ttu-id="cc63e-111">Cuando llegan los conjuntos de 35 y 36 en el equipo B, reparará utilizando 35.</span><span class="sxs-lookup"><span data-stu-id="cc63e-111">When sets 35 and 36 arrive on computer B, it will repair itself using 35.</span></span> <span data-ttu-id="cc63e-112">Una vez completada la reparación, equipo A y B se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="cc63e-112">After the repair is complete, computer A and B will be in sync.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc63e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc63e-113">See Also</span></span>  
 [<span data-ttu-id="cc63e-114">Solución de problemas de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="cc63e-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)