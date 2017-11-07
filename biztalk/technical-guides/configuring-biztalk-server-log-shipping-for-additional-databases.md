---
title: Configurar BizTalk trasvase de registros para las bases de datos adicionales | Documentos de Microsoft
description: Agregar bases de datos personalizadas para el trabajo de copia de seguridad de BizTalk Server y el trasvase de registros en el servidor BizTalk Server
ms.custom: 
ms.date: 11/01/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f4eb0b690f81b16d739183633c6507b2ad87226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a><span data-ttu-id="7d05d-103">Configurar el servidor BizTalk Server trasvase de registros para las bases de datos adicionales</span><span class="sxs-lookup"><span data-stu-id="7d05d-103">Configuring BizTalk Server Log Shipping for Additional Databases</span></span>

## <a name="overview"></a><span data-ttu-id="7d05d-104">Información general</span><span class="sxs-lookup"><span data-stu-id="7d05d-104">Overview</span></span>
<span data-ttu-id="7d05d-105">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], trabajos que se agregará al trabajo de copia de seguridad de BizTalk Server se agregan automáticamente a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="7d05d-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], jobs added to the Backup BizTalk Server job are automatically added to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="7d05d-106">No es necesario realizar pasos adicionales para configurar el trasvase de registros para nuevas bases de datos agregará al trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7d05d-106">You do not have to take additional steps to configure log shipping for new databases added to the Backup BizTalk Server job.</span></span> <span data-ttu-id="7d05d-107">Sin embargo, no olvide agregar bases de datos personalizadas según corresponda en el \<OtherDatabases > sección del archivo SampleUpdateInfo.xml.</span><span class="sxs-lookup"><span data-stu-id="7d05d-107">However, be sure to add custom databases as appropriate under the \<OtherDatabases> section of the SampleUpdateInfo.xml file.</span></span> <span data-ttu-id="7d05d-108">[Configurar el sistema de destino para el trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md) y [volver de seguridad de la bases de datos personalizado](../core/how-to-back-up-custom-databases.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="7d05d-108">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) and [Back Up Custom Databases](../core/how-to-back-up-custom-databases.md) provides some guidance.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d05d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d05d-109">See Also</span></span>  
 [<span data-ttu-id="7d05d-110">Configuración del trasvase de registros de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7d05d-110">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)