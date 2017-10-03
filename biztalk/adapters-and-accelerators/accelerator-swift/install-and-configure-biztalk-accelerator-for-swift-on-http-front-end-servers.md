---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe0a320f9f60f72975faf903c1355b8730840b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a>Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP
Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores front-end de HTTP. Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a>Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor front-end HTTP  
  
1.  Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]. Instalar el **MRSR** y **componentes Web de reparación de mensajes y nuevo envío** características.  
  
    > [!NOTE]
    >  Una vez completada la instalación, se inicia el Asistente para configuración.  
  
2.  En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR** y **WebService**.  
  
3.  Después de completar el Asistente para configuración, en los servidores Web, abra el archivo web.config en la carpeta \< *unidad*>: \Program [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ en el Bloc de notas. Búsqueda de "Autorización". En el **autorización** sección, establezca el valor de roles en el nombre del grupo de usuarios de A4SWIFT.