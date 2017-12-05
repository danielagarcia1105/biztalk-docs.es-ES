---
title: "Instalar y configurar el servidor BizTalk Server en el servidor de mensajería | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527b0d707d0f78672018f31e60ea54ac436e1db4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="16c4f-102">Instalar y configurar el servidor BizTalk Server en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="16c4f-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="16c4f-103">Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor de mensajería para conectarse a la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="16c4f-103">This section describes how to install and configure BizTalk Server to be used as the messaging server for connecting to the SWIFT network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="16c4f-104">Para instalar y configurar BizTalk Server en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="16c4f-104">To install and configure BizTalk Server on the Messaging Server</span></span>  
  
1.  <span data-ttu-id="16c4f-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir todas las características excepto EDI, servicios de flujo de trabajo de usuarios (HWS) y el sitio MRSR, a menos que el requerido por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="16c4f-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16c4f-106">Tenga en cuenta que en la implementación de equipo único, este equipo es el mismo equipo que el que se ejecuta el servicio de front-end de HTTP.</span><span class="sxs-lookup"><span data-stu-id="16c4f-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  
  
2.  <span data-ttu-id="16c4f-107">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16c4f-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16c4f-108">No instalar Message Queue Server, ya que se va a instalar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] versión de MSMQ que se conoce como MSMQT.</span><span class="sxs-lookup"><span data-stu-id="16c4f-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="16c4f-109">Para obtener más información acerca de MSMQT, consulte Configuración de adaptador de puesta en cola de mensajes de BizTalk (MSMQT) en el sitio Web de MSDN en [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span><span class="sxs-lookup"><span data-stu-id="16c4f-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  
  
3.  <span data-ttu-id="16c4f-110">Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="16c4f-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="16c4f-111">En el momento de esta publicación, no hay ningún las revisiones necesarias.</span><span class="sxs-lookup"><span data-stu-id="16c4f-111">At the time of this publication, there are no required hotfixes.</span></span>