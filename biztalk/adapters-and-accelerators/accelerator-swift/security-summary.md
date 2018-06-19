---
title: Resumen de seguridad | Documentos de Microsoft
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
ms.openlocfilehash: b5d327de93941278b9b1dcecc9378183c6a2f77a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213980"
---
# <a name="security-summary"></a>Resumen de seguridad
## <a name="overview"></a>Información general
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona componentes de desarrollo y tiempo de ejecución para facilitar las aplicaciones de BizTalk que proporcionan funcionalidad de mensajería y la automatización de SWIFT. Las aplicaciones desarrolladas mediante [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] son aplicaciones de BizTalk y están protegidos por nativo [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]y IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] características de seguridad.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]protege la privacidad de los elementos del sistema mediante protocolos y estándares de comunicaciones de Internet cifrada de hecho. Los participantes de comunicación, procesos e información se protegen mediante el uso de certificados de firma, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] y autenticación de Enterprise Single Sign-On. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]También exige autorización de uso de recursos con los mecanismos como [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles y [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y la base de datos de cuadro de mensajes.  
  
 Además de nativo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] características de seguridad, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] define y exige la semántica de seguridad para la creación, la reparación, la aprobación y el envío de mensajes SWIFT por los usuarios empresariales. Esta seguridad de nivel de usuario se aplica mediante [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] en la comprobación de integridad de estación de trabajo y el certificado y datos de usuario mediante las tecnologías de firma digital [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicios en tiempo de ejecución en el servidor.  
  
 Juntos, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporcionan la plataforma, infraestructura y herramientas para diseñar, desarrollar y ejecutar secure SWIFT sistemas de automatización de la mensajería y flujo de trabajo.  
  
## <a name="more-information"></a>Más información  
 Para obtener información acerca de prácticas recomendadas de seguridad, vea lo siguiente:  
  
-   Centro de recursos de seguridad de TechNet:  
  
     [http://go.Microsoft.com/fwlink/p/?LinkId=27741](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

-   Guía de seguridad de Symantec que muestra cómo utilizar las herramientas para implementar las prácticas recomendadas que se describe en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Guía de operaciones de seguridad para [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:  
  
     [http://go.Microsoft.com/fwlink/p/?LinkId=28274](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
-   Obtener información sobre la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] servicio de notificación de seguridad:  
  
     [http://go.Microsoft.com/fwlink/p/?LinkId=27744](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a>Vea también  
[En tiempo de ejecución, reparación de mensajes, respuesta FIN y de mensajería](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)