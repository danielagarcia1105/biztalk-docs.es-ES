---
title: 'Mensaje: 2 de control de versiones | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 5b7b9202-9f45-450e-918f-b26a03711aab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04514a9c55fa29a930b6ba7467177d6a754ff3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a><span data-ttu-id="cf1a0-102">Compatibilidad de versiones de mensaje</span><span class="sxs-lookup"><span data-stu-id="cf1a0-102">Message Versioning Support</span></span>
<span data-ttu-id="cf1a0-103">El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] admite el control de versiones mediante la inclusión de un componente de la cadena de versión de las acciones de mensajes, los espacios de nombres e identificadores de nodo exhibe para las operaciones.</span><span class="sxs-lookup"><span data-stu-id="cf1a0-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="cf1a0-104">La versión actual es http://Microsoft.LobServices.Siebel/2007/03.</span><span class="sxs-lookup"><span data-stu-id="cf1a0-104">The current version is http://Microsoft.LobServices.Siebel/2007/03.</span></span> <span data-ttu-id="cf1a0-105">Esto significa que para una operación de inserción en un objeto de negocio de la cuenta en el repositorio de Siebel, la operación de inserción obtenida por el adaptador tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1a0-105">This means that for an Insert operation on an Account business object in the Siebel repository, the Insert operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="cf1a0-106">Id. de nodo: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="cf1a0-106">Node ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="cf1a0-107">Acción del mensaje: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="cf1a0-107">Message action: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="cf1a0-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span><span class="sxs-lookup"><span data-stu-id="cf1a0-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf1a0-109">Esta característica no proporciona compatibilidad con versiones anteriores con las versiones anteriores del adaptador.</span><span class="sxs-lookup"><span data-stu-id="cf1a0-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1a0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf1a0-110">See Also</span></span>  
 [<span data-ttu-id="cf1a0-111">Mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="cf1a0-111">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)