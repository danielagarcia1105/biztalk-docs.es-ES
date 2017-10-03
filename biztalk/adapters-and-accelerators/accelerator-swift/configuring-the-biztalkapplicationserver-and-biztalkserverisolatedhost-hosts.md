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
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a>Configurar el BizTalkApplicationServer y los Hosts de BizTalkServerIsolatedHost
Para limitar la mensajería (enviar y recibir mensajes) en los servidores de mensajería de BizTalk, debe configurar los hosts de manera predeterminada, que se están ejecutando el envío MSMQT y controladores de recepción, para ejecutar solo en los servidores de mensajería.  
  
### <a name="to-configure-the-default-hosts"></a>Para configurar los hosts predeterminados  
  
1.  Mediante la consola de administración de BizTalk, elimine las instancias de host de servidores de orquestación del host de BizTalkApplicationServer:  
  
    -   Haga clic en cada instancia de host y haga clic en **detener**.  
  
    -   Haga clic en cada instancia de host y haga clic en **eliminar**.  
  
2.  Mediante la consola de administración de BizTalk, elimine las instancias de host de servidores de orquestación del host BizTalkServerIsolatedHost:  
  
    -   Haga clic en cada instancia de host y haga clic en eliminar.  
  
3.  Después de configurar los hosts, reinicie todas las instancias de host en todos los servidores.