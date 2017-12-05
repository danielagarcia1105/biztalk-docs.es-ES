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
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a>Instalar y configurar el servidor BizTalk Server en los servidores front-end HTTP
Esta sección describe cómo instalar y configurar BizTalk Server que se usará como el servidor front-end HTTP para hospedar el sitio MRSR y [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios de plantilla.  
  
### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a>Para instalar y configurar BizTalk Server en los servidores front-end HTTP de BizTalk  
  
1.  Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] elegir las siguientes características: **motor de reglas de negocios** y **adaptador de SharePoint**.  
  
    > [!NOTE]
    >  Otras características no son necesarias para esta instalación.  
  
    > [!NOTE]
    >  En uno de los servidores front-end HTTP de BizTalk, al realizar la configuración, cree el grupo de BizTalk.  
  
2.  Realizar la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
3.  Instalar las revisiones adicionales requeridas por [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] como disponibles en la Guía de instalación.