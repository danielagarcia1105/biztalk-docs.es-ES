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
ms.openlocfilehash: caeac28ce33e2f5eeacbb73b03d9873ec1e74c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="what-is-the-msmq-adapter"></a>¿Qué es el adaptador de MSMQ?
Con el adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para MSMQ (el adaptador de MSMQ), podrá enviar mensajes a las colas de Microsoft Message Queuing (también conocido como MSMQ), así como efectuar la recepción desde éstas, mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador de MSMQ admite Message Queue Server 4.0. El adaptador funciona con colas remotas y locales, públicas y privadas, y transaccionales y no transaccionales. Además, el adaptador de MSMQ ofrece compatibilidad para mensajes de gran tamaño (más de 4 MB), y proporciona acceso a características de Message Queuing 4.0 como, por ejemplo, lecturas transaccionales remotas y lectura desde subcolas.  
  
 Si ha actualizado la instalación de BizTalk Server a BizTalk Server, no se quita el adaptador de BizTalk Server 2009 para MSMQ. Dado que BizTalk Server instala una nueva versión del adaptador de MSMQ, puede desinstalar de manera segura el adaptador de BizTalk Server 2009 para MSMQ y, a continuación, quitar manualmente la estructura de directorios para esta versión del adaptador.