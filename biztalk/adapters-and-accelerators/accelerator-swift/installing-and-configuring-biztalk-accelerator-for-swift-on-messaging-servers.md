---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for SWIFT, configuring
- BizTalk Accelerator for SWIFT, installing on Messaging servers
- BizTalk Messaging servers, installing BizTalk Accelerator for SWIFT
ms.assetid: 7a8f60aa-5ff2-4584-9d4a-dc4a0ba61aca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef434603c1740375f4399f368e89f99a923cba86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209396"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers"></a>Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería
Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores de mensajería. Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-a4swift-on-the-messaging-server"></a>Para instalar y configurar el Acelerador de BizTalk para A4SWIFT en el servidor de mensajería  
  
1.  Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]. Instalar el **MRSR** y **mensajes de SWIFT** características.  
  
    > [!NOTE]
    >  No es necesario instalar los componentes Web para la característica de reparación de mensajes y nuevo envío porque este servidor no tiene sitios MRSR.  
  
    > [!NOTE]
    >  Una vez completada la instalación, se inicia el Asistente para configuración.  
  
2.  En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR**.