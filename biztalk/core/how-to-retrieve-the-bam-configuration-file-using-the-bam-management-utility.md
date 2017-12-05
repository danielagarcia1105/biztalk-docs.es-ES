---
title: "Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef0f4802aa44a042f39adbdc9f169b11a16796d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="84cb7-102">Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="84cb7-102">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>
<span data-ttu-id="84cb7-103">Los administradores y programadores pueden utilizar la herramienta de administración de BAM para recuperar la configuración actual de la infraestructura de BAM.</span><span class="sxs-lookup"><span data-stu-id="84cb7-103">Administrators and developers can use the BAM Management utility to retrieve the current configuration of the BAM infrastructure.</span></span> <span data-ttu-id="84cb7-104">La configuración recuperada se puede utilizar para migrar una instalación de BAM a un servidor nuevo o se puede modificar y utilizar para actualizar una instalación de BAM existente.</span><span class="sxs-lookup"><span data-stu-id="84cb7-104">The retrieved configuration can be used to migrate a BAM installation to a new server or it can be modified and used to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84cb7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="84cb7-105">Prerequisites</span></span>  
 <span data-ttu-id="84cb7-106">A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:</span><span class="sxs-lookup"><span data-stu-id="84cb7-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="84cb7-107">Bases de datos de BAM configuradas</span><span class="sxs-lookup"><span data-stu-id="84cb7-107">Configured BAM databases</span></span>  
  
-   <span data-ttu-id="84cb7-108">Permisos para leer la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="84cb7-108">Permissions to read the BAM Primary Import database</span></span>  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a><span data-ttu-id="84cb7-109">Para recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="84cb7-109">To retrieve the BAM configuration file using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="84cb7-110">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="84cb7-110">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="84cb7-111">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="84cb7-111">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="84cb7-112">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm get-config - FileName:\<archivo de salida\>**, donde \< *archivo de salida* \> se sustituye por el nombre de su archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="84cb7-112">Type the following at the command line prompt: **bm get-config -FileName:\<output file\>**, where \<*output file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="84cb7-113">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="84cb7-113">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cb7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="84cb7-114">See Also</span></span>  
 [<span data-ttu-id="84cb7-115">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="84cb7-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)