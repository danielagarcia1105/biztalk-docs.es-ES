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
ms.openlocfilehash: 3b1ceb760a5f842f8c24a372d793e0074114b81f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>Configurar el servidor BizTalk Server trasvase de registros para las bases de datos adicionales

## <a name="overview"></a>Información general
En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], trabajos que se agregará al trabajo de copia de seguridad de BizTalk Server se agregan automáticamente a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros. No es necesario realizar pasos adicionales para configurar el trasvase de registros para nuevas bases de datos agregará al trabajo de copia de seguridad de BizTalk Server. Sin embargo, no olvide agregar bases de datos personalizadas según corresponda en el \<OtherDatabases\> sección del archivo SampleUpdateInfo.xml. [Configurar el sistema de destino para el trasvase de registros](../core/how-to-configure-the-destination-system-for-log-shipping.md) y [volver de seguridad de la bases de datos personalizado](../core/how-to-back-up-custom-databases.md) proporciona alguna orientación.
  
## <a name="see-also"></a>Vea también  
 [Configuración del trasvase de registros de BizTalk Server](../technical-guides/configuring-biztalk-server-log-shipping.md)