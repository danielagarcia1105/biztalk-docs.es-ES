---
title: "Estándares de seguridad y privacidad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e652ff10c4ebfaf00069f3a7197dfd739eb680e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="87883-102">Estándares de seguridad y privacidad</span><span class="sxs-lookup"><span data-stu-id="87883-102">Security and privacy standards</span></span>
<span data-ttu-id="87883-103">Las aplicaciones de servicios financieras y soluciones de integración desarrollan con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] generalmente se protegen mediante nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87883-103">Financial Services applications and integration solutions developed using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="87883-104">utiliza los mecanismos de seguridad rigurosa como Internet de hecho cifra estándares de mensajes y protocolos de transporte, firmar los certificados, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] y autenticación de Enterprise Single Sign-On para proteger [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones, datos, y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="87883-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  
  
 <span data-ttu-id="87883-105">Soluciones creadas con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], y A4SWIFT puede ayudar a cumplir las directrices de seguridad y privacidad para la sociedad para transacciones financieras de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="87883-105">Solutions built with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  
  
 <span data-ttu-id="87883-106">Además de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad, A4SWIFT proporciona seguridad de nivel de usuario específico para proteger la entrada de mensaje para el usuario final, reparación, aprobación y envío de mensajes SWIFT.</span><span class="sxs-lookup"><span data-stu-id="87883-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="87883-107">Esta seguridad se consigue mediante [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] tecnologías de firma digital y utilizando los servicios de tiempo de ejecución de A4SWIFT para comprobar la integridad de datos y de certificado.</span><span class="sxs-lookup"><span data-stu-id="87883-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  
  
 <span data-ttu-id="87883-108">Es importante tener en cuenta las medidas para proteger los mensajes de SWIFT y la información que contienen cuando se crean o se editado por los usuarios finales, en tránsito y mientras [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesa y almacena.</span><span class="sxs-lookup"><span data-stu-id="87883-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  
  
 <span data-ttu-id="87883-109">Juntos, [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] y A4SWIFT proporcionan la plataforma, infraestructura y herramientas para diseñar, desarrollar y ejecutar secure SWIFT sistemas de automatización de la mensajería y flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="87883-109">Together, [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
 <span data-ttu-id="87883-110">Al implementar la seguridad, debe diseñar y desarrollar muchas áreas.</span><span class="sxs-lookup"><span data-stu-id="87883-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="87883-111">En la lista siguiente es una vista de alto nivel de estas áreas:</span><span class="sxs-lookup"><span data-stu-id="87883-111">The following list is a high-level view of these areas:</span></span>  
  
-   <span data-ttu-id="87883-112">Desarrollar una directiva de seguridad de TI</span><span class="sxs-lookup"><span data-stu-id="87883-112">Develop an IT security policy</span></span>  
  
-   <span data-ttu-id="87883-113">Diseñar e implementar una estrategia de defensa</span><span class="sxs-lookup"><span data-stu-id="87883-113">Design and implement a defense strategy</span></span>  
  
-   <span data-ttu-id="87883-114">Diseñar e implementar una estrategia de bloqueo de servidor</span><span class="sxs-lookup"><span data-stu-id="87883-114">Design and implement a server lockdown strategy</span></span>  
  
-   <span data-ttu-id="87883-115">Diseñar e implementar una estrategia de antivirus</span><span class="sxs-lookup"><span data-stu-id="87883-115">Design and implement an antivirus strategy</span></span>  
  
-   <span data-ttu-id="87883-116">Diseñar, implementar una copia de seguridad y restaurar estrategia</span><span class="sxs-lookup"><span data-stu-id="87883-116">Design and implement a backup and restore strategy</span></span>  
  
-   <span data-ttu-id="87883-117">Diseñar e implementar una estrategia de administración de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="87883-117">Design and implement an update management strategy</span></span>  
  
-   <span data-ttu-id="87883-118">Diseñar e implementar una estrategia de detección de intrusos y auditoría</span><span class="sxs-lookup"><span data-stu-id="87883-118">Design and implement an auditing and intrusion detection strategy</span></span>  
  
-   <span data-ttu-id="87883-119">Diseñar un plan de respuesta a incidentes</span><span class="sxs-lookup"><span data-stu-id="87883-119">Design an incident response plan</span></span>  
  
 <span data-ttu-id="87883-120">La información proporcionada en este tema no abarcan toda la información en la lista anterior o entregar una solución compatible con servicios financiera.</span><span class="sxs-lookup"><span data-stu-id="87883-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="87883-121">El propósito de este tema es proporcionar un buen punto de partida y para ayudar a la importancia de un enfoque estructurado y más completa de seguridad de carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="87883-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  
  
 <span data-ttu-id="87883-122">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="87883-122">This section contains:</span></span>  
  
-   [<span data-ttu-id="87883-123">Características de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="87883-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  
  
-   [<span data-ttu-id="87883-124">Características de seguridad de A4SWIFT de reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="87883-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="87883-125">Seguridad de InfoPath</span><span class="sxs-lookup"><span data-stu-id="87883-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  
  
-   [<span data-ttu-id="87883-126">Seguridad del servidor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="87883-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  
  
-   [<span data-ttu-id="87883-127">Seguridad de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="87883-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  
  
-   [<span data-ttu-id="87883-128">Seguridad del servicio Web de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="87883-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  
  
-   [<span data-ttu-id="87883-129">Resumen de seguridad</span><span class="sxs-lookup"><span data-stu-id="87883-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)