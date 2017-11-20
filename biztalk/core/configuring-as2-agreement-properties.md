---
title: Configurar propiedades del acuerdo AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6f09f85b726869e98712abf354ad3943ce97a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-as2-agreement-properties"></a><span data-ttu-id="a0d1e-102">Configuración de las propiedades de acuerdo AS2</span><span class="sxs-lookup"><span data-stu-id="a0d1e-102">Configuring AS2 Agreement Properties</span></span>
<span data-ttu-id="a0d1e-103">Esta sección describe las propiedades de acuerdo de transporte AS2.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-103">This section describes AS2 transport agreement properties.</span></span> <span data-ttu-id="a0d1e-104">Como parte de la configuración del protocolo de transporte, también puede definir si debe firmarse, cifrarse, etc. el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-104">As part of the transport protocol settings, you can also define whether the message should be signed, whether the message should be encrypted, etc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0d1e-105">La configuración de un acuerdo AS2 es opcional.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-105">Configuring an AS2 agreement is optional.</span></span> <span data-ttu-id="a0d1e-106">Un acuerdo AS2 define cómo se transfieren los mensajes mediante el protocolo AS2.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-106">An AS2 agreement defines how the messages are transferred using the AS2 protocol.</span></span> <span data-ttu-id="a0d1e-107">Si los socios comerciales deciden usar cualquier otro protocolo de transporte para transferir mensajes, pueden elegir no definir un acuerdo AS2.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-107">If the trading partners decide to use any other transport protocol to transfer messages, they can choose not to define an AS2 agreement.</span></span> <span data-ttu-id="a0d1e-108">Sin embargo, los socios comerciales deben definir un acuerdo de codificación que rija cómo se forman y codifican los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-108">However, the trading partners must define an encoding agreement that governs how the messages are formed and encoded.</span></span> <span data-ttu-id="a0d1e-109">Para obtener más información acerca de los acuerdos de codificación, vea [configurar propiedades del acuerdo de codificación](../core/configuring-encoding-agreement-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a0d1e-109">For more information about encoding agreements, see [Configuring Encoding Agreement Properties](../core/configuring-encoding-agreement-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a0d1e-110">Cada vez que modifique una configuración AS2 en un acuerdo, deberá reiniciar la instancia host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-110">Every time you change an AS2 setting in an agreement, you must restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance for the changes to take effect.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0d1e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a0d1e-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a0d1e-112">Configuración General (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-112">Configuring General Settings (AS2)</span></span>](../core/configuring-general-settings-as2.md)  
  
-   [<span data-ttu-id="a0d1e-113">Configuración de identificadores (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-113">Configuring Identifiers (AS2)</span></span>](../core/configuring-identifiers-as2.md)  
  
-   [<span data-ttu-id="a0d1e-114">Configuración de la validación (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-114">Configuring Validation (AS2)</span></span>](../core/configuring-validation-as2.md)  
  
-   [<span data-ttu-id="a0d1e-115">Configuración de confirmaciones (MDN) (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-115">Configuring Acknowledgements (MDNs) (AS2)</span></span>](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [<span data-ttu-id="a0d1e-116">Configuración del Host Local (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-116">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)  
  
-   [<span data-ttu-id="a0d1e-117">Configuración de certificados de firma (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-117">Configuring Signature Certificates (AS2)</span></span>](../core/configuring-signature-certificates-as2.md)  
  
-   [<span data-ttu-id="a0d1e-118">Configuración de la asociación de puerto de envío (AS2)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-118">Configuring Send Port Association (AS2)</span></span>](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0d1e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0d1e-119">See Also</span></span>  
 [<span data-ttu-id="a0d1e-120">Configurar propiedades de AS2</span><span class="sxs-lookup"><span data-stu-id="a0d1e-120">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)