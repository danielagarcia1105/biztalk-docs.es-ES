---
title: Estándares de seguridad y privacidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61daf6e28b03174af2b32a61c758a39b4cd16ff9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980605"
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="48af6-102">Estándares de seguridad y privacidad</span><span class="sxs-lookup"><span data-stu-id="48af6-102">Security and privacy standards</span></span>
<span data-ttu-id="48af6-103">Aplicaciones de servicios financieras y las soluciones de integración desarrollan mediante Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] generalmente se protegen por nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="48af6-103">Financial Services applications and integration solutions developed using Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="48af6-104"> utiliza los mecanismos de seguridad agresivo, como Internet de hecho cifra los estándares de mensajería y protocolos de transporte, la firma de certificados, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] y autenticación de Enterprise Single Sign-On para proteger [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones, datos, y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="48af6-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  

 <span data-ttu-id="48af6-105">Las soluciones creadas con Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], A4SWIFT puede ayudarle a cumplir las directrices de seguridad y privacidad para la sociedad para las transacciones financieras de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="48af6-105">Solutions built with Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  

 <span data-ttu-id="48af6-106">Además de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] A4SWIFT de características de seguridad, proporciona seguridad de nivel de usuario específico para proteger la entrada de mensajes de usuario final, reparación, aprobación y envío de mensajes SWIFT.</span><span class="sxs-lookup"><span data-stu-id="48af6-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="48af6-107">Esta seguridad se logra mediante el uso de [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] las tecnologías de firma digital y de servicios de tiempo de ejecución de A4SWIFT para comprobar la integridad de datos y el certificado.</span><span class="sxs-lookup"><span data-stu-id="48af6-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  

 <span data-ttu-id="48af6-108">Es importante tener en cuenta las medidas para proteger los mensajes de SWIFT y la información que contienen al entrar o editados por los usuarios finales, en tránsito y mientras [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] procesarlos y almacenarlos.</span><span class="sxs-lookup"><span data-stu-id="48af6-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  

 <span data-ttu-id="48af6-109">Juntos, BizTalk Server y A4SWIFT proporcionan la plataforma, infraestructura y herramientas para diseñar, desarrollar y ejecutar SWIFT segura de mensajería y los sistemas de automatización del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="48af6-109">Together, BizTalk Server and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  

 <span data-ttu-id="48af6-110">Al implementar la seguridad, debe diseñar y desarrollar muchas áreas.</span><span class="sxs-lookup"><span data-stu-id="48af6-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="48af6-111">En la lista siguiente es una visión general de estas áreas:</span><span class="sxs-lookup"><span data-stu-id="48af6-111">The following list is a high-level view of these areas:</span></span>  

- <span data-ttu-id="48af6-112">Desarrollar una directiva de seguridad de TI</span><span class="sxs-lookup"><span data-stu-id="48af6-112">Develop an IT security policy</span></span>  

- <span data-ttu-id="48af6-113">Diseñar e implementar una estrategia de defensa</span><span class="sxs-lookup"><span data-stu-id="48af6-113">Design and implement a defense strategy</span></span>  

- <span data-ttu-id="48af6-114">Diseñar e implementar una estrategia de bloqueo de seguridad de servidor</span><span class="sxs-lookup"><span data-stu-id="48af6-114">Design and implement a server lockdown strategy</span></span>  

- <span data-ttu-id="48af6-115">Diseñar e implementar una estrategia antivirus</span><span class="sxs-lookup"><span data-stu-id="48af6-115">Design and implement an antivirus strategy</span></span>  

- <span data-ttu-id="48af6-116">Diseñar e implementar una copia de seguridad y restauración de estrategia</span><span class="sxs-lookup"><span data-stu-id="48af6-116">Design and implement a backup and restore strategy</span></span>  

- <span data-ttu-id="48af6-117">Diseñar e implementar una estrategia de administración de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="48af6-117">Design and implement an update management strategy</span></span>  

- <span data-ttu-id="48af6-118">Diseñar e implementar una estrategia de detección de intrusos y auditoría</span><span class="sxs-lookup"><span data-stu-id="48af6-118">Design and implement an auditing and intrusion detection strategy</span></span>  

- <span data-ttu-id="48af6-119">Diseñar un plan de respuesta a incidentes</span><span class="sxs-lookup"><span data-stu-id="48af6-119">Design an incident response plan</span></span>  

  <span data-ttu-id="48af6-120">La información proporcionada en este tema no cubre toda la información de la lista anterior o entregar una solución compatible de servicios financiera.</span><span class="sxs-lookup"><span data-stu-id="48af6-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="48af6-121">El propósito de este tema es proporcionar un buen punto de partida y ayudar a la importancia de un enfoque de seguridad completa y no estructurados de subrayado.</span><span class="sxs-lookup"><span data-stu-id="48af6-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  

  <span data-ttu-id="48af6-122">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="48af6-122">This section contains:</span></span>  

- [<span data-ttu-id="48af6-123">Características de seguridad de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="48af6-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  

- [<span data-ttu-id="48af6-124">Características de seguridad de A4SWIFT para la reparación de mensajes y nuevo envío</span><span class="sxs-lookup"><span data-stu-id="48af6-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  

- [<span data-ttu-id="48af6-125">Seguridad de InfoPath</span><span class="sxs-lookup"><span data-stu-id="48af6-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  

- [<span data-ttu-id="48af6-126">Seguridad del tiempo de ejecución del servidor</span><span class="sxs-lookup"><span data-stu-id="48af6-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  

- [<span data-ttu-id="48af6-127">Seguridad de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="48af6-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  

- [<span data-ttu-id="48af6-128">Seguridad del servicio web de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="48af6-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  

- [<span data-ttu-id="48af6-129">Resumen de seguridad</span><span class="sxs-lookup"><span data-stu-id="48af6-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)
