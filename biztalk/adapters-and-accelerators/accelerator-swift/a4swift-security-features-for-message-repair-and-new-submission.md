---
title: Características de seguridad de A4SWIFT para la reparación de mensajes y nuevo envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- A4SWIFT, security
- security, A4SWIFT
- messages, security
ms.assetid: c34bcba7-fecd-4e2f-ab49-a6ccfd96198b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff2a4960d95b46ae8c224c17ff279719d51d8b37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986045"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>Características de seguridad de A4SWIFT para la reparación de mensajes y nuevo envío
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Proporciona los medios del cuadro de mensaje SWIFT creación, reparación, comprobación de regeneración de claves y aprobación. Los usuarios empresariales crear, editar y revisar los mensajes de SWIFT mediante Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], que proporciona una interfaz gráfica de usuario y la representación para los mensajes financieros (FIN). [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] representa el formulario de comprobación de la entrada y la reparación o regeneración de claves desde el XML generado por el tiempo de ejecución de A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. A4SWIFT proporciona un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] plantilla para cada FIN del mensaje (según el esquema XSD de A4SWIFT correspondiente) de tipo para que pueda abrir ningún tipo de mensaje SWIFT FIN en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]. A4SWIFT proporciona las siguientes características para ayudar en la seguridad.  
  
## <a name="infopath-forms"></a>Formularios de InfoPath  
 A través de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionados por A4SWIFT, los usuarios empresariales, enviar y recuperar SWIFT mensajes hacia y desde las bandejas de entrada y las bandejas de salida implementado en las carpetas protegidas de Web de Windows SharePoint Services. [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] Seguridad de la carpeta Web completamente, Microsoft proporciona [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] mediante listas de control de acceso (ACL), de sistema de archivos [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y las características de seguridad de Internet Information Services (IIS). Datos estarán protegidos mientras que "en el cable" entre [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] carpetas Web y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] protocolos de transporte mediante la capa de Sockets seguros (SSL) y HTTPS.  
  
 A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] los formularios se crean como "confianza". Este estado proporciona el máximo nivel de seguridad. Para obtener más información acerca de confianza y, consulte [InfoPath seguridad](../../adapters-and-accelerators/accelerator-swift/infopath-security.md).  
  
## <a name="runtime-service"></a>Servicio de tiempo de ejecución  
 A4SWIFT proporciona un tiempo de ejecución de servicio (implementado como una orquestación de BizTalk) para autenticar, validar, procesar y enrutar los mensajes de SWIFT entre las carpetas SharePoint Web, las orquestaciones de reparación/entrada de mensaje, los sistemas back-end y, en última instancia, para SWIFT red. Este servicio en tiempo de ejecución se conoce como la reparación de mensajes de A4SWIFT y nuevo envío.  
  
## <a name="secure-messages"></a>Mensajes seguros  
 El almacenamiento y la entrega de SWIFT mensajes entre [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], y reparación de mensajes y nuevo envío está protegido por los servicios subyacentes ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], IIS, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) y protocolos (SSL, HTTPS) de transporte. Sin embargo, la infraestructura de creación, reparación, aprobación y envío de mensajes se compone de reparación de mensajes y nuevo envío [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] requiere una seguridad de nivel de usuario adicional para exigir la autenticidad y la protección de los mensajes de SWIFT administra los usuarios finales.  
  
 A4SWIFT también define e implementa la semántica de seguridad de nivel de usuario para asegurarse de que envía solo los usuarios de confianza y autorizados y modifican los mensajes de SWIFT, y esos datos de mensaje no se puede modificar o alterados durante los pasos del envío asincrónicos procesar (por ejemplo, mientras que los mensajes se encuentran en una carpeta de SharePoint Web esperando la intervención del usuario). Coordina y choreographed características de seguridad en la estación de trabajo (a través de [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) y servidor (a través de A4SWIFT reparación de mensajes y nuevo envío) aplicar estas directivas de seguridad de nivel de usuario.