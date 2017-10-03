---
title: Seguridad del servicio Web de A4SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IIS security
- Web service [A4SWIFT]
- security, transport-level security
- security, message-level security
- ASP.NET security
- A4SWIFT, Web service
- A4SWIFT, security
- security, IIS
- security, ASP.NET
- security, Web service
- messages, security
ms.assetid: e6c7d275-569f-47f6-81fb-10bcd86ff417
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8510172517d58475d855d258b72b16271835dbc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-web-service-security"></a>Seguridad del servicio Web de A4SWIFT
El [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]servicio Web de forma predeterminada se instala en un modelo de seguridad híbrido altamente seguro. En el modelo de IIS/ASP.NET existe un límite de confianza entre el servicio Web, el [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] sitio y el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]base de datos.  
  
## <a name="iis-and-aspnet-security-settings"></a>Configuración de seguridad ASP.NET e IIS  
 Cuando se realiza una llamada a la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] en primer lugar, servidor Web, IIS autentica al usuario mediante el uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación. El servicio Web de web.config se establece de forma predeterminada para utilizar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación sin suplantación y valida que el llamador es un miembro de la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] grupo de usuarios. Si el llamador es un miembro de la [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] grupo de usuarios, los métodos de servicio Web se ejecutan bajo la identidad del proceso del grupo de aplicaciones. Para [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], este es el grupo de aplicaciones predeterminado para [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)].  
  
 Para el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Web service para eliminar el mensaje de la Bandeja de entrada del llamador del método Web, el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicio Web debe suplantar al autor de la **eliminar** y **GetCheckedOutUser** métodos. Estos son los únicos métodos que se ejecutan en el contexto del llamador original. Dado que el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicio Web suplanta al llamador de estos métodos Web, el llamador debe tener permisos explícitos establecidos en las bibliotecas de documentos de SharePoint en los que actúa el llamador.  
  
## <a name="a4swift-secure-communication-settings"></a>Configuración de una comunicación segura de A4SWIFT  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]se refiere a garantizar la integridad y confidencialidad de los mensajes del servicio Web mientras se transmiten desde [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] a [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] para las aplicaciones de BizTalk a través de la red. Para proporcionar el nivel más alto de seguridad [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] admite dos niveles de una comunicación segura entre aplicaciones: nivel de transporte y de nivel de mensaje.  
  
## <a name="transport-level-security"></a>Seguridad de nivel de transporte  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]admite la comunicación de SSL entre [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] servicio Web, [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]se adapta automáticamente a la configuración de seguridad del sitio MRSR durante la transmisión de mensajes.  
  
 Seguridad de protocolo Internet (IPSec) también puede implementarse para una comunicación segura entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
 Para obtener más información sobre la implementación de IPSec para la comunicación segura entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], vea "Proteger la implementación de BizTalk Server" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
  
## <a name="message-level-security"></a>Seguridad de nivel de mensaje  
[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]seguridad de nivel de mensaje se logra al firmar digitalmente los mensajes para proporcionar integridad. Mensaje de inicio de sesión [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] se describe en detalle en [InfoPath seguridad](../../adapters-and-accelerators/accelerator-swift/infopath-security.md).