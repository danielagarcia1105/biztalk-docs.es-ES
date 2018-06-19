---
title: Instalar y configurar el servidor BizTalk Server en los servidores de orquestación | Documentos de Microsoft
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
ms.openlocfilehash: 18a13d553e31739c959ff6baf317240c3c268ecc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004213"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="0b906-102">Instalar y configurar el servidor BizTalk Server en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="0b906-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="0b906-103">Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor para ejecutar la orquestación de reparación/nuevo envío del mensaje y la reparación de FIN y la orquestación de conciliación.</span><span class="sxs-lookup"><span data-stu-id="0b906-103">This section describes how to install and configure BizTalk Server to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="0b906-104">Para instalar y configurar BizTalk Server en el servidor de orquestación</span><span class="sxs-lookup"><span data-stu-id="0b906-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  
  
1.  <span data-ttu-id="0b906-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y MRSR, a menos que el requerido por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0b906-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b906-106">En la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio de front-end de HTTP y el servidor de mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0b906-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  
  
2.  <span data-ttu-id="0b906-107">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b906-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0b906-108">Tenga en cuenta las siguientes directrices al configurar los servidores de orquestación de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="0b906-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  
  
    -   <span data-ttu-id="0b906-109">Este servidor requiere solo un adaptador de red para conectarse a la [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] equipo.</span><span class="sxs-lookup"><span data-stu-id="0b906-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="0b906-110">No requiere otro adaptador de red en el lado público como el servidor front-end HTTP o el servidor de mensajería, y resulta más seguro frente a intentos procedente de Internet o una intranet o extranet.</span><span class="sxs-lookup"><span data-stu-id="0b906-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  
  
3.  <span data-ttu-id="0b906-111">Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="0b906-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>