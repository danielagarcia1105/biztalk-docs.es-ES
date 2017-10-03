---
title: "¿Qué es el adaptador de MSMQ? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5a543e2fc5db228d249b2db2c445e254384d03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-msmq-adapter"></a>¿Qué es el adaptador de MSMQ?
Con el adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para MSMQ (el adaptador de MSMQ), podrá enviar mensajes a las colas de Microsoft Message Queuing (también conocido como MSMQ), así como efectuar la recepción desde éstas, mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de MSMQ admite Message Queue Server 4.0. El adaptador funciona con colas remotas y locales, públicas y privadas, y transaccionales y no transaccionales. Además, el adaptador de MSMQ ofrece compatibilidad para mensajes de gran tamaño (más de 4 MB), y proporciona acceso a características de Message Queuing 4.0 como, por ejemplo, lecturas transaccionales remotas y lectura desde subcolas.  
  
 Si ha actualizado la instalación de BizTalk Server a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], no se quitará el adaptador de BizTalk Server 2009 para MSMQ. Puesto que [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instala una nueva versión del adaptador de MSMQ, podrá desinstalar el adaptador de BizTalk Server 2009 para MSMQ con toda seguridad y, a continuación, quitar manualmente la estructura de directorios de esta versión del adaptador.