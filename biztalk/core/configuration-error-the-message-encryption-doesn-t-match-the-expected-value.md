---
title: "Error de configuración. El no cifrado de mensaje &#39; t coincide con el valor esperado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b17460c4dcd6f9d2a8c18e5e7284cd36940d6820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a><span data-ttu-id="88260-103">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="88260-103">Configuration error.</span></span> <span data-ttu-id="88260-104">El no cifrado de mensaje &#39; coincidencia t el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="88260-104">The message encryption doesn&#39;t match the expected value</span></span>
## <a name="details"></a><span data-ttu-id="88260-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="88260-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88260-106">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="88260-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="88260-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="88260-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="88260-108">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="88260-108">Event ID</span></span>|-|  
|<span data-ttu-id="88260-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="88260-109">Event Source</span></span>|<span data-ttu-id="88260-110">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88260-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="88260-111">Componente</span><span class="sxs-lookup"><span data-stu-id="88260-111">Component</span></span>|<span data-ttu-id="88260-112">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="88260-112">AS2 Engine</span></span>|  
|<span data-ttu-id="88260-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="88260-113">Symbolic Name</span></span>|<span data-ttu-id="88260-114">AS2DecoderPartyEncryptionConfigurationError</span><span class="sxs-lookup"><span data-stu-id="88260-114">AS2DecoderPartyEncryptionConfigurationError</span></span>|  
|<span data-ttu-id="88260-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="88260-115">Message Text</span></span>|<span data-ttu-id="88260-116">Error de configuración.</span><span class="sxs-lookup"><span data-stu-id="88260-116">Configuration error.</span></span> <span data-ttu-id="88260-117">El cifrado del mensaje no coincide con el valor esperado.</span><span class="sxs-lookup"><span data-stu-id="88260-117">The message encryption doesn't match the expected value.</span></span> <span data-ttu-id="88260-118">Póngase en contacto con el socio remitente y verifique el uso del cifrado.</span><span class="sxs-lookup"><span data-stu-id="88260-118">Contact the sending partner and verify encryption use.</span></span> <span data-ttu-id="88260-119">AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"</span><span class="sxs-lookup"><span data-stu-id="88260-119">AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="88260-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="88260-120">Explanation</span></span>  
 <span data-ttu-id="88260-121">Este evento de error,  indica que el componente de descodificador AS2 de la canalización de recepción no pudo procesar el mensaje AS2 porque el cifrado está especificado en la configuración de la entidad y el mensaje AS2 no está cifrado, o bien el cifrado está especificado para que no se habilite, pero el mensaje está cifrado.</span><span class="sxs-lookup"><span data-stu-id="88260-121">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not process the AS2 message because encryption is specified in the party settings, but the AS2 message is not encrypted, or encryption is specified not to be enabled, but the message is encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88260-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="88260-122">User Action</span></span>  
 <span data-ttu-id="88260-123">Para resolver este error, compruebe que el mensaje AS2 entrante está cifrado si el cifrado está especificado en la configuración de la entidad o bien que el mensaje AS2 entrante no está cifrado si el cifrado está especificado como no habilitada en la configuración de la entidad.</span><span class="sxs-lookup"><span data-stu-id="88260-123">To resolve this error, verify that the incoming AS2 message is encrypted if encryption is specified in the party settings or that the incoming AS2 message is not encrypted if encryption is specified as not enabled in the party settings.</span></span> <span data-ttu-id="88260-124">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="88260-124">Do one of the following:</span></span>  
  
1.  <span data-ttu-id="88260-125">Si el **invalidación está seleccionada la propiedad de propiedades de mensaje entrante** en la página entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en el [!INCLUDE[prague](../includes/prague-md.md)] consola de administración, el **debe cifrarse el mensaje**  propiedad está seleccionada, pero no se cifra el mensaje, póngase en contacto con la entidad que envió el mensaje y pídale que cifre el mensaje y lo vuelva a enviar.</span><span class="sxs-lookup"><span data-stu-id="88260-125">If the **Override inbound message properties property is selected** in the Party as AS2 Message Sender page of the AS2 Properties dialog box in the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, the **Message should be encrypted** property is selected, but the message is not encrypted, contact the party that sent the message and ask them to encrypt the message, and resend it.</span></span> <span data-ttu-id="88260-126">También puede desactivar la **debe cifrarse el mensaje** propiedad, o la **invalidar propiedades de mensajes entrantes** propiedad.</span><span class="sxs-lookup"><span data-stu-id="88260-126">Or you can clear the **Message should be encrypted** property, or the **Override inbound message properties** property.</span></span>  
  
2.  <span data-ttu-id="88260-127">Si el **invalidar propiedades de mensajes entrantes** propiedad está seleccionada, el **debe cifrarse el mensaje** propiedad está desactivada, pero el mensaje está cifrado, póngase en contacto con la entidad que envió el mensaje y pídale que No cifrar el mensaje y lo vuelva a enviar.</span><span class="sxs-lookup"><span data-stu-id="88260-127">If the **Override inbound message properties** property is selected, the **Message should be encrypted** property is cleared, but the message is encrypted, contact the party that sent the message and ask them not to encrypt the message, and resend it.</span></span> <span data-ttu-id="88260-128">O bien puede seleccionar la **debe cifrarse el mensaje** propiedad.</span><span class="sxs-lookup"><span data-stu-id="88260-128">Or you can select the **Message should be encrypted** property.</span></span>