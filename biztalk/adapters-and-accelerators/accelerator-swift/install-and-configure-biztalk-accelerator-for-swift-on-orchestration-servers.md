---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384548de9fb0b7a5ee4ce440869c42fdfa1e93ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209748"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a>Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de orquestación
Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores de la orquestación. Estos servidores se utilizan principalmente para ejecutar la orquestación FINÉS reparación y conciliación y la orquestación de reparación/nuevo envío del mensaje.  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a>Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor de orquestación  
  
1.  Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]. Instalar el **MRSR** característica.  
  
    > [!NOTE]
    >  No es necesario instalar los componentes Web para la característica de reparación de mensajes y nuevo envío porque este servidor no tiene sitios MRSR.  
  
    > [!NOTE]
    >  Una vez completada la instalación, se inicia el Asistente para configuración.  
  
2.  En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR**.