---
title: Uso de certificados para la resolución de entidades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4eb9b616-be1c-4b68-b3de-8721a344a423
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b157191e4004671a8b276f47d15a8589974dfbac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286916"
---
# <a name="using-certificates-for-party-resolution"></a><span data-ttu-id="fde3b-102">Usar certificados para la resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="fde3b-102">Using Certificates for Party Resolution</span></span>
<span data-ttu-id="fde3b-103">A *entidad* es una entidad externa a BizTalk Server que interactúa con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="fde3b-103">A *party* is an entity outside BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="fde3b-104">Cuando BizTalk Server recibe un mensaje, usa el certificado de clave pública para determinar quién envió el mensaje y para resolver el remitente en una entidad conocida en el entorno de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fde3b-104">When BizTalk Server receives a message, it uses the public key certificate to determine who sent the message, and to resolve the sender to a known party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="fde3b-105">Esta sección proporciona información sobre cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] canalizaciones, ubicaciones de recepción, puertos y el entorno de BizTalk Server para resolución de entidades.</span><span class="sxs-lookup"><span data-stu-id="fde3b-105">This section provides information about how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines, receive locations, ports, and the BizTalk Server environment for party resolution.</span></span>  
  
 <span data-ttu-id="fde3b-106">Para obtener más información acerca de la autenticación de un mensaje, vea [autenticación del remitente de un mensaje](../core/authenticating-the-sender-of-a-message.md).</span><span class="sxs-lookup"><span data-stu-id="fde3b-106">For more information about authentication of a message, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fde3b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fde3b-107">In This Section</span></span>  
 [<span data-ttu-id="fde3b-108">Cómo configurar BizTalk Server para la resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="fde3b-108">How to Configure BizTalk Server for Party Resolution</span></span>](../core/how-to-configure-biztalk-server-for-party-resolution.md)