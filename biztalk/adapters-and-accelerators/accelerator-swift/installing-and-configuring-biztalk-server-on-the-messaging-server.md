---
title: Instalación y configuración de BizTalk Server en el servidor de mensajería | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f4013c1fe315646ea7a2ff34772169a03a2d66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989573"
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="80b8a-102">Instalación y configuración de BizTalk Server en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="80b8a-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="80b8a-103">En esta sección se describe cómo instalar y configurar BizTalk Server que se usará como el servidor de mensajería para conectarse a la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="80b8a-103">This section describes how to install and configure BizTalk Server to be used as the messaging server for connecting to the SWIFT network.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="80b8a-104">Para instalar y configurar BizTalk Server en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="80b8a-104">To install and configure BizTalk Server on the Messaging Server</span></span>  

1. <span data-ttu-id="80b8a-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características, excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y el sitio MRSR, a menos que se necesitan otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="80b8a-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="80b8a-106">Tenga en cuenta que en la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio front-end HTTP.</span><span class="sxs-lookup"><span data-stu-id="80b8a-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  

2. <span data-ttu-id="80b8a-107">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80b8a-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="80b8a-108">No instalar Message Queue Server, ya que se va a instalar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] versión de MSMQ que se conoce como MSMQT.</span><span class="sxs-lookup"><span data-stu-id="80b8a-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="80b8a-109">Para obtener más información acerca de MSMQT, vea la configuración del adaptador BizTalk Message Queue (MSMQT) en el sitio Web de MSDN en [ http://go.microsoft.com/fwlink/?LinkID=48875 ](http://go.microsoft.com/fwlink/?LinkID=48875).</span><span class="sxs-lookup"><span data-stu-id="80b8a-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  

3. <span data-ttu-id="80b8a-110">Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="80b8a-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="80b8a-111">En el momento de esta publicación, no hay ninguna revisión necesaria.</span><span class="sxs-lookup"><span data-stu-id="80b8a-111">At the time of this publication, there are no required hotfixes.</span></span>
