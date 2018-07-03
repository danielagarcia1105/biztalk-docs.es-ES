---
title: Cómo enumerar todos los que hace referencia a las bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a953933d72803b718353f7d0456317585b1458
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968477"
---
# <a name="how-to-list-all-referenced-databases"></a><span data-ttu-id="f68e1-102">Cómo enumerar todas las bases de datos a las que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="f68e1-102">How to List All Referenced Databases</span></span>
<span data-ttu-id="f68e1-103">Los administradores utilizan el **get-references** comando para enumerar todas las bases de datos de importación principal de BAM en otros servidores de BizTalk que se han recibido referencias a la base de datos local de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="f68e1-103">Administrators use the **get-references** command to list all of the BAM Primary Import databases on other BizTalk servers that have been given references to the local BAM Primary Import database.</span></span>  
  
### <a name="to-list-all-referenced-databases"></a><span data-ttu-id="f68e1-104">Para enumerar todas las bases de datos a las que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="f68e1-104">To list all referenced databases</span></span>  
  
1. <span data-ttu-id="f68e1-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f68e1-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="f68e1-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="f68e1-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="f68e1-107">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm.exe get-references**.</span><span class="sxs-lookup"><span data-stu-id="f68e1-107">Type the following at the command line prompt: **bm.exe get-references**.</span></span> <span data-ttu-id="f68e1-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f68e1-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68e1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f68e1-109">See Also</span></span>  
 [<span data-ttu-id="f68e1-110">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="f68e1-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)