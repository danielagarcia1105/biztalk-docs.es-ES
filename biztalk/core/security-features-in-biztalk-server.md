---
title: "Características de seguridad de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- Master Secret server, security
- security, Master Secret server
- security, runtime
- security, data
- deploying, security
- security, configuring
- runtime, security
- security, security features
- security, messages
- security, access control
- security, about security
- access control
- security, deploying
- data, security
- messages, security
ms.assetid: 5ab15023-fa71-439e-b3aa-420fe28806fa
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50371f0b0c5d5a56fc9f7c392e4ee8d69e637b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-features-in-biztalk-server"></a><span data-ttu-id="97e44-102">Características de seguridad en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="97e44-102">Security Features in BizTalk Server</span></span>
<span data-ttu-id="97e44-103">Microsoft® BizTalk® Server proporciona una puerta de enlace estándar para enviar y recibir documentos dentro de una intranet y a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="97e44-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="97e44-104">Los mensajes enviados y recibidos por BizTalk Server pueden ser de importancia crucial para la empresa, por lo que es importante contemplar medidas para proteger esos mensajes y la información que contienen tanto durante su tránsito como durante su proceso y almacenamiento por BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="97e44-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures to help secure these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="97e44-105">Esta sección proporciona información acerca de las características de seguridad de BizTalk Server y cómo utilizarlas para ayudar a proteger los datos y el entorno.</span><span class="sxs-lookup"><span data-stu-id="97e44-105">This section provides information about the BizTalk Server security features, and how you can use them to help secure your data and environment.</span></span>  
  
 <span data-ttu-id="97e44-106">BizTalk Server utiliza las siguientes medidas para proteger los mensajes entrantes y salientes, para proteger la información de configuración y de tiempo de ejecución, así como para integrarse de forma segura con otras aplicaciones y sistemas:</span><span class="sxs-lookup"><span data-stu-id="97e44-106">BizTalk Server uses the following measures to help secure inbound and outbound messages, to help secure the runtime and configuration information, and to help integrate securely with other applications and systems:</span></span>  
  
 <span data-ttu-id="97e44-107">**Seguridad de mensajes**</span><span class="sxs-lookup"><span data-stu-id="97e44-107">**Message security**</span></span>  
  
-   <span data-ttu-id="97e44-108">Autenticación del remitente de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="97e44-108">Authenticating the sender of a message.</span></span> <span data-ttu-id="97e44-109">BizTalk Server puede autenticar el remitente de un mensaje (ya sea mediante la información del certificado o la seguridad integrada de Windows) con el fin de validar la identidad del remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="97e44-109">BizTalk Server can authenticate the sender of a message (either by using the certificate information or Windows integrated Security) in order to validate the identity of the sender of the message.</span></span> <span data-ttu-id="97e44-110">Para obtener más información, consulte [autenticación de mensajes de entrada](../core/inbound-message-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="97e44-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
-   <span data-ttu-id="97e44-111">Autorización del receptor de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="97e44-111">Authorizing of the receiver of a message.</span></span> <span data-ttu-id="97e44-112">Una vez recibido el mensaje, BizTalk Server puede determinar qué procesos y usuarios tienen permisos para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="97e44-112">After BizTalk Server receives the message, BizTalk Server can determine what processes and users have permissions to receive the message.</span></span> <span data-ttu-id="97e44-113">Para obtener más información, consulte [autorización del receptor de un mensaje](../core/authorizing-the-receiver-of-a-message.md).</span><span class="sxs-lookup"><span data-stu-id="97e44-113">For more information, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
 <span data-ttu-id="97e44-114">**En tiempo de ejecución y la configuración de seguridad**</span><span class="sxs-lookup"><span data-stu-id="97e44-114">**Runtime and configuration security**</span></span>  
  
-   <span data-ttu-id="97e44-115">**Control de acceso y protección de datos.**</span><span class="sxs-lookup"><span data-stu-id="97e44-115">**Access control and securing data.**</span></span> <span data-ttu-id="97e44-116">BizTalk Server utiliza el control de acceso para garantizar que sus procesos tienen límites adecuados y que se controla el acceso a la información crítica de la empresa.</span><span class="sxs-lookup"><span data-stu-id="97e44-116">BizTalk Server uses access control to ensure that BizTalk Server processes have appropriate limits and that access to business critical information is controlled.</span></span> <span data-ttu-id="97e44-117">En otras palabras, BizTalk Server garantiza que los usuarios y las cuentas tengan los derechos de usuario mínimos necesarios para desempeñar sus tareas.</span><span class="sxs-lookup"><span data-stu-id="97e44-117">In other words, BizTalk Server ensures that users and accounts have the least user rights possible to enable them to do their tasks.</span></span> <span data-ttu-id="97e44-118">Para obtener más información, consulte [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md).</span><span class="sxs-lookup"><span data-stu-id="97e44-118">For more information, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
 <span data-ttu-id="97e44-119">**Seguridad integrada**</span><span class="sxs-lookup"><span data-stu-id="97e44-119">**Integrated security**</span></span>  
  
-   <span data-ttu-id="97e44-120">Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="97e44-120">Enterprise Single Sign-On.</span></span> <span data-ttu-id="97e44-121">BizTalk Server usa el Inicio de sesión único (SSO) empresarial para asegurarse de cifrar la información de configuración confidencial necesaria para los adaptadores y las ubicaciones de envío y recepción, garantizando así el almacenamiento y transmisión seguros de esa información por BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="97e44-121">BizTalk Server uses Enterprise Single Sign-On (SSO) to ensure that it encrypts the sensitive configuration information that the adapters, send, and receive locations require, thus helping to ensure that BizTalk Server stores and transmit this information in a secure manner.</span></span> <span data-ttu-id="97e44-122">Para obtener más información, consulte [mediante SSO](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="97e44-122">For more information, see [Using SSO](../core/using-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e44-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="97e44-123">See Also</span></span>  
 <span data-ttu-id="97e44-124">[Diseñar las arquitecturas de sistema de BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="97e44-124">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 <span data-ttu-id="97e44-125">[Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="97e44-125">[Implementing Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md) </span></span>  
 <span data-ttu-id="97e44-126">[Planear la seguridad de mensaje](../core/planning-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="97e44-126">[Planning Message Security](../core/planning-message-security.md) </span></span>  
 [<span data-ttu-id="97e44-127">Control de acceso y seguridad de los datos</span><span class="sxs-lookup"><span data-stu-id="97e44-127">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)   
