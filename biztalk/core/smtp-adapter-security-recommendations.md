---
title: Recomendaciones de seguridad del adaptador de SMTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], security
- SMTP adapters, security
- security, SMTP adapters
ms.assetid: 45f13744-a0eb-4b4e-85cd-6b862b384ad5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca1aeed0ad8c80cc32d333aeef37d1da6feabfc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-security-recommendations"></a><span data-ttu-id="f7f42-102">Recomendaciones de seguridad del adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="f7f42-102">SMTP Adapter Security Recommendations</span></span>
<span data-ttu-id="f7f42-103">El adaptador de SMTP se utiliza para intercambiar información entre un servidor que ejecuta Microsoft BizTalk Server y otras aplicaciones a través del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="f7f42-103">You use the SMTP adapter to exchange information between a server running BizTalk Server and other applications by means of the Simple Mail Transfer Protocol (SMTP) protocol.</span></span> <span data-ttu-id="f7f42-104">BizTalk Server puede enviar mensajes a otras aplicaciones mediante la creación de un mensaje de correo electrónico y su entrega a una dirección de correo electrónico especificada.</span><span class="sxs-lookup"><span data-stu-id="f7f42-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="f7f42-105">El adaptador de SMTP sólo puede utilizarse para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7f42-105">You can use the SMTP adapter only for sending messages.</span></span> <span data-ttu-id="f7f42-106">Para obtener más información acerca del adaptador de SMTP, consulte [adaptador de SMTP](../core/smtp-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f7f42-106">For more information about the SMTP adapter, see [SMTP Adapter](../core/smtp-adapter.md).</span></span>  
  
 <span data-ttu-id="f7f42-107">Cuando configure la cuenta de servicio para la instancia de host que ejecuta el adaptador de SMTP, deberá especificar el tipo de autenticación que desea utilizar con el servidor SMTP remoto.</span><span class="sxs-lookup"><span data-stu-id="f7f42-107">When you configure the service account for the host instance running the SMTP adapter, you need to specify the type of authentication you want to use with the remote SMTP server.</span></span> <span data-ttu-id="f7f42-108">Las opciones de autenticación son las siguientes: autenticación básica (texto sin cifrar), autenticación NTLM (utiliza las credenciales actuales) o ninguna autenticación (si la autenticación no es necesaria para el servidor SMTP).</span><span class="sxs-lookup"><span data-stu-id="f7f42-108">The authentication options are basic authentication (clear text), NTLM (by using current credentials), or none if authentication is not required by the SMTP server.</span></span>  
  
 <span data-ttu-id="f7f42-109">Cuando se envía un mensaje utilizando el adaptador de SMTP, BizTalk Server envía el mensaje en texto sin cifrar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f7f42-109">When you send a message by using the SMTP adapter, BizTalk Server sends the message in clear text by default.</span></span> <span data-ttu-id="f7f42-110">Si utiliza una canalización que tenga un componente de codificador S/MIME, podrá cifrar el mensaje antes de enviarlo al servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="f7f42-110">If you use a pipeline that has an S/MIME encoder component, you can encrypt the message before you send it to the SMTP server.</span></span> <span data-ttu-id="f7f42-111">Sin embargo, el encabezado SMTP permanecerá como texto sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="f7f42-111">However, the SMTP header is still in clear text.</span></span>  
  
 <span data-ttu-id="f7f42-112">Si desea auditar los mensajes de correo electrónico que envía BizTalk Server, deberá utilizar el adaptador de SMTP para establecer una conexión con su propio servidor SMTP, dónde podrá entonces auditar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7f42-112">If you want to audit the e-mail messages that BizTalk Server sends, you should use the SMTP adapter to connect to your own SMTP server, where you can then audit the messages.</span></span>  
  
 <span data-ttu-id="f7f42-113">El adaptador de SMTP no admite Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="f7f42-113">The SMTP adapter does not support Secure Sockets Layer (SSL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f42-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7f42-114">See Also</span></span>  
 <span data-ttu-id="f7f42-115">[Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md) </span><span class="sxs-lookup"><span data-stu-id="f7f42-115">[Ports for the Receive and Send Servers](../core/ports-for-the-receive-and-send-servers.md) </span></span>  
 [<span data-ttu-id="f7f42-116">Derechos de usuario mínimos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7f42-116">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)