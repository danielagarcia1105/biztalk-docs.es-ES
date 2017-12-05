---
title: Instalar y configurar el servidor BizTalk Server en los servidores front-end HTTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 045a44c05789015d73bc797da14568d2cc3732f8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="7d75f-102">Instalar y configurar el servidor BizTalk Server en los servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="7d75f-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="7d75f-103">Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor front-end HTTP para hospedar el sitio MRSR y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios de plantilla.</span><span class="sxs-lookup"><span data-stu-id="7d75f-103">This section describes how to install and configure BizTalk Server to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="7d75f-104">Para instalar y configurar BizTalk Server en los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7d75f-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="7d75f-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir las siguientes características: **motor de reglas de negocios** y **adaptador de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7d75f-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7d75f-106">Otras características no son necesarias para esta instalación.</span><span class="sxs-lookup"><span data-stu-id="7d75f-106">Other features are not required for this installation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7d75f-107">En uno de los servidores front-end HTTP de BizTalk, al realizar la configuración, cree el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7d75f-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  
  
2.  <span data-ttu-id="7d75f-108">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d75f-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="7d75f-109">Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="7d75f-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>