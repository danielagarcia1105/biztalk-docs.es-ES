---
title: Características de seguridad de A4SWIFT de reparación de mensajes y nuevo envío | Documentos de Microsoft
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
ms.openlocfilehash: 00170fcdca39de36290e73779881a5d697be8010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208172"
---
# <a name="a4swift-security-features-for-message-repair-and-new-submission"></a>Características de seguridad de A4SWIFT de reparación de mensajes y nuevo envío
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ofrece los medios de cuadro de mensaje SWIFT creación, reparación, comprobación de regeneración de claves y aprobación. Los usuarios empresariales crear, editar y revisar los mensajes de SWIFT mediante [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], que proporciona una interfaz gráfica de usuario y de representación para financieros mensajes (FIN). [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]representa el formulario de comprobación de la entrada y la reparación o regeneración de claves desde el XML generado por el tiempo de ejecución de A4SWIFT y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. A4SWIFT proporciona un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] plantilla por cada term mensaje tipo (basado en el esquema XSD de A4SWIFT correspondiente) para que puedan abrir los tipos de mensaje SWIFT FINÉS en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]. A4SWIFT proporciona las siguientes características para ayudar en la seguridad.  
  
## <a name="infopath-forms"></a>Formularios de InfoPath  
 A través de la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad de FormGenerator proporcionado por A4SWIFT, los usuarios empresariales, enviarán y recuperar SWIFT mensajes hacia y desde las bandejas de entrada y bandejas de salida implementado en las carpetas Web de Windows SharePoint Services protegidas. [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]Seguridad de las carpetas Web proporciona de forma totalmente [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] mediante listas de control de acceso (ACL) de sistema de archivos [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] autenticación y las características de seguridad de Internet Information Services (IIS). Los datos están protegidos mientras "en el cable" entre [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)] carpetas Web y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] protocolos de transporte de capa de Sockets seguros (SSL) y HTTPS.  
  
 A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] los formularios se crean como "confianza". Este estado proporciona el mayor nivel de seguridad. Para obtener más información acerca de la confianza y de no confianza, consulte [InfoPath seguridad](../../adapters-and-accelerators/accelerator-swift/infopath-security.md).  
  
## <a name="runtime-service"></a>Servicio de tiempo de ejecución  
 A4SWIFT proporciona un tiempo de ejecución de servicio (se implementa como una orquestación de BizTalk) para autenticar, validar, procesar y enrutar los mensajes de SWIFT entre las carpetas SharePoint Web, las orquestaciones de reparación/entrada de mensaje, sistemas back-end y, en última instancia, para SWIFT red. Este servicio en tiempo de ejecución se conoce como la reparación de mensajes de A4SWIFT y nuevo envío.  
  
## <a name="secure-messages"></a>Mensajes seguros  
 El almacenamiento y la entrega de SWIFT los mensajes entre [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], y reparación de mensajes y nuevo envío está protegido por los servicios subyacentes ([!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], IIS, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]) y el transporte de protocolos (SSL, HTTPS). Sin embargo, la infraestructura de creación, reparación, aprobación y envío de mensajes se compone de reparación de mensajes y nuevo envío [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] requiere una seguridad de nivel de usuario adicional para exigir la autenticidad y la protección de los mensajes de SWIFT administra los usuarios finales.  
  
 A4SWIFT también define e implementa la semántica de seguridad de nivel de usuario para asegurarse de que los mensajes de SWIFT se modifican y se envían únicamente por aquellos usuarios de confianza y autorizados, y esos datos de mensaje no se modifica ni alterados durante los pasos del envío asincrónicos procesar (por ejemplo, al mismo tiempo los mensajes se encontraran en una carpeta Web de SharePoint esperando la intervención del usuario). Coordina y choreographed las características de seguridad en la estación de trabajo (a través de [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]) y servidor (a través de reparación de mensajes de A4SWIFT y nuevo envío) aplicar estas directivas de seguridad de nivel de usuario.