---
title: "Creación de TIBCO Enterprise Message Service controladores de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive handlers
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83163701f897b782d577351cd08b3f2650ae6fb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-tibco-enterprise-message-service-receive-handlers"></a><span data-ttu-id="6bdc2-102">Creación de controladores de recepción de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="6bdc2-102">Creating TIBCO Enterprise Message Service Receive Handlers</span></span>
<span data-ttu-id="6bdc2-103">El receptor TIBCO Enterprise Message Service es un servicio de escucha que registra una cola o tema particular y recibe los mensajes relacionados.</span><span class="sxs-lookup"><span data-stu-id="6bdc2-103">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="6bdc2-104">El adaptador de BizTalk para TIBCO Enterprise Message Service se registra primero con TIBCO Enterprise Message Service, mediante la apertura de una nueva sesión y, después, continúa realizando el sondeo para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="6bdc2-104">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="6bdc2-105">En esta sección se explica cómo configurar el puerto de recepción para conectarse a TIBCO Enterprise Message Service y cómo incluir XML en la orquestación para interactuar con TIBCO EMS en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6bdc2-105">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6bdc2-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6bdc2-106">In This Section</span></span>  
  
-   [<span data-ttu-id="6bdc2-107">Cómo crear puertos de recepción en TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="6bdc2-107">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>](../core/how-to-create-receive-ports-in-tibco-enterprise-message-service.md)  
  
-   [<span data-ttu-id="6bdc2-108">Establecer propiedades de transporte TIBCO Enterprise Message Service para el puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="6bdc2-108">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)  
  
-   [<span data-ttu-id="6bdc2-109">Cómo configurar canalizaciones de recepción para TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="6bdc2-109">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)