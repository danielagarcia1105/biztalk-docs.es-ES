---
title: Instalación y configuración de BizTalk Server en los servidores de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecd5e9e4be9c9274a402b54a5bf6a2eba4ed73cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984101"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>Instalación y configuración de BizTalk Server en los servidores de orquestación
En esta sección se describe cómo instalar y configurar BizTalk Server que se usará como el servidor de la orquestación para la ejecución de la orquestación de envío de reparación/nuevo mensaje y la reparación de FIN y la orquestación de conciliación.  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>Para instalar y configurar BizTalk Server en el servidor de orquestación  

1. Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características, excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y MRSR, a menos que se necesitan otras aplicaciones.  

   > [!NOTE]
   >  En la implementación de equipo único, este equipo es el mismo equipo que ejecuta el servicio de front-end de HTTP y el servidor de mensajería de BizTalk.  

2. Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

   > [!NOTE]
   >  Tenga en cuenta las siguientes directrices al configurar los servidores de orquestación de BizTalk:  

   - Este servidor requiere solo un adaptador de red para conectarse a la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo. No requiere otro adaptador de red en el lado público, como el servidor front-end HTTP o el servidor de mensajería, y así resulta más seguro contra la piratería informática intentos procedentes de Internet o intranet/extranet.  

3. Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación.
