---
title: Mensajes de control de versiones Support1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2175ba0a3aafd052e6830439800569cf5f005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a>Compatibilidad de versiones de mensaje
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite el control de versiones mediante la inclusión de un componente de la cadena de versión de las acciones de mensajes, los espacios de nombres e identificadores de nodo exhibe para las operaciones. La versión actual es http://Microsoft.LobServices.Sap/2007/03. Esto significa que para una solicitud de cambio con el nombre "RFC_SAMPLE", la operación de RFC obtenida por el adaptador tiene lo siguiente:  
  
-   Id. de nodo: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   Acción del mensaje: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc  
  
> [!NOTE]
>  Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)