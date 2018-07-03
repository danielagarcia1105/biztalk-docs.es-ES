---
title: Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 952c163e809ceff8f084e661b542752d30f18096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019915"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="9070e-102">Cómo actualizar la configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="9070e-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="9070e-103">Los administradores pueden utilizar la utilidad de administración de BAM para actualizar una instalación de BAM existente.</span><span class="sxs-lookup"><span data-stu-id="9070e-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9070e-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9070e-104">Prerequisites</span></span>  
 <span data-ttu-id="9070e-105">Debe tener permisos de administrador en la base de datos de BAM que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="9070e-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="9070e-106">Para actualizar la configuración de BAM mediante la utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="9070e-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="9070e-107">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9070e-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="9070e-108">Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span><span class="sxs-lookup"><span data-stu-id="9070e-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="9070e-109">Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm update-config - FileName:\<archivo de configuración\>**, donde \< *archivo de configuración* \> es se sustituye por el nombre de su archivo de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="9070e-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="9070e-110">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9070e-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9070e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9070e-111">See Also</span></span>  
 [<span data-ttu-id="9070e-112">Utilidad de administración de BAM</span><span class="sxs-lookup"><span data-stu-id="9070e-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)