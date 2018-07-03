---
title: Implementación de seguridad de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971977a0-b74e-4408-8a07-ad327658f2bc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae25a8e09b6e9aa8f4b5cef7b6dc5365a601e7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001189"
---
# <a name="implementing-message-security"></a><span data-ttu-id="a2261-102">Implementar seguridad en los mensajes</span><span class="sxs-lookup"><span data-stu-id="a2261-102">Implementing Message Security</span></span>
<span data-ttu-id="a2261-103">Puede configurar el entorno de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar certificados para el envío y recepción de mensajes firmados y cifrados.</span><span class="sxs-lookup"><span data-stu-id="a2261-103">You can configure your Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment to use certificates for sending and receiving signed and encrypted messages.</span></span> <span data-ttu-id="a2261-104">Mediante los certificados para el cifrado y la aplicación de firmas digitales, BizTalk Server puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2261-104">By using certificates for encryption and digital signatures, BizTalk Server can:</span></span>  
  
- <span data-ttu-id="a2261-105">Enviar y recibir datos de confianza.</span><span class="sxs-lookup"><span data-stu-id="a2261-105">Send and receive data that can be trusted.</span></span>  
  
- <span data-ttu-id="a2261-106">Asegurarse de que los datos que procesa son seguros.</span><span class="sxs-lookup"><span data-stu-id="a2261-106">Make sure that the data it processes is secure.</span></span>  
  
- <span data-ttu-id="a2261-107">Asegurarse de que las entidades autorizadas reciben sus mensajes.</span><span class="sxs-lookup"><span data-stu-id="a2261-107">Make sure that authorized parties receive its messages.</span></span>  
  
- <span data-ttu-id="a2261-108">Asegurarse de que recibe mensajes de las entidades autorizadas.</span><span class="sxs-lookup"><span data-stu-id="a2261-108">Make sure that it receives messages from authorized parties.</span></span>  
  
  <span data-ttu-id="a2261-109">En esta sección se proporciona información acerca de cómo configurar canalizaciones, ubicaciones de recepción, puertos y el entorno de BizTalk Server para implementar seguridad en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a2261-109">This section provides information about how to configure BizTalk Server pipelines, receive locations, ports, and the BizTalk Server environment to implement message security.</span></span>  
  
  <span data-ttu-id="a2261-110">Para obtener más información acerca de la seguridad de mensaje, consulte [planear la seguridad de mensaje](../core/planning-message-security.md).</span><span class="sxs-lookup"><span data-stu-id="a2261-110">For more information about message security, see [Planning Message Security](../core/planning-message-security.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2261-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a2261-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a2261-112">Envío y recepción de mensajes cifrados</span><span class="sxs-lookup"><span data-stu-id="a2261-112">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)  
  
-   [<span data-ttu-id="a2261-113">Envío y recepción de mensajes firmados</span><span class="sxs-lookup"><span data-stu-id="a2261-113">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)  
  
-   [<span data-ttu-id="a2261-114">Uso de certificados para la resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="a2261-114">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)