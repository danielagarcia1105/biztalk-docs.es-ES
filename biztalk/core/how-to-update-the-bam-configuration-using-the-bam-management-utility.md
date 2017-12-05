---
title: "Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b08209d3b3a1555bbc674e469ea9f8a4b1f81a9d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="398cb-102">Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="398cb-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="398cb-103">Los administradores pueden utilizar la utilidad de administración de BAM para actualizar una instalación de BAM existente.</span><span class="sxs-lookup"><span data-stu-id="398cb-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="398cb-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="398cb-104">Prerequisites</span></span>  
 <span data-ttu-id="398cb-105">Debe tener permisos de administrador en la base de datos de BAM que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="398cb-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="398cb-106">Para actualizar la configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="398cb-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="398cb-107">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="398cb-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="398cb-108">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="398cb-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="398cb-109">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm update-config - FileName:\<el archivo de configuración\>**, donde \< *archivo de configuración* \> es se sustituye por el nombre de su archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="398cb-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="398cb-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="398cb-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398cb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="398cb-111">See Also</span></span>  
 [<span data-ttu-id="398cb-112">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="398cb-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)