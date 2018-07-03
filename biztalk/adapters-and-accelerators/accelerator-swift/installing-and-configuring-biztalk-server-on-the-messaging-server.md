---
title: Instalación y configuración de BizTalk Server en el servidor de mensajería | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f4013c1fe315646ea7a2ff34772169a03a2d66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989573"
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a>Instalación y configuración de BizTalk Server en el servidor de mensajería
En esta sección se describe cómo instalar y configurar BizTalk Server que se usará como el servidor de mensajería para conectarse a la red SWIFT.  

### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a>Para instalar y configurar BizTalk Server en el servidor de mensajería  

1. Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características, excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y el sitio MRSR, a menos que se necesitan otras aplicaciones.  

   > [!NOTE]
   >  Tenga en cuenta que en la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio front-end HTTP.  

2. Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

   > [!NOTE]
   >  No instalar Message Queue Server, ya que se va a instalar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] versión de MSMQ que se conoce como MSMQT. Para obtener más información acerca de MSMQT, vea la configuración del adaptador BizTalk Message Queue (MSMQT) en el sitio Web de MSDN en [ http://go.microsoft.com/fwlink/?LinkID=48875 ](http://go.microsoft.com/fwlink/?LinkID=48875).  

3. Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación. En el momento de esta publicación, no hay ninguna revisión necesaria.
