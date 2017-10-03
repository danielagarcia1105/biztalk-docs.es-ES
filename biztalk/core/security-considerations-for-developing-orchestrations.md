---
title: Consideraciones de seguridad para el desarrollo de orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-developing-orchestrations"></a>Consideraciones de seguridad para el desarrollo de orquestaciones
Cuando diseñe orquestaciones, debe tener en cuenta una serie de problemas de seguridad potenciales.  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a>Evite el uso de suscripciones basadas en contenido de mensajes que no sean de confianza  
 Para garantizar que un mensaje con pocos privilegios no inicie una instancia de orquestación que potencialmente pueda crear suscripciones basadas en el contenido o el contexto del mensaje, se recomienda que las orquestaciones no creen las suscripciones de mensajes según el contenido o el contexto de un mensaje que no sea de confianza.  
  
 Para obtener información acerca de la seguridad en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [proteger BizTalk Server](../core/securing-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear orquestaciones](../core/creating-orchestrations.md)   
 [Acerca de las orquestaciones](../core/about-orchestrations.md)