---
title: Cómo configurar las bases de datos BAM mediante la utilidad de administración de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cee3564b90b730334d2d891edd2e9abc221a367
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971314"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="58c65-102">Cómo configurar las bases de datos de BAM con la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="58c65-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="58c65-103">Los administradores suelen usar la utilidad de configuración de BizTalk Server para configurar las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="58c65-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="58c65-104">Puede usar la utilidad de administración de BAM (bm.exe) como método alternativo de configuración de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="58c65-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58c65-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="58c65-105">Prerequisites</span></span>  
 <span data-ttu-id="58c65-106">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="58c65-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="58c65-107">Deberá tener permisos de administrador en el servidor SQL en que residen las bases de datos BAMPrimaryImport, BAMStarSchema y BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="58c65-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="58c65-108">Para configurar las bases de datos de servicios de notificación de SQL, deberá tener permiso de administrador y ser miembro del grupo de administradores local, así como ser miembro de otros grupos de administradores que se hayan configurado, como el grupo de administradores de BTS.</span><span class="sxs-lookup"><span data-stu-id="58c65-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="58c65-109">Deberá disponer de un archivo de configuración de BAM que contenga los datos XML con los que configurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="58c65-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="58c65-110">Para configurar las bases de datos de BAM con la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="58c65-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="58c65-111">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="58c65-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="58c65-112">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="58c65-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="58c65-113">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm el programa de instalación-databases - ConfigFile:\<archivo de configuración\>**, donde \< *archivo de configuración* \>se sustituye por el nombre de su archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="58c65-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="58c65-114">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="58c65-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c65-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="58c65-115">See Also</span></span>  
 [<span data-ttu-id="58c65-116">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="58c65-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)