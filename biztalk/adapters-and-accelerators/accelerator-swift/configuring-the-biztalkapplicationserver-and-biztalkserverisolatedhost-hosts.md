---
title: Configurar el BizTalkApplicationServer y los Hosts de BizTalkServerIsolatedHost | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8459debcd52ce990bc98adf3a2a2372206bae336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a><span data-ttu-id="c210c-102">Configurar el BizTalkApplicationServer y los Hosts de BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="c210c-102">Configuring the BizTalkApplicationServer and BizTalkServerIsolatedHost Hosts</span></span>
<span data-ttu-id="c210c-103">Para limitar la mensajería (enviar y recibir mensajes) en los servidores de mensajería de BizTalk, debe configurar los hosts de manera predeterminada, que se están ejecutando el envío MSMQT y controladores de recepción, para ejecutar solo en los servidores de mensajería.</span><span class="sxs-lookup"><span data-stu-id="c210c-103">To limit the messaging (sending and receiving messages) to the BizTalk Messaging servers, you need to configure the default hosts, which are running the MSMQT send and receive handlers, to run only on the messaging servers.</span></span>  
  
### <a name="to-configure-the-default-hosts"></a><span data-ttu-id="c210c-104">Para configurar los hosts predeterminados</span><span class="sxs-lookup"><span data-stu-id="c210c-104">To configure the default hosts</span></span>  
  
1.  <span data-ttu-id="c210c-105">Mediante la consola de administración de BizTalk, elimine las instancias de host de servidores de orquestación del host de BizTalkApplicationServer:</span><span class="sxs-lookup"><span data-stu-id="c210c-105">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkApplicationServer host:</span></span>  
  
    -   <span data-ttu-id="c210c-106">Haga clic en cada instancia de host y haga clic en **detener**.</span><span class="sxs-lookup"><span data-stu-id="c210c-106">Right-click each host instance and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="c210c-107">Haga clic en cada instancia de host y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c210c-107">Right-click each host instance and click **Delete**.</span></span>  
  
2.  <span data-ttu-id="c210c-108">Mediante la consola de administración de BizTalk, elimine las instancias de host de servidores de orquestación del host BizTalkServerIsolatedHost:</span><span class="sxs-lookup"><span data-stu-id="c210c-108">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkServerIsolatedHost host:</span></span>  
  
    -   <span data-ttu-id="c210c-109">Haga clic en cada instancia de host y haga clic en eliminar.</span><span class="sxs-lookup"><span data-stu-id="c210c-109">Right-click each host instance and click Delete.</span></span>  
  
3.  <span data-ttu-id="c210c-110">Después de configurar los hosts, reinicie todas las instancias de host en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="c210c-110">After you have configured the hosts, restart all the host instances on all the servers.</span></span>