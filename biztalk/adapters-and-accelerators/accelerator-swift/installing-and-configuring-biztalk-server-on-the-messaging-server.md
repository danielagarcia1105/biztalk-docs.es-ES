---
title: "Instalar y configurar el servidor BizTalk Server en el servidor de mensajería | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527b0d707d0f78672018f31e60ea54ac436e1db4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a>Instalar y configurar el servidor BizTalk Server en el servidor de mensajería
Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor de mensajería para conectarse a la red SWIFT.  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a>Para instalar y configurar BizTalk Server en el servidor de mensajería  
  
1.  Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y el sitio MRSR, a menos que el requerido por otras aplicaciones.  
  
    > [!NOTE]
    >  Tenga en cuenta que en la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio de front-end de HTTP.  
  
2.  Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
    > [!NOTE]
    >  No instalar Message Queue Server, ya que se va a instalar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] versión de MSMQ que se conoce como MSMQT. Para obtener más información acerca de MSMQT, consulte Configuración de adaptador de puesta en cola de mensajes de BizTalk (MSMQT) en el sitio Web de MSDN en [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).  
  
3.  Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación. En el momento de esta publicación, no hay ningún las revisiones necesarias.