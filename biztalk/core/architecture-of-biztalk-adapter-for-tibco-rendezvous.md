---
title: Arquitectura del adaptador de TIBCO Rendezvous | Microsoft Docs
description: Obtenga información sobre el adaptador de BizTalk para TIBCO Rendezvous works, incluido el traspaso de mensajes, en BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 174d6ceb-8e1d-4c93-827d-8155cfe47836
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28845891181b3f71b31cf4d4dc3f8a20040bb205
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011997"
---
# <a name="architecture-of-the-tibco-rendezvous-adapter"></a>Arquitectura del adaptador de TIBCO Rendezvous

## <a name="overview"></a>Información general
El Adaptador de Microsoft BizTalk para TIBCO Rendezvous proporciona conectividad bidireccional entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y TIBCO Rendezvous. Este adaptador utiliza tanto la API TIBCO Rendezvous como la API del marco de trabajo de adaptadores BizTalk para proporcionar una elevada integración.  
  
 TIBCO Rendezvous es un producto de software que proporciona un bus de mensaje para la integración de aplicaciones empresariales(EAI). TIBCO proporciona API de mensajería en C, C++, Java, Visual Basic y Microsoft .NET Framework para recibir canales de datos en hojas de cálculo de Microsoft Office Excel y otras aplicaciones de su elección.  
  
## <a name="message-passing"></a>Pasar mensajes  
 El concepto básico de pasar mensajes es bastante sencillo:  
  
- Un mensaje tiene un único asunto formado por elementos separados por puntos. Se envía a un único daemon de Rendezvous (aunque podría transmitirse a otros daemons).  
  
- Un escucha anuncia sus asuntos de interés a un daemon (con una función de comodín básica), y los mensajes con asuntos coincidentes se le entregan si los dos daemons están "conectados" entre sí o son el mismo daemon. Para obtener más información, consulte mensajes en [mensajes en el adaptador de BizTalk para TIBCO Rendezvous](../core/messages-in-biztalk-adapter-for-tibco-rendezvous.md).  
  
  En la siguiente ilustración se muestra la arquitectura para el Adaptador de BizTalk para TIBCO Rendezvous.  
  
  ![](../core/media/tibcorend-arch.gif "TibcoRend_Arch")  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)  