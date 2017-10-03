---
title: "Implementación de la seguridad de mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971977a0-b74e-4408-8a07-ad327658f2bc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84c0430b0a8edd0c241706047886f395515c853f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-message-security"></a><span data-ttu-id="5e565-102">Implementar seguridad en los mensajes</span><span class="sxs-lookup"><span data-stu-id="5e565-102">Implementing Message Security</span></span>
<span data-ttu-id="5e565-103">Puede configurar el entorno de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar certificados para el envío y recepción de mensajes firmados y cifrados.</span><span class="sxs-lookup"><span data-stu-id="5e565-103">You can configure your Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment to use certificates for sending and receiving signed and encrypted messages.</span></span> <span data-ttu-id="5e565-104">Mediante los certificados para el cifrado y la aplicación de firmas digitales, BizTalk Server puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e565-104">By using certificates for encryption and digital signatures, BizTalk Server can:</span></span>  
  
-   <span data-ttu-id="5e565-105">Enviar y recibir datos de confianza.</span><span class="sxs-lookup"><span data-stu-id="5e565-105">Send and receive data that can be trusted.</span></span>  
  
-   <span data-ttu-id="5e565-106">Asegurarse de que los datos que procesa son seguros.</span><span class="sxs-lookup"><span data-stu-id="5e565-106">Make sure that the data it processes is secure.</span></span>  
  
-   <span data-ttu-id="5e565-107">Asegurarse de que las entidades autorizadas reciben sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e565-107">Make sure that authorized parties receive its messages.</span></span>  
  
-   <span data-ttu-id="5e565-108">Asegurarse de que recibe mensajes de las entidades autorizadas.</span><span class="sxs-lookup"><span data-stu-id="5e565-108">Make sure that it receives messages from authorized parties.</span></span>  
  
 <span data-ttu-id="5e565-109">En esta sección se proporciona información acerca de cómo configurar canalizaciones, ubicaciones de recepción, puertos y el entorno de BizTalk Server para implementar seguridad en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e565-109">This section provides information about how to configure BizTalk Server pipelines, receive locations, ports, and the BizTalk Server environment to implement message security.</span></span>  
  
 <span data-ttu-id="5e565-110">Para obtener más información acerca de la seguridad de mensaje, consulte [planear la seguridad de mensaje](../core/planning-message-security.md).</span><span class="sxs-lookup"><span data-stu-id="5e565-110">For more information about message security, see [Planning Message Security](../core/planning-message-security.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e565-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5e565-111">In This Section</span></span>  
  
-   [<span data-ttu-id="5e565-112">Enviar y recibir mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="5e565-112">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)  
  
-   [<span data-ttu-id="5e565-113">Enviar y recibir mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="5e565-113">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)  
  
-   [<span data-ttu-id="5e565-114">Uso de certificados para la resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="5e565-114">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)