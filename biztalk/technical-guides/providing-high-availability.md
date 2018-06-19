---
title: Proporcionar una alta disponibilidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4521981bc3df67553c244a55c91c1eb045c8e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302044"
---
# <a name="providing-high-availability"></a>Proporcionar una alta disponibilidad
Se proporciona alta disponibilidad para un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la implementación de redundancia para todos los componentes funcionales en el entorno. Redundancia de un Host de BizTalk puede realizarse mediante la instalación de varios equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un grupo de BizTalk y, a continuación, configurar instancias del host para que se ejecute en más de uno de los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el grupo. Redundancia de otros componentes de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno puede realizarse mediante la configuración de los componentes como recursos en un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]incorpora también configurando los Hosts de BizTalk como recursos en un [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] clúster, lo que se recomienda para proporcionar alta disponibilidad de ciertos adaptadores de BizTalk.  
  
 Esta sección describe cómo proporcionar alta disponibilidad para los componentes funcionales en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Planeación de alta disponibilidad2](../technical-guides/planning-for-high-availability2.md)  
  
-   [Alta disponibilidad para los Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)  
  
-   [Alta disponibilidad para el servidor secreto principal](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)