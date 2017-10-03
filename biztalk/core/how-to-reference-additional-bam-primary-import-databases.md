---
title: "Cómo hacer referencia a las bases de datos de importación principal de BAM adicionales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be973777fda6fad83b4ed6c672b68969cdde5919
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a><span data-ttu-id="e129a-102">Cómo agregar referencias a bases de datos de importación principal de BAM adicionales</span><span class="sxs-lookup"><span data-stu-id="e129a-102">How to Reference Additional BAM Primary Import Databases</span></span>
<span data-ttu-id="e129a-103">Los administradores utilizan el **enable-reference** comando para hacer referencia a otras bases de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="e129a-103">Administrators use the **enable-reference** command to reference additional BAM Primary Import databases.</span></span> <span data-ttu-id="e129a-104">La finalidad de agregar referencias a bases de datos de importación principales de BAM consiste en facilitar las actividades de BAM distribuidas.</span><span class="sxs-lookup"><span data-stu-id="e129a-104">You reference multiple BAM Primary Import databases to facilitate viewing distributed BAM activities.</span></span>  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a><span data-ttu-id="e129a-105">Para habilitar una referencia a una base de datos de importación principal de BAM adicional</span><span class="sxs-lookup"><span data-stu-id="e129a-105">To enable a reference to an additional BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="e129a-106">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e129a-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e129a-107">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="e129a-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="e129a-108">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm enable-reference - TargetServer:\<servidor de destino > - TargetDatabase:\<base de datos de destino >**, donde \< *destino servidor*> se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificado por \<base de datos de destino > reside.</span><span class="sxs-lookup"><span data-stu-id="e129a-108">Type the following at the command line prompt: **bm enable-reference -TargetServer:\<target server> -TargetDatabase:\<target database>**, where \<*target server*> is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<target database> resides.</span></span> <span data-ttu-id="e129a-109">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e129a-109">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e129a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e129a-110">See Also</span></span>  
 [<span data-ttu-id="e129a-111">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="e129a-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)