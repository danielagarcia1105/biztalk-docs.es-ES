---
title: Cómo deshabilitar una referencia de base de datos de importación principal de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b89e9df78d91a6e4737b964223f81983e74dd29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998197"
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a><span data-ttu-id="a09a1-102">Cómo deshabilitar una referencia de base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="a09a1-102">How to Disable a BAM Primary Import Database Reference</span></span>
<span data-ttu-id="a09a1-103">Los administradores utilizan el **disable-reference** comando para deshabilitar una referencia a una base de datos de importación principal de BAM especificado.</span><span class="sxs-lookup"><span data-stu-id="a09a1-103">Administrators use the **disable-reference** command to disable a reference to a specified BAM Primary Import database.</span></span>  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a><span data-ttu-id="a09a1-104">Para deshabilitar una referencia de una base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="a09a1-104">To disable a reference to a BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="a09a1-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a09a1-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="a09a1-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="a09a1-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="a09a1-107">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm disable-reference - TargetServer:\<TargetServer\> - TargetDatabase:\<base de datos de destino\>[-Server:\<server\> ] [-Base de datos:\<base de datos\> ]**, donde **\<** <em>TargetServer</em> **\>** se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificada por \< *base de datos de destino* \> reside.</span><span class="sxs-lookup"><span data-stu-id="a09a1-107">Type the following at the command line prompt: **bm disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**, where **\<**<em>target server</em>**\>** is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<*target database*\> resides.</span></span> <span data-ttu-id="a09a1-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="a09a1-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09a1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a09a1-109">See Also</span></span>  
 [<span data-ttu-id="a09a1-110">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="a09a1-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)