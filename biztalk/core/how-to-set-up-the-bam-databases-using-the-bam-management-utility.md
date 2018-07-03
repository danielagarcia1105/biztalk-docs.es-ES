---
title: Cómo configurar las bases de datos BAM mediante la utilidad de administración de BAM | Microsoft Docs
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
ms.openlocfilehash: 6878e6aa3874384bd17f340c62421c432182f637
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001317"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="0c02b-102">Cómo configurar las bases de datos de BAM con la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="0c02b-102">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>
<span data-ttu-id="0c02b-103">Los administradores suelen usar la utilidad de configuración de BizTalk Server para configurar las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="0c02b-103">Administrators typically use the BizTalk Server configuration utility to set up the BAM databases.</span></span> <span data-ttu-id="0c02b-104">Puede usar la utilidad de administración de BAM (bm.exe) como método alternativo de configuración de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="0c02b-104">You can use the BAM Management utility (bm.exe) as an alternate method to set up the databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c02b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c02b-105">Prerequisites</span></span>  
 <span data-ttu-id="0c02b-106">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="0c02b-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="0c02b-107">Deberá tener permisos de administrador en el servidor SQL en que residen las bases de datos BAMPrimaryImport, BAMStarSchema y BAMArchive.</span><span class="sxs-lookup"><span data-stu-id="0c02b-107">You must have administrator permissions on the SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span>  
  
-   <span data-ttu-id="0c02b-108">Para configurar las bases de datos de servicios de notificación de SQL, deberá tener permiso de administrador y ser miembro del grupo de administradores local, así como ser miembro de otros grupos de administradores que se hayan configurado, como el grupo de administradores de BTS.</span><span class="sxs-lookup"><span data-stu-id="0c02b-108">To set up the SQL Notification Services databases, you must have administrator permission and be a member of the local administrators group, as well as be a member of any additional administrator groups that have been configured, such as the BTS Admins group.</span></span>  
  
-   <span data-ttu-id="0c02b-109">Deberá disponer de un archivo de configuración de BAM que contenga los datos XML con los que configurar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="0c02b-109">You must have a BAM configuration file containing XML data from which to set up the databases.</span></span>  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a><span data-ttu-id="0c02b-110">Para configurar las bases de datos de BAM con la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="0c02b-110">To set up the BAM databases using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="0c02b-111">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c02b-111">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="0c02b-112">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="0c02b-112">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="0c02b-113">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm setup-databases - ConfigFile:\<archivo de configuración\>**, donde \< *archivo de configuración* \>se sustituye por el nombre de su archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="0c02b-113">Type the following at the command line prompt: **bm setup-databases -ConfigFile:\<configuration file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="0c02b-114">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="0c02b-114">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c02b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c02b-115">See Also</span></span>  
 [<span data-ttu-id="0c02b-116">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="0c02b-116">BAM Management Utility</span></span>](../core/bam-management-utility.md)