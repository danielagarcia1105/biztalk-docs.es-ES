---
title: Adaptador de SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277604"
---
# <a name="smtp-adapter"></a><span data-ttu-id="d3db0-102">Adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="d3db0-102">SMTP Adapter</span></span>
<span data-ttu-id="d3db0-103">El protocolo de transferencia de correo (SMTP) se utiliza para intercambiar información entre un servidor que ejecuta Microsoft BizTalk Server y otras aplicaciones a través del protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-103">You use the Simple Mail Transfer Protocol (SMTP) adapter to exchange information between a server running Microsoft BizTalk Server and other applications by means of the SMTP protocol.</span></span> <span data-ttu-id="d3db0-104">BizTalk Server puede enviar mensajes a otras aplicaciones mediante la creación de un mensaje de correo electrónico y su entrega a una dirección de correo electrónico especificada.</span><span class="sxs-lookup"><span data-stu-id="d3db0-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="d3db0-105">De forma interna, el adaptador de envío SMTP crea un mensaje de correo electrónico basado en SMTP y lo envía a una dirección de correo electrónico de destino.</span><span class="sxs-lookup"><span data-stu-id="d3db0-105">Internally, the SMTP send adapter creates an SMTP-based e-mail message and sends it to a target e-mail address.</span></span> <span data-ttu-id="d3db0-106">La dirección de correo electrónico de destino es una propiedad del adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-106">The target e-mail address is a property of the SMTP adapter.</span></span> <span data-ttu-id="d3db0-107">El Explorador de BizTalk expone esta propiedad cuando configura el puerto de envío de SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-107">BizTalk Explorer exposes this property when you configure the SMTP send port.</span></span>  
  
 <span data-ttu-id="d3db0-108">El adaptador de SMTP admite caracteres comodín en el **TO**, **FROM**, **CC** y **asunto** propiedades y se resuelve en su real valores.</span><span class="sxs-lookup"><span data-stu-id="d3db0-108">The SMTP adapter supports wildcard characters in the **TO**, **FROM**, **CC** and **SUBJECT** properties, and resolves them to their actual values.</span></span> <span data-ttu-id="d3db0-109">Si los caracteres comodín en el **TO**, **FROM**, y **CC** propiedades no se pueden resolver, el protocolo de transporte SMTP registra un error y pone el mensaje en la cola de suspensión o redirige el mensaje al transporte de reserva.</span><span class="sxs-lookup"><span data-stu-id="d3db0-109">If wildcard characters in the **TO**, **FROM**, and **CC** properties cannot be resolved, the SMTP transport logs an error and puts the message into the suspended queue or redirects the message to the backup transport.</span></span> <span data-ttu-id="d3db0-110">Si los caracteres comodín no se puede resolver en el **asunto** propiedad, el mensaje se envía con el **asunto** propiedad especificada exactamente igual que en la propiedad (por ejemplo, "Message % MessageID %").</span><span class="sxs-lookup"><span data-stu-id="d3db0-110">If the wildcard characters cannot be resolved in the **SUBJECT** property, the message is sent with the **SUBJECT** property specified exactly as in the property (for example, "Message %MessageID%").</span></span>  
  
 <span data-ttu-id="d3db0-111">De forma predeterminada, el texto de mensaje de los mensajes SMTP es texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="d3db0-111">By default, the message text of SMTP messages is plain text.</span></span> <span data-ttu-id="d3db0-112">Para utilizar HTML en los cuerpos de los mensajes, puede configurar el adaptador para utilizar el contenido de un archivo HTML para el texto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d3db0-112">To use HTML in message bodies, you can configure the adapter to use the contents of an HTML file for the message text.</span></span>  
  
 <span data-ttu-id="d3db0-113">Para obtener más información acerca de los problemas de seguridad de SMTP, consulte [recomendaciones de seguridad del adaptador de SMTP](../core/smtp-adapter-security-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="d3db0-113">For more information about SMTP security issues, see [SMTP Adapter Security Recommendations](../core/smtp-adapter-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="d3db0-114">El adaptador de SMTP consta de un único adaptador, un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="d3db0-114">The SMTP adapter consists of only one adapter, a send adapter.</span></span> <span data-ttu-id="d3db0-115">El adaptador de envío controla los puertos de envío que utilizan el adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-115">The send adapter controls the send ports that use the SMTP adapter.</span></span>  
  
 <span data-ttu-id="d3db0-116">En este tema se describe el flujo de un mensaje a través del adaptador de envío SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-116">This topic discusses the flow of a message through the SMTP send adapter.</span></span>  
  
 <span data-ttu-id="d3db0-117">**Adaptador de envío SMTP**</span><span class="sxs-lookup"><span data-stu-id="d3db0-117">**SMTP Send Adapter**</span></span>  
  
 <span data-ttu-id="d3db0-118">El adaptador de envío SMTP obtiene los mensajes del servidor y los envía a un servidor SMTP que los envía a los destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d3db0-118">The SMTP send adapter gets messages from the server and posts them to an SMTP server that sends them to e-mail recipients.</span></span> <span data-ttu-id="d3db0-119">El adaptador de envío SMTP obtiene el contenido del mensaje de la parte del cuerpo del objeto de mensaje de BizTalk, del archivo especificado, o de un texto que se introdujo en un cuadro de diálogo que está disponible cuando se configura el adaptador.</span><span class="sxs-lookup"><span data-stu-id="d3db0-119">The SMTP send adapter gets the message content from the body part of the BizTalk Message object, from a specified file, or from a text entered into a dialog box that is available when configuring the adapter.</span></span>  
  
 <span data-ttu-id="d3db0-120">Después de que el adaptador de envío SMTP haya enviado el mensaje correctamente al servidor SMTP, el adaptador de envío SMTP elimina el mensaje de la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d3db0-120">After the SMTP send adapter successfully posts a message onto the SMTP server, the SMTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="d3db0-121">El adaptador de envío SMTP puede solicitar la notificación de entrega y la confirmación de lectura de los mensajes enviados a través del adaptador de envío SMTP.</span><span class="sxs-lookup"><span data-stu-id="d3db0-121">The SMTP send adapter can request delivery notification and read receipts for messages sent over the SMTP send adapter.</span></span> <span data-ttu-id="d3db0-122">El adaptador de SMTP entrega la notificación de notificación y lectura a la dirección especificada en el protocolo SMTP **de** encabezado.</span><span class="sxs-lookup"><span data-stu-id="d3db0-122">The SMTP adapter delivers the notification and read receipt to the address specified on the SMTP **From** header.</span></span>  
  
 <span data-ttu-id="d3db0-123">**Autenticación con el servidor SMTP**</span><span class="sxs-lookup"><span data-stu-id="d3db0-123">**Authentication with SMTP Server**</span></span>  
  
 <span data-ttu-id="d3db0-124">Si necesita autenticación de servidor SMTP, el adaptador de envío SMTP utiliza uno de los tipos de autenticación siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3db0-124">If you require SMTP server authentication, the SMTP send adapter uses one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="d3db0-125">**Básica.**</span><span class="sxs-lookup"><span data-stu-id="d3db0-125">**Basic.**</span></span> <span data-ttu-id="d3db0-126">El servidor SMTP utiliza credenciales proporcionadas por el usuario para autenticación.</span><span class="sxs-lookup"><span data-stu-id="d3db0-126">The SMTP server uses user-provided credentials for authentication.</span></span>  
  
-   <span data-ttu-id="d3db0-127">**Cuenta de proceso (NTLM).**</span><span class="sxs-lookup"><span data-stu-id="d3db0-127">**Process account (NTLM).**</span></span> <span data-ttu-id="d3db0-128">El servidor SMTP utiliza credenciales del proceso actual para autenticación.</span><span class="sxs-lookup"><span data-stu-id="d3db0-128">The SMTP server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3db0-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3db0-129">In This Section</span></span>  
  
-   [<span data-ttu-id="d3db0-130">Configurar el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="d3db0-130">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="d3db0-131">Restricciones al configurar el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="d3db0-131">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="d3db0-132">Recomendaciones de seguridad del adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="d3db0-132">SMTP Adapter Security Recommendations</span></span>](../core/smtp-adapter-security-recommendations.md)