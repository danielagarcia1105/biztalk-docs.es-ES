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
# <a name="security-summary"></a>Resumen de seguridad
## <a name="overview"></a>Información general
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona componentes de desarrollo y tiempo de ejecución para facilitar las aplicaciones de BizTalk que proporcionan funcionalidad de mensajería y la automatización de SWIFT. Las aplicaciones desarrolladas mediante el uso de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] son aplicaciones de BizTalk y están protegidos por nativo [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], IIS/ASP y[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] las características de seguridad.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] protege la privacidad de los elementos del sistema mediante el uso de protocolos y estándares de comunicaciones de Internet cifrado de hecho. Los participantes de comunicación, procesos e información se protegen mediante el uso de certificados de firma, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] y autenticación de Enterprise Single Sign-On. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] También exige autorización de uso de recursos con mecanismos como [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y la base de datos de cuadro de mensajes.  
  
 Además de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] define y exige la semántica de seguridad para la creación, reparación, aprobación y envío de mensajes SWIFT por los usuarios empresariales. Este nivel de usuario de seguridad se aplica mediante [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] en la comprobación de integridad de estación de trabajo y el certificado y los datos de usuario mediante las tecnologías de firma digital [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicios en tiempo de ejecución en el servidor.  
  
 Juntos, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporcionan la plataforma, infraestructura y herramientas para diseñar, desarrollar y ejecutar secure SWIFT sistemas de automatización de mensajería y flujo de trabajo.  
  
## <a name="more-information"></a>Más información  
 Para obtener información sobre los procedimientos recomendados de seguridad, vea lo siguiente:  
  
- Centro de recursos de seguridad de TechNet:  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27741](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

- Guía de seguridad de Symantec que se muestra cómo usar sus herramientas para implementar las prácticas recomendadas descritas en la Guía de operaciones de seguridad de Microsoft para [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=28274](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
- Información sobre el servicio de notificación de seguridad de Microsoft:  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27744](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a>Vea también  
[Tiempo de ejecución, reparación de mensajes, respuesta FIN y mensajería](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)