---
title: Instalación y configuración de BizTalk Server en los servidores front-end HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38605a921a1c2761f73c5871544d8853814f6e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014173"
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="d0178-102">Instalación y configuración de BizTalk Server en los servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="d0178-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="d0178-103">Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor front-end HTTP para hospedar el sitio MRSR y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios de plantilla.</span><span class="sxs-lookup"><span data-stu-id="d0178-103">This section describes how to install and configure BizTalk Server to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="d0178-104">Para instalar y configurar BizTalk Server en los servidores front-end HTTP de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d0178-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  

1. <span data-ttu-id="d0178-105">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir las siguientes características: **motor de reglas de negocios** y **adaptador de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d0178-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d0178-106">Otras características no son necesarias para esta instalación.</span><span class="sxs-lookup"><span data-stu-id="d0178-106">Other features are not required for this installation.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d0178-107">En uno de los servidores front-end HTTP de BizTalk, al realizar la configuración, cree el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d0178-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  

2. <span data-ttu-id="d0178-108">Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0178-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

3. <span data-ttu-id="d0178-109">Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación.</span><span class="sxs-lookup"><span data-stu-id="d0178-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
