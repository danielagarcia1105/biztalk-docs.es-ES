---
title: Configurar el servidor BizTalk Server trasvase de registros para las bases de datos adicionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
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
ms.openlocfilehash: 4b16b1d262b07ecaa62e87456f10bece225b3b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a><span data-ttu-id="bf06f-102">Configurar el servidor BizTalk Server trasvase de registros para las bases de datos adicionales</span><span class="sxs-lookup"><span data-stu-id="bf06f-102">Configuring BizTalk Server Log Shipping for Additional Databases</span></span>
<span data-ttu-id="bf06f-103">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], trabajos que se agregará al trabajo de copia de seguridad de BizTalk Server se agregan automáticamente a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="bf06f-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], jobs added to the Backup BizTalk Server job are automatically added to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="bf06f-104">No es necesario realizar pasos adicionales para configurar el trasvase de registros para nuevas bases de datos agregará al trabajo de copia de seguridad de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="bf06f-104">You do not have to take additional steps to configure log shipping for new databases added to the Backup BizTalk Server job.</span></span> <span data-ttu-id="bf06f-105">Sin embargo, no olvide agregar bases de datos personalizadas según corresponda en el \<OtherDatabases> sección del archivo SampleUpdateInfo.xml tal como se describe en el paso 22 de [cómo configurar el sistema de destino para el trasvase de registros](http://go.microsoft.com/fwlink/?LinkId=151402) (http://go.microsoft.com/fwlink/?LinkId=151402) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="bf06f-105">However, be sure to add custom databases as appropriate under the \<OtherDatabases> section of the SampleUpdateInfo.xml file as described in step 22 of [How to Configure the Destination System for Log Shipping](http://go.microsoft.com/fwlink/?LinkId=151402) (http://go.microsoft.com/fwlink/?LinkId=151402) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf06f-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf06f-106">See Also</span></span>  
 [<span data-ttu-id="bf06f-107">Trasvase de registros de configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bf06f-107">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)