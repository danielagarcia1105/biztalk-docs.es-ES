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
# <a name="message-versioning-support"></a><span data-ttu-id="4e46d-102">Compatibilidad de versiones de mensaje</span><span class="sxs-lookup"><span data-stu-id="4e46d-102">Message Versioning Support</span></span>
<span data-ttu-id="4e46d-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite el control de versiones mediante la inclusión de un componente de la cadena de versión de las acciones de mensajes, los espacios de nombres e identificadores de nodo exhibe para las operaciones.</span><span class="sxs-lookup"><span data-stu-id="4e46d-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="4e46d-104">La versión actual es http://Microsoft.LobServices.Sap/2007/03.</span><span class="sxs-lookup"><span data-stu-id="4e46d-104">The current version is http://Microsoft.LobServices.Sap/2007/03.</span></span> <span data-ttu-id="4e46d-105">Esto significa que para una solicitud de cambio con el nombre "RFC_SAMPLE", la operación de RFC obtenida por el adaptador tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e46d-105">This means that for an RFC named "RFC_SAMPLE", the RFC operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="4e46d-106">Id. de nodo: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="4e46d-106">Node ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="4e46d-107">Acción del mensaje: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="4e46d-107">Message action: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="4e46d-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span><span class="sxs-lookup"><span data-stu-id="4e46d-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e46d-109">Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.</span><span class="sxs-lookup"><span data-stu-id="4e46d-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e46d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e46d-110">See Also</span></span>  
 [<span data-ttu-id="4e46d-111">Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="4e46d-111">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)