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
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a>Instalación y configuración de BizTalk Server en los servidores front-end HTTP
Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor front-end HTTP para hospedar el sitio MRSR y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios de plantilla.  

### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a>Para instalar y configurar BizTalk Server en los servidores front-end HTTP de BizTalk  

1. Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir las siguientes características: **motor de reglas de negocios** y **adaptador de SharePoint**.  

   > [!NOTE]
   >  Otras características no son necesarias para esta instalación.  

   > [!NOTE]
   >  En uno de los servidores front-end HTTP de BizTalk, al realizar la configuración, cree el grupo de BizTalk.  

2. Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

3. Instale todas las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponible en la Guía de instalación.
