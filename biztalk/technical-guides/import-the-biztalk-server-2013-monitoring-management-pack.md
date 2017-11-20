---
title: "Importar el módulo de administración de supervisión de BizTalk Server 2013 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a><span data-ttu-id="f07f2-102">Importar el módulo de administración de supervisión de BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="f07f2-102">Import the BizTalk Server 2013 Monitoring Management Pack</span></span>
<span data-ttu-id="f07f2-103">Para obtener instrucciones sobre cómo importar un módulo de administración, vea cómo importar un módulo de administración en [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351).</span><span class="sxs-lookup"><span data-stu-id="f07f2-103">For instructions about how to import a management pack, see How to Import a Management Pack in [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351).</span></span> <span data-ttu-id="f07f2-104">Después de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se importa el módulo de administración, siga estos procedimientos para finalizar la configuración inicial:</span><span class="sxs-lookup"><span data-stu-id="f07f2-104">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack is imported, follow these procedures to finish your initial configuration:</span></span>  
  
### <a name="to-configure-the-management-pack"></a><span data-ttu-id="f07f2-105">Para configurar el módulo de administración</span><span class="sxs-lookup"><span data-stu-id="f07f2-105">To configure the management pack</span></span>  
  
1.  <span data-ttu-id="f07f2-106">Crear un nuevo módulo de administración en el que almacenar invalidaciones y otras personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="f07f2-106">Create a new management pack in which you store overrides and other customizations.</span></span>  
  
2.  <span data-ttu-id="f07f2-107">Para habilitar a la configuración de Proxy del agente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f07f2-107">To enable the Agent Proxy setting, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="f07f2-108">Abra la consola del operador y, a continuación, haga clic en el botón administración.</span><span class="sxs-lookup"><span data-stu-id="f07f2-108">Open the Operations console and then click the Administration button.</span></span>  
  
    2.  <span data-ttu-id="f07f2-109">En el panel Administrador, haga clic en **administrado con agente**.</span><span class="sxs-lookup"><span data-stu-id="f07f2-109">In the Administrator pane, click **Agent Managed**.</span></span>  
  
    3.  <span data-ttu-id="f07f2-110">Haga doble clic en un agente en la lista.</span><span class="sxs-lookup"><span data-stu-id="f07f2-110">Double-click an agent in the list.</span></span>  
  
    4.  <span data-ttu-id="f07f2-111">En la ficha seguridad, seleccione **permitir que este agente actúe como proxy y detectar objetos administrados en otros equipos**.</span><span class="sxs-lookup"><span data-stu-id="f07f2-111">On the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**.</span></span>  
  
    5.  <span data-ttu-id="f07f2-112">Repita los pasos 3 y 4 para cada agente que está instalado en un servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f07f2-112">Repeat steps 3 through 4 for each agent that is installed on a BizTalk Server.</span></span>