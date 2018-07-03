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
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="506b9-102">Instalación y configuración de BizTalk Server en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="506b9-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="506b9-103">En esta sección se describe cómo instalar y configurar BizTalk Server que se usará como el servidor de la orquestación para la ejecución de la orquestación de envío de reparación/nuevo mensaje y la reparación de FIN y la orquestación de conciliación.</span><span class="sxs-lookup"><span data-stu-id="506b9-103">This section describes how to install and configure BizTalk Server to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="506b9-104">Para instalar y configurar BizTalk Server en el servidor de orquestación</span><span class="sxs-lookup"><span data-stu-id="506b9-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  

1. <span data-ttu-id="506b9-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características, excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y MRSR, a menos que se necesitan otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="506b9-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="506b9-106">En la implementación de equipo único, este equipo es el mismo equipo que ejecuta el servicio de front-end de HTTP y el servidor de mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="506b9-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  

2. <span data-ttu-id="506b9-107">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="506b9-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="506b9-108">Tenga en cuenta las siguientes directrices al configurar los servidores de orquestación de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="506b9-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  

   - <span data-ttu-id="506b9-109">Este servidor requiere solo un adaptador de red para conectarse a la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="506b9-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="506b9-110">No requiere otro adaptador de red en el lado público, como el servidor front-end HTTP o el servidor de mensajería, y así resulta más seguro contra la piratería informática intentos procedentes de Internet o intranet/extranet.</span><span class="sxs-lookup"><span data-stu-id="506b9-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  

3. <span data-ttu-id="506b9-111">Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="506b9-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
