---
title: Resumen de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security
ms.assetid: 357ebf63-a35e-4ce4-a754-be880946f9fc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0062eca25e95c41c07d2e8dbf9ccac0a4694a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995357"
---
# <a name="security-summary"></a><span data-ttu-id="66047-102">Resumen de seguridad</span><span class="sxs-lookup"><span data-stu-id="66047-102">Security Summary</span></span>
## <a name="overview"></a><span data-ttu-id="66047-103">Información general</span><span class="sxs-lookup"><span data-stu-id="66047-103">Overview</span></span>
<span data-ttu-id="66047-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona componentes de desarrollo y tiempo de ejecución para facilitar las aplicaciones de BizTalk que proporcionan funcionalidad de mensajería y la automatización de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="66047-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides development and runtime components to facilitate BizTalk applications that provide SWIFT messaging and automation functionality.</span></span> <span data-ttu-id="66047-105">Las aplicaciones desarrolladas mediante el uso de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] son aplicaciones de BizTalk y están protegidos por nativo [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], IIS/ASP y[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] las características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="66047-105">Applications developed by using [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] are BizTalk applications and are secured by native [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], and IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] security features.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="66047-106"> protege la privacidad de los elementos del sistema mediante el uso de protocolos y estándares de comunicaciones de Internet cifrado de hecho.</span><span class="sxs-lookup"><span data-stu-id="66047-106"> protects privacy of system elements by using de facto Internet encrypted communications standards and protocols.</span></span> <span data-ttu-id="66047-107">Los participantes de comunicación, procesos e información se protegen mediante el uso de certificados de firma, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] y autenticación de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="66047-107">Communication participants, processes, and information are secured by using signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="66047-108"> También exige autorización de uso de recursos con mecanismos como [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y la base de datos de cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="66047-108"> also enforces authorization of resource usage with mechanisms such as [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and the MessageBox database.</span></span>  
  
 <span data-ttu-id="66047-109">Además de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] define y exige la semántica de seguridad para la creación, reparación, aprobación y envío de mensajes SWIFT por los usuarios empresariales.</span><span class="sxs-lookup"><span data-stu-id="66047-109">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] defines and enforces security semantics for the creation, repair, approval, and submission of SWIFT messages by business users.</span></span> <span data-ttu-id="66047-110">Este nivel de usuario de seguridad se aplica mediante [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] en la comprobación de integridad de estación de trabajo y el certificado y los datos de usuario mediante las tecnologías de firma digital [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicios en tiempo de ejecución en el servidor.</span><span class="sxs-lookup"><span data-stu-id="66047-110">This user-level security is enforced by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies on the user workstation, and certificate and data integrity verification by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] runtime services on the server.</span></span>  
  
 <span data-ttu-id="66047-111">Juntos, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporcionan la plataforma, infraestructura y herramientas para diseñar, desarrollar y ejecutar secure SWIFT sistemas de automatización de mensajería y flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="66047-111">Together, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="66047-112">Más información</span><span class="sxs-lookup"><span data-stu-id="66047-112">More information</span></span>  
 <span data-ttu-id="66047-113">Para obtener información sobre los procedimientos recomendados de seguridad, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66047-113">For information about security best practices, see the following:</span></span>  
  
- <span data-ttu-id="66047-114">Centro de recursos de seguridad de TechNet:</span><span class="sxs-lookup"><span data-stu-id="66047-114">TechNet Security Resource Center:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27741](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

- <span data-ttu-id="66047-115">Guía de seguridad de Symantec que se muestra cómo usar sus herramientas para implementar las prácticas recomendadas descritas en la Guía de operaciones de seguridad de Microsoft para [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="66047-115">Symantec security guide showing how to use their tools to implement the best practices described in Microsoft Security Operations Guide for [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=28274](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
- <span data-ttu-id="66047-116">Información sobre el servicio de notificación de seguridad de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="66047-116">Information about the Microsoft Security Notification Service:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27744](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a><span data-ttu-id="66047-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="66047-117">See Also</span></span>  
[<span data-ttu-id="66047-118">Tiempo de ejecución, reparación de mensajes, respuesta FIN y mensajería</span><span class="sxs-lookup"><span data-stu-id="66047-118">Runtime, message repair, FIN response, and messaging</span></span>](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)