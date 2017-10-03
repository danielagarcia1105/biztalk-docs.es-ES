---
title: "Cómo enumerar todas hace referencia a las bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69c6411378311892f85821a3e86d65a85f909d0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="72363-102">Cómo enumerar todas las bases de datos a las que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="72363-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="72363-103">Los administradores utilizan el **get-references** comando para enumerar todas las bases de datos de importación principal de BAM en otros servidores de BizTalk que han recibido referencias a la base de datos de importación principal de BAM local.</span><span class="sxs-lookup"><span data-stu-id="72363-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="72363-104">Para enumerar todas las bases de datos a las que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="72363-104">To list all referenced databases</span></span>  
  
1.  <span data-ttu-id="72363-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="72363-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="72363-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="72363-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="72363-107">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm.exe get-references**.</span><span class="sxs-lookup"><span data-stu-id="72363-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="72363-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="72363-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72363-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="72363-109">See Also</span></span>  
 [<span data-ttu-id="72363-110">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="72363-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)