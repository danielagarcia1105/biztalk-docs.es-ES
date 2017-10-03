---
title: "Instalar y configurar el servidor BizTalk Server en los servidores de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d872d58c72110d7af22c6d64e7d212fbee53fae9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>Instalar y configurar el servidor BizTalk Server en los servidores de orquestación
Esta sección describe cómo instalar y configurar [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] que se usará como el servidor para ejecutar la orquestación de reparación/nuevo envío del mensaje y la orquestación FINÉS reparación y conciliación.  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>Para instalar y configurar BizTalk Server en el servidor de orquestación  
  
1.  Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y MRSR, a menos que el requerido por otras aplicaciones.  
  
    > [!NOTE]
    >  En la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio de front-end de HTTP y el servidor de mensajería de BizTalk.  
  
2.  Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
    > [!NOTE]
    >  Tenga en cuenta las siguientes directrices al configurar los servidores de orquestación de BizTalk:  
  
    -   Este servidor requiere solo un adaptador de red para conectarse a la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo. No requiere otro adaptador de red en el lado público como el servidor front-end HTTP o el servidor de mensajería, y resulta más seguro frente a intentos procedente de Internet o una intranet o extranet.  
  
3.  Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación.