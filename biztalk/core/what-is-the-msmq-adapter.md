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
# <a name="what-is-the-msmq-adapter"></a><span data-ttu-id="036fd-103">¿Qué es el adaptador de MSMQ?</span><span class="sxs-lookup"><span data-stu-id="036fd-103">What Is the MSMQ Adapter?</span></span>
<span data-ttu-id="036fd-104">Con el adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para MSMQ (el adaptador de MSMQ), podrá enviar mensajes a las colas de Microsoft Message Queuing (también conocido como MSMQ), así como efectuar la recepción desde éstas, mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="036fd-104">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Adapter for MSMQ (the MSMQ adapter), you can send and receive messages to Microsoft Message Queuing (also known as MSMQ) queues using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="036fd-105">El adaptador de MSMQ admite Message Queue Server 4.0.</span><span class="sxs-lookup"><span data-stu-id="036fd-105">The MSMQ adapter supports Message Queuing 4.0.</span></span> <span data-ttu-id="036fd-106">El adaptador funciona con colas remotas y locales, públicas y privadas, y transaccionales y no transaccionales.</span><span class="sxs-lookup"><span data-stu-id="036fd-106">The adapter works with transactional and non-transactional, public and private, and local and remote queues.</span></span> <span data-ttu-id="036fd-107">Además, el adaptador de MSMQ ofrece compatibilidad para mensajes de gran tamaño (más de 4 MB), y proporciona acceso a características de Message Queuing 4.0 como, por ejemplo, lecturas transaccionales remotas y lectura desde subcolas.</span><span class="sxs-lookup"><span data-stu-id="036fd-107">Additionally, the MSMQ adapter provides large (greater than 4 MB) message support and gives you access to Message Queuing 4.0 features such as remote transactional reads and reading from subqueues.</span></span>  
  
 <span data-ttu-id="036fd-108">Si ha actualizado la instalación de BizTalk Server a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], no se quitará el adaptador de BizTalk Server 2009 para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="036fd-108">If you have upgraded your BizTalk Server installation to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], the BizTalk Server 2009 Adapter for MSMQ is not removed.</span></span> <span data-ttu-id="036fd-109">Puesto que [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] instala una nueva versión del adaptador de MSMQ, podrá desinstalar el adaptador de BizTalk Server 2009 para MSMQ con toda seguridad y, a continuación, quitar manualmente la estructura de directorios de esta versión del adaptador.</span><span class="sxs-lookup"><span data-stu-id="036fd-109">Because [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installs a new version of the MSMQ adapter, you can safely uninstall the BizTalk Server 2009 Adapter for MSMQ and then manually remove the directory structure for this version of the adapter.</span></span>