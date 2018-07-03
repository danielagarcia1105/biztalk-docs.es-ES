---
title: Cómo restaurar las aplicaciones y habilitar el procesamiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aae2a6d9b4f3a35c55ffa731323547b1b54a4d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999413"
---
# <a name="how-to-restore-applications-and-enable-processing"></a><span data-ttu-id="89363-102">Cómo restaurar las aplicaciones y habilitar el procesamiento</span><span class="sxs-lookup"><span data-stu-id="89363-102">How to Restore Applications and Enable Processing</span></span>
<span data-ttu-id="89363-103">Configurar las aplicaciones en el grupo de BizTalk y habilita el procesamiento de la aplicación después de seguir los pasos descritos en el tema [cómo actualizar los equipos en tiempo de ejecución](../technical-guides/how-to-update-the-runtime-computers.md).</span><span class="sxs-lookup"><span data-stu-id="89363-103">Configure the applications in the BizTalk group and enable application processing after following the steps described in the topic [How to Update the Runtime Computers](../technical-guides/how-to-update-the-runtime-computers.md).</span></span>  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a><span data-ttu-id="89363-104">Para habilitar la configuración de la aplicación y restaurar el procesamiento de la aplicación</span><span class="sxs-lookup"><span data-stu-id="89363-104">To enable application configuration and restore application processing</span></span>  
  
1. <span data-ttu-id="89363-105">Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de instalación de aplicación en cada servidor BizTalk server en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89363-105">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Installation MSI file on each BizTalk server in the group.</span></span>  
  
2. <span data-ttu-id="89363-106">Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de la configuración de aplicación en un servidor en el grupo para configurar la aplicación para el sitio de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="89363-106">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file on one server in the group to configure the application for the disaster recovery site.</span></span> <span data-ttu-id="89363-107">Los nombres de las ubicaciones de recepción y envío puertos siguen siendo los mismos.</span><span class="sxs-lookup"><span data-stu-id="89363-107">The names for receive locations and send ports remain the same.</span></span> <span data-ttu-id="89363-108">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo MSI de la configuración de aplicación actualiza los enlaces de manera que hacen referencia estos artefactos a las ubicaciones correctas en el entorno de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="89363-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file updates bindings so that these artifacts point to the correct locations in the disaster recovery environment.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="89363-109">Si las ubicaciones de recepción y envío de los puertos no se ven afectados por la pérdida del sitio de producción, es posible que no sea necesario volver a configurar la aplicación con las ubicaciones de específicos de la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="89363-109">If receive locations and send ports are not affected by the loss of the production site, it may not be necessary to reconfigure the application with disaster recovery-specific locations.</span></span>  
  
3. <span data-ttu-id="89363-110">Procesamiento de la aplicación de restauración habilitando la aplicación de todas las ubicaciones de recepción, puertos de envío y las instancias de host.</span><span class="sxs-lookup"><span data-stu-id="89363-110">Restore application processing by enabling all application receive locations, send ports, and host instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89363-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="89363-111">See Also</span></span>  
 [<span data-ttu-id="89363-112">Recuperación de los equipos en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="89363-112">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)