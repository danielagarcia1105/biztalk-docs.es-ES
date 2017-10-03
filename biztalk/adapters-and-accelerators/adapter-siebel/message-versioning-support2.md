---
title: 'Mensaje: 2 de control de versiones | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message versioning, support for
ms.assetid: 5b7b9202-9f45-450e-918f-b26a03711aab
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04514a9c55fa29a930b6ba7467177d6a754ff3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a>Compatibilidad de versiones de mensaje
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] admite el control de versiones mediante la inclusión de un componente de la cadena de versión de las acciones de mensajes, los espacios de nombres e identificadores de nodo exhibe para las operaciones. La versión actual es http://Microsoft.LobServices.Siebel/2007/03. Esto significa que para una operación de inserción en un objeto de negocio de la cuenta en el repositorio de Siebel, la operación de inserción obtenida por el adaptador tiene lo siguiente:  
  
-   Id. de nodo: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   Acción del mensaje: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation  
  
> [!NOTE]
>  Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)