---
title: "Cómo deshabilitar una referencia de base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6efa79822f6a5406db29c69b5ba0892a63bcc5f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a><span data-ttu-id="5ba23-102">Cómo deshabilitar una referencia de base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="5ba23-102">How to Disable a BAM Primary Import Database Reference</span></span>
<span data-ttu-id="5ba23-103">Los administradores utilizan el **disable-reference** comando para deshabilitar una referencia a una base de datos de importación principal de BAM especificado.</span><span class="sxs-lookup"><span data-stu-id="5ba23-103">Administrators use the **disable-reference** command to disable a reference to a specified BAM Primary Import database.</span></span>  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a><span data-ttu-id="5ba23-104">Para deshabilitar una referencia de una base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="5ba23-104">To disable a reference to a BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="5ba23-105">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ba23-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="5ba23-106">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="5ba23-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="5ba23-107">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm disable-reference - TargetServer:\<servidor de destino > - TargetDatabase:\<base de datos de destino > [-Server:\<servidor >] [-base de datos:\< base de datos >]**, donde  **\<**  *TargetServer*  **>**  se sustituye por el nombre de SQL server en el que la base de datos de importación principal de BAM de destino especificado por \< *base de datos de destino*> reside.</span><span class="sxs-lookup"><span data-stu-id="5ba23-107">Type the following at the command line prompt: **bm disable-reference -TargetServer:\<target server> -TargetDatabase:\<target database>[ -Server:\<server> ][ -Database:\<database> ]**, where **\<***target server***>** is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<*target database*> resides.</span></span> <span data-ttu-id="5ba23-108">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="5ba23-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba23-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ba23-109">See Also</span></span>  
 [<span data-ttu-id="5ba23-110">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="5ba23-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)